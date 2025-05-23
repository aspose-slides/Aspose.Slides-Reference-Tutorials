---
"date": "2025-04-23"
"description": "Apprenez à créer et personnaliser des graphiques SmartArt dans PowerPoint à l’aide d’Aspose.Slides pour Python, en améliorant vos présentations avec des organigrammes dynamiques."
"title": "Comment créer et personnaliser des SmartArt dans PowerPoint avec Aspose.Slides pour Python"
"url": "/fr/python-net/smart-art-diagrams/create-custom-smartart-powerpoint-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment créer et personnaliser des SmartArt dans PowerPoint avec Aspose.Slides pour Python

## Introduction

Les présentations sont un outil essentiel pour représenter visuellement les structures organisationnelles ou les séances de brainstorming. Avec Aspose.Slides pour Python, créez et personnalisez facilement des graphiques SmartArt. Ce tutoriel vous guidera dans l'ajout d'un organigramme SmartArt à vos diapositives PowerPoint.

**Ce que vous apprendrez :**
- Ajout d'un graphique SmartArt dans PowerPoint à l'aide d'Aspose.Slides pour Python.
- Personnalisation de la disposition de votre nœud SmartArt.
- Sauvegarde et exportation efficaces des présentations.

Commençons par configurer votre environnement !

## Prérequis

Avant de vous lancer dans la création de graphiques SmartArt, assurez-vous de disposer des prérequis suivants :

### Bibliothèques requises
- **Aspose.Slides pour Python**: Installez cette bibliothèque en utilisant pip si ce n'est pas déjà fait.

### Configuration requise pour l'environnement
- Une installation fonctionnelle de Python (3.x recommandé).
- Compréhension de base de la programmation Python.
- La connaissance de Microsoft PowerPoint est utile mais pas nécessaire.

## Configuration d'Aspose.Slides pour Python

Pour commencer, configurez la bibliothèque Aspose.Slides dans votre environnement Python :

**Installation de Pip :**
```bash
pip install aspose.slides
```

### Étapes d'acquisition de licence
Aspose propose différentes options de licence :
- **Essai gratuit**: Téléchargez une licence temporaire pour évaluer toutes les fonctionnalités.
- **Permis temporaire**:Obtenez une licence temporaire gratuite pour une utilisation à court terme.
- **Achat**:Envisagez d’acheter un abonnement pour les projets à long terme.

### Initialisation et configuration de base

Une fois installé, initialisez votre script Python avec Aspose.Slides comme ceci :

```python
import aspose.slides as slides

# Initialisez la classe Presentation\avec slides.Presentation() comme présentation :
    # Votre code pour ajouter SmartArt ira ici
```

## Guide de mise en œuvre

Décomposons maintenant le processus d’ajout et de personnalisation de SmartArt dans PowerPoint à l’aide d’Aspose.Slides pour Python.

### Ajout d'un graphique SmartArt

#### Aperçu
Créez une nouvelle diapositive et ajoutez-y un graphique SmartArt de type organigramme :

```python
import aspose.slides as slides

# Créez une instance de présentation avec slides.Presentation() comme présentation :
    # Ajouter SmartArt avec les dimensions spécifiées à la position (10, 10)
    smart = presentation.slides[0].shapes.add_smart_art(
        x=10,
        y=10,
        width=400,
        height=300,
        layout_type=slides.smartart.SmartArtLayoutType.ORGANIZATION_CHART
    )
```

#### Paramètres et objectif de la méthode
- **x, y**: Position du graphique SmartArt sur la diapositive.
- **largeur, hauteur**: Dimensions pour une bonne visibilité.
- **type_de_mise_en_page**: Spécifie le type de mise en page SmartArt, dans ce cas, un organigramme.

### Personnalisation de la mise en page de l'organigramme

#### Aperçu
Personnalisez le premier nœud de notre graphique SmartArt en définissant sa disposition sur LEFT_HANGING :

```python
# Définissez le premier nœud sur la disposition suspendue à gauche
smart.nodes[0].organization_chart_layout = slides.smartart.OrganizationChartLayoutType.LEFT_HANGING
```

#### Explication des principales options de configuration
- **OrganizationChartLayoutType**:Détermine la manière dont les nœuds sont affichés, améliorant ainsi la lisibilité et l'attrait esthétique.

### Enregistrer la présentation

Enfin, enregistrez votre présentation dans un répertoire spécifié :

```python
# Enregistrez la présentation avec SmartArt\presentation.save("YOUR_OUTPUT_DIRECTORY/smart_art_organization_chart_layout_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}