# 2027 싱가포르 여행 모바일 웹앱

## 배포 (GitHub Pages)
1. GitHub에서 새 공개 저장소(예: singapore-trip-2027)를 생성합니다.
2. 이 폴더의 `index.html`, `site-config.js`, `manifest.webmanifest`, `sw.js`, `icon-192.png`, `icon-512.png` 파일을 저장소 루트에 올립니다.
3. 저장소 Settings > Pages > Build and deployment > Deploy from a branch > main / (root)를 선택합니다.
4. 게시된 `https://사용자명.github.io/저장소명/` 주소를 Android Chrome으로 엽니다.
5. 메뉴(⋮) > 앱 설치 또는 홈 화면에 추가. 사이트에서 '공유하기' 버튼을 누르거나 링크를 보내면 여자친구도 동일한 일정을 봅니다.

## Google Maps API 키 공유 설정
- 기본적으로 각 기기에서 Maps JavaScript API 키를 입력하는 방식입니다. 키는 저장하지 않으며 파일·사이트에 포함하지 않습니다.
- 두 기기 모두 자동으로 지도가 나타나도록 하려면 `site-config.js`의 mapsApiKey에 **웹사이트 용도로 제한된** 키를 입력하여 재배포하세요. 이 키는 웹페이지 소스에서 보이므로 비밀 키로 간주하면 안 됩니다.
- Google Cloud Console > Credentials > 해당 API 키 > Application restrictions: Websites > `https://사용자명.github.io/*` (실제 게시 주소에 맞게). API restrictions: Maps JavaScript API만 허용(추가 사용 서비스에 따라 조정). 비용 예산 및 사용량 한도도 확인하세요.
- 이미 다른 목적으로 쓰는 키보다 배포 사이트 전용 키를 새로 만드는 편이 안전합니다.

## 기능 / 제한
- 기존 여행 일정, 남색 헤더, 번호 마커, 오프라인 경로도, 이동 구간별 Google Maps 길찾기 유지.
- 모바일 지도 확대 버튼, 공유하기, Android 홈 화면 설치 기능 추가.
- PWA 자체 UI와 순서도는 오프라인 캐시 사용 가능. 실제 Google 지도 타일과 외부 길찾기는 인터넷 필요.
- 연결선은 방문 순서 직선이며 실제 도로가 아닙니다. 실제 도로는 구간별 Google Maps 길찾기를 사용하세요.
- GitHub Pages 주소는 공개 링크입니다. 일정에 민감한 개인정보나 비공개 API 자격증명을 넣지 마세요.
- 여행 일정의 영업시간, 야간 칠리크랩/마사지 예약 가능 여부를 출발 전에 재확인하세요.

## 이번 버전 추가 사항
- 탭 4개: 일정·지도 / 예산 계산 / 예약 체크 / 장소 정보
- 일정 카드마다 2인 예상 비용과 사용 내역 노출. 무료 일정과 교통 공통 예산은 중복 합산하지 않습니다.
- 예산은 원본 엑셀 `02_예산계산`의 중심 예상치(S$723), 환율 S$1=1,100원 가정과 동일합니다.
- 예상 숙박비 S$160 포함 / 제외 변경 가능; 실제 지출은 개별 입력 후 기기별 localStorage에만 저장됩니다.
- 예약 체크 상태도 각자 기기에만 저장됩니다. URL 공유는 일정 내용을 공유하지만 입력 내용은 동기화되지 않습니다.
- 여행 정보는 추정치이며 특히 늦은 시간 칠리크랩·마사지 운영 확인 필요.
