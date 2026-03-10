# Cap 1: A Busca de Dados — Preparando o Terreno para a Inteligência Cardiológica

**Aluno:** Luiz Felipe Alves Gomes
**Curso:** Inteligência Artificial para Automação de Processos Robóticos — FIAP
**Turma:** 2TIAOA 2026/1

## Sobre o projeto

O CardioIA simula o ecossistema de uma cardiologia moderna, integrando Machine Learning, Visão Computacional, IoT e agentes inteligentes para lidar com triagem, diagnósticos e previsões médicas. Nesta primeira fase, o objetivo é levantar, organizar e documentar os dados cardiológicos que vão alimentar os módulos inteligentes ao longo das próximas fases do projeto.

Os dados foram organizados em três tipos: numéricos, textuais e visuais, cada um com fontes públicas, documentadas e de acesso livre.

## Estrutura do repositório

```
cardio-ia-fase1/
├── data/
│   ├── numeric/        # Dados numéricos (IoT) — CSV
│   ├── text/           # Dados textuais (NLP) — TXT
│   └── images/         # Dados visuais (VC) — JPG
└── README.md
```

Os arquivos de dados estão hospedados no Google Drive por conta do tamanho. Os links estão na seção abaixo.

## Parte 1: Dados Numéricos (IoT)

Para os dados numéricos, utilizamos o Heart Disease UCI Dataset, disponível no repositório da Universidade da Califórnia em Irvine. O dataset contém 303 registros de pacientes com variáveis clínicas como idade, sexo, tipo de dor no peito, pressão arterial em repouso, colesterol sérico, glicemia em jejum, resultado do eletrocardiograma em repouso, frequência cardíaca máxima atingida, angina induzida por exercício e o diagnóstico de doença cardíaca.

Fonte: [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/45/heart+disease)

Do ponto de vista clínico, as variáveis mais relevantes para um modelo de IA são a frequência cardíaca máxima (thalach), o tipo de dor no peito (cp) e o diagnóstico final (target), pois são indicadores diretos de comprometimento cardíaco e servirão como features e label nos algoritmos de classificação das fases seguintes.

Link Google Drive: https://drive.google.com/drive/folders/1P2XFFFI5cmWxcTSeAldToITHJZYMpUR2?usp=sharing

## Parte 2: Dados Textuais (NLP)

Para os dados textuais, coletamos dois artigos científicos publicados nos Arquivos Brasileiros de Cardiologia, acessados pela plataforma SciELO. Os artigos abordam dois temas centrais da cardiologia clínica:

| Arquivo | Tema |
|---|---|
| `artigo_01.txt` | Manejo das Lesões Circulatórias Sistêmicas Dependentes do Canal no Período Neonatal |
| `artigo_02.txt` | Revisão Sistemática sobre a Eficácia de Metas Intensivas do Tratamento Anti-Hipertensivo (Recomendação SBC) |

Esses textos podem ser explorados por algoritmos de NLP de diferentes formas. Uma delas é a extração de entidades nomeadas (NER), que permite identificar automaticamente termos clínicos como "dor no peito", "arritmia" e "hipertensão" em prontuários e laudos. Outra aplicação é a classificação de tópicos, que pode categorizar documentos por tipo de doença ou protocolo de tratamento. Há ainda a análise de sentimentos, útil para identificar o tom de relatos clínicos e auxiliar na triagem de urgências.

Dados textuais são abundantes em sistemas hospitalares. Transformá-los em informação estruturada é uma das aplicações mais impactantes da IA na saúde, pois viabiliza automação de processos que hoje dependem de leitura manual.

Link Google Drive: https://drive.google.com/drive/folders/1P2XFFFI5cmWxcTSeAldToITHJZYMpUR2?usp=sharing

## Parte 3: Dados Visuais (Visão Computacional)

Para os dados visuais, utilizamos o ECG Images Dataset of Cardiac Patients, publicado no Kaggle sob licença MIT. O dataset contém imagens de eletrocardiogramas de 12 derivações, organizadas em quatro categorias clínicas. Selecionamos 25 imagens de cada categoria, totalizando 100 imagens.

Fonte: [Kaggle — evilspirit05/ecg-analysis](https://www.kaggle.com/datasets/evilspirit05/ecg-analysis)

| Categoria | Prefixo | Descrição |
|---|---|---|
| Infarto do Miocárdio | `MI_*.jpg` | ECGs de pacientes com IM confirmado |
| Histórico de IM | `History_MI_*.jpg` | ECGs de pacientes com IM prévio |
| Batimento Anormal | `Abnormal_*.jpg` | ECGs com arritmias e padrões irregulares |
| Normal | `Normal_*.jpg` | ECGs de indivíduos sem cardiopatia |

Algoritmos de Visão Computacional podem analisar essas imagens de várias maneiras. CNNs são capazes de classificar automaticamente o tipo de alteração no ECG com alta precisão, algo que normalmente exige um cardiologista experiente. Técnicas de detecção de bordas, como o algoritmo de Canny, permitem segmentar as ondas P, QRS e T para extração de características morfológicas. Autoencoders podem ser usados para detecção de anomalias, identificando padrões atípicos que fogem do ECG normal. Em ambientes de emergência, essa capacidade de análise automática pode reduzir significativamente o tempo entre o exame e a intervenção médica.

Link Google Drive: https://drive.google.com/drive/folders/1P2XFFFI5cmWxcTSeAldToITHJZYMpUR2?usp=sharing

## Links dos dados

| Tipo | Link |
|---|---|
| Dados Numéricos (CSV) | https://drive.google.com/drive/folders/1P2XFFFI5cmWxcTSeAldToITHJZYMpUR2?usp=sharing |
| Dados Textuais (TXT) | https://drive.google.com/drive/folders/1P2XFFFI5cmWxcTSeAldToITHJZYMpUR2?usp=sharing |
| Dados Visuais (JPG) | https://drive.google.com/drive/folders/1P2XFFFI5cmWxcTSeAldToITHJZYMpUR2?usp=sharing |

## Governança de Dados

Todos os datasets utilizados são públicos e de acesso livre. Nenhum dado pessoal identificável de pacientes reais foi coletado diretamente. As fontes estão documentadas para garantir rastreabilidade e reprodutibilidade do projeto.
