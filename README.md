# 🧠 CyberScoopAI

> Une plateforme autonome de veille technologique en cybersécurité, propulsée par des agents IA intelligents, multi-thématiques et pilotés par Docker 🐳.

---

## 🚀 Objectif

**CyberScoopAI** récupère automatiquement des flux RSS liés à la cybersécurité, les classe par thématique (vulnérabilités, malwares, politique, etc.) et délègue à des agents IA le soin de résumer les articles les plus pertinents. Tu peux ensuite **lire, sélectionner et publier manuellement** ce que tu juges digne d’être partagé.

---

## 🧩 Architecture

```

RSS Feeds ➡️ RSS Fetcher 📰
⬇️
Classifier AI 🧠
⬇️
┌────────────┬────────────┬────────────┐
│ Agent Vuln │ Agent Malware │ Agent Policy │
└────────────┴────────────┴────────────┘
⬇️
Review Interface (Streamlit) ✅

```

---

## 📁 Structure du projet

```

CyberScoopAI/
├── docker-compose.yml
├── .env (à créer)
├── fetcher/              → Récupère les flux RSS
│   ├── Dockerfile
│   ├── fetch.py
│   └── rss-list.txt
├── classifier/           → Classe les articles par thème
│   ├── Dockerfile
│   └── classifier\_ai.py
├── agents/               → Agents IA spécialisés par thème
│   ├── vuln/
│   ├── malware/
│   └── policy/
├── review/               → Interface Streamlit de revue humaine
│   ├── Dockerfile
│   └── review\_app.py
├── data/                 → Articles bruts & classés (volume partagé)
└── output/               → Résumés générés par les agents

````

---

## ⚙️ Lancement (sur Mac ou Linux)

1. ✅ Installe Docker Desktop si ce n’est pas déjà fait : https://www.docker.com/products/docker-desktop

2. 🗝️ Crée un fichier `.env` à la racine avec ta clé OpenAI :
   ```bash
   OPENAI_API_KEY=sk-xxxxxxxxxxxxxxxx
````

3. 🚀 Lance l’ensemble de la stack :

   ```bash
   docker compose up --build
   ```

4. 🖥️ Accède à l’interface de revue :
   [http://localhost:8501](http://localhost:8501)

---

## 🧠 Technologies utilisées

* **Python 3.11**
* **feedparser** : pour lire les flux RSS
* **CrewAI / OpenAI API** : pour classer et résumer
* **Docker Compose** : pour orchestrer les containers
* **Streamlit** : pour l’interface de revue humaine
* **Hugo + Blowfish** *(optionnel)* : pour déployer les articles sélectionnés sur ton site

---

## ✍️ Prochaines étapes

* [ ] Ajouter des agents pour d’autres thématiques (CloudSec, Ransomware, etc.)
* [ ] Intégrer un système de scoring pour affiner la pertinence
* [ ] Déploiement automatique sur Hugo après validation manuelle

---

## 🎉 Crédits

Projet imaginé pour les passionnés de **veille cyber**, d’**automatisation** et de **génération IA**.
Made with ❤️, Python, Docker, et un peu de parano.

---

## 📜 Licence

Ce projet est open-source sous licence MIT. À utiliser, forker et améliorer sans modération !

```

---
