---
"date": "2025-04-22"
"description": "Apprenez à créer des graphiques en boîte et à moustaches avec Aspose.Slides pour Python. Améliorez la visualisation des données dans vos présentations."
"title": "Créer des graphiques en boîte et à moustaches en Python avec Aspose.Slides"
"url": "/fr/python-net/charts-graphs/create-box-whisker-charts-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Créer des graphiques en boîte et à moustaches en Python avec Aspose.Slides

## Comment créer un graphique en boîte et à moustaches avec Aspose.Slides pour Python

Améliorez vos compétences en visualisation de données en apprenant à créer des graphiques en boîte et à moustaches grâce à la puissante bibliothèque Aspose.Slides. Ces graphiques sont parfaits pour afficher des distributions statistiques et faciliter l'interprétation de données complexes en un coup d'œil.

**Ce que vous apprendrez :**
- Configurer votre environnement avec Aspose.Slides pour Python
- Création et personnalisation de graphiques en boîte et à moustaches
- Applications pratiques et opportunités d'intégration
- Conseils d'optimisation pour de meilleures performances

## Prérequis

Avant de commencer, assurez-vous d’avoir les éléments suivants :
- **Aspose.Slides pour Python :** Une bibliothèque essentielle pour créer et manipuler des présentations PowerPoint.
- **Environnement Python :** Vous aurez besoin d'une installation Python fonctionnelle (de préférence Python 3.x).
- **Connaissances de base en Python :** La familiarité avec la programmation Python vous aidera à suivre plus facilement.

## Configuration d'Aspose.Slides pour Python

### Informations d'installation

Pour commencer, installez la bibliothèque Aspose.Slides à l'aide de pip :

```bash
pip install aspose.slides
```

### Étapes d'acquisition de licence

Aspose propose différentes options de licence :
- **Essai gratuit :** Téléchargez une licence temporaire pour explorer toutes les fonctionnalités sans limitations d'évaluation.
- **Licence temporaire :** Idéal pour les projets à court terme ou à des fins de test.
- **Achat:** Obtenez une licence permanente si vous avez besoin d’un accès continu.

