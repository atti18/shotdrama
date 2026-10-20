# Shot Drama — GitHub Pages 사이트

TikTok 개발자센터 폼(Website / Terms / Privacy / Redirect URI)을 채우기 위한 정적 사이트입니다.

## 1. 자리표시자 바꾸기
| 찾을 문자열 | 바꿀 값 | 파일 |
|---|---|---|
| `CONTACT_EMAIL` | 문의 이메일 | index, terms, privacy |
| `OPERATOR_NAME` | 운영자 이름(영문) | terms, privacy |
| `atti18` | 깃허브 아이디 | index.html |
| `YOUR_CLIENT_KEY` | 개발자센터 Client key (공개돼도 되는 값, Secret은 절대 넣지 말 것) | index.html |
| `192.168.0.100:8080` | GX10 내부 IP와 대시보드 포트 | callback.html |

## 2. 배포
1. GitHub에 `shotdrama` 이름의 **Public** 저장소 생성
2. 이 폴더 파일 전부 업로드
3. Settings → Pages → Branch: `main` / `(root)` → Save
4. 1~2분 뒤 `https://atti18.github.io/shotdrama/` 접속 확인

## 3. TikTok 개발자센터 입력값
- Website URL: `https://atti18.github.io/shotdrama/`
- Terms of Service URL: `https://atti18.github.io/shotdrama/terms.html`
- Privacy Policy URL: `https://atti18.github.io/shotdrama/privacy.html`
- Platforms: **Web**
- Login Kit Redirect URI: `https://atti18.github.io/shotdrama/callback.html`

## 4. URL properties 인증
우측 상단 URL properties → URL prefix 방식으로 `https://atti18.github.io/shotdrama/` 등록 →
TikTok이 주는 인증 파일(예: `tiktokXXXX.txt`)을 내려받아 이 저장소 루트에 그대로 올리고 Verify.

## 5. 로그인 흐름
홈의 "Continue with TikTok" → TikTok 승인 → callback.html이 code 표시 →
"Finish on Shot Drama server" 클릭 시 GX10 로컬 대시보드(`/tiktok/callback`)로 code 전달 →
GX10이 Client secret으로 토큰 교환 후 refresh token 저장 (이후 Hermes가 무인 업로드).

※ 이 버튼은 GX10과 같은 네트워크에 있는 브라우저에서 눌러야 합니다. 외부에서는 "Copy code"로 복사해 수동 전달.
