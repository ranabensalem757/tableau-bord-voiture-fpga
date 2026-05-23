# 🚗 Tableau de Bord d'une Voiture — Projet FPGA (Vivado)

Conception et simulation d'un tableau de bord automobile sur FPGA à l'aide de l'environnement **Xilinx Vivado**, implémentant une unité arithmétique et logique (UAL) opérant sur des opérandes de **4 bits**.

> Projet universitaire 

---

## 🎯 Objectif

Réaliser une UAL (Unité Arithmétique et Logique) capable d'exécuter un ensemble d'opérations arithmétiques, logiques et séquentielles simulant le comportement des systèmes électroniques embarqués d'un véhicule.

---

## ⚙️ Modules Implémentés

| Module | Rôle dans le projet |
|--------|---------------------|
| **Multiplication (4 bits)** | Calcule la distance restante à parcourir |
| **Compteur Synchrone à Cycle Aléatoire** | Teste les capteurs de la voiture au démarrage |
| **Compteur Asynchrone Binaire** | Compte la vitesse de rotation du moteur |
| **Registre à Décalage (Gauche/Droite)** | Anime la lumière des clignotants |
| **Registre LFSR (Séquence Pseudo-Aléatoire)** | Génère un code de sécurité changeant pour le système de clé sans fil |
| **Codeur / Décodeur** | Traduit la position du levier de vitesse → affichage (P, R, N, D) |
| **Machine à États de Moore** | Gestion des essuie-glaces (Arrêt / Continu / Rapide) selon la pluie |
| **Afficheur 7 Segments** | Affiche le rapport de vitesse engagé (P, R, N, D) |

---

## 📁 Structure du Projet

```
.
├── projet electronique.srcs/        # Sources HDL (VHDL/Verilog) — fichiers principaux
│   ├── sources_1/                   # Fichiers de conception (modules)
│   ├── constrs_1/                   # Fichiers de contraintes (.xdc)
│   └── sim_1/                       # Fichiers de simulation (testbenches)
├── projet electronique 2 tt en 7 seg.srcs/  # Sources du module afficheur 7 segments
├── projet electronique.xpr          # Fichier projet Vivado (point d'entrée)
└── README.md
```

> Les dossiers `.cache`, `.hw`, `.runs`, `.sim`, `.ip_user_files` et `.Xil` sont **exclus du dépôt** car générés automatiquement par Vivado.

---

## 🛠️ Environnement & Outils

- **Outil de conception** : Xilinx Vivado (version 2020+)
- **Langage HDL** : VHDL / Verilog
- **Cible** : Simulation comportementale + synthèse FPGA
- **OS** : Windows 10/11

---

## 🚀 Comment ouvrir le projet

### Prérequis
- Xilinx Vivado installé ([téléchargement](https://www.xilinx.com/support/download.html))

### Étapes

1. Cloner le dépôt :
```bash
git clone https://github.com/VOTRE_USERNAME/tableau-bord-voiture.git
```

2. Ouvrir Vivado

3. Aller dans **File → Open Project**

4. Sélectionner le fichier `projet electronique.xpr`

5. Pour lancer la simulation : **Flow → Run Simulation → Run Behavioral Simulation**

---

## 🔬 Simulation

Chaque module dispose d'un testbench de simulation permettant de vérifier son comportement :

- Vérification des transitions de la machine à états (Moore)
- Validation du séquençage du registre à décalage
- Test du compteur synchrone et asynchrone
- Simulation de l'afficheur 7 segments

---

## 📌 Notes

- Ce projet est réalisé à des fins pédagogiques dans le cadre d'un cours de conception électronique
- Les fichiers générés par Vivado (`.cache`, `.runs`, `.hw`, etc.) ne sont pas versionnés
- La cible FPGA et les contraintes de placement sont définies dans les fichiers `.xdc`

---


## 📄 Licence

MIT License — libre d'utilisation à des fins éducatives.
