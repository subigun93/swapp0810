# PRD: 코드론 리모콘 연습 웹앱

## 1. 개요
- **목적**: 코드론 미니 드론 수업 첫 시간, 실제 드론을 만지기 전에 리모콘 조작법(버튼·스틱 위치)을 손에 익히는 연습용 웹앱
- **형태**: 설치 불필요, 브라우저에서 바로 실행되는 단일 웹페이지 (class-tool 폴더 내 HTML 파일)
- **저장/로그인**: 없음. 서버 없음. 새로고침하면 기록도 초기화됨.

## 2. 왜 (문제 정의)
학생들이 실제 드론 앞에서 리모콘 버튼과 스틱 위치를 몰라 당황하는 것을 줄인다. 말로 설명하기 어려운 "스틱을 이렇게 움직이면 드론이 이렇게 움직인다"는 감각을, 직접 손으로 조작해보며 익히게 한다.

## 3. 사용자
- **대상**: 중학교 학생
- **언어**: 한국어 / 러시아어 선택 가능 (화면 내 언어 전환 버튼)
- **사용 시점**: 코드론 수업 1교시, 실습 드론을 만지기 직전 약 10분간
- **사용 기기**: 노트북(마우스) + 휴대폰(터치) 모두 지원 — 반응형 레이아웃

## 4. 기능 범위

### 4.1 튜토리얼 모드 (1단계~7단계, 순서대로 진행)
| 단계 | 내용 |
|---|---|
| 1 | 전원 켜는 방법 |
| 2 | 이륙 |
| 3 | 호버링(제자리 비행) |
| 4 | 전진 / 후진 |
| 5 | 좌우 이동 |
| 6 | 드론 위치 정렬(회전) |
| 7 | 착륙 |

각 단계마다:
- 화면에 **글자 설명** (현재 언어에 맞게)
- 화면에 **리모콘 그림** (양손 스틱 위치 표시)
- 스틱을 마우스로 드래그(휴대폰은 터치 드래그)하면 그에 맞춰 **드론이 애니메이션으로 반응**
- 해당 단계 동작을 올바르게 수행하면 **효과음** 재생 + 완료 표시
- **"이전 단계" / "다음 단계" 버튼** — 헷갈리면 언제든 되돌아가 다시 시도 가능
- **진행 표시** (예: "3 / 7단계")

### 4.2 미니 게임 모드 (튜토리얼 7단계 완료 후 진입)
- **목표**: 출발지에서 이륙 → 높낮이가 다른 원형 장애물(4~8개) 통과 → H 착륙장에 착륙
- **난이도 선택**: 초급 / 중급 / 고급 (장애물 개수·간격·높낮이 차이로 난이도 구분)
- **시간 측정**: 이륙~착륙까지 걸린 시간을 화면에 표시 (저장하지 않고 그 세션에서만 보여줌)
- **조작**: 튜토리얼과 동일하게 리모콘 스틱 드래그

## 5. 화면 구성 (레이아웃)

화면은 세로로 길게 3구역(상단 정보 / 중앙 시뮬레이션 / 하단 조작부)으로 나뉜다. 노트북·휴대폰 모두 이 순서를 그대로 유지하되, 휴대폰에서는 각 구역 높이가 화면 비율에 맞게 줄어든다.

### 5.1 튜토리얼 화면 (위 → 아래 순서)
1. **상단바**
   - 왼쪽: 언어 선택 버튼 (한국어 / русский)
   - 오른쪽: 진행 표시 ("3 / 7단계")
2. **단계 제목** — 큰 글씨로 현재 단계 이름 (예: "이륙하기")
3. **드론 시뮬레이션 영역** (화면 중앙, 가장 넓은 공간)
   - 드론이 배경 위에서 스틱 조작에 따라 움직이는 애니메이션
4. **단계 설명 텍스트** — 드론 영역 바로 아래, 쉬운 말로 1~2문장
   - 성공 시 이 자리에 완료 표시(체크 아이콘 등) + 효과음
5. **리모콘 조작부** (화면 하단, 고정)
   - 왼쪽 스틱 + 오른쪽 스틱 (마우스/터치로 드래그)
6. **맨 아래 버튼줄**
   - 왼쪽: "이전 단계" 버튼
   - 오른쪽: "다음 단계" 버튼 (해당 단계 성공 전에는 비활성화 또는 계속 시도 가능)

### 5.2 미니 게임 화면 진입 전 — 난이도 선택 화면
1. **상단바**: 언어 선택
2. **중앙**: "난이도를 선택하세요" 안내 문구
3. **난이도 버튼 3개** (세로 또는 가로 나열): 초급 / 중급 / 고급
4. **하단**: "튜토리얼 다시 하기" 버튼 (돌아가기용)

