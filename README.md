Sprint 3 – Edge Computing and Computer Systems

👥 Integrantes

Vitor Bordalo Corrêa Guimarães – RM: 561592

Lucas Flekner Branquinho – RM: 562262

Ronaldo Aparecido Monteiro Almeida – RM: 565017

Lucas Rowlands Abat – RM: 562994

📖 Descrição do Projeto

O Quiz IoT é uma aplicação baseada em conceitos de IoT (Internet of Things) e Edge Computing, que promove um gameshow interativo com perguntas e respostas em tempo real.

A proposta é criar uma experiência em que:

O usuário recebe perguntas via console (dispositivo IoT – ESP32).

As respostas são enviadas via Postman/HTTP, simulando a interação do jogador.

O sistema valida se a resposta está correta e retorna o feedback instantâneo.

Esse fluxo une coleta de dados, processamento em tempo real e interação remota, demonstrando como dispositivos conectados podem ser aplicados em jogos, treinamentos educacionais e ambientes de entretenimento.

🎯 Objetivos

Criar um gameshow interativo usando IoT.

Processar perguntas e respostas em tempo real.

Integrar dispositivos IoT (ESP32) com FIWARE/Orion para gerenciamento de contexto.

Permitir que o usuário receba perguntas e envie respostas via diferentes canais (console/Postman).

Armazenar dados de desempenho dos participantes para análise posterior.

🏗️ Arquitetura Proposta

O sistema foi modelado em camadas IoT, aproveitando tecnologias já aplicadas em edge computing:

Dispositivo IoT (ESP32) → recebe perguntas e exibe no console para o jogador.

Protocolo de Comunicação (MQTT/HTTP) → intermedia a troca de mensagens entre usuários, Postman e o Orion Context Broker.

Plataforma de Gerenciamento (FIWARE Orion + MongoDB) → armazenamento, validação e gerenciamento das entidades "Pergunta" e "Resposta".

Edge Computing → validação de respostas próxima ao dispositivo, reduzindo latência.

Interface Postman → envio das respostas e feedback ao usuário.

📊 Diagrama Simplificado da Arquitetura:

[ESP32/Console] <--> [Broker MQTT / HTTP API] <--> [Orion Context Broker + MongoDB] --> [Validação/Feedback] --> [Usuário]

⚙️ Desenvolvimento e Configuração

Integração IoT

Configuração do ESP32 para receber perguntas via MQTT e exibir no console.

Conexão do dispositivo ao broker MQTT.

Configuração do FIWARE Orion

Entidades Pergunta e Resposta armazenadas no MongoDB.

Mapeamento dos tópicos para entidades NGSIv2.

Simulação de Usuário

Perguntas são exibidas no console.

Respostas enviadas via Postman (HTTP) para o endpoint /v2/entities/Resposta.

O sistema valida e retorna se a resposta está Correta ou Incorreta.

Edge Computing

Parte do processamento ocorre no dispositivo (feedback imediato).

Parte ocorre na camada de FIWARE, permitindo análise posterior.

🧪 Demonstração

Envio de Pergunta: o sistema publica no ESP32.

Recebimento no Console: jogador lê a questão em tempo real.

Envio de Resposta: via Postman (API REST).

Validação: sistema compara a resposta enviada com o gabarito.

Feedback: exibido no console ("Correto" / "Incorreto").

📂 Estrutura do Repositório
/Quiz-IoT
│── /docs              → Documentação e diagramas
│── /esp32-code        → Código Arduino para ESP32
│── /fiware-config     → Configuração do Orion e MongoDB
│── /postman           → Coleções de requisições
│── /tests             → Scripts de teste de perguntas e respostas
│── README.md          → Este documento

🚀 Como Executar

Clone o repositório:

git clone https://github.com/<seu-repositorio>/Quiz-IoT.git
cd Quiz-IoT


Configure o ESP32 com o código em /esp32-code.

Inicie o Orion + MongoDB via Docker.

Importe as coleções do Postman em /postman.

Execute o fluxo:

Perguntas → enviadas ao ESP32.

Respostas → enviadas via Postman.

Feedback → mostrado no console do usuário.

📌 Futuras Melhorias

Implementar ranking de jogadores com pontuação acumulada.

Criar interface web com dashboard ao vivo do quiz.

Armazenar histórico completo para relatórios.

Ampliar para múltiplos dispositivos IoT em rede.

<img width="997" height="671" alt="Captura de Tela 2025-09-16 às 18 34 31" src="https://github.com/user-attachments/assets/088a4614-f1d8-489b-81d9-5a57097fbf23" />
📜 Licença

Este projeto é acadêmico e desenvolvido para fins educacionais na disciplina Edge Computing and Computer Systems.
