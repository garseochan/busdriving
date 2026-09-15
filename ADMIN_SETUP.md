# PLANET BUS CHALLENGE 운영 설정 (v14)

## 구조 참고
- 햄스터 모험: 고정 캐릭터 + 배경/오브젝트 이동 방식, 실시간 랭킹 `ranking.getMyRank`, `ranking.getTopRanks`
- 래키 재우기: 모바일 430px 세로 규격, 유의사항 레이아웃, 결과 전면광고, 광고 추가기회, 공유 완료 1P 흐름

## 주요 정책
- 플레이 제한: 30초
- 퀴즈: 8개 정류장
- 점수: 통과 1개당 1,000점 + 완주 시 남은 시간 보너스(10ms당 1점) - 오답 1회당 100점
- 결과: COMPLETE 전송 → 결과 전면광고 → 점수/실시간 랭킹 표시
- 완주: `CLEAR_30SEC` 시 1P claim 대상
- 공유: `planet-bus-share-point` 완료 시 1P (중복 제한 정책은 어드민에서 관리)
- 기회 소진: 광고 완료 후 `participation.getExtraChance()`로 1회 추가

## Flow / Benefit
- clear flow: `planet-bus-clear-point` / `planet-bus-clear-1p`
- share flow: `planet-bus-share-point` / `planet-bus-share-1p`
- extra play flow: `planet-bus-ad-extra` / `planet-bus-ad-extra`

## 광고 Placement
- 결과 광고: `planet-bus-result-interstitial`
- 추가 기회 광고: `planet-bus-extra-play`

## Ranking
- `ranking.getMyRank()` : 결과 및 메인 내 순위
- `ranking.getTopRanks({limit:100})` : 랭킹 팝업
- 권장 scope: EVENT_BEST_SCORE
