# MAC5768
Eps da disciplina de Visão e Processamento de Imagens 2020-2

## Integrantes 
  - Diego 
  - Luiz Manrique
  - Jose Luiz Maciel Pimenta

## Drive com as fotos utilizadas e com o Google Colab
  - https://drive.google.com/drive/folders/1bvwXFjPWP-Sdb5Lwh6zFd_vQs24mJ6_c?usp=sharing

*  Base de dados organizada em:
    * RAW - Base contendo as fotos sem qualquer alteração, ou pré-processamento;
    * dataset - Base contendo as fotos cuja sua resolução está padronizada em HD;
      * dataset.csv - metadados dos dados originais ./dataset/*
      * normalizedDataset.csv - metadados dos dados normalizados ./dataset/augmentation/normalizedDataset/*
      * meanDataset.csv - metadados dos dados após o filtro da média ./dataset/augmentation/augmentedDataset/mean/*
      * logDataset.csv - metadados dos dados após log ./dataset/augmentation/augmentedDataset/log/*
      * gradientDataset.csv - metadados dos dados após somo com novo gradiente ./dataset/augmentation/augmentedDataset/gradient/*
      * expDataset.csv - metadados dos dados após exp ./dataset/augmentation/augmentedDataset/exp/*
      * grayDataset.csv - metadados dos dados após transformar em escalas de cinza ./dataset/augmentation/grayDataset/*
    * Ep_01.ipynb - Notebook (Google Colab) do ep01
    * Ep_02-1.ipynb - Notebook (Google Colab) do ep02 parte 01
    * Ep_02-2.ipynb - Notebook (Google Colab) do ep02 parte 02
    * Ep_03.ipynb - Notebook (Google Colab) do ep03

## EP01 - Descrição
O EP1 consiste em:
*  Formação da base de imagens;
*  Notebook contendo a tabela de imagens, distribuição das classes e uma apresentação das imagens no formato MNIlist like;

## EP02 - Descrição
O EP02 consiste em duas etapas:
* Etapa 01:
  * Aumentar a base de dados utilizando uma técnica conhecida como Data Augmentation. Cada uma das funções de Data Augmentation foram aplicadas nas imagens na      base de dados em níveis de cinza. Portanto, o primeiro passo foi converter as imagens da base de dados em níveis de cinza. Essas imagens foram colocadas no drive na pasta '/dataset/augmentation/originalGrayDataset/'.

  * Após essa converção, as seguinte funções foram utilizadas, seguidas de seus respectivos diretorios:
    * Soma de fundo com gradiente de níveis de cinza: '/dataset/augmentation/augmentedDataset/gradient/'
    * Logaritmo da imagem: '/dataset/augmentation/augmentedDataset/log/'
    * Exponencial da imagem: '/dataset/augmentation/augmentedDataset/exp/'
    * Filtro da média implementado usando convolução: '/dataset/augmentation/augmentedDataset/mean/'
    
* Etapa 02:
  * Criar um novo dataset chamado de normalizedDataset contendo a equalização de cada classe do augmentedDataSet;
  * As funções de análise de cada classe abaixo devem ser aplicadas ao originalGrayDataset, augmentedDataset e normalizedDataset.
    * Mostrar o protótipo médio de cada classe;
    * Histograma médio de cada classe;
    * Variância do histograma de cada classe.

## EP03 - Descrição
* Este trabalho tem dois objetivos principais.

  * O primeiro objeto é a segmentação do objeto de interesse, onde será objeto será separado do fundo, produzindo uma imagem binária: 0 para o fundo e 1 para o objeto. Nesta seção, dois tipos de segmentação serão usados: manual, para geração do ground-truth, para pelo menos 15% de cada classe do dataset, e automática, onde vários algoritmos serão testados para chegar a um resultado mais perto possível da segmentação manual. Depois, será calculado a Bounding Box da imagem segmentada.

  * O segundo objetivo é a classificação do objeto de interesse, onde será calculado as um vetor de features para a região definida pelo Bounding Box e com este vetor, será possível prever a qual classe um objeto em uma imagem pertence.