### 5.3 미니 게임 플레이 화면 (위 → 아래 순서)
1. **상단바**
   - 왼쪽: 언어 선택
   - 가운데: 선택한 난이도 표시
   - 오른쪽: 경과 시간(타이머)
2. **코스 시뮬레이션 영역** (화면 중앙, 가장 넓은 공간)
   - 출발지, 높낮이가 다른 원형 장애물(4~8개), H 착륙장이 한 화면에 보이는 코스
   - 드론이 스틱 조작에 따라 코스를 통과
3. **리모콘 조작부** (화면 하단, 고정) — 튜토리얼과 동일한 위치/형태
4. **완료 시**: 코스 화면 위에 결과 팝업
   - 성공/충돌 여부, 걸린 시간
   - "다시 하기" 버튼, "난이도 다시 선택" 버튼

## 6. 완료 조건
1. 튜토리얼 7단계를 순서대로 모두 완료
2. 이어서 미니 게임에서 이륙 → 장애물 통과 → H 착륙장 착륙을 성공
3. (반복 연습 목적이므로 게임은 여러 번 재도전 가능, "끝"이 고정되어 있지 않음)

## 7. 비범위 (Out of Scope)
- 로그인/계정 기능 없음
- 서버 저장, 기록 공유/랭킹 없음
- 실제 코드론 기기와의 블루투스/실물 연동 없음
- 별도 프로그램 설치 없음 (브라우저만 있으면 실행)

## 8. 기술 방향 (참고)
- 단일 HTML/CSS/JS 파일 (또는 최소 구성의 몇 개 파일), class-tool 폴더에 저장
- 외부 설치·빌드 과정 없이 브라우저에서 파일을 열면 바로 동작
- 반응형 CSS로 노트북/휴대폰 모두 대응, 마우스 드래그와 터치 드래그 모두 처리

