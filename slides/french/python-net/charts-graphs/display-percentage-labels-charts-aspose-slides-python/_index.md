---
"date": "2025-04-22"
"description": "Apprenez à afficher facilement des étiquettes de pourcentage sur des graphiques PowerPoint avec Aspose.Slides pour Python. Idéal pour améliorer la visualisation des données."
"title": "Comment afficher des étiquettes de pourcentage sur des graphiques à l'aide d'Aspose.Slides pour Python ? Un guide complet"
"url": "/fr/python-net/charts-graphs/display-percentage-labels-charts-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment afficher les étiquettes de pourcentage sur les graphiques avec Aspose.Slides pour Python

## Introduction

Visualiser efficacement les données est essentiel dans les présentations et les rapports, notamment pour mettre clairement en évidence les proportions ou les distributions. Mais que faire si vous souhaitez afficher ces pourcentages directement sur vos graphiques ? Ce guide complet vous guidera dans leur utilisation. **Aspose.Slides pour Python** pour afficher sans effort les valeurs de pourcentage sous forme d'étiquettes sur un graphique.

### Ce que vous apprendrez :
- Comment créer et intégrer des graphiques dans des présentations PowerPoint à l'aide d'Aspose.Slides pour Python.
- Affichage des points de données sous forme d’étiquettes de pourcentage sur vos graphiques.
- Sauvegarder et gérer efficacement les présentations PowerPoint.

Prêt à ajouter des visuels perspicaces à vos données ? Voyons d'abord ce dont vous avez besoin avant de vous plonger dans le code !

## Prérequis

Avant de commencer, assurez-vous de disposer des éléments suivants :
- **Aspose.Slides pour Python**:Cette bibliothèque est essentielle pour créer et manipuler des présentations PowerPoint par programmation.
- **Environnement Python**:Une compréhension de base de la programmation Python et de la configuration de l'environnement.
- **Gestionnaire de packages PIP**: Utilisé pour installer Aspose.Slides.

## Configuration d'Aspose.Slides pour Python

Pour commencer à utiliser Aspose.Slides, vous devez d'abord l'installer :

```bash
pip install aspose.slides
```

### Étapes d'acquisition de la licence :
Vous pouvez commencer avec un essai gratuit ou obtenir une licence temporaire pour explorer toutes les fonctionnalités d'Aspose.Slides. Pour une utilisation prolongée, envisagez de souscrire un abonnement.

#### Initialisation et configuration de base

Une fois installé, vous initialiserez votre environnement de présentation comme suit :

```python
import aspose.slides as slides

# Initialiser un objet de présentation
def create_presentation():
    with slides.Presentation() as presentation:
        # Votre code ici
```

## Guide de mise en œuvre

Maintenant que nous sommes configurés, passons à l'affichage des pourcentages sur les graphiques.

### Création du graphique et ajout de données

#### Aperçu
Nous allons créer un graphique à colonnes empilées avec des étiquettes de pourcentage pour chaque point de données, permettant aux spectateurs de voir les proportions exactes en un coup d'œil.

##### Étape 1 : ajouter un graphique à votre diapositive

```python
# Accédez à la première diapositive de votre présentation
def add_chart_to_slide(presentation):
    slide = presentation.slides[0]

    # Ajouter un graphique à colonnes empilées
    chart = slide.shapes.add_chart(slides.charts.ChartType.STACKED_COLUMN, 20, 20, 400, 400)
```

Cet extrait de code ajoute un graphique de base à la première diapositive. `add_chart` la méthode spécifie le type de graphique ainsi que sa position et sa taille.

##### Étape 2 : Calculer les valeurs totales des catégories

```python
def calculate_totals(chart):
    total_for_category = []
    # Additionnez les valeurs de toutes les séries pour chaque catégorie
    for k in range(len(chart.chart_data.categories)):
        value = sum(
            chart.chart_data.series[i].data_points[k].value.data 
            for i in range(len(chart.chart_data.series))
        )
        total_for_category.append(value)
```

Cette boucle calcule le total de tous les points de données sur les séries, ce qui est crucial pour les calculs de pourcentage.

#### Définition des étiquettes de pourcentage

##### Étape 3 : Configurer les points de données de la série

```python
def set_percentage_labels(chart, totals):
    for series in chart.chart_data.series:
        # Définir les options d'étiquette par défaut pour masquer les informations non essentielles
        series.labels.default_data_label_format.show_legend_key = False
        
        # Calculer et définir des étiquettes de pourcentage
        for j in range(len(series.data_points)):
            lbl = series.data_points[j].label
            data_point_percent = (series.data_points[j].value.data / totals[j]) * 100.0
            
            # Créer une partie de texte avec la valeur en pourcentage
            port = slides.Portion()
            port.text = "{0:4.2f} %".format(data_point_percent)
            port.portion_format.font_height = 8

            # Effacer les étiquettes existantes et ajouter une nouvelle étiquette de pourcentage
            lbl.text_frame_for_overriding.text = ""
            para = lbl.text_frame_for_overriding.paragraphs[0]
            para.portions.add(port)

            # Masquer les autres éléments d'étiquette de données
            lbl.data_label_format.show_series_name = False
            lbl.data_label_format.show_percentage = False
            lbl.data_label_format.show_legend_key = False
            lbl.data_label_format.show_category_name = False
            lbl.data_label_format.show_bubble_size = False
```

Ce segment traite chaque point de données pour calculer son pourcentage du total et lui attribue une étiquette.

### Enregistrer votre présentation

```python
def save_presentation(presentation, output_directory):
    # Enregistrez votre présentation avec des modifications
    presentation.save(f"{output_directory}/charts_display_percentage_as_labels_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}