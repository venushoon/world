# world
반영했어요! 새 파일 **“프랑스 메모리 게임 V4 (Wikipedia API 이미지 자동로딩)”**을 캔버스에 올렸습니다.

이번 변경 핵심
	•	Wikipedia API 연동(기본 ON, 상단 체크박스로 ON/OFF):
	•	우선 ko.wikipedia.org에서 페이지 대표 썸네일을 가져오고, 없으면 en.wikipedia.org로 재시도.
	•	1차: action=query&prop=pageimages&pithumbsize=…
2차: REST /page/summary/{title}
	•	둘 다 실패 시 기존 Wikimedia 고정 URL로 폴백.
	•	결과는 메모리 캐시해 중복 호출을 줄였습니다.
	•	비동기 로딩 UI: 이미지 뒷면에 스피너 표시 후 로드 완료 시 교체.
	•	캐시 우회: 최종 URL에 ?v=랜덤을 덧붙여 학교/브라우저 캐시 이슈 최소화.
	•	타이틀 매핑: 각 카드에 title_ko, title_en을 추가해 한글→영문 순으로 조회.

사용 팁
	•	상단의 “Wikipedia API로 이미지 불러오기” 체크가 켜져 있어야 API 썸네일을 사용합니다.
(네트워크 사정상 Wikipedia는 열리지만 Wikimedia가 차단된 환경이라면, 이 옵션 ON이 특히 유용합니다.)
	•	세트/난이도 변경 시 즉시 새로 로드합니다.
