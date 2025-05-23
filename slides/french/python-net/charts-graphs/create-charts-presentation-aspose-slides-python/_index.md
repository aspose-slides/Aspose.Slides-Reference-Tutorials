---
"date": "2025-04-23"
"description": "Apprenez à enrichir vos présentations PowerPoint avec des graphiques dynamiques grâce à Aspose.Slides pour Python. Suivez ce guide étape par étape pour créer, gérer et mettre en forme efficacement des histogrammes groupés."
"title": "Créer et formater des graphiques dans des présentations PowerPoint à l'aide d'Aspose.Slides pour Python"
"url": "/fr/python-net/charts-graphs/create-charts-presentation-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Créer et formater des graphiques dans des présentations PowerPoint avec Aspose.Slides pour Python

## Introduction

Dans un monde où les données sont omniprésentes, l'intégration de graphiques visuellement attrayants dans les présentations est essentielle pour une communication efficace. Que vous soyez analyste de données, chef de projet ou professionnel, les graphiques dynamiques peuvent considérablement enrichir votre message. Ce tutoriel vous guidera dans la création et la mise en forme de graphiques à colonnes groupées avec Aspose.Slides pour Python, vous permettant ainsi de sublimer vos diapositives PowerPoint sans effort.

**Ce que vous apprendrez :**
- Comment installer et configurer Aspose.Slides pour Python
- Créez une nouvelle présentation et ajoutez un graphique à colonnes groupées
- Gérer les séries de données et les catégories dans le graphique
- Renseigner et formater les données des séries pour une meilleure visualisation

Prêt à améliorer vos présentations ? Découvrons comment utiliser Aspose.Slides pour créer des graphiques attrayants.

## Prérequis

Avant de commencer, assurez-vous d’avoir les éléments suivants :

- **Python installé :** La version 3.6 ou supérieure est recommandée.
- **Package Aspose.Slides pour Python :** Installez ce package en utilisant pip.
- **Connaissances de base de la programmation Python :** Une connaissance de la syntaxe Python et de la gestion des fichiers sera bénéfique.

## Configuration d'Aspose.Slides pour Python

Pour commencer, vous devez installer la bibliothèque Aspose.Slides. Cet outil puissant simplifie la création et la manipulation de présentations PowerPoint en Python.

### Installation

Exécutez la commande suivante pour installer le package :

```bash
pip install aspose.slides
```

### Acquisition de licence

Aspose propose une licence d'essai gratuite qui vous permet d'explorer toutes ses fonctionnalités sans aucune restriction. Suivez ces étapes pour l'obtenir :

