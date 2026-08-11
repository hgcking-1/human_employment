# humanms.co.kr → 채용 포털 연결 가이드

> WordPress 사이트(humanms.co.kr) 방문자가 채용 포털(hgcking-1.github.io/human_employment/)에서 고용·지원할 수 있도록 연결하는 방법입니다.

## 🎯 추천: 방법 A + 방법 B 병행

- **방법 B(헤더 메뉴)**: 모든 방문자에게 자연스럽게 상시 노출
- **방법 A(팝업)**: 첫 방문 시 눈에 띄게 강조

두 가지를 함께 쓰면 자연스러움과 강조를 모두 잡을 수 있습니다.

---

## 방법 A — 팝업 (즉시 적용, 준비 완료)

방문자에게 눈에 띄는 채용 팝업을 우측 상단에 배치. 클릭 시 채용 포털이 새 탭으로 열림.

### 미리보기
**https://hgcking-1.github.io/human_employment/wp-renewal/popup-recruit-preview.html**

### 붙여넣기 코드
**https://hgcking-1.github.io/human_employment/wp-renewal/popup-recruit-snippet.html**

### 붙여넣기 방법 — Elementor Pro Custom Code (권장)

1. `wp-admin` 로그인
2. **Elementor** → **Site Settings** → **Custom Code** → **Add New**
3. 설정:
   - Name: `채용 팝업`
   - Location: `</body> - End`
   - Status: Active
4. 위 스니펫 파일에서 `↓↓↓ 여기서부터 복사 ↓↓↓` ~ `↑↑↑ 여기까지 복사 ↑↑↑` 부분 복사
5. Custom Code 텍스트 상자에 붙여넣기 → **Publish**
6. Include Conditions → **Entire Site** 선택

### 대안 — 플러그인 사용

Elementor Pro가 없으시면 `Insert Headers and Footers` 또는 `WPCode` 플러그인 설치:
1. **플러그인** → **새로 추가** → 검색 → 설치 → 활성화
2. **설정** → **Insert Headers and Footers** (또는 WPCode > 코드 스니펫)
3. **Scripts in Footer** 상자에 스니펫 붙여넣기 → 저장

### 대안 — The7 테마 옵션

1. `wp-admin` → **The7** → **Theme Options** → **Advanced Settings** → **Custom Code**
2. **Body Code** 항목에 스니펫 붙여넣기 → **Save Changes**

---

## 방법 B — 헤더 메뉴 링크 (자연스러운 상시 노출)

WordPress 상단 메뉴에 "**채용/지원**" 항목을 추가.

### 순서

1. `wp-admin` 로그인
2. 좌측 메뉴 → **외모(Appearance)** → **메뉴(Menus)**
3. 편집할 메뉴 선택 (Primary Menu 등)
4. 좌측 패널에서 **사용자 정의 링크(Custom Links)** 클릭 (안 보이면 상단 **화면 옵션(Screen Options)**에서 체크)
5. 입력:
   - **URL**: `https://hgcking-1.github.io/human_employment/`
   - **링크 텍스트**: `채용/지원` (또는 `채용 안내`, `구직자 지원` 등 원하시는 문구)
6. **메뉴에 추가** 클릭 → 원하는 위치로 드래그 (예: CONTACT 옆)
7. **메뉴 저장**

### 새 탭에서 열리게 설정 (권장 — 방문자가 humanms.co.kr을 잃지 않음)

1. **화면 옵션(Screen Options)** — 우측 상단에서 펼치기
2. **링크 타겟(Link Target)** 체크박스 활성화
3. 다시 메뉴로 돌아가 방금 추가한 "채용/지원" 항목의 화살표를 눌러 펼침
4. **새 탭으로 링크 열기** 체크 → **메뉴 저장**

---

## 요약 비교

| 항목 | 방법 A (팝업) | 방법 B (메뉴) |
|---|---|---|
| 소요 시간 | 5분 | 3분 |
| 눈에 띔 | 매우 강함 (모든 페이지에 팝업) | 자연스러움 (상단 메뉴) |
| 방문자 부담 | 있음 (닫기 필요) | 없음 |
| 재출현 | 세션마다 새로 뜸 | 항상 노출 |

---

## 다음 단계

1. **오늘 바로**: 방법 A + B 둘 다 붙여넣기 (총 8분)
2. **1주 이내**: 실제 방문자 반응 확인 (문의 늘었는지, 채용 지원 늘었는지)
3. **필요 시**: 팝업 문구·색상·이미지 등 조정 요청

수정하고 싶으신 부분(팝업 텍스트, 링크 URL, 노출 페이지 제한 등)이 있으면 언제든 알려주세요.
