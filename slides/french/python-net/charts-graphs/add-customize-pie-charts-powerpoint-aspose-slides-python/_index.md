---
"date": "2025-04-22"
"description": "Apprenez à ajouter et personnaliser des graphiques à secteurs dans vos présentations PowerPoint avec Aspose.Slides pour Python. Gagnez du temps et assurez la cohérence grâce à ce guide étape par étape."
"title": "Comment ajouter et personnaliser des graphiques à secteurs dans PowerPoint avec Aspose.Slides pour Python"
"url": "/fr/python-net/charts-graphs/add-customize-pie-charts-powerpoint-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment ajouter et personnaliser des graphiques à secteurs dans PowerPoint avec Aspose.Slides pour Python

## Introduction
Créer des présentations visuellement attrayantes est crucial, surtout lorsqu'il s'agit de transmettre des données complexes de manière concise. Qu'il s'agisse de rapports financiers ou d'indicateurs de performance, les diagrammes circulaires peuvent être un outil efficace pour illustrer les proportions d'un coup d'œil. Cependant, l'ajout manuel de ces graphiques à vos diapositives peut être chronophage et source d'incohérences.

Grâce à la bibliothèque Python Aspose.Slides, l'automatisation de ce processus devient fluide. Ce tutoriel vous guidera dans l'utilisation d'Aspose.Slides pour Python pour ajouter et personnaliser facilement des graphiques à secteurs dans vos présentations PowerPoint. En suivant ces instructions, vous gagnerez non seulement du temps, mais vous garantirez également l'uniformité de vos diapositives.

**Ce que vous apprendrez :**
- Comment ajouter un graphique à secteurs à une diapositive
- Définir le titre et centrer le texte sur un graphique à secteurs
- Configuration des séries de données et des catégories pour des informations détaillées
- Activation des variations de couleur automatiques pour des tranches distinctes

Voyons comment implémenter efficacement ces fonctionnalités. Avant de commencer, assurez-vous que votre environnement est correctement configuré.

## Prérequis
Pour suivre ce tutoriel, vous aurez besoin de :
- Python installé sur votre machine (version 3.x recommandée)
- La bibliothèque Aspose.Slides pour Python
- Compréhension de base de la programmation Python et des présentations PowerPoint

Assurez-vous de disposer de la configuration nécessaire pour exécuter des scripts Python. Dans le cas contraire, envisagez d'installer Python depuis [python.org](https://www.python.org/downloads/).

## Configuration d'Aspose.Slides pour Python
Pour commencer à utiliser Aspose.Slides dans votre projet, installez-le via pip :

```bash
pip install aspose.slides
```

