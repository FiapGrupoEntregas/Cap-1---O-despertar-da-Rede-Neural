# FIAP - Faculdade de Informática e Administração Paulista

<img width="2385" height="642" alt="image" src="https://github.com/user-attachments/assets/a89f7c8f-54a2-4f18-b20b-c0393a747058" />


# FarmTech Solutions – Fase 6: Visão Computacional com YOLO

## NOME_DO_GRUPO

## 👨‍🎓 Integrantes: 
- <a href="LINK_LINKEDIN_1">Jonattas Felipe (RM572692)</a>
- <a href="LINK_LINKEDIN_2">Natanael Filho (RM572474)</a>
- <a href="LINK_LINKEDIN_3">Pedro Henrique (RM571394)</a> 
- <a href="LINK_LINKEDIN_4">Andrews Oliveira (RM572311)</a>

## 👩‍🏫 Professores:
### Tutor(a) 
- <a href="LINK_LINKEDIN_TUTOR">Nome do Tutor</a>
### Coordenador(a)
- <a href="LINK_LINKEDIN_COORDENADOR">Nome do Coordenador</a>


## 📜 Descrição

A FarmTech Solutions expandiu seus serviços de IA para além do agronegócio e passou a atuar com visão computacional. Este projeto demonstra, na prática e para um cliente fictício, como um sistema de visão computacional funciona e qual é a sua acurácia.

O sistema detecta **tratores** e **vacas**, objetos alinhados ao contexto agro da FarmTech, usando o **YOLOv5s** com *fine-tuning* a partir dos pesos pré-treinados no COCO. O dataset tem 80 imagens do Open Images V7 (40 de cada classe, divididas em 32 treino, 4 validação e 4 teste), com caixas rotuladas manualmente no Make Sense. O modelo foi treinado em duas simulações, com **30 e 60 épocas**, e comparado em erro, precisão, recall, mAP e tempo de treino.

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


## 📁 Estrutura de pastas

Dentre os arquivos e pastas presentes na raiz do projeto, definem-se:

- <b>.github</b>: Nesta pasta ficarão os arquivos de configuração específicos do GitHub que ajudam a gerenciar e automatizar processos no repositório.

- <b>assets</b>: aqui estão os arquivos relacionados a elementos não-estruturados deste repositório, como imagens (logo da FIAP e prints das detecções).

- <b>config</b>: Posicione aqui arquivos de configuração que são usados para definir parâmetros e ajustes do projeto (por exemplo, o `data.yaml` do YOLOv5).

- <b>dataset</b>: imagens e rótulos em formato YOLO, separados em `images/` e `labels/` com as pastas `train`, `val` e `test`.

- <b>document</b>: aqui estão todos os documentos do projeto que as atividades poderão pedir. Na subpasta "other", adicione documentos complementares e menos importantes.

- <b>scripts</b>: Posicione aqui scripts auxiliares para tarefas específicas do seu projeto. Exemplo: deploy, migrações de banco de dados, backups.

- <b>src</b>: Todo o código fonte criado para o desenvolvimento do projeto ao longo das 7 fases (nesta fase, o notebook `JonattasFelipe_rm572692_pbl_fase6.ipynb`).

- <b>README.md</b>: arquivo que serve como guia e explicação geral sobre o projeto (o mesmo que você está lendo agora).

## 🔧 Como executar o código

**Pré-requisitos**
- Conta Google, para usar o [Google Colab](https://colab.research.google.com/) com GPU (*Ambiente de execução > Alterar tipo > GPU*).
- Bibliotecas instaladas automaticamente pelo notebook: PyTorch, TensorFlow/Keras, FiftyOne, pandas, scikit-learn, matplotlib e Pillow. As versões usadas em cada execução são impressas na célula "Versões do ambiente".

**Passo a passo**
1. Abra o notebook no Colab: [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/SEU_USUARIO/SEU_REPOSITORIO/blob/main/src/JonattasFelipe_rm572692_pbl_fase6.ipynb)
2. Na célula com `REPO_URL`, confirme o link deste repositório. O notebook detecta a pasta `dataset/` e pula o download e a rotulação.
3. Execute as células em ordem:
   - **Fase 1 – Dataset:** carregamento das imagens e rótulos YOLO.
   - **Fase 2 – Entrega 1:** treino do YOLOv5s com 30 e 60 épocas, validação (curvas e métricas) e teste (imagens processadas).
   - **Fase 3 – Entrega 2:** YOLO padrão, CNN do zero e comparação final.
4. Os resultados do YOLO ficam em `yolov5/runs/` e são copiados para o seu Drive ao final.


## 🗃 Histórico de lançamentos

* 1.0.0 - XX/XX/2026
    * Entrega final: conclusões, vídeo demonstrativo e documentação
* 0.3.0 - XX/XX/2026
    * Entrega 2: YOLO padrão, CNN do zero e comparação crítica
* 0.2.0 - XX/XX/2026
    * Entrega 1: treino do YOLOv5s com 30 e 60 épocas, validação e teste
* 0.1.0 - XX/XX/2026
    * Dataset de 80 imagens (Open Images V7) e rotulação no Make Sense

## 📋 Licença

<img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/cc.svg?ref=chooser-v1"><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/by.svg?ref=chooser-v1"><p xmlns:cc="http://creativecommons.org/ns#" xmlns:dct="http://purl.org/dc/terms/"><a property="dct:title" rel="cc:attributionURL" href="https://github.com/agodoi/template">MODELO GIT FIAP</a> por <a rel="cc:attributionURL dct:creator" property="cc:attributionName" href="https://fiap.com.br">Fiap</a> está licenciado sobre <a href="http://creativecommons.org/licenses/by/4.0/?ref=chooser-v1" target="_blank" rel="license noopener noreferrer" style="display:inline-block;">Attribution 4.0 International</a>.</p>