## 9. 확정되지 않은 세부사항 (개발 중 결정 예정)
- 효과음 종류 및 구체적 트리거 조건
- 게임 모드 장애물 배치(좌표) 및 난이도별 정확한 파라미터
- 코드론 실제 리모콘(https://robolink.co.kr/web/cate02/product05.php) 버튼 배치와의 대응 여부 확인 필요

## 10. 그래픽 자산 (드론 · 리모콘 SVG)

원본 파일: `assets/drone.svg`, `assets/remote.svg` (코드론 공식 제품 사진의 색상·형태를 참고한 벡터 그림)

### 10.1 드론

검정 몸체 + 앞쪽(노란 프로펠러 사이)을 가리키는 빨간 세로줄, 프로펠러 가드 4개 (앞 2개 노란 프로펠러, 뒤 2개 흰색 프로펠러). `class="propeller"` 그룹은 회전 애니메이션을 걸기 위해 분리되어 있음.

<svg viewBox="0 0 400 400" xmlns="http://www.w3.org/2000/svg" id="drone-illustration" width="260">
  <g id="drone-arms" stroke="#2b2b2b" stroke-width="26" stroke-linecap="round">
    <line x1="200" y1="200" x2="95" y2="95"/>
    <line x1="200" y1="200" x2="305" y2="95"/>
    <line x1="200" y1="200" x2="95" y2="305"/>
    <line x1="200" y1="200" x2="305" y2="305"/>
  </g>
  <g id="drone-legs" fill="#1a1a1a">
    <rect x="130" y="300" width="12" height="55" rx="6"/>
    <rect x="258" y="300" width="12" height="55" rx="6"/>
  </g>
  <g id="drone-guards" fill="none" stroke="#111111" stroke-width="12">
    <circle cx="95" cy="95" r="66"/>
    <circle cx="305" cy="95" r="66"/>
    <circle cx="95" cy="305" r="66"/>
    <circle cx="305" cy="305" r="66"/>
  </g>
  <g class="propeller" id="prop-back-left" transform="translate(95,95)">
    <ellipse rx="52" ry="9" fill="#f4f4f4" stroke="#1a1a1a" stroke-width="3" transform="rotate(20)"/>
    <ellipse rx="52" ry="9" fill="#f4f4f4" stroke="#1a1a1a" stroke-width="3" transform="rotate(110)"/>
    <circle r="9" fill="#1a1a1a"/>
  </g>
  <g class="propeller" id="prop-back-right" transform="translate(305,95)">
    <ellipse rx="52" ry="9" fill="#f4f4f4" stroke="#1a1a1a" stroke-width="3" transform="rotate(20)"/>
    <ellipse rx="52" ry="9" fill="#f4f4f4" stroke="#1a1a1a" stroke-width="3" transform="rotate(110)"/>
    <circle r="9" fill="#1a1a1a"/>
  </g>
  <g class="propeller" id="prop-front-left" transform="translate(95,305)">
    <ellipse rx="52" ry="9" fill="#f5c518" stroke="#1a1a1a" stroke-width="3" transform="rotate(20)"/>
    <ellipse rx="52" ry="9" fill="#f5c518" stroke="#1a1a1a" stroke-width="3" transform="rotate(110)"/>
    <circle r="9" fill="#1a1a1a"/>
  </g>
  <g class="propeller" id="prop-front-right" transform="translate(305,305)">
    <ellipse rx="52" ry="9" fill="#f5c518" stroke="#1a1a1a" stroke-width="3" transform="rotate(20)"/>
    <ellipse rx="52" ry="9" fill="#f5c518" stroke="#1a1a1a" stroke-width="3" transform="rotate(110)"/>
    <circle r="9" fill="#1a1a1a"/>
  </g>
  <g id="drone-body">
    <ellipse cx="200" cy="200" rx="72" ry="46" fill="#1c1c1c"/>
    <path d="M 200 168 L 200 300" stroke="#e2231a" stroke-width="8" stroke-linecap="round"/>
    <circle cx="200" cy="200" r="10" fill="#3a3a3a"/>
  </g>
</svg>

```svg
<svg viewBox="0 0 400 400" xmlns="http://www.w3.org/2000/svg" id="drone-illustration">
  <!-- 팔(중심 -> 프로펠러) -->
  <g id="drone-arms" stroke="#2b2b2b" stroke-width="26" stroke-linecap="round">
    <line x1="200" y1="200" x2="95" y2="95"/>
    <line x1="200" y1="200" x2="305" y2="95"/>
    <line x1="200" y1="200" x2="95" y2="305"/>
    <line x1="200" y1="200" x2="305" y2="305"/>
  </g>

  <!-- 착륙 다리 -->
  <g id="drone-legs" fill="#1a1a1a">
    <rect x="130" y="300" width="12" height="55" rx="6"/>
    <rect x="258" y="300" width="12" height="55" rx="6"/>
  </g>

  <!-- 프로펠러 가드(링) -->
  <g id="drone-guards" fill="none" stroke="#111111" stroke-width="12">
    <circle cx="95" cy="95" r="66"/>
    <circle cx="305" cy="95" r="66"/>
    <circle cx="95" cy="305" r="66"/>
    <circle cx="305" cy="305" r="66"/>
  </g>

  <!-- 프로펠러 (뒤쪽 흰색) -->
  <g class="propeller" id="prop-back-left" transform="translate(95,95)">
    <ellipse rx="52" ry="9" fill="#f4f4f4" stroke="#1a1a1a" stroke-width="3" transform="rotate(20)"/>
    <ellipse rx="52" ry="9" fill="#f4f4f4" stroke="#1a1a1a" stroke-width="3" transform="rotate(110)"/>
    <circle r="9" fill="#1a1a1a"/>
  </g>
  <g class="propeller" id="prop-back-right" transform="translate(305,95)">
    <ellipse rx="52" ry="9" fill="#f4f4f4" stroke="#1a1a1a" stroke-width="3" transform="rotate(20)"/>
    <ellipse rx="52" ry="9" fill="#f4f4f4" stroke="#1a1a1a" stroke-width="3" transform="rotate(110)"/>
    <circle r="9" fill="#1a1a1a"/>
  </g>

  <!-- 프로펠러 (앞쪽 노란색) -->
  <g class="propeller" id="prop-front-left" transform="translate(95,305)">
    <ellipse rx="52" ry="9" fill="#f5c518" stroke="#1a1a1a" stroke-width="3" transform="rotate(20)"/>
    <ellipse rx="52" ry="9" fill="#f5c518" stroke="#1a1a1a" stroke-width="3" transform="rotate(110)"/>
    <circle r="9" fill="#1a1a1a"/>
  </g>
  <g class="propeller" id="prop-front-right" transform="translate(305,305)">
    <ellipse rx="52" ry="9" fill="#f5c518" stroke="#1a1a1a" stroke-width="3" transform="rotate(20)"/>
    <ellipse rx="52" ry="9" fill="#f5c518" stroke="#1a1a1a" stroke-width="3" transform="rotate(110)"/>
    <circle r="9" fill="#1a1a1a"/>
  </g>

  <!-- 몸체 -->
  <g id="drone-body">
    <ellipse cx="200" cy="200" rx="72" ry="46" fill="#1c1c1c"/>
    <path d="M 200 168 L 200 300" stroke="#e2231a" stroke-width="8" stroke-linecap="round"/>
    <circle cx="200" cy="200" r="10" fill="#3a3a3a"/>
  </g>
</svg>
```

### 10.2 리모콘

검정 바디, 노란 테두리 스틱 2개, "ROBOLINK" 로고, 상단 스위치 2개. `stick-left`/`stick-right` 그룹은 드래그 조작 시 위치를 옮기기 위해 분리되어 있음.

<svg viewBox="0 0 420 260" xmlns="http://www.w3.org/2000/svg" id="remote-illustration" width="260">
  <rect x="10" y="10" width="400" height="240" rx="34" fill="#1c1c1c"/>
  <rect x="10" y="10" width="400" height="240" rx="34" fill="none" stroke="#000000" stroke-width="4"/>
  <rect x="30" y="0" width="26" height="24" rx="6" fill="#f5c518"/>
  <rect x="364" y="0" width="26" height="24" rx="6" fill="#f5c518"/>
  <text x="210" y="42" text-anchor="middle" font-family="Arial, sans-serif" font-size="18" font-weight="bold" fill="#f5c518">ROBOLINK</text>
  <rect x="45" y="55" width="46" height="16" rx="8" fill="#3a3a3a" stroke="#f5c518" stroke-width="2"/>
  <rect x="329" y="55" width="46" height="16" rx="8" fill="#3a3a3a" stroke="#f5c518" stroke-width="2"/>
  <g id="stick-left-base">
    <circle cx="120" cy="160" r="62" fill="#111111"/>
    <circle cx="120" cy="160" r="62" fill="none" stroke="#f5c518" stroke-width="4"/>
  </g>
  <g id="stick-left" class="stick" data-stick="left" transform="translate(120,160)">
    <circle r="34" fill="#2b2b2b"/>
    <circle r="34" fill="none" stroke="#f5c518" stroke-width="5"/>
    <circle r="12" fill="#f5c518"/>
  </g>
  <g id="stick-right-base">
    <circle cx="300" cy="160" r="62" fill="#111111"/>
    <circle cx="300" cy="160" r="62" fill="none" stroke="#f5c518" stroke-width="4"/>
  </g>
  <g id="stick-right" class="stick" data-stick="right" transform="translate(300,160)">
    <circle r="34" fill="#2b2b2b"/>
    <circle r="34" fill="none" stroke="#f5c518" stroke-width="5"/>
    <circle r="12" fill="#f5c518"/>
  </g>
  <circle cx="210" cy="200" r="14" fill="#e2231a"/>
  <circle cx="210" cy="160" r="10" fill="#3a3a3a" stroke="#f5c518" stroke-width="2"/>
</svg>

```svg
<svg viewBox="0 0 420 260" xmlns="http://www.w3.org/2000/svg" id="remote-illustration">
  <!-- 몸체 -->
  <rect x="10" y="10" width="400" height="240" rx="34" fill="#1c1c1c"/>
  <rect x="10" y="10" width="400" height="240" rx="34" fill="none" stroke="#000000" stroke-width="4"/>

  <!-- 상단 안테나/손잡이 느낌 -->
  <rect x="30" y="0" width="26" height="24" rx="6" fill="#f5c518"/>
  <rect x="364" y="0" width="26" height="24" rx="6" fill="#f5c518"/>

  <!-- 로고 영역 -->
  <text x="210" y="42" text-anchor="middle" font-family="Arial, sans-serif" font-size="18" font-weight="bold" fill="#f5c518">ROBOLINK</text>

  <!-- 좌측 상단 스위치 -->
  <rect x="45" y="55" width="46" height="16" rx="8" fill="#3a3a3a" stroke="#f5c518" stroke-width="2"/>
  <!-- 우측 상단 스위치 -->
  <rect x="329" y="55" width="46" height="16" rx="8" fill="#3a3a3a" stroke="#f5c518" stroke-width="2"/>

  <!-- 왼쪽 스틱 -->
  <g id="stick-left-base">
    <circle cx="120" cy="160" r="62" fill="#111111"/>
    <circle cx="120" cy="160" r="62" fill="none" stroke="#f5c518" stroke-width="4"/>
  </g>
  <g id="stick-left" class="stick" data-stick="left" transform="translate(120,160)">
    <circle r="34" fill="#2b2b2b"/>
    <circle r="34" fill="none" stroke="#f5c518" stroke-width="5"/>
    <circle r="12" fill="#f5c518"/>
  </g>

  <!-- 오른쪽 스틱 -->
  <g id="stick-right-base">
    <circle cx="300" cy="160" r="62" fill="#111111"/>
    <circle cx="300" cy="160" r="62" fill="none" stroke="#f5c518" stroke-width="4"/>
  </g>
  <g id="stick-right" class="stick" data-stick="right" transform="translate(300,160)">
    <circle r="34" fill="#2b2b2b"/>
    <circle r="34" fill="none" stroke="#f5c518" stroke-width="5"/>
    <circle r="12" fill="#f5c518"/>
  </g>

  <!-- 하단 작은 버튼 2개 (이착륙 등) -->
  <circle cx="210" cy="200" r="14" fill="#e2231a"/>
  <circle cx="210" cy="160" r="10" fill="#3a3a3a" stroke="#f5c518" stroke-width="2"/>
</svg>
```