### Étapes d'acquisition de licence
Aspose propose un essai gratuit de sa bibliothèque. Vous pouvez télécharger une licence temporaire pour explorer toutes les fonctionnalités sans aucune limitation. Pour commencer :
- Visite [Page d'achat d'Aspose](https://purchase.aspose.com/buy) pour les options d'achat.
- Obtenir un permis temporaire via le [Page de licence temporaire](https://purchase.aspose.com/temporary-license/).

### Initialisation de base
Voici comment vous pouvez initialiser Aspose.Slides dans votre script Python :

```python
import aspose.slides as slides

# Initialiser la classe Presentation pour créer ou ouvrir un fichier de présentation
with slides.Presentation() as presentation:
    # Votre code va ici
    pass
```

Avec cette configuration, vous êtes prêt à commencer à ajouter des graphiques à secteurs à vos présentations.

## Guide de mise en œuvre

### Ajout d'un graphique à secteurs à une diapositive
#### Aperçu
L'ajout d'un graphique à secteurs de base implique la création d'une nouvelle forme de type `Chart` sur votre diapositive. Cette section vous guidera à travers les étapes pour ajouter un graphique à secteurs par défaut.

#### Mesures
1. **Accéder à la première diapositive**
   
   ```python
   slide = presentation.slides[0]
   ```

2. **Ajouter une forme de graphique à secteurs**
   
   ```python
   chart = slide.shapes.add_chart(slides.charts.ChartType.PIE, 100, 100, 400, 400)
   ```

   - Paramètres: `ChartType.PIE` spécifie le type de graphique.
   - Les coordonnées et les dimensions définissent la position et la taille du graphique à secteurs.

3. **Enregistrer la présentation**
   
   ```python
   presentation.save("YOUR_OUTPUT_DIRECTORY/charts_add_pie_chart_out.pptx", slides.export.SaveFormat.PPTX)
   ```

### Définition du titre et du texte central du graphique à secteurs
#### Aperçu
Personnaliser votre graphique à secteurs avec un titre améliore sa lisibilité et fournit un contexte aux spectateurs.

#### Mesures
1. **Accéder à la première diapositive**
   
   ```python
   slide = presentation.slides[0]
   ```

2. **Ajouter un graphique et définir un titre**
   
   ```python
   chart = slide.shapes.add_chart(slides.charts.ChartType.PIE, 100, 100, 400, 400)
   
   # Titre du paramètre
   chart.chart_title.add_text_frame_for_overriding("Sample Title")
   chart.chart_title.text_frame_for_overriding.text_frame_format.center_text = slides.NullableBool.TRUE
   chart.chart_title.height = 20
   chart.has_title = True
   ```

3. **Enregistrer la présentation**
   
   ```python
   presentation.save("YOUR_OUTPUT_DIRECTORY/charts_set_pie_chart_title_out.pptx", slides.export.SaveFormat.PPTX)
   ```

### Configuration des séries de données et des catégories de graphiques à secteurs
#### Aperçu
Pour que votre graphique à secteurs soit informatif, vous devez y saisir des données réelles.

#### Mesures
1. **Accéder à la première diapositive**
   
   ```python
   slide = presentation.slides[0]
   ```

2. **Configurer les données**
   
   ```python
   chart = slide.shapes.add_chart(slides.charts.ChartType.PIE, 100, 100, 400, 400)
   
   fact = chart.chart_data.chart_data_workbook
   
   # Effacer les données existantes
   chart.chart_data.series.clear()
   chart.chart_data.categories.clear()
   
   # Ajouter des catégories et des séries avec des points de données
   chart.chart_data.categories.add(fact.get_cell(0, 1, 0, "First Qtr"))
   chart.chart_data.categories.add(fact.get_cell(0, 2, 0, "2nd Qtr"))
   chart.chart_data.categories.add(fact.get_cell(0, 3, 0, "3rd Qtr"))

   series = chart.chart_data.series.add(fact.get_cell(0, 0, 1, "Series 1"), chart.type)
   
   # Ajouter des points de données
   series.data_points.add_data_point_for_pie_series(fact.get_cell(0, 1, 1, 20))
   series.data_points.add_data_point_for_pie_series(fact.get_cell(0, 2, 1, 50))
   series.data_points.add_data_point_for_pie_series(fact.get_cell(0, 3, 1, 30))
   ```

3. **Enregistrer la présentation**
   
   ```python
   presentation.save("YOUR_OUTPUT_DIRECTORY/charts_configure_pie_chart_data_out.pptx", slides.export.SaveFormat.PPTX)
   ```

### Activation des couleurs automatiques des tranches de graphique à secteurs
#### Aperçu
Améliorer l’attrait visuel en faisant varier automatiquement les couleurs des tranches peut rendre votre graphique plus attrayant.

#### Mesures
1. **Accéder à la première diapositive**
   
   ```python
   slide = presentation.slides[0]
   ```

2. **Activer la variation de couleur**
   
   ```python
   chart = slide.shapes.add_chart(slides.charts.ChartType.PIE, 100, 100, 400, 400)
   
   series = chart.chart_data.series[0]
   series.parent_series_group.is_color_varied = True
   ```

3. **Enregistrer la présentation**
   
   ```python
   presentation.save("YOUR_OUTPUT_DIRECTORY/charts_enable_automatic_pie_slice_colors_out.pptx", slides.export.SaveFormat.PPTX)
   ```

## Applications pratiques
1. **Rapports d'activité**:Utilisez des graphiques à secteurs pour montrer la répartition des parts de marché entre les concurrents.
2. **Matériel pédagogique**:Illustrer les pourcentages de différents sujets abordés dans un programme.
3. **Analyse financière**:Afficher les catégories de dépenses sous forme de proportions du budget total.
4. **Informations marketing**:Visualisez la segmentation des clients par données démographiques ou préférences.

L'intégration avec des outils d'analyse de données comme Pandas peut automatiser davantage le processus, rendant possibles des mises à jour en temps réel dans les présentations.

## Considérations relatives aux performances
Lorsque vous travaillez avec Aspose.Slides et Python :
- Optimisez votre code pour gérer efficacement la mémoire, en particulier lorsque vous traitez de grands ensembles de données.
- Évitez les opérations redondantes sur les objets de présentation.
- Utiliser `with` déclarations de gestion du contexte pour garantir que les ressources sont libérées de manière appropriée après utilisation.

## Conclusion
Vous maîtrisez désormais parfaitement la création et la personnalisation de graphiques à secteurs dans PowerPoint avec Aspose.Slides pour Python. En automatisant ces tâches, vous pouvez considérablement améliorer votre productivité tout en garantissant la cohérence de vos présentations. 

Pour aller plus loin, envisagez d’intégrer des sources de données dynamiques ou d’automatiser la génération de diapositives entières.

## Recommandations de mots clés
- « Aspose.Slides pour Python »
- « Graphique à secteurs PowerPoint »
- « Automatiser les graphiques PowerPoint avec Python »

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}