---
"date": "2025-04-22"
"description": "Apprenez à créer des graphiques en anneau avec Python et Aspose.Slides. Ce guide étape par étape couvre la configuration, la personnalisation et les bonnes pratiques pour améliorer vos présentations."
"title": "Comment créer des graphiques en anneau en Python avec Aspose.Slides &#58; un guide étape par étape"
"url": "/fr/python-net/charts-graphs/python-aspose-slides-doughnut-chart-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment créer des graphiques en anneau en Python avec Aspose.Slides : guide étape par étape

Dans le domaine de la visualisation de données, une présentation efficace des informations peut avoir un impact significatif sur la compréhension et la prise de décision. Que vous rédigiez une présentation commerciale ou analysiez des ensembles de données complexes, les graphiques sont des outils essentiels. Parmi les différents types de graphiques, les graphiques en anneau offrent une façon attrayante de représenter des données proportionnelles grâce à un trou central intuitif. Ce guide étape par étape vous guidera dans la création d'un graphique en anneau en Python avec Aspose.Slides, une puissante bibliothèque pour la manipulation de présentations.

## Ce que vous apprendrez
- Comment configurer et utiliser Aspose.Slides pour Python
- Le processus d'ajout d'un graphique en anneau à vos diapositives de présentation
- Personnalisation des séries et des catégories dans le graphique
- Ajuster les éléments visuels tels que les étiquettes, les couleurs et les effets d'explosion
- Bonnes pratiques pour optimiser les performances avec Aspose.Slides

## Prérequis
Avant de commencer, assurez-vous d'avoir :
- **Environnement Python**:Python 3.x installé sur votre machine.
- **Aspose.Slides pour Python**: Installez cette bibliothèque en utilisant pip.
- **Compréhension de base de la programmation Python**:Une connaissance des boucles et de la programmation orientée objet sera utile.

## Configuration d'Aspose.Slides pour Python
Pour commencer, installez la bibliothèque Aspose.Slides via pip :

```bash
pip install aspose.slides
```

