# HealthImagingTrials

**Comparação de Algoritmos de Aprendizado de Máquina para Classificação de Estágios da Doença de Alzheimer em Imagens de Ressonância Magnética**

![UFABC Logo](assets/logotipo-ufabc-extenso.png)

Universidade Federal do ABC - Bacharelado em Ciência e Tecnologia Sistemas Inteligentes 2024/Q3

Lenin Cristi, Milena R. de Camargo, Diego Guerra, Letícia Martins

lenin.cristi@aluno.ufabc.edu.br, milena.camargo@aluno.ufabc.edu.br, diego.guerra@aluno.ufabc.edu.br, martins.leticia@aluno.ufabc.edu.br

## Resumo

**Resumo. Comparação de Algoritmos de Aprendizado de Máquina para Classificação de Estágios da Doença de Alzheimer em Imagens de Ressonância Magnética**

**Abstract. Comparison of Machine Learning Algorithms for Classifying Stages of Alzheimer's Disease in Magnetic Resonance Imaging**

## Objetivos

A classificação de imagens médicas desempenha um papel crucial no diagnóstico precoce e monitoramento da doença de Alzheimer, permitindo intervenções mais eficazes e melhorando os desfechos clínicos. Este projeto investiga a aplicação de diferentes classificadores de aprendizado de máquina para analisar imagens de ressonância magnética (RM, MRI) de pacientes em diferentes estágios da doença.

## Dados utilizados

