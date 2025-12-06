# Tech Stack

## Framework
| Tech | Version | Reason |
|------|---------|--------|
| Next.js | 15.x (App Router) | Vercel 유지보수, 풀스택 프레임워크, AI 학습 데이터 풍부 |
| React | 19.x | Meta 유지보수, 가장 인기있는 UI 라이브러리 |
| TypeScript | 5.x | Microsoft 유지보수, 타입 안정성 |

## Backend/API
| Tech | Version | Reason |
|------|---------|--------|
| Hono | 4.x | Next.js API Routes 대체, 경량 및 빠른 라우팅, Cloudflare 후원 |
| Supabase | - | PostgreSQL 기반, 인증/DB/스토리지 통합, 오픈소스 |

## Authentication
| Tech | Version | Reason |
|------|---------|--------|
| Clerk | - | Google 로그인 간편 구현, Webhook 지원, 요구사항 명시 |

## Payment
| Tech | Version | Reason |
|------|---------|--------|
| TossPayments | - | 국내 결제 1위, 빌링키 기반 정기결제, 요구사항 명시 |

## AI
| Tech | Version | Reason |
|------|---------|--------|
| Google Gemini API | 2.5 | gemini-2.5-flash(Free), gemini-2.5-pro(Pro), 요구사항 명시 |

## Styling
| Tech | Version | Reason |
|------|---------|--------|
| Tailwind CSS | 4.x | 유틸리티 퍼스트, AI 코드 생성 용이, 빠른 프로토타이핑 |
| shadcn/ui | - | Radix UI 기반, 복사-붙여넣기 방식, 커스터마이징 용이 |

## State Management
| Tech | Version | Reason |
|------|---------|--------|
| Zustand | 5.x | 간결한 API, 보일러플레이트 최소화, MVP에 적합 |
| TanStack Query | 5.x | 서버 상태 관리, 캐싱/리페칭 자동화 |

## Form/Validation
| Tech | Version | Reason |
|------|---------|--------|
| React Hook Form | 7.x | 성능 최적화, 간결한 API |
| Zod | 3.x | TypeScript 친화적 스키마 검증 |

## Deployment/Infra
| Tech | Version | Reason |
|------|---------|--------|
| Vercel | - | Next.js 제작사, 간편한 배포, 자동 CI/CD |
| Supabase (DB/Cron) | - | PostgreSQL + Edge Functions + Cron Jobs 통합 |

## Testing
| Tech | Version | Reason |
|------|---------|--------|
| Vitest | 3.x | Vite 기반 초고속 테스트, Jest 호환 API, TDD에 적합 |
| React Testing Library | 16.x | 컴포넌트 테스트, 사용자 행동 기반 테스트 |
| MSW (Mock Service Worker) | 2.x | API 모킹, 네트워크 레벨 인터셉트, 통합 테스트용 |
| Playwright | 1.x | E2E 테스트, 크로스 브라우저, Acceptance 테스트용 |

## Dev Tools
| Tech | Version | Reason |
|------|---------|--------|
| ESLint | 9.x | 코드 품질 관리 |
| Prettier | 3.x | 코드 포맷팅 |
| pnpm | 9.x | 빠른 패키지 설치, 디스크 효율성 |

---

## 기술 선정 원칙

1. **AI 친화성**: AI가 잘 학습한 인기 기술 우선 (Next.js, React, Tailwind)
2. **안정성**: 대기업/활발한 커뮤니티 유지보수 (Vercel, Meta, Microsoft, Google)
3. **하위호환성**: Breaking Change가 적은 기술 (Tailwind 4.x, React 19.x)
4. **MVP 적합성**: 오버엔지니어링 배제, 빠른 개발 우선 (Zustand > Redux)
5. **요구사항 준수**: Clerk, Supabase, TossPayments, Gemini API 필수 사용
