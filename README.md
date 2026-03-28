# Arduino-Smart-Distance-Alarm
# Système d'Alarme de Proximité Intelligent (Arduino)
**Projet de Systèmes Embarqués | Licence 3 ETSE - ISM Dakar**

## Présentation
Ce projet consiste en la conception et la réalisation d'un système d'alerte de distance utilisant un capteur à ultrasons **HC-SR04**. L'objectif est de fournir un monitoring visuel et sonore en temps réel pour prévenir les collisions ou surveiller un périmètre de sécurité.

## Architecture Matérielle
Le système est articulé autour des composants suivants :
* **Microcontrôleur :** Arduino UNO R3
* **Capteur :** HC-SR04 (Mesure de distance par ultrasons)
* **Affichage :** Écran LCD 16x2 (Piloté par la bibliothèque LiquidCrystal)
* **Alertes Visuelles :** 3 LEDs (Verte, Jaune, Rouge)
* **Alerte Sonore :** Buzzer piézoélectrique
* **Contrôle :** Potentiomètre pour le réglage du contraste de l'écran

## Logique de Fonctionnement
Le programme calcule la distance d'un objet en mesurant le temps de trajet de l'onde sonore. La réponse du système est segmentée en trois niveaux de sécurité :

| Distance (cm) | Alerte Visuelle | Alerte Sonore | État |
| :--- | :--- | :--- | :--- |
| **> 300** | Aucune | Off | Veille |
| **≤ 300** | LED Verte | Off | Vigilance |
| **≤ 150** | LED Jaune | Off | Avertissement |
| **≤ 75** | LED Rouge | **ON** | **Danger Immédiat** |

## Points Forts du Code
* **Traitement des signaux :** Utilisation de la fonction `pulseIn()` pour une lecture précise du retour d'onde.
* **Affichage Dynamique :** Nettoyage sélectif de la ligne LCD pour un affichage fluide et une lecture optimisée des données.
* **Modularité :** Organisation du code avec une fonction dédiée `recup_distance()` permettant une maintenance et une lisibilité accrues.

## Installation et Usage
1. Cloner le repository.
2. Brancher les composants selon les pins définis dans le code source situé dans le dossier `src/`.
3. Téléverser le code via l'IDE Arduino.
4. Ajuster le potentiomètre pour visualiser les mesures sur l'écran LCD.

---
**Développeur :** Dylan Bassinga  
*Projet réalisé dans le cadre de la formation en Électronique, Télécommunications et Systèmes Embarqués (2026).*
