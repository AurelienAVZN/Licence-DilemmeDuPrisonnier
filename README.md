<div align="center">

# 🎭 Dilemme Itéré des Prisonniers
### Simulation de stratégies et tournois autour d'un classique de la théorie des jeux

[![Java](https://img.shields.io/badge/Java-8+-orange)]()
[![Swing](https://img.shields.io/badge/Interface-Swing-blue)]()
[![JUnit](https://img.shields.io/badge/Tests-JUnit-green)]()
[![Pattern](https://img.shields.io/badge/Architecture-MVC%20%2F%20Facade-purple)]()

Projet universitaire permettant de simuler des **tournois de stratégies du Dilemme Itéré des Prisonniers** et d'étudier l'émergence de comportements coopératifs ou opportunistes au fil des confrontations.

</div>

---

# 📖 À propos

Le **Dilemme du Prisonnier** est l'un des problèmes les plus célèbres de la théorie des jeux.

Deux joueurs doivent simultanément choisir entre :

- 🤝 **Coopérer**
- 🗡️ **Trahir**

Chaque décision influence le gain des deux participants.

Lorsque cette interaction est répétée un grand nombre de fois, le problème devient particulièrement intéressant : les joueurs peuvent adapter leur comportement en fonction des actions passées de leurs adversaires.

Ce projet propose une implémentation complète permettant :

- de modéliser différentes stratégies
- d'organiser des confrontations entre elles 
- d'exécuter des tournois complets
- d'analyser les résultats obtenus 
- de comparer les performances des comportements coopératifs et agressifs

---

# ✨ Fonctionnalités

## 🎮 Simulation du Dilemme Itéré

- Gestion automatique des confrontations
- Nombre de tours paramétrable
- Historique des actions
- Calcul des scores
- Classement final des participants

## 🧠 Bibliothèque de stratégies

Le projet intègre plusieurs stratégies classiques :

| Stratégie | Description |
|------------|-------------|
| 😇 Gentille | Coopère toujours |
| 😈 Méchante | Trahit toujours |
| 🤨 Méfiante | Commence par trahir |
| 🔄 Donnant-Donnant | Reproduit le dernier coup adverse |
| 💢 Rancunière | Coopère jusqu'à la première trahison |
| 🎲 Pourcentage Gentille | Coopère avec une certaine probabilité |
| 🎲 Pourcentage Méchante | Trahit avec une certaine probabilité |
| 🛡️ Donnant-Donnant Dur | Variante plus punitive du Tit-for-Tat |

Le système a été conçu pour permettre l'ajout de nouvelles stratégies facilement.

---

## 🏆 Gestion de tournois

- Toutes les stratégies peuvent s'affronter
- Génération automatique des confrontations
- Classement général
- Statistiques de performance
- Résumés textuels et HTML

---

## 🖥️ Interface graphique

Application Java Swing permettant :

- la configuration d'un tournoi
- la sélection des stratégies
- le paramétrage du nombre de tours
- la consultation des résultats
- la visualisation des confrontations

---

# 🏗️ Architecture

Le projet suit une séparation claire entre :

```text
src/
└── fr/uga/miage/pc/dilemme
    ├── back/
    │   ├── ApiDilemme
    │   ├── Tournoi
    │   ├── Confrontation
    │   └── strategie/
    │
    ├── front/
    │   ├── JDilemme
    │   ├── JParamTournoi
    │   └── composants UI
    │
    ├── System/
    │   ├── Logs
    │   ├── Helpers
    │   └── Utilitaires
    │
    └── Main.java
```

---

# 🎯 Principes de conception

## Facade

La classe :

```java
ApiDilemme
```

sert de point d'entrée unique entre l'interface graphique et le moteur métier.

Cela permet :

- d'isoler la logique métier ;
- de simplifier les appels ;
- de réduire le couplage entre les couches.

---

## MVC

L'application suit globalement une architecture inspirée du modèle :

```text
Model
 ├─ Tournoi
 ├─ Confrontation
 └─ Stratégies

View
 ├─ JDilemme
 └─ JParamTournoi

Controller
 └─ API + événements Swing
```

---

## Observer

Le projet contient également des interfaces :

```java
IObservable
IObserver
```

permettant la mise à jour automatique de certaines vues.

---

# ⚙️ Fonctionnement d'un tournoi

```text
Création des stratégies
          │
          ▼
Création du tournoi
          │
          ▼
Génération des confrontations
          │
          ▼
Simulation des tours
          │
          ▼
Calcul des scores
          │
          ▼
Classement final
```

---

# 🧪 Tests

Le projet dispose d'une suite de tests unitaires couvrant :

- les stratégies ;
- les confrontations ;
- les tournois ;
- les utilitaires ;
- l'API métier.

Arborescence :

```text
test/
├── back/
├── back/strategie/
└── front/
```

---

# 🚀 Lancer l'application

## Prérequis

- Java 8 ou supérieur
- Eclipse (recommandé)

---

## Depuis Eclipse

1. Importer le projet.
2. Vérifier le JDK configuré.
3. Exécuter :

```java
fr.uga.miage.pc.dilemme.Main
```

---

## Depuis la ligne de commande

Compilation :

```bash
javac src/fr/uga/miage/pc/dilemme/Main.java
```

Exécution :

```bash
java fr.uga.miage.pc.dilemme.Main
```

---

# 📚 Exemple de scénario

Imaginons un tournoi entre :

- Gentille
- Méchante
- Donnant-Donnant
- Rancunière

Sur 100 tours :

```text
Gentille      🤝🤝🤝🤝🤝
Méchante      🗡️🗡️🗡️🗡️🗡️
DonnantDonnant 🤝🤝🗡️🗡️🤝
Rancunière     🤝🤝🤝🗡️🗡️
```

Le tournoi permet alors d'observer :

- quelles stratégies dominent
- lesquelles favorisent la coopération
- lesquelles exploitent les autres joueurs
- l'impact du comportement initial

---

# 🎓 Objectifs pédagogiques

Ce projet a été réalisé dans le cadre d'un enseignement autour :

- de la théorie des jeux
- de l'UML
- de la programmation orientée objet
- des patrons de conception
- des interfaces graphiques Java
- des tests unitaires

---

# 🔮 Améliorations possibles

- Export CSV des résultats
- Graphiques statistiques
- Génération de rapports PDF
- Nouvelles stratégies évolutives
- IA adaptative
- Tournois multi-générations
- Interface graphique modernisée (JavaFX)

---

# 👥 Auteurs

**Aurélien Avanzino**  
**Stéphanie Gourdon**

Projet universitaire réalisé dans le cadre de l'étude du **Dilemme Itéré des Prisonniers**.

---

<div align="center">

### 🤝 Coopérer ou trahir ?
### À vous de découvrir quelle stratégie survivra au tournoi.

</div>