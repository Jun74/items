# Google Sheets 연동형 링크 모음 (Tistory iframe)

## 폴더 구성
- index.html  : 카드 UI + 검색/정렬/카테고리 + CSV 파싱
- config.js   : 🔧 CSV_URL 설정 파일 (여기에 시트 CSV 주소를 붙여넣기)
- (옵션) sample.csv : 시트와 동일한 형식의 예시 데이터

## Google Sheets 준비
1) 시트 1행에 컬럼명 입력: `id, title, desc, href, img, category`
2) 몇 줄 예시 데이터 입력
3) **CSV로 공개**하는 URL 만들기 (2가지 방법 중 택1)
   - 방법 A: `파일 → 웹에 게시 → 링크 → 현재 시트 선택 → 형식: CSV` → 게시 → 주소 복사
   - 방법 B: 주소 변환
     - 시트 주소 예: `https://docs.google.com/spreadsheets/d/문서ID/edit#gid=0`
     - CSV 주소: `https://docs.google.com/spreadsheets/d/문서ID/export?format=csv&gid=0`
4) `config.js` 의 `CSV_URL` 값에 붙여넣기

## 배포 (GitHub Pages 예)
- 저장소 만들기 → `index.html`, `config.js` 업로드 → Settings → Pages 활성화
- URL 예: `https://username.github.io/links`
- Tistory 글에:
  <iframe src="https://username.github.io/links" width="100%" height="2000" style="border:0;"></iframe>

## 테스트 팁
- URL에 `?csv=...` 쿼리스트링으로 임시 CSV 주소 지정 가능:
  예) `https://username.github.io/links?csv=https%3A%2F%2Fdocs.google.com%2Fspreadsheets%2Fd%2F...%2Fexport%3Fformat%3Dcsv%26gid%3D0`

## 이미지 경로
- 권장: 티스토리에 이미지 업로드 후 HTML 보기에서 `<img src="...">` 주소 복사 → 시트의 `img` 컬럼에 넣기

## 자주 묻는 질문
- **카드 클릭 링크는?** `href` 컬럼에 넣으면 카드 전체가 해당 링크로 이동합니다.
- **카테고리는 어떻게?** `category` 컬럼에 값(예: 주방/수납)을 적으면 상단 필터로 필터링됩니다.
- **iframe 높이는?** Tistory 정책상 자동 변경이 제한될 수 있어 `height` 값을 넉넉히 주는 걸 권장합니다.
