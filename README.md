# 🔬 Nanotechnology Image Classifier: Deep Learning para Micrografias MEV

### 📝 Visão Geral

Este projeto aplica Redes Neurais Convolucionais (CNNs) para a classificação automatizada de imagens de Microscopia Eletrônica de Varredura (MEV). O objetivo é distinguir entre três estágios críticos da síntese de nanomateriais de carbono: Grafite, Óxido de Grafeno (GO) e Óxido de Grafeno Reduzido (rGO).

O diferencial deste trabalho é a viabilização do treinamento de modelos complexos em cenários de escassez de dados, típicos em ambientes laboratoriais de pesquisa acadêmica.

### 🧠 Metodologia e Arquitetura

Para superar o desafio de um dataset reduzido, foram implementadas duas estratégias fundamentais:

Transfer Learning: Utilização da arquitetura MobileNetV2 (pré-treinada no ImageNet) como extrator de características fixas, treinando apenas a "cabeça" de classificação para os padrões de textura dos materiais.

Data Augmentation: Implementação de transformações em tempo real (rotação, zoom, shear e flips) para aumentar artificialmente a diversidade das amostras e reduzir o overfitting.

### 📊 Performance e Análise de Treinamento

O modelo foi treinado por 10 épocas, apresentando os seguintes resultados de convergência:

<img width="1189" height="390" alt="image" src="https://github.com/user-attachments/assets/6da9c194-564d-4b98-b539-a69b158bca44" />



Análise Técnica:
Convergência: Observa-se uma queda consistente na função de perda (loss) de treino, indicando que a rede neural conseguiu identificar padrões morfológicos nas folhas de grafeno.

Desafios: As oscilações nas métricas de validação refletem a sensibilidade do modelo ao tamanho do lote (batch) e à alta similaridade visual entre GO e rGO, sugerindo a necessidade de expansão do dataset para maior precisão em ambientes de produção.

### 🛠️ Tecnologias Utilizadas

TensorFlow & Keras: Frameworks principais de Deep Learning.

MobileNetV2: Modelo base otimizado para eficiência.

Matplotlib & Seaborn: Visualização científica e análise de métricas.

ImageDataGenerator: Pipeline de processamento de imagens e aumento de dados.

### 🚀 Como Utilizar

Organize suas imagens MEV em pastas nomeadas por classe dentro de dataset/train e dataset/validation.

Execute o notebook principal para realizar o fine-tuning do modelo.

Utilize a função predizer_material('caminho_da_imagem') para classificar novas micrografias.
