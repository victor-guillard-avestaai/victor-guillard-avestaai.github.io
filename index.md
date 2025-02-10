## Projets de Data Science et d'IA

---

### 1. Stage de recherche : Estimation d’incertitude dans les réseaux de neurones
Les réseaux de neurones profonds sont performants, mais délicats à employer en milieux sensibles. Dans ce projet, j’ai étudié et ré-implémenté des approches avancées d’estimation de l’incertitude (Monte Carlo Dropout, ConfidNet) et proposé de nouvelles méthodes pour améliorer l’état de l’art.

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
À partir de 130 000 vins, j’ai conçu un modèle pour prédire leur note (1 à 5 étoiles). Après un nettoyage approfondi des variables (prix, région, cépage, descriptifs de dégustation), j’ai implémenté une régression logistique puis un XGBoost, obtenant d’excellents résultats.

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

### 5. Chatbot d'assistance aux hôtes d'accueil : LLM & RAG
Au cours de ma création d’entreprise, j’ai conçu diverses applications IA (par ex. intégration de LLM, pipeline DataOps, etc.). Je détaillerai bientôt un cas client complet, du concept initial à la mise en production.

[![](https://img.shields.io/badge/GoLang-white?logo=Go)](#)
[![](https://img.shields.io/badge/Cloud_Computing-white?logo=Google-Cloud)](#)
[![](https://img.shields.io/badge/DevOps-white?logo=Docker)](#)

[Coming soon](#)

---

### 6. Système de chatbots d’assistance (RAG)
J’ai développé un système de chatbots pour assister les hôtes d’accueil et leurs managers, en utilisant un algorithme Retrieval-Augmented Generation (RAG). Le premier chatbot répond aux questions courantes en s’appuyant sur la base de connaissances interne, tandis que le second permet aux managers de mettre à jour cette base, en collectant et résolvant les questions restées sans réponse.

[![](https://img.shields.io/badge/Python-white?logo=Python)](#)
[![](https://img.shields.io/badge/GCP-white?logo=GoogleCloud)](#)
[![](https://img.shields.io/badge/VertexAI-white?logo=Google)](#)
[![](https://img.shields.io/badge/RAG-white)](#)

```mermaid
flowchart TB

    %% Début du flux
    A[Message entrant<br>(handle_message)] --> B{Message<br>Commence par 'REQ' ?}

    %% Bloc "REQ"
    B -->|Oui| C[Ticket Workflow<br>(Ex. renvoyer 'Requête reçue')]
    C --> D[Fin]

    %% Si ce n'est pas un message 'REQ'
    B -->|Non| E[Évaluation<br>de la complexité<br>via LLM classify]

    %% Évaluation de la complexité
    E --> F{Complexité<br>= 0,1 ou 2 ?}

    %% Catégorie 0
    F -->|0 (Non pertinent)| G[Répondre<br>"Je n'ai pas compris..."]
    G --> D[Fin]

    %% Catégorie 1
    F -->|1 (Simple)| H[Réponse directe<br>(fourni par l'LLM)]
    H --> D[Fin]

    %% Catégorie 2
    F -->|2 (Recherche requise)| I[Extraire mots-clés]

    %% RAG Pipeline
    I --> J[Calcul Embeddings<br>(user_message)]
    I --> K[Extraction par mots-clés]

    %% Lancement en parallèle (Async)
    J --> L[Recherche par<br>Similarité (embedding)]
    K --> M[Recherche par<br>Mots-clés]
    L --> N[Combinaison<br>des résultats]
    M --> N

    %% Fusion & RRF
    N --> O[Fusion & RRF<br>(fused_score)]
    O --> P{Documents<br>pertinents ?}

    %% Si pas de résultats => question sans réponse
    P -->|Non| Q[Stocker la<br>question en base<br>(unanswered_questions)]
    P -->|Oui| R[Générer Prompt final<br>avec extraits pertinents]

    R --> S[Modèle LLM<br>=> Génération de la réponse]
    S --> T[Répondre à l'utilisateur]
    Q --> T
    T --> D[Fin]
```


[View Code/Details](#) <!-- Remplace par un lien réel (GitHub/Colab) si disponible -->

---
