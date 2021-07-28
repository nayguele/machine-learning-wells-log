# Classificação de litofácies com o auxílio de algoritmo detector de camadas

#### Aluno:[Nayguel de Castro Costa](https://github.com/nayguele)
#### Orientador: [Pedro Diaz](https://github.com/pedro9589).

---

Trabalho apresentado ao curso [BI MASTER](https://ica.puc-rio.ai/bi-master) como pré-requisito para conclusão de curso e obtenção de crédito na disciplina "Projetos de Sistemas Inteligentes de Apoio à Decisão".

---

### Resumo

O objetivo desse trabalho é aprimorar as técnics conhecidas de classificação supervisionada de litofácies a partir de perfis geofísicos de poços. Alguns autores, a exemplo de (citar referências) tem proposto a utilização de algoritmos de aprendizado de máquina para a partir de uma base de testes interpretada, isto é, com cada ponto amostrado com perfis classificado quanto a sua litofácie característica, poder determinar qual a litofácie mais provavél em um conjunto de teste que contenha os mesmos perfis do treinamento. O professor Diaz aplicou com bastante sucesso as técnicas SVM e Random Forest na base de dados XXXXX. 

Reid (1989) estabeleceu uma técnica muito simples e interessante de detectar a transição entre camadas no registro geológico a partir do perfil Gamma Ray (GR). A estrategia consiste em aplicar dois filtros de média móvel com janelas diferentes, um com janela menor para eliminar os ruídos de alta frequência e outro com uma janela maior para capturar a tendência mais geral de variação de propriedade do perfil ao longo do poço. As interseções entre esses dois perfis processados determina a segmentação das camadas do poço e então basta atribuir um valor de acordo com uma estatística dos valores medidos no intervalo. Nesse trabalho, aplicamos a técnica de Reid e utilizamos os novos perfis criados como variáveis adicionais de entrada do SVM e do Random Forest. Em seguida aplicamos o mesmo fluxo do trabalho de Diaz comparamos os resultados obtidos. 

Concluímos que do ponto de vista de diferentes métricas (Acurácia, F-1 Score e MCC) vale a pena incluir esse passo de pré-processamento no fluxo, pois em todos os casos conseguimos alcançar resultados melhores na classificação das litofácies em nossa base. O custo computacional da adição desses passos é baixíssimo, o que incentiva ainda mais sua utilização.


### Abstract 

The book is on the table ... bla bla bla


---

Matrícula: 192.671.080

Pontifícia Universidade Católica do Rio de Janeiro

Curso de Pós Graduação *Business Intelligence Master*
