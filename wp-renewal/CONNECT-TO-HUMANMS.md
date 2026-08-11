# humanms.co.kr → 채용 포털 연결 가이드

> WordPress 사이트(humanms.co.kr) 방문자가 채용 포털(hgcking-1.github.io/human_employment/)에서 고용·지원할 수 있도록 연결하는 3가지 방법입니다.

---

## 🎯 추천 조합

**즉시**: 방법 A(팝업) + 방법 B(헤더 메뉴) 병행
**여유될 때**: 방법 C(서브도메인)로 브랜드 완전 통합

---

## 방법 A — 팝업 (즉시 적용, 준비 완료)

방문자에게 눈에 띄는 채용 팝업을 우측 상단에 배치. 클릭 시 채용 포털이 새 탭으로 열림.

### 미리보기
**https://hgcking-1.github.io/human_employment/wp-renewal/popup-recruit-preview.html**

### 붙여넣기 코드
**https://hgcking-1.github.io/human_employment/wp-renewal/popup-recruit-snippet.html**

### 붙여넣기 방법 (Elementor Pro Custom Code)

1. `wp-admin` 로그인
2. **Elementor** → **Site Settings** → **Custom Code** → **Add New**
3. 설정:
   - Name: `채용 팝업`
   - Location: `</body> - End`
   - Status: Active
4. 스니펫 파일에서 `↓↓↓ 여기서부터 복사 ↓↓↓` ~ `↑↑↑ 여기까지 복사 ↑↑↑` 부분 복사
5. Custom Code 텍스트 상자에 붙여넣기 → **Publish**
6. Include Conditions → **Entire Site**

**대안**: Elementor Pro가 없다면 `Insert Headers and Footers` 또는 `WPCode` 플러그인 설치 후 Footer 영역에 붙여넣기.

---

## 방법 B — 헤더 메뉴 링크 (자연스러운 상시 노출)

WordPress 상단 메뉴에 "**채용/지원**" 항목을 추가.

### 순서

1. `wp-admin` 로그인
2. 좌측 메뉴 → **외모(Appearance)** → **메뉴(Menus)**
3. 편집할 메뉴 선택 (Primary Menu 등)
4. 좌측 **사용자 정의 링크(Custom Links)** 클릭
5. 입력:
   - **URL**: `https://hgcking-1.github.io/human_employment/`
   - **링크 텍스트**: `채용/지원` (또는 `채용 안내`, `구직자 지원` 등)
6. **메뉴에 추가** → 원하는 위치로 드래그 (예: CONTACT 옆)
7. **메뉴 저장**

### 새 탭에서 열리게 설정 (권장)

메뉴 항목 오른쪽 화살표를 눌러 펼친 뒤:
- **화면 옵션(Screen Options)** 우측 상단 → **링크 타겟(Link Target)** 체크
- 다시 메뉴 항목에서 **새 탭으로 링크 열기** 체크

이러면 방문자가 humanms.co.kr을 잃지 않고 채용 포털을 볼 수 있습니다.

---

## 방법 C — 서브도메인 연결 (완전 통합)

`채용.humanms.co.kr` 또는 `employment.humanms.co.kr` 같은 서브도메인을 만들어 GitHub Pages로 라우팅. 방문자에게는 여전히 **humanms.co.kr 도메인으로 보임**.

### 필요한 것

- humanms.co.kr 도메인 관리 권한 (도메인 등록기관 또는 DNS 관리 콘솔 접근)
- GitHub 저장소 관리 권한 (`hgcking-1/human_employment`)

### 순서

#### 1단계: DNS 설정 (도메인 등록기관에서)

CNAME 레코드 추가:

| Type | Name | Value |
|---|---|---|
| CNAME | 채용 (또는 employment) | `hgcking-1.github.io` |

한국어 서브도메인(`채용`)을 쓰려면 **Punycode**로 자동 변환됩니다. 관리자 페이지가 한국어 서브도메인을 지원 안 하면 영어(`employment`)를 추천.

#### 2단계: GitHub Pages에 커스텀 도메인 등록

1. GitHub 저장소 `hgcking-1/human_employment` → **Settings** → **Pages**
2. **Custom domain** 입력란에 `employment.humanms.co.kr` 입력 → **Save**
3. DNS 검증 성공하면 **Enforce HTTPS** 체크

#### 3단계: 저장소에 CNAME 파일 추가

터미널에서:

```bash
cd /path/to/human_employment
echo "employment.humanms.co.kr" > CNAME
git add CNAME
git commit -m "Custom domain: employment.humanms.co.kr"
git push
```

(제가 이 부분은 도메인 결정 후 대신 해드릴 수 있습니다.)

#### 4단계: DNS 전파 대기

- 보통 10분~1시간 (최대 24시간)
- 완료되면 **https://employment.humanms.co.kr** 로 채용 포털 접속 가능

#### 완성 후

방법 B의 헤더 메뉴 URL을 `https://hgcking-1.github.io/...` 대신 `https://employment.humanms.co.kr/` 로 교체하면 브랜드 완전 통합.

---

## 요약 비교

| 항목 | 방법 A (팝업) | 방법 B (메뉴) | 방법 C (서브도메인) |
|---|---|---|---|
| 소요 시간 | 5분 | 3분 | 30분 + 전파 대기 |
| wp-admin 필요 | ✓ | ✓ | ✗ |
| DNS 관리 필요 | ✗ | ✗ | ✓ |
| 도메인 표시 | 새 탭 (github.io) | 새 탭 (github.io) | humanms.co.kr 유지 |
| 눈에 띔 | 매우 강함 | 자연스러움 | 자연스러움 |
| 브랜드 통합 | 낮음 | 중간 | 최상 |

---

## 다음 단계

1. **오늘 바로**: 방법 A 팝업 + 방법 B 메뉴 붙여넣기
2. **1주 이내**: 사용 통계 확인 (방문자가 실제로 클릭하는지)
3. **여유될 때**: 방법 C 서브도메인 결정 → 알려주시면 CNAME 파일 대신 커밋해드림
