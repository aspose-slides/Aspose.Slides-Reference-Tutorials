---
"date": "2025-04-22"
"description": "Apprenez à personnaliser les propriétés de police des légendes de graphiques avec Aspose.Slides pour Python. Améliorez vos présentations avec des polices en gras, en italique et en couleur pour chaque entrée de légende."
"title": "Personnaliser la police des légendes de graphiques avec Aspose.Slides pour Python &#58; un guide complet"
"url": "/fr/python-net/charts-graphs/customize-chart-legends-font-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Personnalisation de la police des légendes de graphiques dans les présentations avec Aspose.Slides pour Python

## Introduction
Créer des présentations visuellement attrayantes est essentiel, notamment pour afficher des données sous forme de graphiques. Personnaliser les légendes des graphiques pour les adapter à votre style de présentation ou à votre image de marque représente un défi fréquent. Ce guide explique comment personnaliser les propriétés de police, telles que le gras, l'italique, la taille et la couleur, pour chaque entrée de légende d'un graphique à l'aide d'Aspose.Slides pour Python.

**Ce que vous apprendrez :**
- Configuration et utilisation d'Aspose.Slides pour Python
- Personnalisation des propriétés de police des légendes des graphiques
- Appliquer des styles de police spécifiques comme le gras, l'italique et changer de couleur
- Exemples pratiques d'amélioration des graphiques avec des polices personnalisées

Explorons comment vous pouvez réaliser cette personnalisation.

## Prérequis
Avant de commencer, assurez-vous de disposer des éléments suivants :
- **Bibliothèques**: Aspose.Slides pour Python. Installez-le avec pip.
- **Environnement**:Un environnement Python (de préférence Python 3.x) configuré sur votre machine.
- **Connaissance**:Compréhension de base de la programmation Python et familiarité avec la gestion des présentations par programmation.

## Configuration d'Aspose.Slides pour Python
### Installation
Pour commencer, installez la bibliothèque Aspose.Slides en exécutant la commande suivante dans votre terminal :

```bash
pip install aspose.slides
```

### Acquisition de licence
Aspose.Slides est un produit commercial avec différentes options de licence :
- **Essai gratuit**: Obtenez une licence temporaire pour toutes les fonctionnalités.
- **Permis temporaire**:Demandez une licence temporaire pour tester toutes les fonctionnalités sans limitations.
- **Achat**: Achetez un abonnement ou une licence perpétuelle en fonction de vos besoins.

### Initialisation de base
Voici comment vous pouvez initialiser et configurer Aspose.Slides dans votre script Python :

```python
import aspose.slides as slides

# Initialiser une instance de présentation\avec slides.Presentation() comme pres :
    # Votre code ici
```

## Guide de mise en œuvre
Dans cette section, nous allons parcourir la personnalisation des propriétés de police des entrées de légende individuelles.

### Ajout et accès à un graphique
Commençons par ajouter un graphique à colonnes groupées à votre diapositive :

```python
# Ajoutez un graphique à colonnes groupées à la position (50, 50) avec une largeur de 600 et une hauteur de 400
class ShapeCollection:
    def __init__(self):
        self.chart = None

    def add_chart(self, chart_type, x, y, width, height):
        # Il s'agit simplement d'un espace réservé pour la méthode Aspose.Slides réelle.
        return "ChartObject"

class SlideCollection:
    def __init__(self):
        self.shapes = ShapeCollection()

# Simulation de pres.slides[0].shapes
slide_shapes = SlideCollection()
chart = slide_shapes.shapes.add_chart(slides.charts.ChartType.CLUSTERED_COLUMN, 50, 50, 600, 400)
```

### Personnalisation des propriétés de police de légende
#### Accéder au format de texte de l'entrée de légende
Pour modifier les propriétés de police d’une entrée de légende spécifique :

```python
class Chart:
    def __init__(self):
        self.legend = "LegendObject"

# Simulation de chart.legend.entries[1].text_format
chart_object = Chart()
tf = "SimulatedTextFormatObject"
```

#### Définition des propriétés de police
Ici, nous personnalisons des aspects tels que le gras, la taille, l'italique et la couleur :

```python
class TextFormat:
    def __init__(self):
        self.portion_format = PortionFormat()

class PortionFormat:
    def __init__(self):
        self.font_bold = False
        self.font_height = 0
        self.font_italic = False
        self.fill_format = FillFormat()

class FillFormat:
    def __init__(self):
        self.fill_type = "None"
        self.solid_fill_color = SolidFillColor()

class SolidFillColor:
    def __init__(self):
        self.color = None

class Color:
    blue = 'blue'

tf.portion_format.font_bold = True
# Définir la taille de la police à 20 points
tf.portion_format.font_height = 20  
tf.portion_format.font_italic = True

# Définissez la couleur de la police sur bleu à l'aide d'un type de remplissage uni
tf.portion_format.fill_format.fill_type = "SOLID"
tf.portion_format.fill_format.solid_fill_color.color = Color.blue
```

### Enregistrer la présentation
Enfin, enregistrez votre présentation avec ces personnalisations :

```python
pres.save("YOUR_OUTPUT_DIRECTORY/charts_font_properties_for_individual_legend_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}