```markdown
# Solar System Ultimate v4.4 — Real Sky Alignment

![Solar System Logo](https://svgshare.com/i/11r9.svg)  
**실제 천구좌표계와 정확히 정렬된 고품질 3D 태양계 시뮬레이터**  
은하수 배경 + 주요 별자리 + 행성/소행성 궤도 + 실시간 천문 계산

[![MIT License](https://img.shields.io/badge/license-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![AI Assisted](https://img.shields.io/badge/AI_Assisted-Gemini_3_&_Grok_4-purple.svg)](#)
[![Three.js](https://img.shields.io/badge/Three.js-r158-000000.svg?logo=three.js)](#)

## 데모 바로가기
→ [https://whitebee-dev.github.io/solar-system-ultimate/](https://whitebee-dev.github.io/solar-system-ultimate/)

## 텍스처 출처 (Textures Credits)

모든 행성/위성/고리 텍스처는 **Solar System Scope**에서 제공하는 무료 고해상도 맵을 사용하였으며,  
비상업적·상업적 모두 허용되는 라이선스(CC BY 4.0 또는 동등)로 배포되고 있습니다.


| 객체              | 사용 파일명                        | 링크 (2K 기준)                                                                 |
|-------------------|------------------------------------|------------------------------------------------------------------------------------|
| Sun               | 2k_sun.jpg                         | https://www.solarsystemscope.com/textures/download/2k_sun.jpg                      |
| Mercury           | 2k_mercury.jpg                     | https://www.solarsystemscope.com/textures/download/2k_mercury.jpg                  |
| Venus             | 2k_venus_surface.jpg               | https://www.solarsystemscope.com/textures/download/2k_venus_surface.jpg            |
| Earth (Day)       | 2k_earth_daymap.jpg                | https://www.solarsystemscope.com/textures/download/2k_earth_daymap.jpg             |
| Earth (Night)     | 2k_earth_nightmap.jpg              | https://www.solarsystemscope.com/textures/download/2k_earth_nightmap.jpg           |
| Earth (Clouds)    | 2k_earth_clouds.jpg                | https://www.solarsystemscope.com/textures/download/2k_earth_clouds.jpg             |
| Moon              | 2k_moon.jpg                        | https://www.solarsystemscope.com/textures/download/2k_moon.jpg                    |
| Mars              | 2k_mars.jpg                        | https://www.solarsystemscope.com/textures/download/2k_mars.jpg                    |
| Jupiter           | 2k_jupiter.jpg                     | https://www.solarsystemscope.com/textures/download/2k_jupiter.jpg                 |
| Saturn            | 2k_saturn.jpg                      | https://www.solarsystemscope.com/textures/download/2k_saturn.jpg                  |
| Saturn Ring       | 2k_saturn_rings.png                | https://www.solarsystemscope.com/textures/download/2k_saturn_rings.png            |
| Uranus            | 2k_uranus.jpg                      | https://www.solarsystemscope.com/textures/download/2k_uranus.jpg                  |
| Neptune           | 2k_neptune.jpg                     | https://www.solarsystemscope.com/textures/download/2k_neptune.jpg                 |
| Pluto             | plutomap2k.jpg                       | https://planetpixelemporium.com/pluto.html                   |
| Stars (Milky Way) | 8k_stars_milky_way.jpg             | https://www.solarsystemscope.com/textures/download/8k_stars_milky_way.jpg          |
| Ceres, Vesta 등   | 2k~8k 공식 맵 또는 fictional map   | 동일 도메인 내 파일 사용                                                            |

**출처 명시 예시 (README나 페이지 하단에 넣으면 완벽)**
> Textures by [Solar System Scope](https://www.solarsystemscope.com/textures/) / CC BY 4.0

**8K 버전이 필요하면**  
→ `8k_earth_daymap.jpg`, `8k_stars_milky_way.jpg` 등 파일명만 8k_ 로 바꾸면 됩니다.  
모바일 성능을 위해 현재 프로젝트는 2K~4K 위주로 사용 중.

### 배포 시 텍스처 경로 수정 권장

현재 코드의 `./textures/` → 아래와 같이 바꾸면 로컬 파일 없이 바로 GitHub Pages 등에서 동작합니다.

```js
const TEX_PATH = 'https://www.solarsystemscope.com/textures/download/';
```

## 특징

- 실제 천문 데이터 기반 실시간 위치 계산 (`astronomy-engine`)
- 은하수 배경을 실제 관측과 정렬할 수 있는 **X/Y축 캘리브레이션 슬라이더** (v4.4 신규)
- 주요 40개 별자리 라벨 + 클릭 시 설명 툴팁
- 태양계 행성 11개 + 달 + 주요 소행성/왜행성 9개
- 정확한 케플러 궤도 계산 (소행성)
- 지구 야간 조명, 구름 레이어, 토성 고리 등 고품질 텍스처
- Unreal Bloom + 후처리 효과
- 카메라 락, 시간 가속, 날짜 지정 이동 가능
- 순수 HTML/CSS/JS → 서버 없이 `index.html` 하나로 실행

## 설치 및 실행 (너무 쉽습니다)

```bash
# 1. 저장소 클론 or index.html 단일 파일 다운로드
git clone https://github.com/whitebee-dev/solar-system-ultimate.git
cd solar-system-ultimate

