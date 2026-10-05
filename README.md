# FarmTech Solutions – Fase 6: Visão Computacional com YOLO

Projeto da Fase 6 (FIAP – IA): sistema de visão computacional que detecta **tratores** e **vacas** usando YOLOv5, comparado com o YOLO padrão (COCO) e com uma CNN treinada do zero.

**Grupo:**

| Nome | RM |
|---|---|
| Jonattas Felipe | RM572692 |
| Natanael Filho | RM572474 |
| Pedro Henrique | RM571394 |
| Andrews Oliveira | RM572311 |

## Links

- 📓 **Notebook (passo a passo completo):** [`JonattasFelipe_rm572692_pbl_fase6.ipynb`](./JonattasFelipe_rm572692_pbl_fase6.ipynb)
- 🎥 **Vídeo de demonstração (YouTube, não listado):** COLE_O_LINK_AQUI

## Visão geral

| Entrega | O que foi feito |
|---|---|
| **1** | Dataset de 80 imagens (40 trator + 40 vaca; 32/4/4 por classe), rotuladas no Make Sense; fine-tuning do YOLOv5s com **30 e 60 épocas** e comparação dos resultados |
| **2** | Comparação entre YOLO customizado, YOLO padrão e CNN do zero (facilidade de uso, precisão, tempo de treino e tempo de inferência) |

## Dataset

Imagens obtidas do **Open Images V7** (via biblioteca FiftyOne), uso exclusivamente acadêmico. A rotulação das caixas foi feita manualmente no [Make Sense](https://www.makesense.ai).

```
dataset/
├── images/ (train | val | test)
└── labels/ (train | val | test)   # formato YOLO
```

## Como executar

1. Abra o notebook no Google Colab (ambiente com GPU: *Ambiente de execução > Alterar tipo > GPU*).
2. Execute as células em ordem. O dataset é baixado automaticamente; os rótulos do Make Sense devem estar em `labels_zips/` no seu Drive (veja a seção 2 do notebook).

## Estrutura do repositório

```
├── JonattasFelipe_rm572692_pbl_fase6.ipynb
├── README.md
└── (opcional) best.pt, data.yaml
```
