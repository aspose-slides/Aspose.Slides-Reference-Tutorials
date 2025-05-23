---
"date": "2025-04-22"
"description": "Apprenez à créer et personnaliser des graphiques à secteurs dans PowerPoint avec Aspose.Slides pour Python. Améliorez vos présentations grâce à des informations basées sur les données."
"title": "Créez des graphiques PowerPoint attrayants avec Aspose.Slides pour Python | Tutoriel sur les graphiques et les diagrammes"
"url": "/fr/python-net/charts-graphs/aspose-slides-python-powerpoint-pie-charts/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Créer des graphiques à secteurs PowerPoint avec Aspose.Slides pour Python

**Catégorie:** Tableaux et graphiques

Créer des présentations engageantes et informatives est essentiel pour communiquer efficacement des informations basées sur des données. Si vous souhaitez enrichir vos diapositives PowerPoint en y intégrant des diagrammes à secteurs visuellement attrayants, **Aspose.Slides pour Python** La bibliothèque est un excellent outil qui simplifie ce processus. Dans ce tutoriel, nous vous expliquerons comment créer un graphique à secteurs dans PowerPoint avec Aspose.Slides pour Python.

## Ce que vous apprendrez :
- Installer et configurer Aspose.Slides pour Python
- Créer un graphique à secteurs de base dans des diapositives PowerPoint
- Personnalisez votre graphique à secteurs avec des points de données, des couleurs, des bordures, des étiquettes, des lignes de repère et une rotation
- Optimiser les performances lorsque vous travaillez avec des graphiques

Plongeons dans les étapes nécessaires pour commencer.

## Prérequis

Avant d’implémenter le code, assurez-vous de disposer des éléments suivants :
- Python installé sur votre système (version 3.6 ou ultérieure recommandée)
- `pip` gestionnaire de paquets pour l'installation des bibliothèques
- Compréhension de base de la programmation Python et des présentations PowerPoint

## Configuration d'Aspose.Slides pour Python

Pour commencer à travailler avec Aspose.Slides pour Python, vous devez installer la bibliothèque à l'aide de pip :

```bash
pip install aspose.slides
```

