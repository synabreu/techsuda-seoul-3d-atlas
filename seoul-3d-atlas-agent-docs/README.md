# Seoul 3D Atlas

서울 전역을 웹 브라우저에서 직접 탐색할 수 있도록 만든 인터랙티브 미니어처 3D 지도 프로젝트이다.

사용자는 서울 전체를 한눈에 보고, 지도를 회전·확대·축소·이동할 수 있다. 25개 자치구, 한강, 주요 도로, 건물, 산악 지형, 14개 주요 랜드마크를 하나의 3D 장면에서 탐색하는 것을 목표로 한다.

## 프로젝트 요구사항과 AGENTS.md의 차이

### 프로젝트 요구사항

프로젝트 요구사항은 **무엇을 만들어야 하는가**를 정의한다.

예:
- 서울 25개 자치구를 표시한다.
- 14개 랜드마크 자동 비행을 제공한다.
- 낮, 노을, 야경 모드를 제공한다.
- 건물 데이터를 압축 이진 형식으로 저장한다.

즉, 제품의 목표, 기능, 품질 기준, 완료 조건을 정의한다.

### AGENTS.md

`AGENTS.md`는 **AI 에이전트가 이 저장소에서 어떻게 작업해야 하는가**를 정의한다.

예:
- 기존 코드를 먼저 읽는다.
- 측정하지 않은 FPS를 주장하지 않는다.
- 실행하지 않은 테스트를 통과했다고 보고하지 않는다.
- 실제 확인한 배포 URL만 보고한다.
- 세부 제품 요구사항은 `docs/product-spec.md`를 기준으로 구현한다.

즉, `AGENTS.md`는 제품 사양서가 아니라 **AI 작업 규칙, 검증 방식, 보고 방식, 금지사항**을 정의하는 운영 문서이다.

## 문서 구조

```text
/
├── AGENTS.md
├── README.md
├── ARCHITECTURE.md
└── docs/
    ├── product-spec.md
    ├── data-sources.md
    ├── rendering.md
    ├── validation.md
    └── deployment.md
```

## 문서별 역할

- `AGENTS.md`: AI 에이전트 작업 규칙과 완료 기준
- `README.md`: 프로젝트 개요와 문서 진입점
- `ARCHITECTURE.md`: 시스템 구조와 데이터 흐름
- `docs/product-spec.md`: 제품 요구사항
- `docs/data-sources.md`: 데이터 출처·스냅샷·라이선스
- `docs/rendering.md`: Three.js 렌더링 및 성능 전략
- `docs/validation.md`: 기능·데이터·시각 검증 기준
- `docs/deployment.md`: 빌드 및 OpenAI Sites 배포 절차

## 기술 방향

- Three.js 기반 정적 웹사이트
- OpenStreetMap 기반 공개 벡터 데이터
- OpenFreeMap / OpenMapTiles 형식 사용 가능
- AWS Terrain Tiles / Mapzen / SRTM 계열 공개 표고 데이터
- `InstancedMesh`, 공유 Geometry/Material, 배치 렌더링
- 압축 이진 건물 데이터
- 데스크톱 및 모바일 입력 지원

## 문서 변경 원칙

제품 기능이나 완료 조건이 바뀌면 `docs/product-spec.md`를 수정한다.

에이전트의 작업 방식, 검증 방식, 보고 방식이 바뀌면 `AGENTS.md`를 수정한다.

데이터 출처나 라이선스가 바뀌면 `docs/data-sources.md`를 수정한다.

렌더링 또는 성능 전략이 바뀌면 `docs/rendering.md`와 필요 시 `ARCHITECTURE.md`를 수정한다.
