<div align="center">

# 👋 Olá, eu sou **Abner Borda Fonseca**!

[![Typing SVG](https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=22&pause=1000&color=9745F5&center=true&vCenter=true&random=false&width=700&lines=Senior+Information+Security+Specialist+%F0%9F%94%90;Data+Engineering+%7C+Spark+%E2%80%A2+Databricks+%E2%80%A2+Kafka;51GB+processados+em+34+min+%F0%9F%94%A5;SIEM%2FSOAR+Agentless+com+IA+Local+%F0%9F%9B%A1%EF%B8%8F;Construindo+ferramentas+reais+em+produ%C3%A7%C3%A3o+%F0%9F%9A%80)](https://git.io/typing-svg)

<img src="https://komarev.com/ghpvc/?username=afborda&label=Visitantes&color=9745F5&style=flat" alt="afborda" />

[![LinkedIn](https://img.shields.io/badge/-Abner_Fonseca-0077B5?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/abner-fonseca-25658b67)
[![Email](https://img.shields.io/badge/-abner.borda@gmail.com-D14836?style=flat&logo=gmail&logoColor=white)](mailto:abner.borda@gmail.com)
[![Location](https://img.shields.io/badge/-Porto_Alegre,_RS-333?style=flat&logo=google-maps&logoColor=white)]()

</div>

---

## 🚀 Sobre mim

```javascript
const abner = {
    cargo: "Senior Information Security Specialist | Data Engineering",
    empresa: "SAP (São Leopoldo, RS)",
    experiencia: "+5 anos em sistemas de alta escala",

    transicao: {
        de: "Mobile Engineering (React Native)",
        para: "Data Engineering (Spark, Databricks, Lakehouse)"
    },

    diferenciais: [
        "Clean Code & Design Patterns aplicados a Data Pipelines",
        "Experiência com milhões de usuários (App BB)",
        "Automação com N8N + LLMs (AI Agents)",
        "Segurança agentless com IA local (Guardian)",
        "SaaS de infraestrutura gerenciada com provisionamento Docker"
    ],

    objetivo: "Resolver problemas complexos de dados em escala 🚀"
};
```

---

## 🏗️ Projetos

> Projetos ativos — alguns em produção, outros em desenvolvimento.

---

### 🔍 Fraud Detection Pipeline — `spark-medallion-fraud-detection`

**Pipeline de detecção de fraudes bancárias com arquitetura Medallion + Lambda**

[![Ver Repositório](https://img.shields.io/badge/Ver_Repositório-spark--medallion--fraud--detection-181717?style=for-the-badge&logo=github)](https://github.com/afborda/spark-medallion-fraud-detection)

| 📊 Métrica | 🎯 Resultado |
|------------|--------------|
| **Dados Processados** | 51.2M transações (51GB) |
| **Tempo Total** | ~34 minutos |
| **Throughput** | ~85.000 tx/segundo |
| **Compressão** | 90% (51GB JSON → 5GB Parquet) |
| **Fraudes Detectadas** | R$ 14.1 Bilhões protegidos |
| **Recall** | 89.88% (captura 90% das fraudes) |

**Arquitetura implementada:**
```
Raw (JSON) → Bronze (Parquet) → Silver (Clean) → Gold (Aggregated)
   51 GB   →      5 GB        →      5.4 GB    →     2 GB
```

Combina **processamento batch** (51M transações históricas via PySpark) com **streaming em tempo real** (Kafka → Spark Structured Streaming, ~10 tx/s, latência ~1s) gravando no mesmo `fraud_db` — permitindo que o Metabase misture histórico e tempo real no mesmo dashboard.

**Acesse ao vivo:**

| Serviço | Link | Descrição |
|---------|------|-----------|
| 🌊 **Dashboard Streaming** | [Fraudes em tempo real](https://metabase.abnerfonseca.com.br/public/dashboard/d43f14da-5c01-4ab4-a4a9-8e54d0bcc5dd) | Atualiza a cada 1 min |
| 📦 **Dashboard Batch** | [Análise histórica 51M tx](http://metabase.abnerfonseca.com.br/public/dashboard/3cc49faf-2860-413a-9da8-ff82ffaba34a) | 51M transações processadas |
| 📊 **Metabase** | [metabase.abnerfonseca.com.br](https://metabase.abnerfonseca.com.br) | Plataforma BI completa |
| ⚡ **Spark Master** | [spark.abnerfonseca.com.br](https://spark.abnerfonseca.com.br) | Cluster com 5 workers |
| 📦 **MinIO Console** | [minio.abnerfonseca.com.br](https://minio.abnerfonseca.com.br) | Data Lake (Object Storage) |

![Apache Spark](https://img.shields.io/badge/Apache_Spark-E25A1C?style=flat&logo=apachespark&logoColor=white)
![Apache Kafka](https://img.shields.io/badge/Apache_Kafka-231F20?style=flat&logo=apachekafka&logoColor=white)
![Python](https://img.shields.io/badge/Python_3.13-3776AB?style=flat&logo=python&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=flat&logo=postgresql&logoColor=white)
![MinIO](https://img.shields.io/badge/MinIO-C72E49?style=flat&logo=minio&logoColor=white)
![Metabase](https://img.shields.io/badge/Metabase-509EE3?style=flat&logo=metabase&logoColor=white)

---

### 🇧🇷 SynthFin Data — `synthfin-core`

**Gerador de dados sintéticos realistas de fraudes bancárias brasileiras**

[![Ver Repositório](https://img.shields.io/badge/Ver_Repositório-synthfin--core-181717?style=for-the-badge&logo=github)](https://github.com/afborda/synthfin-core)
[![Docker Hub](https://img.shields.io/badge/Docker_Hub-afborda%2Fsynthfin--data-2496ED?style=for-the-badge&logo=docker&logoColor=white)](https://hub.docker.com/r/afborda/synthfin-data)

Criado para suprir a falta de datasets brasileiros de qualidade para estudos de Data Engineering e Machine Learning. Gera dados **realistas e labeleados**, prontos para pipelines de fraude, modelos de ML e QA de plataformas.

| 🎯 Feature | 📋 Descrição |
|------------|---------------|
| **Qualidade ML** | AUC-ROC 0.9991 · nota 9.70/10 |
| **Clientes** | CPF válido, nomes, endereços, renda (Faker pt_BR + Censo 2022) |
| **Transações** | PIX (45%), Cartão Crédito/Débito, TED, Boleto — proporção real |
| **Fraudes** | 25 padrões bancários + 11 ride-share (Engenharia Social, PIX falso, Cartão Clonado...) |
| **Bancos** | 17 bancos com market share real (BB, Itaú, Nubank, C6...) |
| **Escala** | Gera 50GB+ em ~35 min com processamento paralelo |
| **Streaming** | Kafka · Webhook · stdout · Redis Stream |
| **Geolocalização** | Coordenadas correlacionadas por estado (IBGE) |

```bash
# Open source — self-hosted
python generate.py --size 10GB --workers 8 --fraud-rate 0.03 --seed 42

# Ou via API hospedada (beta aberto)
curl -X POST https://api.synthfin.com.br/v2/generate \
  -H "Authorization: Bearer YOUR_KEY" \
  -d '{"type":"transactions","count":100000,"format":"parquet"}'
```

**Plataforma hospedada (beta):**

| Serviço | Link |
|---------|------|
| 🌐 **Site** | [synthfin.com.br](https://synthfin.com.br) |
| ⚡ **API** | [api.synthfin.com.br](https://api.synthfin.com.br) |
| 📊 **Dashboard** | [app.synthfin.com.br](https://app.synthfin.com.br) |

> Relatório de qualidade ML (LightGBM + AUC-ROC por tipo de fraude) entregue por email após cada job. Quer testar? → [devabnerfonseca@gmail.com](mailto:devabnerfonseca@gmail.com)

![Python](https://img.shields.io/badge/Python_3.10+-3776AB?style=flat&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat&logo=fastapi&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)
![version](https://img.shields.io/badge/version-4.18.0-0F766E?style=flat)
![AUC-ROC](https://img.shields.io/badge/AUC--ROC-0.9991-0F766E?style=flat)

---

### 🛡️ Guardian Blue Team — `guardian-blue-team`

**SIEM/SOAR agentless com IA local — detecta, analisa, bloqueia e aprende**

[![Ver Repositório](https://img.shields.io/badge/Ver_Repositório-guardian--blue--team-181717?style=for-the-badge&logo=github)](https://github.com/afborda/guardian-blue-team)
[![CI](https://github.com/afborda/guardian-blue-team/actions/workflows/ci.yml/badge.svg)](https://github.com/afborda/guardian-blue-team/actions/workflows/ci.yml)
[![Docker](https://img.shields.io/badge/Docker-ghcr.io%2Fafborda%2Fguardian--blue--team-2496ED?style=flat&logo=docker&logoColor=white)](https://ghcr.io/afborda/guardian-blue-team)
[![Version](https://img.shields.io/badge/version-2.1.0-9745F5?style=flat)]()
[![License](https://img.shields.io/badge/License-AGPL_v3-blue?style=flat)](https://github.com/afborda/guardian-blue-team/blob/main/LICENSE)

Monitora servidores via SSH (sem instalar nada nos targets), detecta ameaças em tempo real e responde automaticamente com bloqueios permanentes no firewall. Usa **IA local** (Ollama) para análise, constrói **memória semântica** de incidentes (RAG com embeddings bge-m3) e faz **threat hunting proativo** a cada 4 horas.

**Setup em 30 segundos:**
```bash
git clone https://github.com/afborda/guardian-blue-team.git
cd guardian-blue-team && cp .env.example .env
# edite .env com TELEGRAM_BOT_TOKEN e TELEGRAM_CHAT_ID
docker compose up -d
# depois: /add-server meuserver 1.2.3.4 22 root
```

| Proteção | Ameaças | Resposta |
|----------|---------|----------|
| **SSH** | Brute force, logins suspeitos, horários fora do padrão | Bloqueio permanente |
| **DDoS** | SYN flood, connection rate, bandwidth anomaly (STL) | Rate-limit → escalada → bloqueio |
| **Network** | Port scan, DGA C2 (ML ONNX), TLDs suspeitos | Bloqueio permanente |
| **Containers** | Crypto mining, escape attempts, crashloops | Kill + bloquear |
| **FIM** | Alteração em /etc/passwd, sudoers, sshd_config, authorized_keys | Alerta crítico |
| **CVE** | Pacotes instalados com CVEs (OSV.dev + EPSS + CISA KEV) | Alerta + remediação |

**Comparativo:**

| | Fail2ban | CrowdSec | Wazuh | **Guardian** |
|--|----------|----------|-------|:------------:|
| Setup | 5 min | 30 min | 2+ horas | **30 segundos** |
| Agente nos targets | Sim | Sim | Sim | **Não** |
| IA para decisões | — | — | — | **IA local** |
| Aprende com incidentes | — | — | — | **RAG + Embeddings** |
| Threat hunting | — | — | — | **A cada 4h** |

**Dashboard:** 12 páginas (Overview · Fleet · Incidents · CVE · Blocks · Attack Map · Intelligence)
**Telegram Bot:** 30+ comandos — `/status`, `/block`, `/unblock`, `/ask`, `/threat <ip>`, `/report`...

> Demo ao vivo em breve — por enquanto: clone, configure e rode em 5 minutos.

![Node.js](https://img.shields.io/badge/Node.js_20-339933?style=flat&logo=nodedotjs&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=flat&logo=typescript&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL_16-316192?style=flat&logo=postgresql&logoColor=white)
![Ollama](https://img.shields.io/badge/Ollama-qwen3%3A4b+bge--m3-black?style=flat)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)

---

### 🤖 AutomaBotHub *(em desenvolvimento)*

**Plataforma SaaS de automações gerenciadas — n8n, Evolution API, Typebot e Chatwoot na nuvem**

![Em Desenvolvimento](https://img.shields.io/badge/Status-Em_Desenvolvimento-orange?style=for-the-badge)

Clientes escolhem tier de infraestrutura (Sandbox → Starter → Business → Professional → Enterprise) e as ferramentas que precisam. Stripe processa o pagamento, e em segundos containers Docker isolados sobem com subdomínio próprio e roteamento via Traefik — sem o cliente precisar configurar nada.

**Como funciona:**
```
Stripe Checkout → Webhook → Provisioning Engine (XState v5)
    → Docker (containers isolados) → Traefik (HTTPS + subdomain)
    → n8n / Evolution API / Typebot / Chatwoot
```

| Recurso | Detalhe |
|---------|---------|
| **Serviços** | n8n, Evolution API, Typebot, Chatwoot |
| **Tiers** | Sandbox → Starter → Business → Professional → Enterprise |
| **Infra** | Containers Docker isolados por cliente, subdomínio automático |
| **Billing** | Stripe (webhooks + planos + addons) |
| **Workers** | Métricas, abuse detection, relatórios, limpeza de órfãos |
| **Stack** | Node.js + TypeScript + Express + Drizzle ORM + PostgreSQL |

![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat&logo=nodedotjs&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=flat&logo=typescript&logoColor=white)
![Next.js](https://img.shields.io/badge/Next.js_15-000000?style=flat&logo=nextdotjs&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)
![Stripe](https://img.shields.io/badge/Stripe-635BFF?style=flat&logo=stripe&logoColor=white)
![n8n](https://img.shields.io/badge/n8n-EA4B71?style=flat&logo=n8n&logoColor=white)

---

## 🛠️ Tech Stack

<div align="center">

### 📊 Data Engineering & Big Data
![Apache Spark](https://img.shields.io/badge/Apache_Spark-E25A1C?style=for-the-badge&logo=apachespark&logoColor=white)
![Databricks](https://img.shields.io/badge/Databricks-FF3621?style=for-the-badge&logo=databricks&logoColor=white)
![Delta Lake](https://img.shields.io/badge/Delta_Lake-00ADD8?style=for-the-badge&logo=delta&logoColor=white)
![Apache Kafka](https://img.shields.io/badge/Apache_Kafka-231F20?style=for-the-badge&logo=apachekafka&logoColor=white)
![Apache Airflow](https://img.shields.io/badge/Apache_Airflow-017CEE?style=for-the-badge&logo=apacheairflow&logoColor=white)

### 🗄️ Bancos de Dados & Storage
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=for-the-badge&logo=mongodb&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white)
![MinIO](https://img.shields.io/badge/MinIO-C72E49?style=for-the-badge&logo=minio&logoColor=white)

### 💻 Software Engineering
![React Native](https://img.shields.io/badge/React_Native-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![PySpark](https://img.shields.io/badge/PySpark-E25A1C?style=for-the-badge&logo=apachespark&logoColor=white)

### 🤖 AI & Automação
![OpenAI](https://img.shields.io/badge/OpenAI-412991?style=for-the-badge&logo=openai&logoColor=white)
![LangChain](https://img.shields.io/badge/LangChain_RAG-1C3C3C?style=for-the-badge&logo=langchain&logoColor=white)
![n8n](https://img.shields.io/badge/n8n-EA4B71?style=for-the-badge&logo=n8n&logoColor=white)
![Ollama](https://img.shields.io/badge/Ollama_Local_AI-black?style=for-the-badge)

### ⚙️ DevOps & Infra
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=githubactions&logoColor=white)
![Traefik](https://img.shields.io/badge/Traefik-24A1C1?style=for-the-badge&logo=traefikproxy&logoColor=white)

</div>

---

## 💼 Experiência Profissional

```
🏢 SAP (Mar 2026 - Atual)
   └─ Senior Information Security Specialist
      • São Leopoldo, RS

🏢 Cast Group (Set 2022 - Jan 2026)
   └─ Desenvolvedor Mobile Sênior | App Banco do Brasil (PF e PJ)
      • Apps com milhões de usuários ativos
      • Integração com APIs de alto volume transacional
      • Automação com N8N + LLMs (AI Agents)

🏢 Equifax | Boa Vista (Jul 2021 - Set 2022)
   └─ Analista de Sistemas Pleno - React Native | Score de Crédito
      • Ambiente Data-Driven
      • Telemetria e Analytics para decisões técnicas
      • CI/CD com Bitrise · Firebase · App Store + Google Play

🏢 TargetTrust (Jun 2021 - Mar 2023)
   └─ Instrutor Técnico
      • TypeScript avançado e engenharia de software moderna
      • Lógica de programação e estruturas de dados

🏢 DBServer (Dez 2020 - Dez 2021)
   └─ Desenvolvedor Mobile | Consultoria varejo

🏢 ilegra (Nov 2019 - Nov 2020)
   └─ Desenvolvedor Front-end / Mobile
      • Angular 7+ · React Native · Firebase · TypeScript

🏢 ViaFlow Consultoria e Tecnologia (Abr 2019 - Out 2019)
   └─ Desenvolvedor Júnior / UX e UI
      • React.js · React Native · Node.js · AdobeXD · Figma

🏢 Previsul Seguradora (Nov 2016 - Mar 2019)
   └─ Estagiário → Assistente Técnico de Sistemas
```

---

## 🎓 Formação & Certificações

| 📚 Curso | 🏫 Instituição | 📅 Período |
|----------|----------------|------------|
| Formação Spark & Databricks (240h) | Engenharia de Dados Academy | 2025 |
| Especialização em Banco de Dados | PostgreSQL, Tuning, NoSQL | 2024-2025 |
| Análise e Desenvolvimento de Sistemas | UniRitter | 2019-2025 |
| Técnico em Redes e Telecomunicações | SENAI | 2019-2025 |

---

## 📊 GitHub Stats

<div align="center">
  <a href="https://github.com/afborda">
    <img height="180em" src="https://github-readme-stats-git-masterrstaa-rickstaa.vercel.app/api?username=afborda&show_icons=true&theme=tokyonight&include_all_commits=true&count_private=true&hide_border=true&bg_color=0D1117"/>
  </a>
  <a href="https://github.com/afborda">
    <img height="180em" src="https://github-readme-stats-git-masterrstaa-rickstaa.vercel.app/api/top-langs/?username=afborda&layout=compact&langs_count=8&theme=tokyonight&hide_border=true&bg_color=0D1117"/>
  </a>
</div>

---

## 🔥 Streak Stats

<div align="center">
  <a href="https://github.com/afborda">
    <img src="https://github-readme-streak-stats.herokuapp.com/?user=afborda&theme=tokyonight&hide_border=true&background=0D1117&stroke=9745F5&ring=9745F5&fire=FF6B6B&currStreakNum=FFFFFF&sideNums=FFFFFF&currStreakLabel=9745F5&sideLabels=9745F5&dates=888888" alt="GitHub Streak"/>
  </a>
</div>

---

## 📈 Gráfico de Contribuições

<div align="center">
  <a href="https://github.com/afborda">
    <img src="https://github-readme-activity-graph.vercel.app/graph?username=afborda&theme=tokyo-night&bg_color=0D1117&color=9745F5&line=9745F5&point=FFFFFF&area=true&hide_border=true&custom_title=Contribuições%20nos%20últimos%2031%20dias" alt="Contribution Graph"/>
  </a>
</div>

> 💡 *Se o gráfico não carregar, [clique aqui](https://github.com/afborda?tab=overview) para ver no GitHub*

---

## 🏆 Troféus GitHub

<div align="center">
  <img src="https://github-profile-trophy.vercel.app/?username=afborda&theme=tokyonight&no-frame=true&no-bg=true&margin-w=4&row=1" alt="Trophies"/>
</div>

---

<div align="center">

### 💬 *"Aplicando o rigor da Engenharia de Software na construção de Pipelines de Dados robustos"*

<a href="https://linkedin.com/in/abner-fonseca-25658b67">
  <img src="https://img.shields.io/badge/Vamos_conversar%3F-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"/>
</a>

</div>

---

<div align="center">
  <sub>Feito com ❤️ por Abner Fonseca</sub>
</div>
