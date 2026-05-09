# Quantifi Research

국내 주식 데이터를 활용해 퀀트 투자 아이디어를 실증 분석하고 백테스트한 리서치 노트북 모음입니다. 고배당, 밸류/퀄리티, 검색량 기반 관심도, 베타/레짐, Amihud 비유동성 팩터를 중심으로 전략을 설계하고 성과를 검증했습니다.

> 이 저장소는 취업 포트폴리오 공개를 전제로 정리한 버전입니다. 원천 데이터는 용량과 라이선스 이슈로 GitHub에 포함하지 않습니다.

## 핵심 내용

- 국내 KOSPI/KOSDAQ 종목 대상 팩터 기반 포트폴리오 구성
- 시가총액, PBR, ROE, DPS, 수정주가, 거래대금 등 재무/가격 데이터 전처리
- 분위수 포트폴리오, 리밸런싱, NAV, 벤치마크 대비 성과 계산
- 회귀분석과 팩터 중립 분석을 통한 전략 검증
- ETF 운용 제안서 및 월간 운용보고서 산출물 관리 구조 포함

## 프로젝트 구조

```text
.
├── README.md
├── requirements.txt
├── data/
│   ├── raw/          # 원천 데이터 설명만 보관
│   ├── interim/      # 중간 산출 데이터 설명만 보관
│   ├── processed/    # 최종 분석용 데이터 설명만 보관
│   └── external/     # 외부 수집 데이터 설명만 보관
├── docs/
│   ├── notebook_index.md
│   └── github_upload_checklist.md
├── outputs/          # 공개 가능한 결과물 설명만 보관
├── 전략_notebook/
│   ├── 01_고배당_저DPS변화율_전략/
│   ├── 02_PBR_ROE_전략/
│   ├── 03_VIP_score_전략/
│   ├── 04_검색량데이터_전략/
│   ├── 05_고베타_레짐반영_전략/
│   ├── 06_Value_Quality_전략/
│   └── 07_Amihud_전략/
└── 제안서&운용보고서/
```

## 전략 노트북

| 구분 | 전략 | 주요 아이디어 | 노트북 |
| --- | --- | --- | --- |
| 01 | 고배당 + 저 DPS 변화율 | 배당 관련 지표와 변동성 필터를 활용한 포트폴리오 구성 | [고배당전략_DPS변화율필터.ipynb](전략_notebook/01_고배당_저DPS변화율_전략/고배당전략_DPS변화율필터.ipynb) |
| 02 | PBR + ROE | 저 PBR과 고 ROE를 결합한 소형주 중심 밸류/퀄리티 전략 | [pbr+roe_new.ipynb](전략_notebook/02_PBR_ROE_전략/pbr+roe_new.ipynb) |
| 03 | VIP Score | Value, Investment, Profitability 요소를 결합한 종합 점수 전략 | [VIP_Score.ipynb](전략_notebook/03_VIP_score_전략/VIP_Score.ipynb) |
| 04 | 검색량 데이터 | 검색량 지표의 계절성을 제거한 ASVI와 배당 포트폴리오/회귀분석 | [Empirical Analysis.ipynb](전략_notebook/04_검색량데이터_전략/Empirical%20Analysis.ipynb) |
| 05 | 고베타 + 레짐 | 시장 레짐에 따라 고베타 종목군을 활용하는 동적 전략 | [Beta&regime_코스피_코스닥.ipynb](전략_notebook/05_고베타_레짐반영_전략/Beta%26regime_코스피_코스닥.ipynb) |
| 06 | Value-Quality 동적 배분 | 레짐 기반 Value/Quality 포트폴리오 배분과 벤치마크 비교 | [Value_quality_레짐동적배분.ipynb](전략_notebook/06_Value_Quality_전략/Value_quality_레짐동적배분.ipynb) |
| 07 | Amihud 비유동성 | Amihud illiquidity 팩터와 평균 기간/리밸런싱 조합 비교 | [07_Amihud_전략](전략_notebook/07_Amihud_전략) |

자세한 노트북별 요약은 [docs/notebook_index.md](docs/notebook_index.md)에 정리했습니다.


## 데이터 정책

이 저장소의 원천 데이터는 대부분 한국 주식 가격/재무/거래대금 데이터입니다. 공개 GitHub에는 다음 이유로 포함하지 않습니다.

- 파일 용량이 큼
- 데이터 제공처 라이선스 확인 필요
- 재현용 샘플과 원천 데이터의 역할을 분리하는 편이 안전함

데이터를 직접 준비할 경우 `data/raw/` 또는 각 노트북의 `input/` 폴더에 배치한 뒤 실행합니다. 현재 일부 노트북에는 기존 로컬 환경 기준의 절대경로가 남아 있으므로, 재실행 전 상대경로로 수정해야 합니다.

## 기술 스택

- Python
- pandas, numpy
- matplotlib, plotly
- statsmodels
- joblib, tqdm
- Jupyter Notebook
