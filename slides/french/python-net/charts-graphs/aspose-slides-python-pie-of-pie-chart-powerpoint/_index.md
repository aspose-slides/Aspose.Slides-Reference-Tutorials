---
"date": "2025-04-22"
"description": "Apprenez à créer et à personnaliser des graphiques à secteurs dans des présentations PowerPoint à l'aide d'Aspose.Slides pour Python, améliorant ainsi vos compétences en visualisation de données."
"title": "Comment créer un graphique à secteurs dans PowerPoint avec Aspose.Slides pour Python"
"url": "/fr/python-net/charts-graphs/aspose-slides-python-pie-of-pie-chart-powerpoint/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment créer un graphique à secteurs dans PowerPoint avec Aspose.Slides pour Python

Créer des graphiques attrayants, comme le graphique en secteurs, peut considérablement améliorer vos présentations PowerPoint en rendant les informations complexes plus lisibles. Ce tutoriel vous guide dans la création d'un graphique en secteurs avec Aspose.Slides pour Python.

## Ce que vous apprendrez

- Configuration d'Aspose.Slides pour Python
- Étapes pour créer une présentation PowerPoint avec un graphique à secteurs
- Configuration des étiquettes de données et des options de groupe de séries pour une meilleure lisibilité
- Applications pratiques du graphique en secteurs dans les présentations

Plongeons dans la configuration de votre environnement et la mise en œuvre de ces fonctionnalités.

### Prérequis

Avant de commencer, assurez-vous d’avoir les éléments suivants :

- **Python installé**:Python 3.6 ou supérieur est recommandé.
- **Aspose.Slides pour Python**:Installer en utilisant pip :
  ```bash
  pip install aspose.slides
  ```
- **Licence**: Obtenez une licence d'essai gratuite d'Aspose pour explorer toutes les fonctionnalités sans limitations.

#### Prérequis en matière de connaissances

Une connaissance de base de la programmation Python et une compréhension des présentations PowerPoint seront utiles. Si vous débutez dans ces domaines, pensez d'abord à explorer les ressources d'introduction.

### Configuration d'Aspose.Slides pour Python

Pour démarrer avec Aspose.Slides pour Python, suivez ces étapes simples :

1. **Installation**: Utilisez pip pour installer la bibliothèque :
   ```bash
   pip install aspose.slides
   ```

2. **Acquisition de licence**: 
   - Visite [Page d'achat d'Aspose](https://purchase.aspose.com/buy) pour acheter une licence ou obtenir un essai gratuit temporaire.
   - Appliquez votre licence en utilisant l'extrait de code suivant dans votre projet :
     ```python
     import aspose.slides as slides

     # Charger le fichier de licence
     license = slides.License()
     license.set_license("path_to_your_license.lic")
     ```

3. **Initialisation de base**:
   Commencez par importer Aspose.Slides et lancer un objet de présentation.

### Guide de mise en œuvre

#### Fonctionnalité 1 : Créer une présentation avec un graphique

Cette fonctionnalité montrera comment créer une présentation PowerPoint et ajouter un graphique à secteurs à la première diapositive.

##### Ajout du graphique

Commencez par créer une nouvelle présentation et ajoutez un graphique à secteurs à la position (50, 50) sur la première diapositive :

```python
import aspose.slides as slides

with slides.Presentation() as presentation:
    # Ajouter un graphique « Pie of Pie » avec des dimensions spécifiées
    chart = presentation.slides[0].shapes.add_chart(
        slides.charts.ChartType.PIE_OF_PIE, 50, 50, 500, 400)
```

##### Configuration des étiquettes de données

Pour améliorer la lisibilité, configurez les étiquettes de données pour afficher les valeurs :

```python
# Activer l'affichage des valeurs dans les étiquettes de données pour une meilleure clarté
chart.chart_data.series[0].labels.default_data_label_format.show_value = True
```

##### Définition des options de tarte à tarte

Configurez des propriétés spécifiques pour le graphique à secteurs, telles que la taille du deuxième secteur et la position de division :

```python
# Définir la taille du deuxième graphique et les propriétés de division
chart.chart_data.series[0].parent_series_group.second_pie_size = 149
chart.chart_data.series[0].parent_series_group.pie_split_by = slides.charts.PieSplitType.BY_PERCENTAGE
chart.chart_data.series[0].parent_series_group.pie_split_position = 53
```

##### Enregistrer la présentation

Enfin, enregistrez votre présentation dans le répertoire souhaité :

```python
# Enregistrer la présentation avec le graphique
presentation.save("YOUR_OUTPUT_DIRECTORY/charts_second_plot_options_out.pptx", slides.export.SaveFormat.PPTX)
```

### Applications pratiques

Le graphique Pie of Pie est polyvalent et peut être utilisé dans divers scénarios :

1. **Rapports d'activité**:Visualisez la répartition des données entre différents départements ou produits.
2. **Projets académiques**: Présenter les résultats de l’enquête en montrant les principaux thèmes ainsi que les résultats moins significatifs.
3. **Analyse financière**:Comparez les dépenses principales avec les coûts secondaires dans un rapport budgétaire.

### Considérations relatives aux performances

Pour des performances optimales lors de l'utilisation d'Aspose.Slides :

- Réduisez le nombre de diapositives et de graphiques si possible pour réduire l’utilisation de la mémoire.
- Nettoyez régulièrement les ressources ou références inutilisées dans votre code.
- Utilisez le ramasse-miettes intégré de Python (`gc` module) pour gérer efficacement la mémoire.

### Conclusion

Vous avez appris à créer une présentation PowerPoint avec un graphique à secteurs avec Aspose.Slides pour Python. Cette compétence peut grandement améliorer l'attrait visuel et l'efficacité de vos présentations. N'hésitez pas à explorer d'autres fonctionnalités d'Aspose.Slides, comme l'ajout d'animations ou l'intégration d'éléments multimédias.

### Prochaines étapes

- Expérimentez avec différents types de graphiques disponibles dans Aspose.Slides.
- Intégrez cette fonctionnalité dans un flux de travail d’automatisation de présentation plus vaste.

### Section FAQ

**Q : Puis-je personnaliser les couleurs du graphique à secteurs ?**
: Oui, vous pouvez personnaliser les couleurs du graphique à l’aide du `fill_format` propriété pour chaque segment.

**Q : Comment gérer de grands ensembles de données avec Aspose.Slides ?**
A : Optimisez votre saisie de données et envisagez de les diviser en morceaux plus petits pour maintenir les performances.

**Q : Existe-t-il un moyen d’automatiser l’ajout de plusieurs graphiques en une seule fois ?**
R : Oui, parcourez vos ensembles de données et utilisez le `add_chart` méthode dans un contexte de présentation unique.

### Ressources

- **Documentation**: Explorez des guides détaillés sur [Documentation Aspose.Slides](https://reference.aspose.com/slides/python-net/).
- **Télécharger**: Obtenez la dernière version à partir de [Communiqués](https://releases.aspose.com/slides/python-net/).
- **Achat et essai gratuit**:Accédez aux options de licence sur [Achat Aspose](https://purchase.aspose.com/buy) ou essayez un [Essai gratuit](https://releases.aspose.com/slides/python-net/).
- **Soutien**:Rejoignez la discussion sur [Forum Aspose](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}