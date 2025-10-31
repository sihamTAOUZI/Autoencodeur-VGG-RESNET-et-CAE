# Autoencodeur-VGG-RESNET-et-CAE
Etude comparative de trois approches d’auto encodage appliquées à des images de la base Fashion-MNIST : deux autoencodeurs basés sur des réseaux convolutionnels profonds construits à partir de modèles préentraînés (VGG16 et ResNet50) et un contractive autoencoder (CAE) classique
#  Comparaison des Autoencodeurs : CAE, VGG16 et ResNet50 sur Fashion-MNIST

##  Description
Ce projet présente une étude comparative entre trois architectures d’autoencodeurs :
- **Contractive Autoencoder (CAE)**  
- **VGG16 Autoencoder**  
- **ResNet50 Autoencoder**

L’objectif est d’évaluer leurs performances en termes de **reconstruction d’images** et de **erreur quadratique moyenne (MSE)**, en exploitant le **transfert d’apprentissage** des modèles profonds préentraînés.

---

##  Jeu de données : Fashion-MNIST
- **Source :** [Zalando Research – Kaggle](https://www.kaggle.com/datasets/zalando-research/fashionmnist)  
- **Description :** 70 000 images de vêtements (28×28 pixels, niveaux de gris) réparties en 10 classes.  
- **Répartition :**
  - Entraînement : 60 000 images  
  - Test : 10 000 images  

Les classes incluent : T-shirt/top, pantalon, pull, robe, manteau, sandale, chemise, basket, sac et botte.

---

##  Étapes du Notebook
1. **Prétraitement des données**  
   - Normalisation et redimensionnement des images.  
   - Division en ensembles d’entraînement et de test.  

2. **Implémentation des architectures**
   - **CAE** : autoencodeur convolutionnel contractif avec régularisation jacobienne.  
   - **VGG16 / ResNet50** : autoencodeurs construits à partir de couches convolutionnelles préentraînées (transfert d’apprentissage).  

3. **Entraînement des modèles**
   - Optimiseur : Adam  
   - Fonction de perte : MSE  
   - Arrêt anticipé (EarlyStopping)  

4. **Évaluation**
   - Calcul du **Mean Squared Error (MSE)** sur l’ensemble de test.  
   - Visualisation des reconstructions d’images.  
   - Comparaison graphique des performances.

---

##  Résultats obtenus
| Modèle | MSE | Stabilité | Qualité visuelle |
|:-------:|:---:|:----------:|:----------------:|
| CAE | 0.0158 | Moyenne | Moyenne |
| VGG16 Autoencoder | 0.0119 | Bonne | Bonne |
| **ResNet50 Autoencoder** | **0.0114** | **Très stable** | **Excellente** |

---

##  Conclusion
Les architectures profondes préentraînées (VGG16 et ResNet50) surpassent nettement le CAE classique.  
**ResNet50** se distingue comme le modèle le plus performant, combinant précision et stabilité.  
Le transfert d’apprentissage s’avère donc une approche efficace pour la **reconstruction d’images complexes**.

---

##  Références
- He, K., Zhang, X., Ren, S., & Sun, J. (2016). *Deep Residual Learning for Image Recognition*. CVPR.  
  [arXiv:1512.03385](https://arxiv.org/pdf/1512.03385.pdf)
- *Comparaison de la classification des nyalas mâles et des koudous mâles à l'aide de l'apprentissage par transfert avec ResNet-50 et VGG-16*.  
  [arXiv:2311.05981](https://arxiv.org/pdf/2311.05981)
- Zalando Research. (2017). *Fashion-MNIST Dataset*.  
  [Kaggle](https://www.kaggle.com/datasets/zalando-research/fashionmnist)

---

##  Environnement
- Python 3.12  
- TensorFlow / Keras  
- NumPy, Matplotlib, Scikit-learn  

---

jupyter notebook Autoencodeurs_VGG_RESNET_CAE.ipynb
