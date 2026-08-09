# 🌊 SCUBA MAP

Leaflet + OpenStreetMap 기반의 정적 인터랙티브 세계 스쿠버다이빙 지도입니다. 빌드 과정이나 서버 없이 브라우저에서 바로 실행되며, 개인 데이터는 브라우저 `localStorage`에 저장됩니다.

## 기능

- 14개 주요 세계 다이빙 포인트: 환경, 시즌, 생물, 권장 자격, 여행 주의사항
- 생물·지역·추천 월·난이도·자유 검색 필터
- 난이도별 지도 마커: 🟢 초급 / 🟡 중급 / 🔴 상급
- 포인트 카드와 가고 싶은 곳/다녀온 곳 상태 저장
- 다이빙 로그북 CRUD, 통계, JSON 내보내기·가져오기
- 모바일까지 대응하는 반응형 레이아웃

## 로컬에서 실행

`index.html`을 브라우저에서 열면 됩니다. Leaflet 지도 타일은 인터넷 연결이 필요합니다. 로컬 정적 서버가 필요하다면 `npx serve .` 등의 도구를 사용할 수 있습니다.

## GitHub Pages 배포

`.github/workflows/deploy-pages.yml`이 `main` 브랜치에 푸시될 때 GitHub Pages를 배포합니다.

1. GitHub 저장소 **Settings → Pages → Build and deployment**에서 Source를 **GitHub Actions**로 선택합니다.
2. `main`에 푸시합니다.
3. Actions의 **Deploy static content to Pages** 완료 후 표시되는 URL로 접속합니다.

## 데이터와 개인정보

다이빙 포인트 데이터는 `app.js`의 `spots` 배열에서 관리합니다. 위시리스트, 방문 기록, 로그북은 외부 서버로 전송되지 않고 현재 브라우저에만 저장됩니다. 브라우저/기기 변경 전에는 로그북의 JSON 내보내기를 권장합니다.

> 수온·시야·생물 출현은 해양 환경에 따라 달라집니다. 실제 여행 전에는 현지 다이브 센터와 최신 기상 정보를 확인하세요.
