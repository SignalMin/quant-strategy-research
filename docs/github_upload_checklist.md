# GitHub Upload Checklist

GitHub 공개 전 아래 항목을 확인합니다.

## 1. 커밋 제외 대상

다음 항목은 기본적으로 커밋하지 않습니다.

- `data/raw/` 원천 데이터
- `data/interim/`, `data/processed/`, `data/external/`의 실제 데이터 파일
- 각 노트북 폴더의 `input/`, `output/` 데이터 파일
- `.env`, `.venv/`, `.conda/`
- `.DS_Store`, `.ipynb_checkpoints/`, `__pycache__/`
- `*.csv`, `*.xlsx`, `*.parquet`, `*.pkl`

## 2. 공개 가능성 확인

- 데이터 제공처 라이선스 확인
- 팀 프로젝트 산출물의 공개 가능 여부 확인
- 보고서/PPT에 개인정보, 학번, 연락처, 내부 평가 내용이 남아 있는지 확인
- 노트북 출력에 원본 데이터가 과도하게 노출되어 있지 않은지 확인
- `제안서&운용보고서/`의 PPT/PDF/DOCX는 기본적으로 제외되므로, 공개 가능한 파일만 `git add -f <파일명>`으로 추가

## 3. 재현성 확인

- `requirements.txt`로 환경 설치 가능 여부 확인
- 절대경로(`/Users/...`)를 상대경로로 바꿀 대상 확인
- 노트북별 입력 파일 목록 정리
- 공개 가능한 샘플 데이터가 필요한지 결정

## 4. 업로드 전 명령어

```bash
git init
git status --short
git status --ignored --short
git add README.md requirements.txt .gitignore docs data outputs 전략_notebook '제안서&운용보고서/README.md'
git status --short
git commit -m "Organize quant strategy research portfolio"
```

원격 저장소를 만든 뒤 아래처럼 연결합니다.

```bash
git branch -M main
git remote add origin <GitHub repository URL>
git push -u origin main
```

## 5. 추천 저장소 설명

- Repository name: `quant-strategy-research`
- Description: `Korean equity quant strategy research notebooks covering dividend, value-quality, search volume, beta regime, and Amihud illiquidity factors.`
- Topics: `quant`, `finance`, `backtesting`, `factor-investing`, `portfolio`, `python`, `jupyter-notebook`
