# AG2 — Classificação de Espécies de Pinguins

**Instituto Nacional de Telecomunicações (Inatel)**
**Engenharias de Computação e Software — 1º semestre de 2026**

**Alunos:** Clara de Lima Azevedo e Tiago Rodrigues Gregório

---

# Sobre o projeto

Este projeto foi desenvolvido como parte da atividade AG2 da disciplina, com o objetivo de aplicar conceitos de aprendizado de máquina na classificação de espécies de pinguins.

Foi utilizado o dataset **palmerpenguins**, contendo informações físicas de pinguins observados no Arquipélago Palmer, na Antártica. A partir desses dados, foi treinado um modelo capaz de identificar automaticamente a espécie do animal.

As espécies classificadas são:

* Adeline
* Chinstrap
* Gentoo

O algoritmo utilizado foi o **k-Nearest Neighbors (k-NN)**, escolhido por apresentar bom desempenho em conjuntos de dados pequenos e com atributos numéricos bem definidos.

---

# Estrutura do projeto

```text id="4ec6c1"
.
├── AG2_Pinguins.ipynb
├── penguins.csv
└── README.md
```

| Arquivo              | Descrição                                              |
| -------------------- | ------------------------------------------------------ |
| `AG2_Pinguins.ipynb` | Notebook principal contendo todas as etapas do projeto |
| `penguins.csv`       | Dataset pré-processado utilizado no treinamento        |
| `README.md`          | Documentação do projeto                                |

---

# Execução do projeto

O desenvolvimento foi realizado utilizando o **Google Colab**.

Para executar:

1. Abrir o notebook `AG2_Pinguins.ipynb`;
2. Fazer upload do arquivo `penguins.csv`;
3. Executar as células em ordem.

O notebook já contém as bibliotecas necessárias instaladas nas primeiras células.

---

# Etapas implementadas

O notebook segue a sequência proposta no enunciado da AG2:

1. Leitura do arquivo CSV
2. Manipulação dos dados com Pandas
3. Conversão de atributos categóricos para inteiros
4. Reorganização das colunas
5. Divisão entre treino e teste
6. Escolha do modelo de classificação
7. Treinamento e predição
8. Avaliação do desempenho
9. Classificação de novas amostras inseridas pelo usuário

Além das etapas obrigatórias, também foram adicionados:

* padronização dos atributos com `StandardScaler`;
* validação cruzada para escolha do melhor valor de `k`;
* matriz de confusão;
* exemplos automáticos de classificação.

---

# Sobre o dataset

O conjunto de dados utilizado foi o **palmerpenguins**, contendo informações morfológicas de diferentes espécies de pinguins.

Após o pré-processamento, o dataset utilizado passou a conter:

* 333 amostras válidas;
* 6 atributos de entrada;
* 3 espécies diferentes.

## Atributos utilizados

* `island`
* `sex`
* `culmen_length_mm`
* `culmen_depth_mm`
* `flipper_length_mm`
* `body_mass_g`

## Classe alvo

* `species`

---

# Conversão dos dados

Para permitir o treinamento do modelo, os valores categóricos foram convertidos para números inteiros.

| Coluna  | Conversão                              |
| ------- | -------------------------------------- |
| island  | Biscoe → 0, Dream → 1, Torgersen → 2   |
| sex     | FEMALE → 0, MALE → 1                   |
| species | Adeline → 0, Chinstrap → 1, Gentoo → 2 |

---

# Modelo utilizado

O algoritmo escolhido foi o **k-Nearest Neighbors (k-NN)**.

Esse modelo classifica uma nova amostra com base nos exemplos mais próximos presentes no conjunto de treinamento. Como os atributos do dataset possuem boa separação entre as espécies, o modelo apresentou excelente desempenho durante os testes.

Também foi utilizada a padronização dos dados com `StandardScaler`, já que o k-NN é sensível à escala dos atributos.

---

# Resultados

Após os testes realizados:

* Melhor valor de `k`: 2
* Acurácia aproximada: 98%
* Excelente desempenho na classificação das três espécies

As métricas foram avaliadas utilizando:

* `classification_report`
* matriz de confusão
* validação cruzada

---

# Conclusão

O projeto permitiu aplicar conceitos importantes de aprendizado de máquina, incluindo pré-processamento de dados, treinamento supervisionado, avaliação de desempenho e classificação de novas amostras.

Os resultados obtidos demonstraram que o modelo foi capaz de identificar corretamente a maior parte das espécies presentes no conjunto de teste, atingindo alta acurácia mesmo utilizando um algoritmo relativamente simples.

---

# Referências

[1] Gorman, K. B., Williams, T. D., & Fraser, W. R. *Ecological sexual dimorphism and environmental variability within a community of Antarctic penguins (Genus Pygoscelis)*. PLoS ONE, 2014.

[2] Horst, A. M., Hill, A. P., & Gorman, K. B. *palmerpenguins: Palmer Archipelago (Antarctica) penguin data*. 2020.
