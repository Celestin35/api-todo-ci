# API TODO – CI/CD Multi-Environnements

API TODO développée en Node.js avec Express, intégrant un pipeline CI/CD complet
basé sur **GitHub Actions** et un déploiement automatique sur **Render**.

Le projet met en œuvre un workflow professionnel avec **staging** et **production**,
des tests obligatoires avant déploiement et un **versioning automatique**.

---

## 🚀 Environnements déployés

- **Staging (branche `develop`)**  
  👉 https://api-todo-celestin-staging.onrender.com

- **Production (branche `main`)**  
  👉 https://api-todo-celestin-prod.onrender.com

Chaque environnement expose son statut via l’endpoint `/health`
et indique son environnement (`staging` / `production`) sur la route `/`.

---

## ✨ Fonctionnalités

- CRUD complet pour les todos
- API REST simple et documentée
- Tests unitaires automatisés (Jest + Supertest)
- CI/CD automatisé avec GitHub Actions
- Déploiement automatique sur Render
- Versioning automatique via tags Git (`v1.0.x`)

---

## 📌 Endpoints API

| Méthode | Route | Description |
|---|---|---|
| GET | `/` | Informations générales de l’API |
| GET | `/todos` | Liste des todos |
| GET | `/todos/:id` | Récupérer un todo |
| POST | `/todos` | Créer un todo |
| PUT | `/todos/:id` | Modifier un todo |
| DELETE | `/todos/:id` | Supprimer un todo |
| GET | `/health` | Statut de l’API |

---

## 🧪 Exemples d’utilisation

### Récupérer les todos
```bash
curl https://api-todo-celestin-prod.onrender.com/todos
```

### Créer un todo
```bash
curl -X POST https://api-todo-celestin-prod.onrender.com/todos \
  -H "Content-Type: application/json" \
  -d '{"title":"Apprendre le CI/CD"}'
```

### Health check
```bash
curl https://api-todo-celestin-prod.onrender.com/health
```

---

## 💻 Développement local

```bash
# Installer les dépendances
npm install

# Lancer le serveur
npm start

# Lancer les tests
npm test
```

---

## 🔄 Pipeline CI/CD

Le pipeline CI/CD est entièrement automatisé :

### Branche `develop`

- Lancement des tests unitaires
- Déploiement automatique sur staging

### Branche `main`

- Lancement des tests unitaires
- Déploiement automatique sur production
- Création automatique d’un tag Git de version

Le pipeline empêche tout déploiement si les tests échouent.

---

## 🎓 Contexte pédagogique

Projet réalisé dans le cadre du cours CI/CD  
MyDigitalSchool – Janvier 2026

Auteur : Célestin Piaton

