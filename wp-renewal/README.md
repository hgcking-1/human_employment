# WordPress 사이트 수정 스니펫 모음

`humanms.co.kr` (WordPress + The7 + Elementor Pro) 에 붙여넣을 수 있도록 준비된 코드입니다.

## 파일 목록

| 파일 | 용도 |
|---|---|
| `popup-recruit-snippet.html` | 실제 붙여넣을 팝업 코드 (HTML + CSS + JS 자체 완결) |
| `popup-recruit-preview.html` | 붙여넣기 전에 팝업 모양을 확인할 수 있는 미리보기 페이지 |
| `index-mockup.html` | (참고용) 전체 리뉴얼 방향 목업 — 이번엔 사용 안 함 |

## 채용 팝업 미리보기

붙여넣기 전에 어떻게 보이는지 확인:

**https://hgcking-1.github.io/human_employment/wp-renewal/popup-recruit-preview.html**

## 붙여넣기 방법 (3가지 중 택 1)

### 방법 A — Elementor Pro Custom Code (가장 권장)

1. `wp-admin` 로그인
2. 좌측 메뉴 상단 **☰** → **Elementor** → **Site Settings**
3. **Custom Code** 클릭 → **Add New**
4. 다음과 같이 설정:
   - Name: `채용 팝업`
   - Location: **`</body> - End`**
   - Status: **Active**
5. `popup-recruit-snippet.html` 파일을 열어 `↓↓↓ 여기서부터 복사 ↓↓↓` 이후 부분부터 `↑↑↑ 여기까지 복사 ↑↑↑` 앞부분까지 전체 복사
6. 큰 텍스트 상자에 붙여넣기 → 우측 상단 **Publish**
7. **Include Conditions** 팝업이 뜨면 **Entire Site** 선택 → Save & Close

### 방법 B — "Insert Headers and Footers" 플러그인

Elementor Pro가 없거나 Custom Code 메뉴가 안 보일 때:

1. `wp-admin` > **플러그인** > **새로 추가**
2. `Insert Headers and Footers` 또는 `WPCode` 검색 → 설치 → 활성화
3. **설정** > **Insert Headers and Footers**
4. **Scripts in Footer** 상자에 스니펫 전체 붙여넣기
5. **Save**

### 방법 C — The7 테마 옵션

1. `wp-admin` > **The7** > **Theme Options** > **Advanced Settings** > **Custom Code**
2. **Body Code** 항목에 스니펫 전체 붙여넣기
3. **Save Changes**

## 결과 확인

- humanms.co.kr 로 접속하면 우측 상단(헤더 아래)에 채용 팝업이 살짝 튀어나오며 나타납니다.
- 팝업을 클릭하면 새 창에서 `https://hgcking-1.github.io/human_employment/contact.html#chaeum-apply` 로 이동합니다.
- 우측 상단 X 버튼을 누르면 팝업이 사라지고, 같은 브라우저 세션 동안 다시 나타나지 않습니다 (탭을 닫았다가 다시 열면 다시 표시).

## 조정 방법

`popup-recruit-snippet.html` 파일의 CSS 값을 수정한 뒤 다시 붙여넣으면 반영됩니다.

| 항목 | CSS 위치 | 기본값 |
|---|---|---|
| 팝업 위치 (헤더 아래 여백) | `#hms-recruit-popup { top: ... }` | `100px` |
| 팝업 위치 (우측 여백) | `#hms-recruit-popup { right: ... }` | `24px` |
| 팝업 너비 | `#hms-recruit-popup { width: ... }` | `260px` |
| 이미지 세로 크기 | `.hms-image { height: ... }` | `320px` |
| 링크 URL | `<a class="hms-link" href="...">` | chaeum-apply |
| 배지 문구 | `<div class="hms-badge">채용중</div>` | `채용중` |
| 상단 배지 색상 | `.hms-badge { background: ... }` | `#FF5252` (빨강) |
| CTA 버튼 색상 | `.hms-cta { background: ... }` | `#FFB800` 그라디언트 (골드) |

## 팝업 삭제 방법

붙여넣은 방법에 따라:

- **방법 A**: Elementor > Site Settings > Custom Code > "채용 팝업" > 삭제
- **방법 B**: Insert Headers and Footers > 붙여넣은 부분 지우고 저장
- **방법 C**: The7 Theme Options > Body Code 비우고 저장
