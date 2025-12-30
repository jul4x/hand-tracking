# Hand Tracking avec MediaPipe

Détection et tracking des mains en temps réel avec MediaPipe et OpenCV.

## Prérequis

- **macOS** (testé sur macOS 15 Sequoia)
- **Python 3.12** (⚠️ Python 3.14 n'est pas compatible avec MediaPipe)

## Installation

### 1. Installer Python 3.12 (si nécessaire)

```bash
brew install python@3.12
```

### 2. Créer un environnement virtuel

```bash
/opt/homebrew/opt/python@3.12/bin/python3.12 -m venv venv
source venv/bin/activate
```

### 3. Installer les dépendances

```bash
pip install mediapipe==0.10.14 opencv-python
```

> ⚠️ **Important** : Utiliser mediapipe version **0.10.14**. Les versions plus récentes (0.10.30+) ont une API différente sans `mp.solutions`.

## Utilisation

```bash
source venv/bin/activate
python handtrack.py
```

- Appuie sur **Q** pour quitter

## Versions testées

| Package | Version |
|---------|---------|
| Python | 3.12.12 |
| mediapipe | 0.10.14 |
| opencv-python | 4.12.0 |

## Structure du projet

```
.
├── .gitignore
├── README.md
├── handtrack.py
└── requirements.txt
```

## Fichier requirements.txt

```
mediapipe==0.10.14
opencv-python
```

## Fonctionnalités

- Détection de 2 mains simultanées
- 21 landmarks par main
- Affichage du squelette avec connexions colorées
- Fonctionne en temps réel via webcam

## Troubleshooting

### "module 'mediapipe' has no attribute 'solutions'"
→ Tu utilises une version trop récente de MediaPipe. Installe la version 0.10.14 :
```bash
pip uninstall mediapipe -y
pip install mediapipe==0.10.14
```

### "externally-managed-environment"
→ Utilise un environnement virtuel (voir section Installation)

### La fenêtre ne s'ouvre pas
→ Vérifie que tu as autorisé l'accès à la caméra dans Préférences Système > Confidentialité > Caméra