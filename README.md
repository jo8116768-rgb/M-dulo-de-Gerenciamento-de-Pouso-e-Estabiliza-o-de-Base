# 🚀 MGPEB - Módulo de Gerenciamento de Pouso e Estabilização de Base
> **Missão Aurora Siger** | Controle de tráfego orbital e autorização de pouso em Marte

---

## 📄 Documentação Completa

O relatório acadêmico e técnico detalhado do projeto (incluindo modelagem matemática, análise ESG e histórico computacional) pode ser acessado no link abaixo:

🔗 **[Acessar Relatório Completo do Projeto](https://1drv.ms/w/c/795ed93c519cc49d/IQBBZ2CzEfzPR6WL85Ynqp-0ATGO4qSNvQN1AeUynNbUmvo?e=ZyNp68)**

---

## 📌 Visão Geral do Projeto

A base **Aurora Siger** encontra-se em fase inicial de instalação no solo marciano. Com apenas uma área de pouso disponível e cinco módulos em órbita aguardando autorização para descida, o **MGPEB** atua no controle crítico do fluxo operacional, garantindo a integridade dos módulos e a sobrevivência da colônia.

---

## 🛰️ Módulos em Órbita

| Módulo | Chegada | Massa | Combustível | Criticidade | Prioridade | Função Primária |
|---|:---:|:---:|:---:|:---:|:---:|---|
| **Energia** | 08:00 | 9 t | 55% | Alta | Alta | Fornecimento elétrico para a infraestrutura |
| **Habitação** | 08:30 | 12 t | 70% | Alta | Alta | Abrigo da tripulação em condições controladas |
| **Comunicações** | 09:00 | 4 t | 25% | Alta | Média | Enlace de contato com a Terra |
| **Estufa** | 09:30 | 8 t | 40% | Média | Baixa | Produção alimentar local |
| **Suporte Médico** | 10:00 | 5 t | 35% | Alta | Alta | Cuidados de saúde da tripulação |

---

## ⚙️ Estruturas de Dados Utilizadas

- **Fila de Espera Orbital (`Queue` - FIFO):** Organiza a fila de espera (`fila_pouso`), assegurando processamento estritamente sequencial.
- **Lista Linear (`List`):** Registra a base permanente de dados dos módulos já estabilizados em solo (`modulos_pousados`).
- **Pilha de Alertas (`Stack` - LIFO):** Rastreia incidentes e falhas operacionais (`pilha_alertas`), priorizando na interface a notificação mais recente.

---

## 🧠 Regras Lógicas de Decisão

O algoritmo avalia quatro variáveis booleanas de telemetria: `Combustivel_OK` (> 30%), `Sensores_OK`, `Clima_Favoravel` e `Pista_Livre`.

1. **Pouso Padrão (Porta AND):**
   ```text
   Pouso_Padrao = Combustivel_OK AND Sensores_OK AND Clima_Favoravel AND Pista_Livre
## 📂 Código Fonte

- O algoritmo completo e implementado está disponível no arquivo: [`mgpeb.py`](./mgpeb.py)
