# FIAP - Faculdade de Informática e Administração Paulista

<p align="center">
<a href= "https://www.fiap.com.br/"><img src="assets/logo-fiap.png" alt="FIAP - Faculdade de Informática e Admnistração Paulista" border="0" width=40% height=40%></a>
</p>

<br>

# Cap 1 - CardioIA Conectada: IoT e Visualização de Dados para a Saúde Digital

# Integrante: 
- <a href="https://www.linkedin.com/in/renanmendes26/">Renan de Oliveira Mendes - RM563145</a>


# Descrição
Nessa fase, desenvolvi.

Indo além, criamos uma interface moderna com React e Vite. Também desenvolvemos e treinamos um modelo de visão computacional para a análise de exames de eletrocardiograma.



### Parte 1
Criei uma solução que utiliza Edge Computing com ESP32 para monitoramento em aplicações críticas de saúde. O sistema coleta dados localmente através de sensores e continua funcionando mesmo sem conexão com a internet.
**Link do projeto non Wokwi: https://wokwi.com/projects/463496096459659265**
**Relatório com mais detalhes dentro da pasta Parte1**

<img src="assets/Parte1_wokwi.png" widht="150">

##### Sensores utilizados

 - Sensor DHT22 para temperatura e umidade 
 - Sensor LDR para luminosidade 

#### Funcionamento
O ESP32 realiza leituras periódicas dos sensores e armazena os dados localmente em memória. Uma variável booleana simula a conectividade Wi-Fi.


Quando o sistema está offline:
-	os dados continuam sendo armazenados localmente 
Quando a conexão retorna:
-	os dados armazenados são enviados para a “nuvem” utilizando o Monitor Serial 
- 	após o envio, os dados locais são apagados 



##### Resiliência Offline


Foi implementada uma estratégia FIFO com capacidade máxima de 10 registros. Quando o armazenamento atinge o limite, os dados mais antigos são removidos automaticamente.
Essa abordagem garante:
-   continuidade operacional 
-	tolerância à falha de rede 
-	baixo consumo de memória

<img src="assets/Parte1_wokwiII.png" widht="150">


### Parte 2
Na segunda parte desenvolvi e implementei um sistema completo de monitoramento, distribuição e visualização de dados, usando MQTT, HiveMQ e Node-RED.

**Link do projeto non Wokwi: https://wokwi.com/projects/463502084128323585**
**Link do vídeo: https://youtu.be/qpGmhhiO1mw**
**Relatório com mais detalhes dentro da pasta Parte1**

<img src="assets/wokwi.png" widht="150">


O projeto implementa uma arquitetura IoT utilizando Edge, Fog e Cloud Computing para monitoramento de sinais vitais em tempo real.

O ESP32 realiza coleta de dados locais e transmite informações via protocolo MQTT para um broker em nuvem.

##### Tecnologias utilizadas
- ESP32
- Wokwi
- MQTT
- HiveMQ Cloud
- Node-RED
- Dashboard IoT
- Fluxo MQTT

O ESP32 conecta-se ao Wi-Fi e estabelece comunicação MQTT com o broker HiveMQ Cloud.

<img src="assets/wokwi.png" widht="150">

<img src="assets/HiveMQ.png" widht="150">

Os dados são publicados nos tópicos:

- hospital/temperatura
- hospital/bpm

<img src="assets/NODE_RED.png" widht="150">

O Node-RED atua como camada Fog Computing:

- recebe dados
- processa alertas
- atualiza dashboard em tempo real

##### Dashboard

A dashboard apresenta:

- gráfico de BPM
- gauge de temperatura
- alertas críticos

<img src="assets/Dashboard.png" widht="150">

Os alertas são ativados quando:

- BPM > 120
- temperatura > 38°C

##### Conceitos aplicados
Edge Computing; Coleta local no ESP32; Fog Computing; Processamento intermediário no Node-RED; Cloud Computing e Broker MQTT HiveMQ Cloud.

<img src="assets/Parte1_wokwiII.png" widht="150">



### Ir Além 2

# 📁 Estrutura de pastas

Dentre os arquivos e pastas presentes na raiz do projeto, definem-se:

- <b>assets</b>: Imagens relevantes para documentação desse repositório.

- <b>Ir_Alem</b>: Interface e todo código React + Vite.

- <b>Ir_Alem_2</b>: Notebook python com o modelo MLP para visão computacional.

- <b>Parte_1</b>: Arquivo txt, csv e código Python referentes ao classificador NPL baseado em regras e mapa ontologico criado.

- <b>Parte_2</b>: Arquivo csv e programa Python classificador NPL probabilistico, usando TF_IDF.
  

  
## Requisitos
#### Ambiente
- Node.js 20.x ou 22.x LTS (recomendado para Vite 8) + npm
- Python 3.10–3.12 
- Portal web: Node 20/22, React 19, Vite 8, React Router 7. 
- Notebook: Python 3.10–12, pip install -r requirements.txt (pandas, scikit-learn, numpy, JupyterLab).

#### Versões 
- react 19.2.4
- react-dom 19.2.4
- react-router-dom 7.13.2
- pandas 2.1
- scikit-learn 1.4
- numpy 1.26
- jupyterlab 4 