1. Visite [Essai gratuit d'Aspose](https://releases.aspose.com/slides/python-net/) pour télécharger le package d'essai.
2. Vous pouvez également demander une licence temporaire via [Page de licence temporaire](https://purchase.aspose.com/temporary-license/).

Une fois que vous avez votre fichier de licence, initialisez-le dans votre script Python :

```python
from aspose.slides import License

# Configurer la licence Aspose.Slides
license = License()
license.set_license("path/to/your/license/file.lic")
```

## Guide de mise en œuvre

Nous allons décomposer le processus en trois fonctionnalités principales : la création de graphiques, la gestion des séries et des catégories de données, ainsi que le remplissage et le formatage des données des séries.

### Fonctionnalité 1 : Créer et ajouter un graphique à une présentation

#### Aperçu

Cette fonctionnalité se concentre sur l'ajout d'un graphique à colonnes groupées à votre présentation à l'aide d'Aspose.Slides pour Python.

#### Mise en œuvre étape par étape

```python
import aspose.slides as slides

def create_and_add_chart():
    with slides.Presentation() as pres:
        # Ajoutez un graphique à colonnes groupées à la position (100, 100) avec une largeur de 400 et une hauteur de 300.
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 100, 100, 400, 300
        )
        
        # Enregistrez la présentation dans un fichier dans votre répertoire de sortie.
        pres.save("YOUR_OUTPUT_DIRECTORY/charts_creation_out.pptx", slides.export.SaveFormat.PPTX)

create_and_add_chart()
```

**Explication:**
- **Position et taille du graphique :** Le `add_chart` la méthode est utilisée avec des paramètres spécifiant le type de graphique, la position (x, y), la largeur et la hauteur.
- **Sauvegarde de la présentation :** La présentation est enregistrée dans un répertoire spécifié.

### Fonctionnalité 2 : Gestion des séries et des catégories de données graphiques

#### Aperçu

Cette section montre comment gérer efficacement les séries de données et les catégories dans votre graphique.

#### Mise en œuvre étape par étape

```python
import aspose.slides as slides

def manage_chart_data_series_and_categories():
    with slides.Presentation() as pres:
        # Ajoutez un graphique à colonnes groupées à la position (100, 100) avec une largeur de 400 et une hauteur de 300.
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 100, 100, 400, 300
        )
        
        workbook = chart.chart_data.chart_data_workbook
        
        # Effacez les séries et catégories existantes avant d’en ajouter de nouvelles.
        chart.chart_data.series.clear()
        chart.chart_data.categories.clear()
        
        # Ajout d'une nouvelle série nommée « Série 1 » au graphique.
        chart.chart_data.series.add(
            workbook.get_cell(0, 0, 1, "Series 1"), chart.type
        )
        
        # Ajout de trois catégories aux données du graphique.
        chart.chart_data.categories.add(workbook.get_cell(0, 1, 0, "Category 1"))
        chart.chart_data.categories.add(workbook.get_cell(0, 2, 0, "Category 2"))
        chart.chart_data.categories.add(workbook.get_cell(0, 3, 0, "Category 3"))
        
        # Enregistrez la présentation dans un fichier dans votre répertoire de sortie.
        pres.save("YOUR_OUTPUT_DIRECTORY/chart_series_categories_out.pptx", slides.export.SaveFormat.PPTX)

manage_chart_data_series_and_categories()
```

**Explication:**
- **Effacement des données existantes :** Avant d'ajouter de nouvelles séries et catégories, celles existantes sont effacées pour éviter la duplication des données.
- **Ajout de séries et de catégories :** De nouvelles séries et catégories sont ajoutées à l'aide du `chart_data_workbook` objet.

### Fonctionnalité 3 : Remplissage des données de la série et formatage du graphique

#### Aperçu

Dans cette fonctionnalité, nous allons remplir votre graphique avec des points de données et appliquer une mise en forme pour améliorer son attrait visuel.

#### Mise en œuvre étape par étape

```python
import aspose.slides as slides
import aspose.pydrawing as drawing

def populate_and_format_series_data():
    with slides.Presentation() as pres:
        # Ajoutez un graphique à colonnes groupées à la position (100, 100) avec une largeur de 400 et une hauteur de 300.
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 100, 100, 400, 300
        )
        
        workbook = chart.chart_data.chart_data_workbook
        
        # Effacez les séries et catégories existantes avant d’en ajouter de nouvelles.
        chart.chart_data.series.clear()
        chart.chart_data.categories.clear()
        
        # Ajout d'une nouvelle série nommée « Série 1 » au graphique.
        chart.chart_data.series.add(
            workbook.get_cell(0, 0, 1, "Series 1"), chart.type
        )
        
        # Ajout de trois catégories aux données du graphique.
        chart.chart_data.categories.add(workbook.get_cell(0, 1, 0, "Category 1"))
        chart.chart_data.categories.add(workbook.get_cell(0, 2, 0, "Category 2"))
        chart.chart_data.categories.add(workbook.get_cell(0, 3, 0, "Category 3"))
        
        # Prenez la première série de graphiques et remplissez-la avec des points de données.
        series = chart.chart_data.series[0]
        series.data_points.add_data_point_for_bar_series(
            workbook.get_cell(0, 1, 1, -20)
        )
        series.data_points.add_data_point_for_bar_series(
            workbook.get_cell(0, 2, 1, 50)
        )
        series.data_points.add_data_point_for_bar_series(
            workbook.get_cell(0, 3, 1, -30)
        )
        
        # Définissez la couleur des valeurs négatives en série.
        invert_color = drawing.Color.red
        series.invert_if_negative = True
        series.format.fill.fill_type = slides.FillType.SOLID
        series.format.fill.solid_fill_color.color = series.get_automatic_series_color()
        series.inverted_solid_fill_color.color = invert_color
        
        # Enregistrez la présentation dans un fichier dans votre répertoire de sortie.
        pres.save("YOUR_OUTPUT_DIRECTORY/populate_format_series_out.pptx", slides.export.SaveFormat.PPTX)

populate_and_format_series_data()
```

**Explication:**
- **Ajout de points de données :** Les points de données sont ajoutés à l'aide de `add_data_point_for_bar_series`.
- **Formatage des valeurs négatives :** Les options de formatage des graphiques, telles que l'inversion des couleurs pour les valeurs négatives, améliorent la lisibilité des données.

## Applications pratiques

L'utilisation d'Aspose.Slides pour ajouter et formater des graphiques dans des présentations a de nombreuses applications :

1. **Rapports d'activité :** Améliorez les rapports trimestriels avec des visuels dynamiques qui transmettent clairement les indicateurs clés.
2. **Matériel pédagogique :** Créez du contenu éducatif attrayant en représentant visuellement des informations complexes.
3. **Présentations de projets :** Utilisez des graphiques pour illustrer efficacement la progression et les résultats du projet.

En suivant ce guide, vous pouvez exploiter Aspose.Slides pour Python pour créer des présentations percutantes qui se démarquent.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}