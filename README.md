# FIAP - Faculdade de Informática e Administração Paulista

<img width="2385" height="642" alt="image" src="https://github.com/user-attachments/assets/a89f7c8f-54a2-4f18-b20b-c0393a747058" />


# FarmTech Solutions – Fase 6: Visão Computacional com YOLO

## NOME_DO_GRUPO

## 👨‍🎓 Integrantes: 
- <a href="LINK_LINKEDIN_1">Jonattas Felipe (RM572692)</a>
- <a href="LINK_LINKEDIN_2">Natanael Filho (RM572474)</a>
- <a href="LINK_LINKEDIN_3">Pedro Henrique (RM571394)</a> 
- <a href="LINK_LINKEDIN_4">Andrews Oliveira (RM572311)</a>

## 📜 Descrição

A FarmTech Solutions expandiu seus serviços de IA para além do agronegócio e passou a atuar com visão computacional. Este projeto demonstra, na prática e para um cliente fictício, como um sistema de visão computacional funciona e qual é a sua acurácia.

O sistema detecta **tratores** e **vacas**, objetos alinhados ao contexto agro da FarmTech, usando o **YOLOv5s** com *fine-tuning* a partir dos pesos pré-treinados no COCO. O dataset tem 80 imagens do Open Images V7 (40 de cada classe, divididas em 32 treino, 4 validação e 4 teste). As caixas são pré-rotuladas automaticamente (caixas desenhadas por humanos do próprio Open Images para vaca e YOLO-World para trator, já que o Open Images não tem caixas de trator) e revisadas no Make Sense. O modelo foi treinado em duas simulações, com **30 e 60 épocas**, e comparado em erro, precisão, recall, mAP e tempo de treino.

Na Entrega 2, o YOLO customizado foi comparado com o **YOLO padrão** (pesos do COCO, sem treino) e com uma **CNN treinada do zero**, considerando facilidade de uso, precisão, tempo de treino e tempo de inferência.

O passo a passo completo, os gráficos, as imagens de teste processadas e as conclusões estão no notebook [`src/JonattasFelipe_rm572692_pbl_fase6.ipynb`](./src/JonattasFelipe_rm572692_pbl_fase6.ipynb).

🎥 **Vídeo de demonstração (YouTube, não listado):** COLE_O_LINK_AQUI

### 🤖 Modelos de linguagem (IA generativa) utilizados

| Modelo | Versão | Desenvolvedor | Uso no projeto |
|---|---|---|---|
| Claude Sonnet | 5.5 | Anthropic | Revisão do notebook e do README, sugestões de correção de código e apoio na redação das conclusões automáticas |

*Se o grupo usou outras ferramentas de IA generativa, acrescente-as nesta tabela com nome e versão.* Todo o código foi executado e validado pelo grupo no Google Colab.

### 🧠 Modelos de visão computacional

| Modelo | Versão / origem | Papel |
|---|---|---|
| YOLOv5s | repositório `ultralytics/yolov5` (commit registrado no notebook), pesos `yolov5s.pt` do COCO | Detecção customizada (Entrega 1) e YOLO padrão (Entrega 2) |
| CNN própria | Keras / TensorFlow (versão registrada no notebook) | Classificação do zero (Entrega 2) |
| YOLO-World | `yolov8s-worldv2.pt` (Ultralytics), detecção por texto | Pré-rotulação das caixas de trator, revisadas no Make Sense |


## 📁 Estrutura de pastas

Dentre os arquivos e pastas presentes na raiz do projeto, definem-se:

- <b>assets</b>: prints das detecções nas imagens de teste e curvas de treino, gerados pelo notebook.

- <b>dataset</b>: imagens e rótulos em formato YOLO, separados em `images/` e `labels/` com as pastas `train`, `val` e `test`. O arquivo `origem.csv` registra o ID de cada foto no Open Images e a origem do pré-rótulo.

- <b>models</b>: `best.pt` do modelo escolhido pela validação, usado na detecção em tempo real do "Ir Além".

- <b>src</b>: código-fonte do projeto (nesta fase, o notebook `JonattasFelipe_rm572692_pbl_fase6.ipynb`).

- <b>README.md</b>: arquivo que serve como guia e explicação geral sobre o projeto (o mesmo que você está lendo agora).

- <b>pyproject.toml</b>, <b>uv.lock</b> e <b>requirements.txt</b>: dependências do ambiente Python local. O `uv.lock` trava as versões exatas e o `requirements.txt` é gerado a partir dele.

## 🔧 Como executar o código

**Pré-requisitos**
- Conta Google, para usar o [Google Colab](https://colab.research.google.com/) com GPU (*Ambiente de execução > Alterar tipo > GPU*), **ou** uma máquina local com [uv](https://docs.astral.sh/uv/) (veja abaixo).
- No Colab, o notebook instala sozinho o que falta (dependências do YOLOv5). As versões usadas em cada execução são impressas na célula "Versões do ambiente".

**Passo a passo**
1. Abra o notebook no Colab: [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/FiapGrupoEntregas/Cap-1---O-despertar-da-Rede-Neural/blob/main/src/JonattasFelipe_rm572692_pbl_fase6.ipynb)
2. Execute as células em ordem. O notebook clona este repositório, detecta a pasta `dataset/` e pula o download e a pré-rotulação:
   - **Seções 1 e 2 – Dataset:** carregamento das imagens e rótulos YOLO (ou montagem do zero a partir do Open Images).
   - **Seção 3 – Entrega 1:** treino do YOLOv5s com 30 e 60 épocas, validação (curvas e métricas) e teste (imagens processadas).
   - **Seção 4 – Entrega 2:** YOLO padrão, CNN do zero e comparação final.
3. Os resultados do YOLO ficam em `yolov5/runs/` e são copiados para o seu Drive ao final.

**Ambiente local (opcional: uv ou pip)**

O mesmo notebook roda localmente, sem Google Drive: dataset, prints e `best.pt` ficam nas pastas do repositório, e os arquivos temporários (YOLOv5, execuções e logs) ficam em `.trabalho/`, ignorada pelo git. Sem GPU NVIDIA, o treino roda na CPU e leva bem mais tempo que no Colab. No Colab não rode `pip install -r requirements.txt`, pois isso reinstalaria o PyTorch e o TensorFlow do Colab.

Com [uv](https://docs.astral.sh/uv/) (recomendado; ele baixa o Python 3.12 automaticamente):
```bash
uv sync                    # cria o .venv com as dependências e o Jupyter
uv sync --extra dataset    # inclui o CLIP do YOLO-World (só para refazer o dataset do zero)
uv run jupyter lab         # abra src/JonattasFelipe_rm572692_pbl_fase6.ipynb
```

Para executar o notebook inteiro sem abrir o navegador, gravando as saídas no próprio arquivo:
```bash
uv run jupyter nbconvert --to notebook --execute --inplace --ExecutePreprocessor.timeout=-1 src/JonattasFelipe_rm572692_pbl_fase6.ipynb
```

Com pip:
```bash
python -m venv .venv
source .venv/bin/activate        # Windows: .venv\Scripts\activate
pip install -r requirements.txt
```

Para mudar uma dependência, edite o `pyproject.toml` e regenere os arquivos:
```bash
uv lock
uv export --format requirements.txt --no-hashes --no-dev --no-emit-project -o requirements.txt
```