**Acquisition de licence :**
Vous pouvez commencer par télécharger une licence d'essai gratuite à partir de [Page de téléchargement d'Aspose](https://releases.aspose.com/slides/python-net/)Pour une utilisation plus étendue, envisagez d’acheter une licence complète ou d’obtenir une licence temporaire à des fins d’évaluation.

### Initialisation et configuration de base

Une fois Aspose.Slides installé, importez les modules nécessaires dans votre script Python :

```python
import aspose.slides as slides
import aspose.pydrawing as drawing
```

## Guide de mise en œuvre

Dans cette section, nous allons décomposer la création d'un graphique à secteurs en étapes détaillées.

### Création et personnalisation de votre graphique à secteurs

#### Aperçu
La création d'un graphique à secteurs implique l'initialisation d'un objet de présentation, l'ajout d'une diapositive, puis l'insertion d'un graphique avec des points de données personnalisés et des éléments visuels.

#### Étapes pour créer un graphique à secteurs

1. **Instancier la classe de présentation**
   Commencez par créer une instance de présentation. Elle servira de conteneur pour vos diapositives et graphiques.

   ```python
   with slides.Presentation() as presentation:
       # Accéder à la première diapositive
       slide = presentation.slides[0]
   ```

2. **Ajouter un graphique à secteurs à la diapositive**
   Utilisez le `add_chart` méthode pour insérer un graphique à secteurs à des coordonnées spécifiées sur la diapositive.

   ```python
   chart = slide.shapes.add_chart(slides.charts.ChartType.PIE, 100, 100, 400, 400)
   ```

3. **Définir le titre du graphique**
   Personnalisez votre graphique avec un titre approprié et formatez-le pour centrer le texte.

   ```python
   chart.chart_title.add_text_frame_for_overriding("Sample Title")
   chart.chart_title.text_frame_for_overriding.text_frame_format.center_text = slides.NullableBool.TRUE
   chart.chart_title.height = 20
   chart.has_title = True
   ```

4. **Cahier d'exercices sur les données des graphiques Access**
   Utilisez le `chart_data_workbook` pour gérer et personnaliser vos catégories et séries de données.

   ```python
   fact = chart.chart_data.chart_data_workbook
   default_worksheet_index = 0

   # Effacer toutes les séries ou catégories existantes
   chart.chart_data.series.clear()
   chart.chart_data.categories.clear()

   # Ajouter de nouvelles catégories (trimestres)
   chart.chart_data.categories.add(fact.get_cell(0, 1, 0, "First Qtr"))
   chart.chart_data.categories.add(fact.get_cell(0, 2, 0, "2nd Qtr"))
   chart.chart_data.categories.add(fact.get_cell(0, 3, 0, "3rd Qtr"))

   # Ajouter une nouvelle série
   series = chart.chart_data.series.add(fact.get_cell(0, 0, 1, "Series 1"), chart.type)
   ```

5. **Remplir la série avec des points de données**
   Insérez des points de données dans votre série pour représenter différentes parties du graphique.

   ```python
   series.data_points.add_data_point_for_pie_series(fact.get_cell(default_worksheet_index, 1, 1, 20))
   series.data_points.add_data_point_for_pie_series(fact.get_cell(default_worksheet_index, 2, 1, 50))
   series.data_points.add_data_point_for_pie_series(fact.get_cell(default_worksheet_index, 3, 1, 30))
   ```

6. **Appliquer des couleurs variées au graphique**
   Personnalisez chaque part de tarte avec des couleurs différentes.

   ```python
   chart.chart_data.series_groups[0].is_color_varied = True

   # Définir une fonction pour personnaliser l'apparence des points
   def customize_point(point, fill_color, line_color):
       point.format.fill.fill_type = slides.FillType.SOLID
       point.format.fill.solid_fill_color.color = drawing.Color(fill_color)
       
       point.format.line.fill_format.fill_type = slides.FillType.SOLID
       point.format.line.fill_format.solid_fill_color.color = drawing.Color(line_color)
       point.format.line.width = 3.0
       point.format.line.style = slides.LineStyle.THIN_THICK
       point.format.line.dash_style = slides.LineDashStyle.DASH_DOT
   
   # Personnaliser l'apparence du premier point de données
   customize_point(series.data_points[0], "Cyan", "Gray")
   ```

7. **Personnaliser les étiquettes des points de données**
   Ajustez les paramètres d’étiquette pour afficher des valeurs, des pourcentages ou des noms de séries.

   ```python
   def customize_label(point, show_value=True, show_legend_key=False,
                       show_percentage=False, show_series_name=False):
       lbl = point.label
       lbl.data_label_format.show_value = show_value
       lbl.data_label_format.show_legend_key = show_legend_key
       lbl.data_label_format.show_percentage = show_percentage
       lbl.data_label_format.show_series_name = show_series_name
   
   # Définir les propriétés de l'étiquette pour le premier point de données
   customize_label(series.data_points[0], True)
   ```

8. **Activer les lignes de repère et faire pivoter les tranches de tarte**
   Pour une meilleure lisibilité, activez les lignes de repère et faites pivoter les tranches selon vos besoins.

   ```python
   series.labels.default_data_label_format.show_leader_lines = True

   # Faites pivoter la première part de tarte à 180 degrés
   chart.chart_data.series_groups[0].first_slice_angle = 180
   ```

9. **Enregistrer la présentation**
   Enfin, enregistrez votre présentation avec toutes les personnalisations appliquées.

   ```python
   presentation.save("YOUR_OUTPUT_DIRECTORY/charts_pie_chart_out.pptx", slides.export.SaveFormat.PPTX)
   ```

### Conseils de dépannage
- Assurez-vous qu'Aspose.Slides est correctement installé et importé.
- Vérifiez les fautes de frappe dans les noms de méthode ou les paramètres, car elles peuvent entraîner des erreurs.
- Vérifiez que le chemin du répertoire dans lequel vous enregistrez votre fichier de sortie existe.

## Applications pratiques

Les graphiques à secteurs sont polyvalents et utiles dans divers domaines :
1. **Analyse commerciale**:Visualisez la répartition des revenus entre différents produits ou services.
2. **Rapports marketing**:Afficher la part de marché des concurrents dans un secteur donné.
3. **Présentations éducatives**: Démontrer des données statistiques liées aux performances des étudiants ou à la démographie.

## Considérations relatives aux performances
- Minimisez l’utilisation des ressources en optimisant les éléments du graphique et en réduisant la complexité inutile.
- Utilisez des structures de données efficaces lors de la gestion de grands ensembles de données pour les graphiques.
- Gérez efficacement la mémoire en libérant les ressources rapidement après utilisation.

## Conclusion

En suivant ce guide, vous avez appris à créer un graphique à secteurs dans PowerPoint avec Aspose.Slides pour Python. Vous pouvez désormais appliquer ces techniques à vos présentations et explorer d'autres options de personnalisation. Envisagez d'intégrer d'autres types de graphiques ou d'exploiter les fonctionnalités supplémentaires d'Aspose.Slides pour améliorer vos compétences en visualisation de données.

### Prochaines étapes
- Expérimentez différentes personnalisations de graphiques
- Découvrez l'intégration de graphiques dans des rapports dynamiques
- Plongez plus profondément dans la documentation Aspose.Slides pour des fonctionnalités plus avancées

## Section FAQ

1. **Qu'est-ce qu'Aspose.Slides ?**
   - Une bibliothèque puissante qui permet la création et la manipulation de présentations PowerPoint par programmation.
2. **Puis-je utiliser Aspose.Slides gratuitement ?**
   - Oui, vous pouvez commencer avec une licence d’essai ou évaluer ses capacités avant d’acheter.
3. **Quels sont les autres types de graphiques que je peux créer ?**
   - Outre les graphiques à secteurs, vous pouvez créer des graphiques à barres, des graphiques linéaires, des nuages de points et bien plus encore à l'aide d'Aspose.Slides.

## Recommandations de mots clés
- « Aspose.Slides pour Python »
- « Graphique à secteurs PowerPoint »
- « Graphiques PowerPoint Python »

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}