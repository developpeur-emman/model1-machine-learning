# model1-machine-learning
# 📓 Jour 1 — Linear Regression
## Prédire le poids d'un patient à partir de ses constantes physiques

---

## 📂 Dataset
**Body Performance Data** — 13 393 patients coréens
mesurés dans un contexte de performance physique et sportive.

---

## 🎯 Objectif
Prédire le **poids (kg)** d'un patient à partir de ses
caractéristiques physiques et cliniques.

---

## 📋 Features utilisées

| Feature | Description |
|---------|-------------|
| `age` | Âge du patient |
| `taille_cm` | Taille en cm |
| `graisse_corporelle` | % de graisse corporelle |
| `tension_diastolique` | Pression artérielle diastolique |
| `tension_systolique` | Pression artérielle systolique |
| `force_prehension` | Force de préhension (kg) |
| `abdominaux` | Nombre d'abdominaux |
| `saut_longueur` | Saut en longueur (cm) |
| `flexibilite_cm` | Flexibilité assise (cm) |

---

## 🧹 Nettoyage effectué

- Suppression des tensions à 0 (impossible biologiquement)
- Suppression des tensions diastolique < 40 et systolique < 70
- Suppression des poids < 35 kg
- Suppression des âges < 21 ans
- Suppression des graisses corporelles > 55%
- Suppression des forces de préhension > 165 kg
- Suppression des sauts > 375 cm
- Suppression des flexibilités hors [-30, +50] cm
- **Dataset final : 13 354 lignes** (39 lignes supprimées)

---

## 🔍 Observations EDA

- `taille_cm` → meilleur prédicteur visuel (corrélation 0.74)
- `force_prehension` → bon prédicteur (corrélation 0.70)
- `age` et `graisse_corporelle` → corrélation faible mais utile en combinaison
- Supprimer les features faibles fait chuter le R² de 0.79 à 0.65

---

## 🤖 Modèle

- **Algorithme** : Linear Regression (sklearn)
- **Normalisation** : StandardScaler
- **Split** : 80% train / 20% test

---

## 📊 Résultats

| Métrique | Valeur |
|----------|--------|
| MAE | 4.18 kg |
| RMSE | 5.44 kg |
| R² | 0.7932 |
| R² Cross-Validation (cv=5) | 0.7978 |

---

## ⚠️ Limites

- Le modèle sous-estime les patients > 110 kg (peu représentés)
- La Linear Regression ne capte pas les relations non linéaires
- L'âge influence le poids de façon non linéaire — mal capté ici

---

## 💾 Fichiers

| Fichier | Description |
|---------|-------------|
| `model_prediction_1.ipynb` | Notebook complet |
| `model_j1_linear_regression.pkl` | Modèle sauvegardé |
| `scaler_j1.pkl` | Scaler sauvegardé |

---

## 🔮 Possibilités d'amélioration

- Tester RobustScaler à la place de StandardScaler
- Ajouter du feature engineering
- Créer une interface Streamlit pour visualiser
les prédictions en temps réel *(non prioritaire)*

---

## 👨‍💻 Auteur
**Emmanuel SAVI**
Infirmier Diplômé d'État 🩺 | Developer HealthTech 💻
📍 Parakou, Bénin
