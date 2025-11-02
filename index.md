## Sélection de projets de Data Science, d'IA et de Développement Web

---

### 1. Stage de recherche : Estimation d’incertitude dans les réseaux de neurones
Les réseaux de neurones profonds sont très performants, mais leur manque d'explicabilité les rend délicats à utiliser, notamment en milieux sensibles comme le médical. Dans ce projet, j’ai étudié et ré-implémenté des approches avancées d’estimation de l’incertitude (Monte Carlo Dropout, ConfidNet) et proposé de nouvelles méthodes pour améliorer l’état de l’art.

[![](https://img.shields.io/badge/Python-white?logo=Python)](#)
[![](https://img.shields.io/badge/Tensorflow-white?logo=Tensorflow)](#)

<img src="images/ConfidNet.png" alt="Exemple de méthodes de mesure de l'incertitude : ConfidNet">

<a href="/pdf/Rapport_de_Stage.pdf" target="_blank" rel="noopener noreferrer">
  Voir l'Abstract
</a>

---

### 2. Segmentation d’une base de données client (projet marketing)
Sur une base de 900 000 clientes, j’ai mis en place un pipeline de segmentation afin de créer des profils clients interprétables. L’objectif était de mieux comprendre les comportements d’achat et de guider des actions marketing ciblées.

[![](https://img.shields.io/badge/Python-white?logo=Python)](#)
[![](https://img.shields.io/badge/Scikit_Learn-white?logo=Scikit-Learn)](#)

<img src="images/SEGBO_Heatmap.png" alt="Heatmap de la performance de l'algorithme d'affectation">

<a href="/pdf/Projet_SEGBO.pdf" target="_blank" rel="noopener noreferrer">
  Voir le Rapport
</a>

<a href="https://colab.research.google.com/drive/1B94dVjn-zX4Q8ZtYT8QObMjvjULUpKbD" target="_blank" rel="noopener noreferrer">
  Voir le Code sur Google Colab
</a>

---

### 3. Prédiction de la note d’un vin (classification multiclasse)
À partir des données de 130 000 vins, j’ai conçu un modèle pour prédire leur note decernée par des critiques (1 à 5 étoiles). Après un nettoyage approfondi des variables (prix, région, cépage, descriptifs de dégustation), j’ai implémenté une régression logistique puis un XGBoost, obtenant d’excellents résultats.

[![](https://img.shields.io/badge/Python-white?logo=Python)](#)
[![](https://img.shields.io/badge/Scikit_Learn-white?logo=Scikit-Learn)](#)
[![](https://img.shields.io/badge/XGBoost-white?logo=Xing)](#)

<img src="images/SE_Countries.png" alt="Analyse exploratoire de la relation entre notes des vins et pays producteurs">

<a href="/pdf/Projet_SDE_Victor_GUILLARD.pdf" target="_blank" rel="noopener noreferrer">
  Voir le Rapport
</a>

<a href="https://colab.research.google.com/drive/1uIB-5KZ02RgDeXS8ZM-ytIbKiyp1N5HZ#scrollTo=iNhjekzgFfok" target="_blank" rel="noopener noreferrer">
  Voir le Code sur Google Colab
</a>

---

### 4. Reinforcement Learning : IA pour jouer au Puissance 4
J’ai développé un agent de Reinforcement Learning (Q-learning) capable de jouer au Puissance 4. Cela m’a permis de comprendre plus finement la dynamique de l’apprentissage par récompenses et la gestion des états de jeu.

[![](https://img.shields.io/badge/Python-white?logo=Python)](#)
[![](https://img.shields.io/badge/RL-white?logo=Python)](#)

<img src="images/GraphRL.png" alt="Evolution du winrate de l'algorithme de Q-Learning">

<a href="https://colab.research.google.com/drive/1HZegRx9fYePS_Wf6cg2Psetrcyz1bhKy" target="_blank" rel="noopener noreferrer">
  Voir le Code sur Google Colab
</a>

---

### 5. Chatbot d’assistance aux hôtes d'accueil (RAG)
J’ai développé un système de chatbots pour assister les hôtes d’accueil et leurs managers, en utilisant un algorithme Retrieval-Augmented Generation (RAG). Le premier chatbot répond aux questions courantes des hôtes d'accueil en s’appuyant sur la base de connaissances interne, tandis que le second chatbot permet aux managers de mettre à jour cette base, en collectant et résolvant les questions restées sans réponse.

[![](https://img.shields.io/badge/Python-white?logo=Python)](#)
[![](https://img.shields.io/badge/GCP-white?logo=GoogleCloud)](#)
[![](https://img.shields.io/badge/VertexAI-white?logo=Google)](#)
[![](https://img.shields.io/badge/RAG-white)](#)

<a href="images/PipelineRAG.png" target="_blank" rel="noopener noreferrer">
  Voir un diagramme explicatif de la pipeline RAG
</a>

---

### 6. AvestaAI — Application Web en Go (Echo, HTMX, Tailwind, Docker)

J’ai développé AvestaAI, une application web SaaS destinée aux praticiens de santé indépendants. La plateforme leur permet de créer en quelques minutes un site web professionnel multilingue avec un assistant IA intégré capable de répondre automatiquement aux questions des patients.

L’application repose sur une architecture modulaire en Go (Echo) avec rendu serveur via HTMX et Templ, une interface moderne conçue avec Tailwind CSS et DaisyUI, et un hébergement scalable sur Google Cloud Run.
Chaque utilisateur peut modifier son site (services, galerie, équipe, documentation) grâce à une interface d’édition en ligne fluide et sécurisée.

La gestion des abonnements est assurée via Stripe (paiements récurrents, changements de plan, portail client), et la CI/CD est automatisée avec GitHub Actions pour les tests, builds Docker et déploiements continus.
Chaque cabinet dispose d’un sous-domaine dédié géré par un multiplexeur HTTP sur mesure ce qui garantit un hébergement isolé et entièrement automatisé.

Vous pouvez tester cette web app en cliquant sur le lien ci-dessous.

[![](https://img.shields.io/badge/-Go-white?logo=go)](#)
[![](https://img.shields.io/badge/-Echo-white?logo=go)](#)
[![](https://img.shields.io/badge/-Tailwind_CSS-white?logo=tailwindcss)](#)
[![](https://img.shields.io/badge/-Docker-white?logo=docker)](#)
[![](https://img.shields.io/badge/-PostgreSQL-white?logo=postgresql)](#)

<a href="https://avestaai.com" target="_blank" rel="noopener noreferrer">
  Lien vers l'application web
</a>
