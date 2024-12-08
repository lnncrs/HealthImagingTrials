# HealthImagingTrials

**Comparação de Algoritmos de Aprendizado de Máquina para Classificação de Estágios da Doença de Alzheimer em Imagens de Ressonância Magnética**

![UFABC Logo](assets/logotipo-ufabc-extenso.png)

Universidade Federal do ABC - Bacharelado em Ciência e Tecnologia Sistemas Inteligentes 2024/Q3

Lenin, Milena, Diego, Leticia

lenin.cristi@aluno.ufabc.edu.br, ?, ?, ?

## Resumo

**Resumo. Comparação de Algoritmos de Aprendizado de Máquina para Classificação de Estágios da Doença de Alzheimer em Imagens de Ressonância Magnética**

**Abstract. Comparison of Machine Learning Algorithms for Classifying Stages of Alzheimer's Disease in Magnetic Resonance Imaging**

## Objetivos

A classificação de imagens médicas desempenha um papel crucial no diagnóstico precoce e monitoramento da doença de Alzheimer, permitindo intervenções mais eficazes e melhorando os desfechos clínicos. Este projeto investiga a aplicação de diferentes classificadores de aprendizado de máquina para analisar imagens de ressonância magnética (RM, MRI) de pacientes em diferentes estágios da doença.

## Dados utilizados

O conjunto de dados utilizado como base foi o ???

Os dados foram obtidos de uma base pública, já processados para atender o tamanho de ? x ? e divididos em 4 pastas que representam 4 classes.

## Preparação dos dados

A preparação dos dados está no notebook [PrepareData](PrepareData.ipynb).

É preciso ter em mente também que modelos de aprendizado de máquina implementados na área de saúde **sempre** devem:

- Ter sua acurácia acompanhada por retorno humano (Human Feedback)

- Ter explicabilidade (Explainability)

- Ter critérios de honestidade definidos (Fairness)

- (Para dados de Brasileiros) Obedecer a LGPD para treinamento do modelo e inferência dos dados

- (Na União Européia) Obedecer a GPDR para treinamento do modelo e inferência dos dados

- (Nos Estados Unidos) Obedecer a HIPAA para treinamento do modelo e inferência dos dados

## Modelos

Foram utilizados os modelos Redes Neurais Convolucionais (CNN), ?, ? e ?. Eles foram comparados em termos de precisão, sensibilidade e especificidade, também foi estabelecida e uma métrica de emissão de carbono equivalente baseado no tempo de treino e tempo de inferência médio.

### Redes Neurais Convolucionais (CNN / ResNet)

Redes neurais convolucionais (CNN, do inglês Convolutional Neural Network) são um tipo de rede neural do tipo feed-foward regularizada que consegue aprender features via filtros específicos (convoluções). É considerado o tipo de rede mais relevante para deep learning em visão computacional, em especial em imagens médicas.

CNNs usam relativamente menos pré processamento que outros métodos de classificação, pois são capazes de aprender a otimizar seus filtros de maneira automatizada, o que dispensa a criação e testes de filtros diretamente. Esta capacidade a destaca em tarefas como a classificação de imagens médicas no diagnóstico de doenças, pois aprendem a identificar anomalias e padrões sutis nos dados estudados.

### Modelo A

abc

### Modelo B

abc

### Modelo C

abc

## Resultados

abc

## Conclusões

abc

## Anexo: Como gerar o ambiente para reproduzir os experimentos

Vamos mostrar a seguir um exemplo de como criar o ambiente necessário usando o gerenciador de ambientes e pacotes Anaconda como base com o arquivo environments.yml neste repositório.

### Instalando o conda

Utilize a referência oficial Anaconda para instalar o miniconda no seu ambiente https://docs.anaconda.com/miniconda/install/

### Criando o ambiente

Para criar o ambiente com os pacotes base a partir do arquivo

```bash
conda env create -f environment.yml
```

### Ativando o ambiente

Após a instalação do ambiente base, ative ele com

```bash
conda activate health
```

### Pytorch

Instale o pytorch conforme seu sistema e dispositivos disponíveis, usando a referência oficial aqui https://pytorch.org/get-started/locally/

Abaixo um comando usando dispositivos Nvidia

```bash
pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu121
```

### Hugginface & Transformers

Instale as bibliotecas Hugginface usando a referência oficial aqui https://huggingface.co/docs/transformers/installation

```bash
pip install transformers datasets evaluate
pip install accelerate
pip install huggingface_hub
```

## Referências

Alzheimer's disease dataset<br>
https://data.mendeley.com/datasets/ch87yswbz4/1

Alzheimer MRI 4 classes dataset<br>
https://www.kaggle.com/datasets/marcopinamonti/alzheimer-mri-4-classes-dataset?select=Alzheimer_MRI_4_classes_dataset

___

CMCC - Universidade Federal do ABC (UFABC) - Santo André - SP - Brasil
