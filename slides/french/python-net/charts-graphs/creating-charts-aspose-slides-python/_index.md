---
"date": "2025-04-23"
"description": "Apprenez à créer et configurer de superbes graphiques avec Aspose.Slides pour Python. Suivez ce guide étape par étape pour une visualisation efficace des données dans vos présentations."
"title": "Créer des graphiques en Python avec Aspose.Slides &#58; un guide complet"
"url": "/fr/python-net/charts-graphs/creating-charts-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Créer des graphiques en Python avec Aspose.Slides : un guide complet

## Introduction
Créer des graphiques attrayants pour vos présentations peut rendre les données plus digestes et vous permettre de transmettre facilement des informations complexes. Ce tutoriel vous guidera dans la création et la configuration de graphiques avec Aspose.Slides pour Python, une bibliothèque performante qui révolutionne la conception de vos présentations grâce à de puissantes fonctionnalités de manipulation de graphiques.

**Ce que vous apprendrez :**
- Comment créer un graphique à colonnes empilées dans une présentation
- Ajout et formatage de séries de données avec des étiquettes personnalisées
- Enregistrer votre présentation configurée

À la fin de ce tutoriel, vous maîtriserez Aspose.Slides Python pour optimiser vos présentations. Commençons par configurer votre environnement avant de créer de superbes graphiques !

## Prérequis
Avant de commencer, assurez-vous de remplir les conditions préalables suivantes :

1. **Environnement Python :** Vous devez avoir Python installé sur votre système (version 3.x recommandée).
2. **Aspose.Slides pour Python :** Cela peut être installé via pip.
3. **Acquisition de licence :** Bien qu'un essai gratuit soit disponible, envisagez d'acquérir une licence temporaire ou complète pour débloquer toutes les fonctionnalités.

## Configuration d'Aspose.Slides pour Python
Pour commencer à utiliser Aspose.Slides dans vos projets, vous devez installer la bibliothèque et comprendre comment configurer votre environnement :

**Installation:**
```bash
pip install aspose.slides
```

Après l'installation, vous pouvez initialiser et utiliser Aspose.Slides en l'important dans votre script. Pour exploiter pleinement ses fonctionnalités, procurez-vous une licence. Un essai gratuit est disponible. Pour une utilisation plus étendue, envisagez d'acheter ou de demander une licence temporaire.

## Guide de mise en œuvre

### Fonctionnalité 1 : Créer et configurer une présentation avec des graphiques
**Aperçu:** Cette section vous guide dans la configuration d'une diapositive de présentation et dans l'ajout d'un graphique à l'aide d'Aspose.Slides Python.

#### Étape 1 : Initialiser la présentation
Commencez par créer un nouvel objet de présentation. Utilisez le `with` déclaration pour la gestion automatique des ressources :
```python
import aspose.slides as slides

with slides.Presentation() as presentation:
    # Accéder à la première diapositive de la présentation
    slide = presentation.slides[0]
```

#### Étape 2 : ajouter un graphique à la diapositive
Ici, nous ajoutons un graphique à colonnes empilées à une position spécifiée avec des dimensions définies :
```python
# Ajouter un graphique à colonnes empilées à la diapositive
chart = slide.shapes.add_chart(slides.charts.ChartType.PERCENTS_STACKED_COLUMN, 20, 20, 500, 400)
```

#### Étape 3 : Configurer les axes du graphique
Configurer le format numérique de l'axe vertical pour une meilleure représentation des données :
```python
# Configurer le format des nombres de l'axe vertical
chart.axes.vertical_axis.is_number_format_linked_to_source = False
chart.axes.vertical_axis.number_format = "0.00%"
```

### Fonctionnalité 2 : Ajouter et formater des séries de données dans un graphique
**Aperçu:** Cette section se concentre sur l’ajout d’une série de données, son remplissage avec des valeurs et la personnalisation de son apparence.

#### Étape 1 : Définir le classeur de données
Initialisez le classeur de données de votre graphique :
```python
default_worksheet_index = 0
workbook = chart.chart_data.chart_data_workbook
```

#### Étape 2 : Ajouter et renseigner des séries de données
Ajoutez une nouvelle série nommée « Rouges » à votre graphique, puis remplissez-la avec des points de données :
```python
# Ajoutez une nouvelle série et remplissez-la avec des points de données
series = chart.chart_data.series.add(workbook.get_cell(default_worksheet_index, 0, 1, "Reds"), chart.type)

for i in range(1, 5):
    series.data_points.add_data_point_for_bar_series(
        workbook.get_cell(default_worksheet_index, i, 1, [0.30, 0.50, 0.80, 0.65][i-1])
    )
```

