# infra-k8s-terraform

📦 Infrastructure GitOps pour mon site perso [woulf.fr](https://woulf.fr)

Ce dépôt contient toute la configuration **Kubernetes** nécessaire au déploiement de mon portfolio, avec une approche **GitOps**.

> Le code source du site est dans [`Wooulf/forkfolio`](https://github.com/Wooulf/forkfolio).

---

## 🚀 Stack actuelle

- 🐳 **Cluster** : MicroK8s (sur VPS Ubuntu 22.04)
- ☁️ **Infra-as-Code** : YAML (Kubernetes natif)
- 🔁 **Déploiement GitOps** : via GitHub Actions
- 🔐 **HTTPS** : cert-manager + Let’s Encrypt
- 🌐 **Nom de domaine** : `woulf.fr`

---

## ⚙️ Fonctionnement

À chaque commit dans le dossier `k8s/`, une pipeline CI/CD applique automatiquement les configurations sur mon cluster Kubernetes.

```yaml
on:
  push:
    paths:
      - 'k8s/**'
```

🔧 Cela permet de synchroniser mon cluster avec l’état décrit dans le dépôt — Git devient la **source de vérité**.

---

## 🗂️ Structure du dépôt

```bash
infra-k8s-terraform/
├── k8s/
│   ├── clusterissuer.yaml
│   ├── ingress-controller-service.yaml
│   ├── ingress-nodeport.yaml
│   ├── portfolio-clusterip.yaml
│   └── portfolio-deployment.yaml
├── .github/
│   └── workflows/
│       └── deploy.yml
└── README.md
```

---

## 📈 À venir

- [ ] Ajout d’un monitoring Prometheus / Grafana
- [ ] Stack de logs centralisés (EFK ou Loki)
- [ ] Migration vers ArgoCD ou Flux (GitOps full power)

---

## 📬 Contact

Je suis encore en formation et je cherche à progresser dans un environnement encadré.  
Si tu bosses sur de l’infra DevOps et que tu cherches un profil motivé → **on discute !**

🔗 [woulf.fr](https://woulf.fr) | [LinkedIn](https://linkedin.com/in/corentin-boucard) | [GitHub](https://github.com/Wooulf)