### Acquisition de licence
Aspose propose un essai gratuit pour tester les fonctionnalités sans limitation pendant une durée limitée. Pour l'obtenir :
1. Visitez le [Essai gratuit](https://releases.aspose.com/slides/python-net/) page.
2. Suivez les instructions pour télécharger et appliquer votre licence temporaire.

Pour une utilisation continue, pensez à acheter un abonnement auprès du [Page d'achat](https://purchase.aspose.com/buy).

### Initialisation de base
Après avoir configuré Aspose.Slides, initialisez-le comme suit :

```python
import aspose.slides as slides

# Créez une instance de la classe Presentation.
with slides.Presentation() as pres:
    # Votre code pour manipuler les présentations va ici.

# Enregistrez la présentation après avoir apporté des modifications.
pres.save("output.pptx", slides.export.SaveFormat.PPTX)
```

## Guide de mise en œuvre
Une fois Aspose.Slides configuré, suivez ces étapes pour ajouter un graphique en anneau à votre présentation diapositive par diapositive.

### Créer une nouvelle présentation et ajouter une diapositive
Commencez par créer une instance du `Presentation` classe:

```python
import aspose.slides as slides

with slides.Presentation() as pres:
    # Accédez ou créez des diapositives dans ce contexte.
```

### Ajout d'un graphique en anneau à la première diapositive
Accédez à la première diapositive et utilisez le `add_chart` méthode. Spécifiez le type de graphique comme `DOUGHNUT`, ainsi que la position et la taille :

```python
slide = pres.slides[0]
chart = slide.shapes.add_chart(slides.charts.ChartType.DOUGHNUT, 10, 10, 500, 500, False)
```

### Configuration des données du graphique
Effacez les données existantes et configurez les paramètres tels que le masquage de la légende :

```python
workbook = chart.chart_data.chart_data_workbook
chart.chart_data.series.clear()
chart.chart_data.categories.clear()
chart.has_legend = False
```

### Ajout de séries et de catégories
Ajoutez plusieurs séries et catégories pour un graphique en anneau. Voici comment créer 15 séries avec des propriétés spécifiques :

```python
series_index = 0
while series_index < 15:
    series = chart.chart_data.series.add(
        workbook.get_cell(0, 0, series_index + 1, f"SERIES {series_index}"),
        chart.type
    )
    series.explosion = 0
    series.parent_series_group.doughnut_hole_size = 20
    series.parent_series_group.first_slice_angle = 351
    series_index += 1
```

Ajoutez des catégories de la même manière :

```python
category_index = 0
while category_index < 15:
    chart.chart_data.categories.add(
        workbook.get_cell(0, category_index + 1, 0, f"CATEGORY {category_index}")
    )
    # Ajoutez des points de données pour chaque série.
    i = 0
    while i < len(chart.chart_data.series):
        i_cs = chart.chart_data.series[i]
        data_point = i_cs.data_points.add_data_point_for_doughnut_series(
            workbook.get_cell(0, category_index + 1, i + 1, 1)
        )
        
        # Personnalisez l’apparence de chaque point de données.
        data_point.format.fill.fill_type = slides.FillType.SOLID
        data_point.format.line.fill_format.fill_type = slides.FillType.SOLID
        data_point.format.line.fill_format.solid_fill_color.color = drawing.Color.white
        data_point.format.line.width = 1
        
        # Configurez les paramètres d’étiquette pour la dernière série.
        if i == len(chart.chart_data.series) - 1:
            lbl = data_point.label
            lbl.text_format.text_block_format.autofit_type = slides.TextAutofitType.SHAPE
            lbl.data_label_format.text_format.portion_format.font_bold = slides.NullableBool.TRUE
            lbl.data_label_format.text_format.portion_format.latin_font = slides.FontData("DINPro-Bold")
            lbl.data_label_format.text_format.portion_format.font_height = 12
            lbl.data_label_format.show_value = False
            lbl.data_label_format.show_category_name = True
        
        i += 1
    category_index += 1
```

### Enregistrer la présentation
Enfin, enregistrez votre présentation dans un répertoire spécifié :

```python
pres.save("YOUR_OUTPUT_DIRECTORY/chart_add_doughnut_callout_out.pptx", slides.export.SaveFormat.PPTX)
```

## Applications pratiques
Les graphiques en anneau sont polyvalents et peuvent être utilisés dans divers scénarios tels que :
1. **Allocation budgétaire**:Afficher la manière dont les différents départements utilisent les fonds qui leur sont alloués.
2. **Analyse des parts de marché**:Comparer la part de marché des produits ou des entreprises concurrentes.
3. **Résultats de l'enquête**:Visualisation des réponses aux questions d’enquête sur les préférences ou les niveaux de satisfaction.

## Considérations relatives aux performances
Pour garantir des performances optimales lors de l'utilisation d'Aspose.Slides :
- Réduisez l’utilisation de la mémoire en éliminant correctement les objets après utilisation.
- Ne chargez les présentations en mémoire que lorsque cela est nécessaire et fermez-les dès que possible.
- Envisagez le traitement par lots des diapositives si vous travaillez avec un grand nombre de graphiques.

## Conclusion
En suivant ce guide, vous avez appris à créer des graphiques en anneau dynamiques avec Aspose.Slides pour Python. Ces visualisations peuvent enrichir vos présentations en rendant les données plus digestes et attrayantes. Explorez les fonctionnalités de la bibliothèque pour personnaliser et optimiser davantage vos graphiques.

## Section FAQ
1. **Puis-je utiliser Aspose.Slides sans acheter de licence ?**
   - Oui, vous pouvez commencer avec une licence d’essai gratuite à des fins d’évaluation.
2. **Comment modifier les couleurs des graphiques dans Aspose.Slides ?**
   - Utilisez le `fill_format` propriété pour définir la couleur souhaitée pour les éléments de votre graphique.
3. **Est-il possible d'exporter des graphiques sous forme d'images ?**
   - Oui, vous pouvez restituer des diapositives contenant des graphiques dans des formats d'image à l'aide des capacités de rendu de la bibliothèque.
4. **Quels sont les problèmes courants lors de l’ajout de graphiques ?**
   - Assurez-vous que tous les points de données et catégories sont correctement ajoutés avant de tenter d'enregistrer ou d'afficher votre graphique.
5. **Puis-je intégrer Aspose.Slides avec d’autres bibliothèques Python ?**
   - Absolument ! Vous pouvez l'utiliser avec des bibliothèques comme Pandas pour des capacités de manipulation de données améliorées.

## Ressources
- [Documentation Aspose.Slides](https://reference.aspose.com/slides/python-net/)
- [Télécharger Aspose.Slides](https://releases.aspose.com/slides/python-net/)
- [Acheter une licence](https://purchase.aspose.com/buy)
- [Essai gratuit et licence temporaire](https://releases.aspose.com/slides/python-net/)
- [Forum communautaire Aspose](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}