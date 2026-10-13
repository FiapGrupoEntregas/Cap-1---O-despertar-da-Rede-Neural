# Linguagens e versões utilizadas

Projeto: FarmTech Solutions – Fase 6 (Visão Computacional com YOLO)

> As versões marcadas como **"ver saída do notebook"** dependem do ambiente do Google Colab no dia da execução. Elas são impressas automaticamente pela célula **"Versões do ambiente"** (seção 3 do notebook). Depois de executar, copie os valores para a coluna "Versão".

## 1. Linguagens de programação e de marcação

| Linguagem | Versão | Onde é usada |
|---|---|---|
| Python | ver saída do notebook (`Python:` na célula "Versões do ambiente") | Todo o código: preparação do dataset, treino e avaliação do YOLOv5, CNN, gráficos e comparação final |
| Markdown | CommonMark / GitHub Flavored Markdown | Células de texto do notebook e `README.md` |
| YAML | 1.2 | Arquivo `data.yaml` de configuração do dataset do YOLOv5 |
| Shell (Bash) | ver ambiente do Colab (Ubuntu) | Comandos com `!` no notebook (`git clone`, `pip install`, `unzip`, `python train.py`) |
| JSON (formato Jupyter Notebook, `nbformat`) | nbformat 4.5 | Formato do arquivo `.ipynb` |
| HTML | HTML5 | Logo e licença no `README.md` |

## 2. Principais bibliotecas e frameworks (Python)

| Biblioteca | Versão | Uso |
|---|---|---|
| PyTorch (`torch`) | ver saída do notebook | Execução do YOLOv5 |
| YOLOv5 (`ultralytics/yolov5`) | commit impresso no notebook (`YOLOv5 ... commit:`) | Treino, validação, teste e detecção; pesos iniciais `yolov5s.pt` (COCO) |
| TensorFlow / Keras | ver saída do notebook | CNN treinada do zero |
| FiftyOne | ver saída do notebook | Download das imagens do Open Images V7 |
| pandas | ver saída do notebook | Leitura de `results.csv` e tabelas |
| NumPy | ver saída do notebook | Operações numéricas |
| Matplotlib | ver saída do notebook | Gráficos e visualização das detecções |
| scikit-learn | ver saída do notebook | Matriz de confusão da CNN |
| Pillow | ver saída do notebook | Leitura e redimensionamento de imagens |

## 3. Plataformas e ferramentas

| Ferramenta | Versão | Uso |
|---|---|---|
| Google Colab | serviço online (sem versão fixa) | Execução do notebook com GPU |
| Make Sense | serviço online ([makesense.ai](https://www.makesense.ai)) | Rotulação das caixas, exportadas em formato YOLO |
| Open Images | V7 | Fonte das imagens |
| Git / GitHub | ver ambiente do Colab | Versionamento e entrega |

## 4. Modelos de linguagem (IA generativa)

| Modelo | Versão | Desenvolvedor | Uso no projeto |
|---|---|---|---|
| Claude Sonnet | 5.5 | Anthropic | Revisão do notebook e do README, sugestões de correção de código e apoio na redação das conclusões automáticas |

*Se o grupo usou outras ferramentas de IA generativa, acrescente aqui o nome e a versão de cada uma.*
