# 🌱 AquaLynk — Système d'arrosage intelligent basé sur l'IoT

Projet de fin d'études (Licence en informatique de gestion) : une API back-end qui pilote un système d'arrosage automatique à partir des données des capteurs, de la météo en temps réel et de recommandations générées par l'IA.

## 🎯 Problème résolu

L'arrosage manuel gaspille de l'eau et demande une présence constante. AquaLynk décide quand arroser en combinant l'humidité du sol, les prévisions de pluie et une analyse par IA, pour économiser l'eau sans négliger les plantes.

## ⚙️ Fonctionnalités

- Réception et stockage des données des capteurs (humidité du sol, état du système)
- Prévisions météo en temps réel (température, humidité, probabilité de pluie) via l'API Open-Meteo
- Recommandations d'arrosage générées par l'IA (Google Gemini)
- API REST consommée par l'application mobile Flutter et le dispositif IoT
- Interface d'administration Django pour gérer les données
- Déploiement en ligne sur Render

## 🛠️ Technologies utilisées

| Domaine | Technologies |
|---|---|
| Back-end | Python, Django, Django REST Framework |
| Intelligence artificielle | Google Gemini API |
| Météo | Open-Meteo API |
| Base de données | SQLite (développement), PostgreSQL via `dj-database-url` (production) |
| Mobile | Flutter |
| IoT | [ESP32 / Arduino], capteur d'humidité du sol, relais + pompe |
| Déploiement | Render (Gunicorn) |

## 🏗️ Architecture

```
Capteurs IoT ──> API Django (AquaLynk) <── Application mobile Flutter
                     │
                     ├──> Open-Meteo (météo)
                     ├──> Gemini (recommandations IA)
                     └──> Base de données
```

## 📁 Structure du projet

```
aqualynk/      Configuration du projet Django (settings, urls)
irrigation/    Application principale : modèles, API, services météo et IA
manage.py      Point d'entrée Django
render.yaml    Configuration du déploiement sur Render
```

## 🚀 Installation en local

```bash
git clone https://github.com/AISSATA-CISSE/systeme-arrosage-intelligent-iot.git
cd systeme-arrosage-intelligent-iot
python -m venv venv
venv\Scripts\activate        # Windows  (source venv/bin/activate sur Mac/Linux)
pip install -r requirements.txt
```

Créer un fichier `.env` à la racine :

```
SECRET_KEY=votre_cle_secrete
GEMINI_API_KEY=votre_cle_gemini
DEBUG=True
```

Puis lancer le serveur :

```bash
python manage.py migrate
python manage.py runserver
```

## 📈 Améliorations possibles

- Gestion de plusieurs zones d'arrosage
- Notifications en cas d'anomalie (sol trop sec, panne de pompe)
- Tableau de bord web avec historique et graphiques

## 👩🏾‍💻 Auteure

**Aïssata Cissé** — Développeuse Web & Mobile Junior
[LinkedIn](https://www.linkedin.com/in/a%C3%AFssata-cisse-8aa1a3261)