Vous pouvez acquérir ces licences via le [page d'achat](https://purchase.aspose.com/buy) ou demandez un essai gratuit sur leur [page de licence temporaire](https://purchase.aspose.com/temporary-license/).

### Initialisation et configuration de base

Après l'installation, initialisez Aspose.Slides pour Python pour commencer à travailler avec des présentations. Voici comment configurer votre environnement :

```python
import aspose.slides as slides

# Initialiser une instance de présentation
def setup_presentation():
    with slides.Presentation() as pres:
        # Effectuez des opérations telles que l'ajout de graphiques ici
        pass
```

## Guide de mise en œuvre

Dans cette section, nous vous guiderons dans la création d'un graphique en boîte et à moustaches.

### Ajouter un graphique en boîte et à moustaches à votre présentation

#### Aperçu

Pour visualiser efficacement les données dans votre présentation, créez un graphique en boîte et à moustaches avec Aspose.Slides pour Python. Ce type de graphique est idéal pour afficher les distributions et identifier les valeurs aberrantes.

#### Mise en œuvre étape par étape

1. **Créer une nouvelle présentation :**
   
   Commencez par initialiser une nouvelle instance de présentation :
   
   ```python
   import aspose.slides as slides
   
   def create_box_and_whisker_chart():
       # Créer une nouvelle instance de présentation
       with slides.Presentation() as pres:
           # Ajoutez le graphique dans les étapes suivantes
           pass
   ```

2. **Ajoutez le graphique à votre diapositive :**
   
   Insérez le tableau en boîte et à moustaches à la position souhaitée :
   
   ```python
   def create_box_and_whisker_chart():
       with slides.Presentation() as pres:
           # Ajoutez un graphique en boîte et à moustaches sur la première diapositive à la position (50, 50) avec une taille (500, 400)
           chart = pres.slides[0].shapes.add_chart(slides.charts.ChartType.BOX_AND_WHISKER, 50, 50, 500, 400)
   ```

3. **Effacer les données existantes :**
   
   Assurez-vous que le graphique est vide avant d’ajouter de nouvelles données :
   
   ```python
   def create_box_and_whisker_chart():
       with slides.Presentation() as pres:
           chart = pres.slides[0].shapes.add_chart(slides.charts.ChartType.BOX_AND_WHISKER, 50, 50, 500, 400)
           
           # Effacer toutes les catégories et données de série existantes
           chart.chart_data.categories.clear()
           chart.chart_data.series.clear()

           wb = chart.chart_data.chart_data_workbook
           wb.clear(0)  # Vider le classeur pour une nouvelle saisie de données
   ```

4. **Ajoutez des catégories à votre graphique :**
   
   Remplissez votre graphique avec des catégories :
   
   ```python
   def create_box_and_whisker_chart():
       with slides.Presentation() as pres:
           chart = pres.slides[0].shapes.add_chart(slides.charts.ChartType.BOX_AND_WHISKER, 50, 50, 500, 400)
           chart.chart_data.categories.clear()
           chart.chart_data.series.clear()

           wb = chart.chart_data.chart_data_workbook
           wb.clear(0)

           # Définir des catégories pour les données du graphique
           for i in range(1, 7):
               category_name = f"Category {i}"
               chart.chart_data.categories.add(wb.get_cell(0, f"A{i}", category_name))
   ```

5. **Configurer la série :**
   
   Configurez votre série avec les propriétés souhaitées :
   
   ```python
   def create_box_and_whisker_chart():
       with slides.Presentation() as pres:
           chart = pres.slides[0].shapes.add_chart(slides.charts.ChartType.BOX_AND_WHISKER, 50, 50, 500, 400)
           chart.chart_data.categories.clear()
           chart.chart_data.series.clear()

           wb = chart.chart_data.chart_data_workbook
           wb.clear(0)

           for i in range(1, 7):
               category_name = f"Category {i}"
               chart.chart_data.categories.add(wb.get_cell(0, f"A{i}", category_name))

           # Ajouter une nouvelle série et configurer ses propriétés
           series = chart.chart_data.series.add(slides.charts.ChartType.BOX_AND_WHISKER)
           series.quartile_method = slides.charts.QuartileMethodType.EXCLUSIVE
           series.show_mean_line = True
           series.show_mean_markers = True
           series.show_inner_points = True
           series.show_outlier_points = True

           # Définir les points de données pour la série
           values = [15, 41, 16, 10, 23, 16]
           for i, value in enumerate(values, start=1):
               series.data_points.add_data_point_for_box_and_whisker_series(wb.get_cell(0, f"B{i}", value))
   ```

6. **Enregistrer la présentation :**
   
   Enregistrez votre travail avec le graphique nouvellement ajouté :
   
   ```python
   def create_box_and_whisker_chart():
       with slides.Presentation() as pres:
           chart = pres.slides[0].shapes.add_chart(slides.charts.ChartType.BOX_AND_WHISKER, 50, 50, 500, 400)
           chart.chart_data.categories.clear()
           chart.chart_data.series.clear()

           wb = chart.chart_data.chart_data_workbook
           wb.clear(0)

           for i in range(1, 7):
               category_name = f"Category {i}"
               chart.chart_data.categories.add(wb.get_cell(0, f"A{i}", category_name))

           series = chart.chart_data.series.add(slides.charts.ChartType.BOX_AND_WHISKER)
           series.quartile_method = slides.charts.QuartileMethodType.EXCLUSIVE
           series.show_mean_line = True
           series.show_mean_markers = True
           series.show_inner_points = True
           series.show_outlier_points = True

           values = [15, 41, 16, 10, 23, 16]
           for i, value in enumerate(values, start=1):
               series.data_points.add_data_point_for_box_and_whisker_series(wb.get_cell(0, f"B{i}", value))

           # Enregistrer la présentation
           pres.save("YOUR_OUTPUT_DIRECTORY/charts_box_chart_out.pptx", slides.export.SaveFormat.PPTX)

   create_box_and_whisker_chart()
   ```

### Conseils de dépannage

- **Vérifier l'installation de la bibliothèque :** Assurer `aspose.slides` est correctement installé.
- **Vérifier la configuration de la licence :** Si vous rencontrez des limitations, assurez-vous que votre fichier de licence est correctement configuré.
- **Erreurs de syntaxe :** Vérifiez à nouveau s’il y a des fautes de frappe ou des erreurs dans la syntaxe du code.

## Applications pratiques et opportunités d'intégration

Les graphiques en boîtes et à moustaches sont largement utilisés en analyse commerciale pour présenter des données statistiques de manière concise. Ils permettent d'identifier les tendances, les valeurs aberrantes et les variations au sein des ensembles de données, ce qui les rend idéaux pour les présentations, les rapports et les tableaux de bord.

L'intégration d'Aspose.Slides avec Python permet la création transparente de présentations PowerPoint riches et interactives par programmation, améliorant ainsi la façon dont vous communiquez des informations basées sur les données.

## Conseils d'optimisation pour de meilleures performances

- **Rationaliser la saisie des données :** Assurez-vous que vos ensembles de données sont propres et bien structurés avant de générer des graphiques pour éviter les erreurs lors de la visualisation.
- **Optimiser la personnalisation du graphique :** Utilisez judicieusement les options de personnalisation d'Aspose.Slides pour améliorer la lisibilité du graphique sans surcharger la présentation avec des éléments excessifs.
- **Automatiser les tâches répétitives :** Exploitez les scripts Python pour automatiser les tâches répétitives telles que le formatage des données et la génération de graphiques, ce qui permet de gagner du temps et de réduire les erreurs.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}