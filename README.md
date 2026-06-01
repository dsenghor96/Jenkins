# Portfolio personnel

Portfolio web personnel mettant en avant des projets Cloud, DevOps, reseaux, systemes et developpement web.

![Portfolio Banner](https://images.unsplash.com/photo-1451187580459-43490279c0fa?auto=format&fit=crop&q=80&w=1400)

## Apercu

Ce projet presente mon profil, mes competences techniques, mes projets et un espace de contact. Il inclut egalement une interface d'administration privee pour gerer certains contenus du portfolio.

## Fonctionnalites principales

- Interface publique responsive
- Pages projets, competences et contact
- Telechargement du CV
- Dashboard d'administration prive
- API backend pour la gestion des donnees
- Conteneurisation avec Docker
- Pipeline CI/CD avec Jenkins
- Analyse qualite avec SonarQube

## Stack technique

- React
- Vite
- Node.js
- Express
- MongoDB
- Docker / Docker Compose
- Jenkins
- SonarQube

## Lancement local

```bash
git clone https://github.com/dsenghor96/Jenkins.git
cd Jenkins
docker compose up -d --build
```

Application:

```text
http://localhost:5173
```

SonarQube, si active:

```text
http://localhost:9000
```

## Structure simplifiee

```text
portfolio_perso/
|-- api/              # Backend Express
|-- ux_react/         # Frontend React
|-- docker-compose.yml
`-- Jenkinsfile
```

## Notes

Les variables d'environnement, identifiants, tokens et configurations sensibles ne sont pas documentes publiquement dans ce README. Ils doivent etre geres via des fichiers `.env` locaux ou via les credentials Jenkins.

## Contact

Dieynaba Senghor  
Cloud & DevOps

- LinkedIn: [linkedin.com/in/dieynaba-senghor](https://linkedin.com/in/dieynaba-senghor)
- GitHub: [github.com/dieynaba-senghor](https://github.com/dieynaba-senghor)
