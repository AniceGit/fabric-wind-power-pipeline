# Wind Power Analytics - Microsoft Fabric Pipeline

Pipeline de données end-to-end sur Microsoft Fabric pour l'analyse de la production d'énergie éolienne.

## 🎯 Objectifs

Ce projet implémente une architecture Medallion (Bronze/Silver/Gold) complète avec :
- Ingestion automatisée de données depuis GitHub
- Transformations PySpark et SQL
- Modèle dimensionnel (star schema)
- Orchestration avec Data Pipeline
- Visualisation dans Power BI

## 🏗️ Architecture
GitHub (CSV) → Bronze → Silver → Gold → Semantic Model → Power BI

## 📊 Technologies utilisées

- Microsoft Fabric
- Delta Lake
- PySpark
- SQL
- Power BI
- DAX

## 🏅 Le modèle Medaillon
```text
┌─────────────────┐       ┌─────────────────┐       ┌─────────────────┐
│     BRONZE      │       │     SILVER      │       │      GOLD       │
│  (Raw Data)     │   →   │  (Cleaned Data) │   →   │  (Business Data)│
│                 │       │                 │       │                 │
│ • Données brutes│       │ • Nettoyées     │       │ • Modèle        │
│ • Format origine│       │ • Validées      │       │   dimensionnel  │
│ • Pas de transfo│       │ • Enrichies     │       │ • Optimisé BI   │
└─────────────────┘       └─────────────────┘       └─────────────────┘
``` 
- Bronze 🥉 : Données telles qu'ingérées (exactement comme dans la source)
- Silver 🥈 : Données nettoyées, standardisées, enrichies
- Gold 🥇 : Données organisées pour l'analyse métier (modèle dimensionnel)

## Convention de nommage
```text
Type de ressource	| Préfixe	| Exemple
Lakehouse	        |    LH_    |LH_Wind_Power_Bronze
Notebook	        |    NB_    |NB_Get_Daily_Data 
Pipeline	        |    PL_    |PL_Orchestration 
Semantic Model	     |    SM_    |SM_Wind_Turbine_Power 
Report	             |    RPT_   |RPT_Wind_Turbine_Power_Analysis 
```


## Flux de données
```text
Source (GitHub CSV)
        ↓
[Ingestion]
        ↓
LH_Wind_Power_Bronze (données brutes)
        ↓
[Transformation & Enrichissement]
        ↓
LH_Wind_Power_Silver (données nettoyées)
        ↓
[Modélisation dimensionnelle]
        ↓
LH_Wind_Power_Gold (star schema)
        ↓
Semantic Model
        ↓
Power BI Reports
```


## 🚀 Statut

🔨 **En cours de développement**

---

*Projet réalisé dans le cadre d'une formation sur Microsoft Fabric*
*Date de début : 16 novembre 2025*
