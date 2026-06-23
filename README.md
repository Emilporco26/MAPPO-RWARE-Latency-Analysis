# Impact of Network Latency on MAPPO in RWARE Environment

## 📌 Descrizione del Progetto / Project Description

Questo repository contiene il codice sorgente e la documentazione scientifica del progetto per il corso di Network Intelligence. L'obiettivo è dimostrare scientificamente il degrado critico delle prestazioni degli algoritmi di Multi-Agent Reinforcement Learning (MARL), nello specifico MAPPO, in presenza di latenza di rete all'interno dell'ambiente logistico cooperativo Robot Warehouse (RWARE).

*This repository contains the source code and research paper for the Network Intelligence project. It analyzes the critical performance degradation of MARL algorithms (MAPPO) under artificial network latency in the cooperative RWARE environment.*

## 📂 Documentazione / Documentation

L'analisi completa dei risultati, che dimostra l'inefficienza logistica, la "cecità" del Critico centralizzato e il collasso catastrofico dei gradienti causati dal lag, è disponibile qui:

* 📄 [Leggi il Paper Completo (Italiano)](Network_Intelligence_Project)
* 📄 [Read the Full Paper (English)](Network_Intelligence_Project_EN)

*(Nota: assicurati di caricare i due file PDF nella stessa cartella del repository)*

## 🚀 Riproducibilità / How to Run

Gli esperimenti sono stati condotti usando il framework EPyMARL per 40 milioni di step.

**Baseline (Ambiente ideale, No Lag)**

```bash
python src/main.py --config=mappo --env-config=gymma \
  with env_args.time_limit=500 \
  env_args.key="rware:rware-tiny-2ag-v2" \
  t_max=40000000 \
  use_wandb=True \
  wandb_project="Progetto-MAPPO-RWARE" \
  wandb_mode="online"
```

**Test con Latenza (Lag = 2 step)**

```bash
python src/main.py --config=mappo --env-config=gymma \
  with env_args.time_limit=500 \
  env_args.key="rware:rware-tiny-2ag-v2" \
  env_args.obs_lag=2 \
  t_max=40000000 \
  use_wandb=True \
  wandb_project="Progetto-MAPPO-RWARE" \
  wandb_mode="online"
```

## 📖 Citazioni e Riferimenti (References)

Questo progetto è stato costruito utilizzando framework e ambienti di ricerca open-source. Se fai riferimento a questo lavoro, per favore cita i paper originali di RWARE e MAPPO:

* **RWARE:** Christianos, F., et al. (2020). Shared Experience Actor-Critic for Multi-Agent Reinforcement Learning.
* **MAPPO:** Yu, C., et al. (2021). The Surprising Effectiveness of PPO in Cooperative Multi-Agent Games.
