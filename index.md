## Classificação de Imagens com Deep Learning

### Resumo

Este trabalho visa apresentar um modelo de Machine Learning baseado em redes neurais profundas (Deep Learning) para classificação de imagens em dez entidades (aviões, carros, pássaros, gatos, cervos, cães, sapos, cavalos, navios e caminhões), utilizando o dataset CIFAR-10 para o treinamento da rede.

Este dataset consiste de 60 mil imagens, com dimensões de 32x32, no formato RGB, divido 10 classes. Destas, 50 mil imagens são destinadas ao treinamento do modelo, e as demais 10 mil utilizadas para validação. 

É sábido que o desenvolvimento e geração de modelos de _Deep Learning_ são tarefas muito custosas computacionalmente, mas também, de que estas se beneficiam amplamente do paralelismo em larga escala ofertado por GPUs, o que reduz, em ordens de grandeza, o tempo de treinamento da rede. Também faz-se necessário, porém, uma framework capaz de utilizar este paralelismo das GPUs, e por este motivo, optou-se pela utilização das frameworks Tensorflow e Keras, populares no ambito de _Deep Learning_.

A implementação da rede neural por trás do modelo treinado se baseou na arquitetura ResNet proposta por He, K., Zhang, X., Ren, S., Sun, J., et al. (2015), e é composta de uma camada de entrada que espera uma imagem no formato RGB, com dimensões 32x32, seguida de 56 camadas escondidas (_hidden layers_) (ResNet-56), onde a rede aplica pesos (_weights_) aos inputs de cada camada e os direciona a saída (desta mesma camada), através de uma função de ativação, que neste caso, a ReLU (_Rectified Linear Units_). São nestas camadas escondidas que ocorre a extração e classificação de features, necessárias para se computar as probabilidade sobre a imagem representar cada uma das classes, que são apresentadas pela camada  camada de saída.

Para realizar predições em imagens, foi desenvolvida uma API REST, que utiliza a URL de uma imagem na Internet para buscá-la, convertê-la para o formato esperado pela camada de entrada do modelo, e realizar a previsão em todas as classes.

Finalmente, para torná-la mais acessível ao público em geral, foi desenvolvido também um bot na platforma Discord para reagir a um padrão de mensagem específico contendo uma url de imagem, que a faz reagir invocando a API para previsões.

**Palavras-chave**: Classificação de Imagens, Redes Neurais Convolucionais, Redes Neurais Profundas

### Autores
Bruno Pereira de Oliveira
Victor Okada

