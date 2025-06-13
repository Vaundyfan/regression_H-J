# regression_H-J

금융섹터 시계열 분석: Cointegration Test & Hatemi-J 구조변동 VECM
본 저장소는 한국 금융업 주요 부문(은행, 보험, 증권 등) 주가지수 데이터에 대한 공적분/구조변동/장단기 영향분석을 위한 파이썬 코드와 결과

1. 주요 코드 설명
(1) _regression_CItest2b.ipynb
목적:
Johansen 공적분 검정 및 VECM(Vector Error Correction Model) 분석을 통해 금융섹터 간의 장기 동조화(Co-movement) 및 단기·장기 인과관계 추정

주요 내용:

단위근 검정(ADF), Johansen Cointegration Test

공적분 rank(차수) 자동 결정

VECM 파라미터 자동 선택(lag selection), 계수 추정, 잔차 진단

주요 출력:

Johansen 검정 결과(Trace, MaxEigen), 공적분 rank 결정

각 종속변수(VECM)의 단기·장기 계수 및 통계적 유의성 표

잔차 안정성/정상성 진단 그래프

핵심 결과 요약:

금융섹터 주가지수(은행, 보험, 증권) 간 2개 이상의 공적분 관계 존재

VECM에서 각 부문 간 장·단기 상호작용(자기회귀, 교차효과 등) 계수 및 유의성 확인

계수해석: 자기효과(Self-lag), 타산업 효과(Cross-lag), 조정계수(Alpha) 등 장단기 인과구조 진단

구조적 변동점 미반영, 전체 기간 장기 균형 및 단기 동학 분석

(2) _regression_H-J.ipynb
목적:
Hatemi-J(2008) 구조변동 공적분 검정 및 Threshold VECM(TVECM) 분석을 통해 금융섹터 주가지수 간 2개 구조적 변동점을 고려한 장단기 동조화/균형관계 탐색

주요 내용:

데이터 전처리, ADF·ZA 등 단위근 및 구조변동 검정

Hatemi-J 방법론 기반 2-structural-break Cointegration Test 구현

Regime 구간 분리, 각 구간별 VECM/TVECM 계수 추정

Bai-Perron 등 변동점 자동탐지, 각 구간별 정상성/공적분 구조 변화 확인

주요 출력:

구조변동 시점별 구간 정의, 구간별 cointegration 유무 판정

각 Regime(VECM)별 장단기 계수 및 조정속도(Alpha) 비교

변동점/구간별 파라미터/유의성 시각화

핵심 결과 요약:

금융섹터 주가지수에 2회 이상의 구조변동 존재

각 Regime(변동점 기준 구간)별로 공적분 및 장단기 구조가 달라짐 → 동일한 계수구조/인과관계가 전체기간 유지되지 않음

구조변동 반영 시, 각 구간별 동조화·균형관계·조정속도 해석이 필수

정적분/동적분 구간별 분리모형 분석 및 실증적 비교 제공

2. 분석 결과 및 활용법
공적분·VECM 분석:

금융섹터 장기 균형관계, 동조화 강도, 단기 충격 파급 확인 가능

단일/다중 구조변동 반영 여부에 따라 실증결과, 정책 해석 달라짐

구조변동 모형(Hatemi-J):

금융시장 주요 변동점(위기, 정책, 외생충격 등) 식별

구간별 정책·시장 환경 변화가 장기 균형에 미치는 영향 실증

비정상/비선형 금융시계열 동학 해석에 강점

4. 참고
[Hatemi-J, 2008], Bai-Perron(2003), Johansen(1988, 1991) 등

Hatemi-J, Abdulnasser. 2008. Tests for cointegration with two unknown regime shifts with an application to financial market
 integration. Empirical Economics 35: 497–505.
Hatemi-J, Abdulnasser. 2009. CItest2b: GAUSS Module to Implement Tests for Cointegration with Two Unknown Structural Breaks;
 Statistical Software Components G00006. Chestnut Hill: Boston College Department of Economics. Available online: http:
 //ideas.repec.org/c/boc/bocode/g00006.html (accessed on 30 June 2019).
 Siddiqui, A., Shamim, M., Asif, M., & Al-Faryan, M. A. S. (2022). Are stock markets among BRICS members integrated? A regime shift-based co-integration analysis. Economies, 10(4), 87.

분석 데이터: 한국 금융업 세부지수(MK2000), DataGuide 제공

