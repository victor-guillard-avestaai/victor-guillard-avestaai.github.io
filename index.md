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
    A[Incoming HTTP Request] --> B{Message reçu}
    B -->|Starts with 'REQ'| C[(Ticket<br> Workflow)]
    B -->|Else| D[Évaluer la complexité<br>(LLM classify)]
    
    C --> C1[Publier log 'ticket'<br> sur Pub/Sub]
    C1 --> C2[Renvoyer 'Requête reçue !'<br>à l'utilisateur]
    C2 --> O[Fin]
    
    D --> E{Complexité ?}
    E -->|0<br>(Non pertinent)| F[Répondre<br>"Je n'ai pas compris..."]
    E -->|1<br>(Simple)| G[Répondre<br>Answer direct]
    E -->|2<br>(Nécessite recherche)| H[Extraire mots-clés<br>depuis la réponse LLM]
    
    H --> I{Exécuter<br>perform_ensemble_search}
    I --> K[Requête async<br>1) Similarity Search<br>2) Keyword Search]
    K --> L[Combiner résultats<br>avec fused_score<br>et tri RRF]
    L --> M[Générer prompt final<br> + LLM]
    M --> N[Réponse finale<br>renvoyée à l'utilisateur]
    N --> Q{Résultats trouvés ?}
    Q -->|Non| R[Stocker<br>question inanswered<br>(si unique)]
    Q -->|Oui| S[Passer à log]
    R --> S
    
    F --> T[Publier log 'general']
    G --> T
    S --> T[Publier log 'general']
    T --> O[Fin]
```


[View Code/Details](#) <!-- Remplace par un lien réel (GitHub/Colab) si disponible -->

---