#### Étape 3 : Formater l'apparence de la série
Personnaliser la couleur de remplissage et le format de l'étiquette de données :
```python
# Définir le remplissage de la série sur rouge
series.format.fill.fill_type = slides.FillType.SOLID
series.format.fill.solid_fill_color.color = drawing.Color.red

# Configurer les étiquettes de données pour l'affichage en pourcentage
series.labels.default_data_label_format.show_value = True
series.labels.default_data_label_format.number_format = "0.0%"
```

### Fonctionnalité 3 : Ajouter et formater une deuxième série de données au graphique
**Aperçu:** Cette section développe l’ajout d’une deuxième série de données avec son propre style.

#### Étape 1 : Ajouter la deuxième série
Ajoutez une autre série nommée « Blues » :
```python
# Ajouter une deuxième série nommée « Blues »
series2 = chart.chart_data.series.add(workbook.get_cell(default_worksheet_index, 0, 2, "Blues"), chart.type)
```

#### Étape 2 : Remplir et formater la série
Remplissez-le avec des points de données et appliquez la mise en forme :
```python
# Remplir la deuxième série
for i in range(1, 5):
    series2.data_points.add_data_point_for_bar_series(
        workbook.get_cell(default_worksheet_index, i, 2, [0.70, 0.50, 0.20, 0.35][i-1])
    )

# Définissez le remplissage sur bleu et configurez les étiquettes
series2.format.fill.fill_type = slides.FillType.SOLID
series2.format.fill.solid_fill_color.color = drawing.Color.blue

series2.labels.default_data_label_format.show_value = True
```

### Fonctionnalité 4 : Enregistrer la présentation sur le disque
**Aperçu:** Une fois votre graphique configuré, enregistrez la présentation.

#### Étape 1 : Enregistrez votre travail
Utilisez le `save` méthode pour stocker votre fichier :
```python
# Enregistrer la présentation sur le disque
directory = "YOUR_OUTPUT_DIRECTORY"
presentation.save(f"{directory}/charts_set_data_labels_percentage_sign_out.pptx", slides.export.SaveFormat.PPTX)
```

## Applications pratiques
En utilisant Aspose.Slides pour Python, vous pouvez améliorer les présentations dans différents domaines :
1. **Rapports d'activité :** Créez des rapports trimestriels détaillés avec des graphiques dynamiques.
2. **Contenu éducatif :** Concevez des supports pédagogiques attrayants avec une représentation visuelle des données.
3. **Présentations de vente :** Illustrer efficacement les tendances et les prévisions de ventes.

Ces exemples montrent comment Aspose.Slides peut être intégré dans les flux de travail existants pour fournir des présentations soignées.

## Considérations relatives aux performances
Pour garantir des performances optimales :
- Gérez efficacement la mémoire, en particulier lors de la manipulation de grands ensembles de données dans des graphiques.
- Utilisez les meilleures pratiques pour la gestion des ressources Python avec Aspose.Slides.
- Mettez régulièrement à jour votre bibliothèque pour bénéficier d’améliorations de performances.

En suivant ces conseils, vous pouvez maintenir des opérations fluides et efficaces tout en travaillant avec des présentations complexes.

## Conclusion
Dans ce tutoriel, nous avons découvert comment créer et configurer des graphiques dans des présentations avec Aspose.Slides pour Python. Vous avez désormais les connaissances nécessaires pour intégrer des visualisations de données visuellement attrayantes à vos projets. Pour approfondir vos compétences, explorez les fonctionnalités supplémentaires de la bibliothèque ou testez différents types de graphiques.

**Prochaines étapes :** Essayez de mettre en œuvre ces concepts dans un projet réel pour consolider votre compréhension.

## Section FAQ
1. **Comment installer Aspose.Slides pour Python ?**
   - Utiliser `pip install aspose.slides` pour le télécharger et l'installer facilement.
2. **Puis-je utiliser Aspose.Slides sans acheter de licence ?**
   - Oui, vous pouvez commencer par un essai gratuit ou demander une licence temporaire.
3. **Est-il possible de personnaliser davantage les étiquettes de données des graphiques ?**
   - Absolument ! Vous pouvez explorer d'autres options de formatage offertes par l'API de la bibliothèque.
4. **Quels sont les problèmes courants lors de la création de graphiques ?**
   - Assurez-vous que tous les points de données sont correctement formatés et liés à la série appropriée.
5. **Comment intégrer Aspose.Slides avec d'autres systèmes ?**
   - Utilisez son API complète pour une intégration transparente dans vos projets Python existants.

## Ressources
- [Documentation](https://reference.aspose.com/slides/python-net/)
- [Télécharger](https://releases.aspose.com/slides/python-net/)
- [Achat](https://purchase.aspose.com/buy)
- [Essai gratuit](https://releases.aspose.com/slides/python-net/)
- [Permis temporaire](https://purchase.aspose.com/temporary-license/)
- [Forum d'assistance](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}