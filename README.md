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

## Dados

Os dados foram obtidos de uma base pública, já processados para atender o tamanho de ? x ? e divididos em 4 pastas que representam 4 classes.

## Modelos

Foram utilizados os modelos Redes Neurais Convolucionais (CNN), ?, ? e ?. Eles foram comparados em termos de precisão, sensibilidade e especificidade, também foi estabelecida e uma métrica de emissão de carbono equivalente baseado no tempo de treino e tempo de inferência médio.

### Redes Neurais Convolucionais (CNN)

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

### Utilizando Conda

Para criar, ativar e instalar os pacotes necessários num ambiente

```bash
conda create -n health python=3.11
```

```bash
conda activate health
```

```bash
conda install numpy matplotlib scikit-learn ipykernel pandas -c defaults -c conda-forge
```

### Utilizando Conda com o arquivo environments.yml neste repositório

Para criar o ambiente com os pacotes necessários a partir de arquivo

```bash
conda env create -f environment.yml
```

### Utilizando Pip

Crie e ative um ambiente usando pip ou pyenv antes e instale os seguintes pacotes

```bash
pip install numpy matplotlib scikit-learn ipykernel pandas
```

## Anexo: Como baixar os dados para reproduzir os experimentos

Baixar em https://data.mendeley.com/datasets/ch87yswbz4/1 ou utilizar o notebook de preparação de dados

## Referências

Alzheimer's disease dataset<br>
https://data.mendeley.com/datasets/ch87yswbz4/1



___

CMCC - Universidade Federal do ABC (UFABC) - Santo André - SP - Brasil
