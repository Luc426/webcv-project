# Portfolio
Bienvenue sur mon portfolio.
Ce projet regroupe mes travaux, mes compétences et mes expériences dans le domaine du devops (développement web, déploiement IaC, CI/CD, cybersécurité).

## Technologies utilisées
HTML, CSS, Docker, Git, GitHub Actions et GitHub Packages (Partie CI)  
Kubernetes, Kustomize, Argo CD (Partie CD).  
Méthodologie de déploiement GitOps : RollingUpdate multi-environnement.

## Déploiement multi-environnement
Un environnement de développement (develop) et un environnement de production (main). L'environnement de développement est configuré avec une chaîne de déploiement continu.

Celle-ci me permet d'automatiser, à chaque commit, les tests de qualité de code, le stockage et le déploiement la nouvelle image docker via Github Actions(CI) et Argo CD (CD).

Si les tests ont réussi, un job de la partie CI mets à jour le tag de la nouvelle image dans le manifeste k8s. GitHub envoie ensuite une requête POST sur le webhook d'Argo CD, ce qui déclenche la synchronisation et le re-deploiement sur Kubernetes.

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
