# Classificação de litofácies com o auxílio de algoritmo detector de camadas

#### Aluno:[Nayguel de Castro Costa](https://github.com/nayguele)
#### Orientador: [Pedro Diaz](https://github.com/pedro9589).

---

Trabalho apresentado ao curso [BI MASTER](https://ica.puc-rio.ai/bi-master) como pré-requisito para conclusão de curso e obtenção de crédito na disciplina "Projetos de Sistemas Inteligentes de Apoio à Decisão".

---

### Resumo

O objetivo desse trabalho é aprimorar as técnicas conhecidas de classificação supervisionada de litofácies a partir de perfis geofísicos de poços. Os dados de estudo vieram dos campos de gás Hugoton e Panoma, fornecida pela Universidade de Kansas. Esta base contém 3232 amostras com litofácies conhecidas, com cada amostra tendo quatro ou cinco propriedades medidas. Entre os estudos publicados que utilizaram essa base, Dubois et al. (2007) aplicaram sete classificadores clássicos, Potratz et al. (2021) utiliraram uma combinação de t-SNE e KNN. O professor Diaz documentou no repositório https://github.com/ICA-cursos/bi-master_machine
learning/tree/master/Classifica%C3%A7%C3%A3o/Estudo%20de%20caso%20de%20classifica%C3%A7%C3%A3o%20de%20facies%20sismicas o passo a passo para aplicar SVM e Random Forest nesse mesmo conjunto de dados.
Reid et al. (1989) estabeleceu uma técnica muito simples e interessante de detectar a transição entre camadas no registro geológico a partir do perfil Gamma Ray (GR). A estrategia consiste em aplicar dois filtros de média móvel com janelas diferentes, um com janela menor para eliminar os ruídos de alta frequência e outro com uma janela maior para capturar a tendência mais geral de variação de propriedade do perfil ao longo do poço. As interseções entre esses dois perfis processados determina a segmentação das camadas do poço e então basta atribuir um valor de acordo com uma estatística dos valores medidos no intervalo. Nesse trabalho, aplicamos a técnica de Reid nos perfis dos poços e em seguida utilizamos os atibutos obtidos como entrada para o treinamento e previsão de fácies com SVM e Random Forest. Para efeito de comparação utilizamos os resultados de Potratz et al. como referência, utilizando a mesma metodologia de validação e as mesmas métricas de avaliação. Os detalhes da aplicação se encontram no repositório https://github.com/nayguele/machine-learning-wells-log/blob/main/Facies_Classification_detcam.ipynb. Apresentamos aqui a tabela com as métricas para as diferentes configurações testadas.

Método | Precision | Recall| F1-score | Acurácia | Acurácia Fácies Adjacentes | MCC
:---: | :---: | :---: | :--: |:---: | :---: | :---: 
SVM| 0.63 | 0.63 | 0.61 | 0.63 | 0.92 | 0.56
SVM perfis substituídos | 0.58 | 0.62 | 0.60 | 0.62 | 0.90 | 0.55
SVM atributos acrescentados | 0.66 | 0.66 | 0.64 | 0.66 | 0.93 | 0.59
RF  | 0.74 | 0.73 | 0.73 | 0.73 | 0.94 | 0.68
RF perfis substituídos | **0.84** | **0.84** | **0.84** | **0.84** | **0.95** | **0.81**
RF atributos acrescentados | 0.82 | 0.82 | 0.82 | 0.82 | **0.95** | 0.78
t-SNE + KNN (artigo) | 0.79 | 0.79 | 0.79 | - | - | -

Concluímos que do ponto de vista de diferentes métricas (Acurácia, F-1 Score e MCC) vale a pena incluir esse passo de pré-processamento no fluxo, pois em todos os casos conseguimos alcançar resultados melhores na classificação das litofácies em nossa base. Em especial a utilização dessa metodologia com o Random Forest alcançou uma precisão de 84%, bem superios aos resultados da aplicação direta de algoritmos conhecidos de machine learning ou até mesmo técnicas mais sofisticadas como as dos artigos mencionados. O custo computacional da adição desses passos é baixíssimo, o que incentiva ainda mais sua utilização.


### Abstract 

The main goal of this work is to improve state of art rock facies classifiers through well logs measured properties. The study data came from the Hugoton and Panoma gas fields, provided by the University of Kansas. This database contains 3232 samples with known rock facies class, with each sample having either four or five measured properties. Among the published studies that used this database, Dubois et al. (2007) applied seven classic classifiers, Potratz et al. (2021) used a combination of t-SNE and KNN. Professor Diaz documented in the repository https://github.com/ICA-cursos/bi-master_machine
learning/tree/master/Classifica%C3%A7%C3%A3o/Estudo%20de%20caso%20de%20classifica%C3%A7%C3%A3o%20de%20facies%20sismicas the step by step to perform SVM and Random Forest on this same dataset .
Reid et al. (1989) established a very simple and interesting for boundary detection in the geological record through the Gamma Ray log (GR). The idea is to apply two centered moving mean filters with different windows, a smaller one to eliminate high frequency noise and the other with a larger window to capture the general trend of the log. The intersections between these two processed logs determine the discrimination of the well layers and then simply assign a value according to a statistic of the interval measured values. In this work, we applied the Reid technique to the well logs, and then used the attributes obtained as input for the training and prediction of facies with SVM and Random Forest. For comparison purposes, we used the results of Potratz et al. as a reference, using the same validation methodology and the same evaluation metrics. Application details can be found in the repository https://github.com/nayguele/machine-learning-wells-log/blob/main/Facies_Classification_detcam.ipynb. 
We believe that, from the point of view of different metrics (Accuracy, F-1 Score and MCC), it is worth including this pre-processing step in the flow, because in all cases we managed to achieve better results in the rock facies classification. Particularly, the use of this methodology combined with Random Forest achieved an accuracy of 84%, well above the results of the direct application of known machine learning algorithms or even more sophisticated techniques such as those in the aforementioned articles. The computational cost of adding these steps is very low, which further encourages their use.




Matrícula: 192.671.080

Pontifícia Universidade Católica do Rio de Janeiro

Curso de Pós Graduação *Business Intelligence Master*