# 2. 아무 웹서버로 열기 (로컬 파일 열기 가능하지만 CORS 때문에 권장하지 않음)
# 예시:
npx serve .
# 또는
python -m http.server 8000
```

그 후 브라우저에서 `http://localhost:8000` (또는 해당 포트) 접속 → 즉시 실행!

> **필요 환경**: 현대 브라우저 (Chrome/Edge/Firefox/Safari 최신 버전)  
> 웹서버만 있으면 됩니다. Node.js, 빌드 도구 전혀 필요 없음.

## 사용 방법

| 기능                  | 조작 방법                                      |
|-----------------------|------------------------------------------------|
| 시점 이동             | 마우스 드래그 / 터치                                  |
| 확대/축소             | 마우스 휠 / 핀치 제스처                                |
| 행성 이동             | 상단 좌우 버튼 또는 `Tab` 키                          |
| 카메라 락             | 설정 → Lock Camera 체크                               |
| 시간 가속             | 하단 슬라이더 (최대 500,000배속)                       |
| 특정 날짜 이동        | 날짜 선택기 사용                                      |
| 은하수 정렬           | 설정 → SKY CALIBRATION 슬라이더 (Y축 좌우, X축 상하)    |
| 별자리 라벨 토글      | 설정 → Constellation Labels                           |

## 기술 스택 & 주요 계산 공식

| 항목                    | 사용 기술 / 라이브러리                                                                 |
|-------------------------|---------------------------------------------------------------------------------------|
| 3D 엔진                 | Three.js r158                                                                          |
| 궤도/위치 계산          | [Astronomy Engine](https://github.com/cosinekitty/astronomy) v2.1.19                 |
| 케플러 방정식 해           | Newton-Raphson 반복법 (solveKepler 함수)                                               |
| 소행성 궤도 요소         | `a, e, i, Ω, ω, M` → 헬리오센트릭 좌표 변환 (getKeplerPos)                              |
| 지구 자전               | GMST (그리니치 항성시) 기반 실시간 회전                                                |
| 별자리 좌표             | 적경/적위(RA/Dec) → 구면 → 데카르트 변환 → 거대 구에 배치                                  |
| 은하수 배경 정렬         | 배경 스피어에 YXZ 오일러 회전 적용 (실제 관측 사진과 정확히 맞춤)                         |
| 후처리                  | UnrealBloomPass (항성/태양 빛번짐 효과)                                                |
| 라벨 렌더링             | CSS2DRenderer (DOM 라벨, 성능 최적화)                                                  |

### 케플러 방정식 해법 (주요 부분)

```js
function solveKepler(M, ecc) {
    let E = (ecc > 0.8) ? Math.PI : M;
    let delta = 1;
    while (Math.abs(delta) > 1e-12) {
        delta = (E - ecc * Math.sin(E) - M) / (1 - ecc * Math.cos(E));
        E -= delta;
    }
    return E;
}
```

→ 최대 50회 반복, 10⁻¹² 수준 정밀도로 근사 이심각(E)을 구한 뒤 실제 위치 계산

## 라이선스
**Code**: MIT License  
**Textures**: See [LICENSE-textures.md](LICENSE-textures.md) for detail


## Credits & AI Assisted

- **Original Author & Final Review**: whitebee  
- **AI 도움**: Google Gemini 3, xAI Grok 4  


---

즐거운 우주 탐험 되세요!  
문의·버그리포트·스타는 언제나 환영합니다 ✨
```