O conjunto de dados utilizado como base foi o [Alzheimer MRI 4 classes dataset](https://www.kaggle.com/datasets/marcopinamonti/alzheimer-mri-4-classes-dataset?select=Alzheimer_MRI_4_classes_dataset) disponivel no Kaggle, que por sua vez é um subset do conjunto de dados utilizado no artigo [Advancing Automated Diagnosis: Convolutional Neural Networks for Alzheimer's Disease Classification through MRI Image Processing](https://www.researchgate.net/publication/370973426_Advancing_Automated_Diagnosis_Convolutional_Neural_Networks_for_Alzheimer's_Disease_Classification_through_MRI_Image_Processing) que apesar de não estar mais disponível para download, foi possivel localizar uma fonte primária dos mesmos dados em [Alzheimer's disease dataset](https://data.mendeley.com/datasets/ch87yswbz4/1) que contem os dados originais e os dados aumentados para aprendizado.

> Foi importante conseguir rastrear os dados disponiveis publicamente no Kaggle até uma fonte primária para garantir tanto sua integridade quanto assegurar seu uso ético para fins de pesquisa.

Foram utilizados os dados originais sem aumento de dados, que já estavam ajustados para atender o tamanho de 176 x 208 pixels, e divididos em 4 pastas que representam 4 classes para treino, a saber:

- **NonDemented** (Não Demente): Refere-se a indivíduos sem sinais de demência. Essas pessoas não apresentam déficits cognitivos significativos. Contém 3200 imagens.

- **VeryMildDemented** (Muito Leve Demência): Refere-se ao estágio inicial da demência, onde a pessoa pode ter pequenas dificuldades de memória ou em realizar tarefas diárias, mas ainda mantém independência funcional significativa. Contém 2240 imagens.

- **MildDemented** (Leve Demência): Indivíduos com dificuldades mais evidentes na memória, julgamento e resolução de problemas. Eles podem precisar de alguma ajuda nas tarefas diárias, mas ainda conseguem viver de forma relativamente independente. Contém 896 imagens.

- **ModerateDemented** (Moderada Demência): A demência está mais avançada, com a pessoa precisando de mais ajuda nas atividades diárias. Pode haver dificuldades significativas na comunicação, memória e reconhecimento de pessoas. Contém 64 imagens.

## Preparação dos dados

A preparação dos dados está no notebook [PrepareData](PrepareData.ipynb). Este notebook recupera os dados do Kaggle, e os descompacta na pasta **./data** tornando-os prontos para uso nos classificadores.

Tendo em vista o desbalanceamento dos dados nas 4 classes, os diferentes classificadores recuperam até 100 itens em cada pasta com seed fixo para garantir a mesma amostra.

## Considerações sobre uso de IA's na área de saúde

É preciso ter em mente que modelos de aprendizado de máquina implementados na área de saúde **sempre** devem:

- Ter sua acurácia acompanhada por retorno humano (Human Feedback).

- Ter explicabilidade (Explainability).

- Ter critérios de honestidade definidos (Fairness).

- (Para dados de Brasileiros) Obedecer a LGPD para guarda e uso dos dados.

- (Na União Européia) Obedecer a GPDR para guarda e uso dos dados.

- (Nos Estados Unidos) Obedecer a HIPAA para guarda e uso dos dados.

## Modelos

Foram comparados 4 modelos nos experimentos

### Support Vector Machine (Máquina de Vetores de Suporte)

SVM é um algoritmo de aprendizado de máquina utilizado para classificação e regressão, que busca encontrar o hiperplano que melhor separa diferentes classes de dados, maximizando a margem entre elas. Ele pode lidar com dados lineares e não lineares usando a técnica de kernels.

Notebook: [SVM](notebooks/SVM.ipynb)

### Random Forest (Floresta Aleatória)

Random Forest é um algoritmo de aprendizado de máquina baseado em múltiplas árvores de decisão, onde cada árvore é treinada com uma amostra aleatória dos dados. Ele faz previsões através da média (regressão) ou votação (classificação) das árvores, oferecendo maior precisão e robustez contra overfitting.

Notebook: [RandomForest](notebooks/RandomForest.ipynb)

### Convolutional Neural Network (Redes Neurais Convolucionais)

Redes neurais convolucionais (CNN, do inglês Convolutional Neural Network) são um tipo de rede neural do tipo feed-foward regularizada que consegue aprender features via filtros específicos (convoluções). É considerado o tipo de rede mais relevante para deep learning em visão computacional, em especial em imagens médicas.

CNNs usam relativamente menos pré processamento que outros métodos de classificação, pois são capazes de aprender a otimizar seus filtros de maneira automatizada, o que dispensa a criação e testes de filtros diretamente. Esta capacidade a destaca em tarefas como a classificação de imagens médicas no diagnóstico de doenças, pois aprendem a identificar anomalias e padrões sutis nos dados estudados.

ResNet (Residual Network) é uma arquitetura de rede neural profunda desenvolvida para resolver o problema da degradação em redes muito profundas, onde o aumento do número de camadas pode piorar o desempenho. Ela introduz blocos residuais, que permitem que o sinal de entrada seja "pulada" através de uma conexão direta para a camada seguinte, facilitando o treinamento de redes com muitas camadas.

ResNet-50: Um modelo com 50 camadas que utiliza um bloco residual chamado bottleneck, sendo uma das versões mais populares de ResNet devido à sua boa performance em várias tarefas e seu equilíbrio entre profundidade e velocidade de treinamento.

DenseNet (Densely Connected Convolutional Network) é uma arquitetura de rede neural profunda que melhora a eficiência do aprendizado ao conectar cada camada a todas as camadas anteriores. Ou seja, em vez de cada camada receber apenas a saída da camada anterior (como em redes tradicionais), cada camada em uma DenseNet recebe a entrada de todas as camadas anteriores, formando uma conexão densa.

DenseNet-169: Com 169 camadas, oferece maior profundidade e pode capturar características mais complexas, sendo uma boa escolha para tarefas mais desafiadoras.

Notebook: [CNN](notebooks/CNN.ipynb)

## Como foram comparados

Os experimentos compararam os modelos em várias métricas de precisão e também foi estabelecida e uma métrica de emissão de carbono equivalente baseado no tempo de treino e tempo de inferência médio.

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

Alzheimer MRI 4 classes dataset<br>
https://www.kaggle.com/datasets/marcopinamonti/alzheimer-mri-4-classes-dataset?select=Alzheimer_MRI_4_classes_dataset

Advancing Automated Diagnosis: Convolutional Neural Networks for Alzheimer's Disease Classification through MRI Image Processing<br />
May 2023, DOI:10.36227/techrxiv.23002007.v1, Authors: Dheiver Francisco Santos<br />
https://www.researchgate.net/publication/370973426_Advancing_Automated_Diagnosis_Convolutional_Neural_Networks_for_Alzheimer's_Disease_Classification_through_MRI_Image_Processing

Alzheimer's disease dataset<br>
Published: 2 October 2023| Version 1 | DOI: 10.17632/ch87yswbz4.1 Contributor: Ananya Yakkundi<br>
https://data.mendeley.com/datasets/ch87yswbz4/1




___

CMCC - Universidade Federal do ABC (UFABC) - Santo André - SP - Brasil
