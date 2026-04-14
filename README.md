# CardioIA

**Aluno:** Luiz Felipe Alves Gomes
**Curso:** IA para Automação de Processos Robóticos - FIAP
**Turma:** 2TIAOA 2026/1
**Repositório:** https://github.com/luizgomesdev/cardio-ia-fase1

## O que é

Projeto de IA aplicada a cardiologia. A ideia é usar NLP e Machine Learning pra analisar relatos de pacientes, identificar sintomas e classificar risco cardíaco.

## Fase 1 - Coleta de Dados

Coleta e organização dos dados que vão ser usados nas próximas fases:

- **Numéricos:** Heart Disease UCI Dataset (303 pacientes)
- **Textuais:** 2 artigos de cardiologia do SciELO
- **Imagens:** 100 ECGs do Kaggle (normal, infarto, anormal, histórico)

## Fase 2 - Diagnóstico Automatizado

### Parte 1: Extração de Sintomas (NLP)

Código que lê frases de pacientes, identifica sintomas e sugere diagnóstico. Usa um mapa de conhecimento (CSV) com associações entre sintomas e doenças cardíacas baseadas nas diretrizes da SBC.

- 10 frases simulando relatos de pacientes
- 30 associações no mapa de conhecimento
- Resultado: 10/10 identificados corretamente

### Parte 2: Classificador de Risco (ML)

Classificador que recebe uma frase de paciente e diz se é alto risco ou baixo risco. Usa TF-IDF pra transformar texto em números e treina com Decision Tree e Logistic Regression.

- 50 frases rotuladas (25 alto risco, 25 baixo risco)
- Decision Tree: 66% de acurácia
- Logistic Regression: 86% de acurácia

### Ir Alem 2: Classificação de ECG com Rede Neural

Rede neural MLP (Keras/TensorFlow) que classifica imagens de ECG como normal ou anormal. Usa as 233 imagens da Fase 1 convertidas pra 64x64 tons de cinza.

- 233 imagens (98 normal, 135 anormal)
- MLP com BatchNormalization e Dropout
- Acuracia ~50-60% (limitação do MLP com poucas imagens mistas)

## Video

https://youtu.be/FK4Lic0VIkc

## Estrutura

```
├── data/
│   ├── numeric/       # Dataset UCI
│   ├── text/          # Artigos SciELO
│   └── images/        # ECGs Kaggle
├── fase2/
│   ├── data/
│   │   ├── sintomas_pacientes.txt
│   │   ├── mapa_conhecimento.csv
│   │   └── dataset_risco.csv
│   └── notebooks/
│       ├── 01_nlp_diagnostico.ipynb
│       ├── 02_classificador.ipynb
│       └── 03_ecg_neural.ipynb
├── requirements.txt
└── README.md
```

## Como rodar

```bash
git clone https://github.com/luizgomes-dev/cardio-ia.git
cd cardio-ia
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

Abre os notebooks da pasta `fase2/notebooks/` no VS Code ou Jupyter.

## Dados no Google Drive

Os dados da Fase 1 estão no Drive por conta do tamanho:
https://drive.google.com/drive/folders/1P2XFFFI5cmWxcTSeAldToITHJZYMpUR2?usp=sharing

## Referências

- [Diretriz SBC - Angina e IAM](https://pmc.ncbi.nlm.nih.gov/articles/PMC8294740/)
- [Heart Disease UCI Dataset](https://archive.ics.uci.edu/dataset/45/heart+disease)
- [Kaggle ECG Dataset](https://www.kaggle.com/datasets/evilspirit05/ecg-analysis)
- [Scikit-learn TfidfVectorizer](https://scikit-learn.org/stable/modules/generated/sklearn.feature_extraction.text.TfidfVectorizer.html)
- [TensorFlow/Keras](https://www.tensorflow.org/)
