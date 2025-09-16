# 📌 PassaBola – Arquitetura IoT  
**Sprint 3 – Edge Computing and Computer Systems**  

## 👥 Integrantes  
- **Vitor Bordalo Corrêa Guimarães** – RM: 561592  
- **Lucas Flekner Branquinho** – RM: [preencher]  
- **Ronaldo** – RM: [preencher]  
- **Lucas Abbat** – RM: [preencher]  

---

## 📖 Descrição do Projeto  
O **PassaBola** é uma aplicação **IoT (Internet of Things)** voltada para o monitoramento em tempo real de partidas de futebol, especialmente do futebol feminino. A solução busca **coletar, processar e exibir dados de dispositivos conectados**, entregando valor agregado tanto para **torcedores** (com estatísticas ao vivo), quanto para **jogadoras** (com análises de desempenho) e **administradores** (com relatórios e métricas de gestão).  

A arquitetura proposta combina **dispositivos IoT simulados**, **protocolos de comunicação**, e uma **plataforma de gerenciamento** para análise e visualização dos dados.  

---

## 🎯 Objetivos  
- Monitorar dados em tempo real de partidas.  
- Automatizar a coleta e processamento de informações.  
- Fornecer dashboards interativos com estatísticas.  
- Permitir integração futura com sensores físicos em campo.  
- Gerar relatórios de desempenho para equipes e administradores.  

---

## 🏗️ Arquitetura Proposta  
A arquitetura IoT foi estruturada em **camadas**, utilizando os seguintes elementos:  

- **Dispositivos IoT (Virtuais ou Físicos)** → Sensores simulando dados de partidas (posse de bola, finalizações, gols, desempenho individual).  
- **Protocolo de Comunicação (MQTT/HTTP)** → Transmissão de dados entre sensores e a plataforma.  
- **Plataforma de Gerenciamento (FIWARE / HiveMQ / Node-RED)** → Recebimento, tratamento e roteamento das informações.  
- **Processamento em Edge Computing** → Análise de dados em tempo real próxima à origem.  
- **Camada de Visualização (Front-end React + Vite + Tailwind)** → Exibição em dashboards para usuários, jogadoras e administradores.  

📊 **Diagrama Simplificado da Arquitetura**:  
```
[Sensores IoT] --(MQTT/HTTP)--> [Broker HiveMQ/Node-RED] --(FIWARE)--> [Processamento/Armazenamento] --> [Dashboard PassaBola]
```

---

## ⚙️ Desenvolvimento e Configuração  
1. **Instalação da plataforma IoT**  
   - Configuração do **HiveMQ** para broker MQTT.  
   - Integração com **Node-RED** para fluxo de dados.  
   - Uso do **FIWARE** para gerenciamento de contexto.  

2. **Criação de Dispositivos Virtuais**  
   - Simulação de sensores para envio de dados (ex.: gols, posse, finalizações).  
   - Publicação periódica em tópicos MQTT.  

3. **Protocolos de Comunicação**  
   - MQTT (leve e eficiente para tempo real).  
   - HTTP (alternativo para APIs REST de integração).  

4. **Visualização e Interface**  
   - Front-end em **React + Vite + Tailwind**.  
   - Páginas dedicadas para **usuário**, **jogadora** e **administrador**.  
   - Estatísticas ao vivo, rankings, histórico de partidas e relatórios.  

---

## 🧪 Demonstração  
- **Coleta de dados**: envio de métricas simuladas via MQTT.  
- **Health check**: monitoramento de integridade da conexão e status dos dispositivos.  
- **Criação de entidade lógica**: junção de dados de sensores em métricas de partida (posse %, finalizações, ranking).  
- **Dashboard ao vivo**: exibição dos resultados em tempo real no site **PassaBola**.  

---

## 📂 Estrutura do Repositório  
```
/PassaBola-IoT
│── /docs              → Documentação e diagramas
│── /frontend          → Código React (dashboard e site)
│── /iot-devices       → Scripts de simulação de sensores
│── /platform-config   → Configuração do FIWARE / HiveMQ / Node-RED
│── /tests             → Arquivos de teste e simulação
│── README.md          → Este documento
```

---

## 🚀 Como Executar  
1. Clone o repositório:  
   ```bash
   git clone https://github.com/<seu-repositorio>/PassaBola-IoT.git
   cd PassaBola-IoT
   ```
2. Configure os dispositivos IoT simulados em `/iot-devices`.  
3. Inicie o **Node-RED** e o **HiveMQ** localmente.  
4. Execute o front-end:  
   ```bash
   cd frontend
   npm install
   npm run dev
   ```
5. Acesse o dashboard em `http://localhost:5173/`.  

---

## 📌 Futuras Melhorias  
- Integração com sensores físicos de campo.  
- Notificações em tempo real (push para torcedores e jogadoras).  
- Machine Learning para prever resultados com base em estatísticas.  
- Escalabilidade com microsserviços em nuvem.  

---

## 📜 Licença  
Este projeto é acadêmico e desenvolvido para fins educacionais na disciplina **Edge Computing and Computer Systems**.  
