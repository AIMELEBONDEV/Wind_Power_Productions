# Projet : Analyse et Monitoring de la Production Éolienne avec Microsoft Fabric  

## Introduction  

Ce projet a été réalisé pour montrer comment utiliser **Microsoft Fabric** de bout en bout afin de gérer, transformer et analyser des données industrielles en temps quasi réel.  

Le contexte : un pack de **trois turbines éoliennes (A, B et C)** dont la production est mesurée toutes les dix minutes via des capteurs. Nous disposons également d’un historique au format CSV.  

Je me suis posé plusieurs questions au départ :  
- Comment organiser ces données de manière fiable et durable ?  
- Comment automatiser le traitement pour éviter toute intervention manuelle ?  
- Comment transformer ces données en indicateurs compréhensibles pour les équipes techniques et décisionnaires ?  
- Comment mettre en place des rapports utiles, clairs et exploitables au quotidien ?  

---

## Architecture du projet  

Le projet repose sur la logique **Bronze – Silver – Gold** dans Microsoft Fabric :  

- **Bronze Lakehouse** : données brutes issues des capteurs et fichiers CSV.  
- **Silver Lakehouse** : données nettoyées et enrichies.  
- **Gold Lakehouse** : données structurées et prêtes à l’analyse, organisées en schéma en étoile.  

Deux approches ont été utilisées pour transformer les données :  
- **Dataflow** pour une approche sans code, rapide à mettre en place.  
- **Notebooks (SQL et Python)** pour les transformations plus avancées et l’automatisation.  

Une fois les données consolidées, elles alimentent un **modèle sémantique** qui permet de construire des rapports Power BI.  

<img width="1693" height="546" alt="image" src="https://github.com/user-attachments/assets/8b7ac9e5-ea7a-41c5-847c-c75e2ce4c253" />

---

## Automatisation  

L’ensemble est orchestré avec les **Pipelines Fabric** qui gèrent :  
- L’ingestion quotidienne des données  
- Le nettoyage et l’enrichissement  
- La mise à jour des tables Gold  
- Le rafraîchissement automatique des rapports Power BI  

Ainsi, les utilisateurs métier disposent toujours de données fraîches et fiables.  

---

## Rapports et analyses  

Le projet comprend deux pages principales dans Power BI :  

### Page 1 – Production journalière par turbine  
Question principale : *Quelle est la performance globale des turbines chaque jour ?*  

- Visualisation du total de l’électricité produite par turbine (A, B, C).  
- Graphique de l’évolution journalière sur un mois.  
- Exemple : du 1er au 14 juin 2024, la turbine A a produit 4,66 MWh, la turbine B 4,52 MWh et la turbine C également 4,52 MWh.  

Cette page permet d’identifier rapidement les baisses de performance et de déclencher des alertes. 
<img width="1582" height="755" alt="image" src="https://github.com/user-attachments/assets/ef2d66b3-2d1b-4726-a51c-75882438af45" />


---

### Page 2 – Production horaire par turbine  
Question principale : *Comment la production varie-t-elle au fil de la journée ?*  

- Graphique montrant l’évolution de la production heure par heure.  
- Les trois turbines présentent des fluctuations importantes, sans tendance claire.  
- Cette analyse aide à repérer les moments de faiblesse et à envisager des actions correctives.  
<img width="1545" height="747" alt="image" src="https://github.com/user-attachments/assets/6eafdb20-d85d-4a58-b83f-46f191668993" />

---

## Résultats et apprentissages  

Ce projet m’a permis de :  
- Déployer une architecture complète dans Microsoft Fabric (Bronze, Silver, Gold).  
- Combiner des approches sans code (Dataflows) et du code (SQL, Python).  
- Automatiser tout le processus avec des Pipelines.  
- Créer un modèle sémantique et des rapports Power BI qui répondent à des questions précises.  

J’ai surtout appris à transformer des données brutes en **indicateurs exploitables** pour la prise de décision et la maintenance prédictive.  

---

## Prochaines étapes  

- Ajouter un moteur d’alertes en temps réel.  
- Intégrer des données météo pour analyser l’impact sur la production.  
- Tester un modèle de prévision basé sur l’historique.  

---

## Auteur  

Projet réalisé par **Aimé Adjéguéde**.  
À travers ce projet, j’ai cherché à montrer une démarche complète : de l’ingestion des données brutes à la création de rapports clairs et actionnables pour le suivi des performances énergétiques.  
