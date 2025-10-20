# Portfolio
Bienvenue sur mon portfolio.
Ce projet regroupe mes travaux, mes compétences et mes expériences dans le domaine du devops (développement web, déploiement IaC, CI/CD, cybersécurité).

## Technologies utilisées
HTML, CSS
Docker, Git, GitHub Actions et GitHub Packages (Partie CI)
Kubernetes, Kustomize, Argo CD (Partie CD)
Méthodologie GitOps
RollingUpdate classique

## Déploiement multi-environnement
Un environnement de développement (develop). L'environnement de développement me permet d'ajuster le code et d'en obtenir un visuel rapide. Une chaîne CI/CD teste le code HTML, génère l'image de l'application et renseigne le tag de la nouvelle image dans le déploiement k8s. Github envoit une requête POST sur le webhook d'Argo CD, ce qui déclenche le re-déploiement sur develop.

## Liens utiles
- 🌐 [Adresse du portfolio en ligne](https://lumitek.fr)
- ☁️ [Mon Projet Cloud](https://cloud.lumitek.fr/s/tFfkts7BwxtGiBm)
- 💼 [Mon profil LinkedIn](https://www.linkedin.com/in/luclouisdelorme/)  
- 🐙 [Mon GitHub](https://github.com/Luc426)

## Contacter

**Email :** [luclouis.delorme@lumitek.fr]

## Architecture

```bash
webcv-project/
└── webcv
    ├── build
    │   ├── Dockerfile
	  │   └── www
    ├── k8s
    │   ├── base
    │   │   ├── deployment.yaml
    │   │   ├── kustomization.yaml
    │   │   ├── nginx
    │   │   │   ├── default.conf
    │   │   │   └── nginx.conf
    │   │   └── service.yaml
    │   └── overlays
    │       ├── dev
    │       │   ├── ingress.yaml
    │       │   └── kustomization.yaml
    │       └── prod
    │           ├── ingress.yaml
    │           └── kustomization.yaml
    ├── README.md
    └── webcv-application.yaml
```