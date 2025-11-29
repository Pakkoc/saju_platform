### 4. Gemini API: AI 텍스트 생성

Google의 Gemini API는 `@google/generative-ai` SDK를 통해 간단하게 호출할 수 있습니다.

*   **검증 및 개선사항:** 현재 시점(2025년 11월)에서 **`gemini-2.5-pro`와 `gemini-2.5-flash` 모델이 최신이며 유효함을 확인**했습니다. SDK 사용법과 코드 예제는 정확하고 바로 사용할 수 있는 수준입니다.

*   **연동 수단:** **SDK (`@google/generative-ai`)**
*   **사용 기능:**
    *   **SDK:** 사용자 입력을 기반으로 프롬프트를 구성하여 AI 모델에 요청하고, 생성된 텍스트 결과를 수신.

#### 설치 및 세팅

1.  **SDK 설치**
    ```bash
    npm install @google/generative-ai
    ```

#### 인증 정보 관리

1.  **위치:** Google AI Studio > Get API key
2.  **필요한 키:** `API key`
3.  **설정 (`.env.local`):**
    ```env
    # Gemini
    GEMINI_API_KEY=AIzaSyxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
    ```

#### 호출 방법

1.  **SDK 호출 (서버 - API 라우트):**
    *   클라이언트에서 fetch 요청을 보낼 API 라우트 (예: `/app/api/generate/route.ts`)를 생성합니다. 기존 문서의 코드는 최신 상태이며 유효합니다.
    ```typescript
    import { GoogleGenerativeAI } from "@google/generative-ai";
    import { NextResponse } from 'next/server';

    export async function POST(req: Request) {
      const { prompt, usePro } = await req.json();

      try {
        const genAI = new GoogleGenerativeAI(process.env.GEMINI_API_KEY!);
        const modelName = usePro ? "gemini-2.5-pro" : "gemini-2.5-flash"; // 필요에 따른 모델 선택
        const model = genAI.getGenerativeModel({ model: modelName });

        // 사용자가 제공한 프롬프트를 그대로 사용하거나, 시스템 프롬프트와 결합
        const fullPrompt = `${prompt}`;

        const result = await model.generateContent(fullPrompt);
        const response = await result.response;
        const text = response.text();

        // TODO: 필요시 DB에 결과 저장

        return NextResponse.json({ result: text });
      } catch (error) {
        console.error("Gemini API error:", error);
        return NextResponse.json({ error: "Failed to generate content" }, { status: 500 });
      }
    }
    ```