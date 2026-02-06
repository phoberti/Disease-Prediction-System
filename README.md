# Uso de MLP para Classificação de Classes de Doenças

Este projeto implementa um sistema de classificação de doenças utilizando uma Rede Neural Artificial do tipo Multi-Layer Perceptron (MLP).

O sistema recebe como entrada um conjunto estruturado de sintomas e realiza a previsão da classe da doença correspondente com base em aprendizado supervisionado.

Este repositório é um fork do projeto original desenvolvido em grupo na UNIOESTE. Participei ativamente da modelagem, implementação e validação do modelo de Rede Neural MLP utilizado para a classificação das classes de doenças. O fork foi realizado com o objetivo de manter o projeto registrado em meu portfólio acadêmico e profissional.

---

## 1. Objetivo

O objetivo do projeto é desenvolver um modelo de rede neural capaz de:

* Classificar doenças a partir de sintomas informados
* Reduzir a complexidade do problema através do agrupamento de doenças
* Obter alta acurácia na classificação multiclasse
* Demonstrar aplicação prática de MLP em problema real de saúde

O sistema não substitui avaliação clínica, mas pode atuar como ferramenta de apoio para diagnóstico preliminar.

---

## 2. Base de Dados

A base utilizada contém:

* 314 amostras
* 134 sintomas distintos
* 45 doenças originais

Cada sintoma é representado em formato binário (0 = ausência, 1 = presença).

Os sintomas também possuem pesos definidos no arquivo "Symptom Severity".

Para reduzir a complexidade do modelo, as 45 doenças foram agrupadas em 9 classes:

* Respiratória
* Infecciosa
* Inflamatória/Autoimune
* Metabólica/Endócrina
* Gastrointestinal/Hepática
* Dermatológica
* Cardiovascular/Circulatória
* Reações alérgicas
* Neurológica

Esse agrupamento reduziu a quantidade de saídas da rede neural de 45 para 9, simplificando o treinamento e melhorando a generalização.

---

## 3. Metodologia

### 3.1 Pré-processamento

* Normalização com StandardScaler (Scikit-learn)
* Label Encoding para rótulos categóricos
* One-hot encoding para saídas multiclasse
* Separação entre conjunto de treino (307 amostras) e teste (43 amostras)

---

## 4. Arquitetura da Rede Neural

A arquitetura utilizada foi:

* Camada de entrada: 134 neurônios (sintomas)
* Camada oculta: 72 neurônios
* Função de ativação (camada oculta): ReLU
* Camada de saída: 9 neurônios
* Função de ativação (saída): Softmax

### Configuração de Treinamento

* Otimizador: Adam
* Taxa de aprendizado: 0.001
* Função de perda: Categorical Crossentropy
* Métrica: Acurácia
* Batch size: 4
* Máximo de 15 épocas
* Early Stopping com restauração dos melhores pesos

---

## 5. Resultados

O modelo apresentou:

* Acurácia entre 99% e 100%
* No máximo duas classificações incorretas
* Pequena confusão entre duas classes com sintomas semelhantes

O agrupamento das doenças em classes contribuiu significativamente para a alta taxa de acerto e estabilidade do treinamento.

---

## 6. Ambiente Utilizado

* Google Colab
* Python
* TensorFlow / Keras
* Scikit-learn
* Pandas / NumPy

---

## 7. Avaliação

A avaliação foi realizada por meio de:

* Métrica de acurácia
* Matriz de confusão

A matriz de confusão demonstrou alto desempenho geral, com baixo índice de erro entre classes semelhantes.

---

## 8. Referências

ANBUAZHAGAN, Saarathi. A Complete Guide to train Multi-Layered Perceptron Neural Networks. 2021.

HEATON, J. Introduction to Neural Networks with Java. 2. ed. 2008.

JAISWAL, Sejal. Multilayer Perceptrons in Machine Learning: A Comprehensive Guide. 2024.

SENA, Marcus. Building a Perceptron from Scratch. 2023.

VAN OTTEN, Neri. Multilayer Perceptron Explained And How To Train & Optimise MLPs. 2024.

---

## 9. Autores

- Gustavo H. M. Orlandini
- Luiz E. Garzon
- Paulo R. Scalon
- Pedro H. Berti

Universidade Estadual do Oeste do Paraná – UNIOESTE
