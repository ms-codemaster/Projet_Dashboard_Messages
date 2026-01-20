# Portfolio DevOps – Dashboard Node.js
Ce projet présente une mise en œuvre complète d'une chaîne DevOps autour d’une application Node.js offrant un petit dashboard. 
L’objectif est de démontrer la capacité à construire, analyser, containeriser, déployer et automatiser un service applicatif moderne.
---
## Architecture
**Application** : Node.js (Frontend + Backend)
**Containerisation** : Docker
**Orchestration** : Kubernetes
**CI/CD** : Jenkins Pipeline
**Analyse de code** : SonarQube
**Registry** : Docker Registry (Docker Hub ou GitLab Registry)
**Versionning** : GitLab
---
## Stack Technique
| Composant | Outil |
|---|---|
| Backend & Frontend | Node.js |
| Containers | Docker |
| Orchestration | Kubernetes |
| CI/CD | Jenkins |
| Analyse statique | SonarQube |
| SCM | GitLab |
| Registry | Docker Registry |
---
## Containerisation (Docker)
Chaque service possède son propre `Dockerfile` :
/frontend/Dockerfile
/backend/Dockerfile

Les images sont construites par Jenkins puis poussées vers le registry :
docker build -t registry/projet/frontend:latest ./frontend
docker build -t registry/projet/backend:latest ./backend
docker push registry/projet/frontend:latest
docker push registry/projet/backend:latest

## Déploiement Kubernetes

Les déploiements sont décrits via des manifests Kubernetes 
CI/CD avec Jenkins

Pipeline automatisé comprenant les étapes :
a. Checkout
b. Analyse SonarQube
c. Tests
d. Build Docker
e. Push Docker
f. Déploiement Kubernetes
g. Notifications

Qualité & Sécurité

SonarQube a été intégré pour analyser :
	•	Bugs
	•	Vulnerabilités
	•	Code Smells
	•	Maintainability
	•	(Optionnel) Couverture de tests

⸻

Objectifs du Projet

Mettre en place une chaîne DevOps complète
Montrer l’automatisation CI/CD
Déployer sur un cluster Kubernetes
Intégrer l’analyse de code et l’assurance qualité
