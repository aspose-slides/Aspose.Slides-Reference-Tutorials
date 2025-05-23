---
"date": "2025-04-23"
"description": "Apprenez à créer des graphiques en rayons de soleil dynamiques et attrayants avec Aspose.Slides pour Python. Suivez ce guide étape par étape pour améliorer vos présentations de données."
"title": "Comment créer des graphiques Sunburst en Python avec Aspose.Slides"
"url": "/fr/python-net/charts-graphs/create-sunburst-chart-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment créer des graphiques Sunburst en Python avec Aspose.Slides

## Introduction
Créer des graphiques en forme de soleil visuellement attrayants est essentiel pour une visualisation efficace des données, notamment pour la présentation de données hiérarchiques. Ce tutoriel vous guide dans l'utilisation de la puissante bibliothèque Aspose.Slides avec Python pour créer des graphiques en forme de soleil dynamiques adaptés aux rapports d'entreprise et aux ensembles de données complexes.

Dans un monde actuel centré sur les données, des outils comme Aspose.Slides simplifient l'intégration de fonctionnalités graphiques avancées à vos applications. Suivez ce guide de la configuration à la mise en œuvre pour que même les débutants puissent créer facilement des graphiques en forme de soleil attrayants.

**Ce que vous apprendrez :**
- Comment configurer Aspose.Slides pour Python
- Étapes pour initialiser une présentation et ajouter un graphique en forme de soleil
- Configuration des catégories et des séries de données
- Optimiser votre graphique Sunburst pour les performances

Commençons par les prérequis nécessaires avant de commencer !

## Prérequis
Avant de commencer, assurez-vous de disposer des éléments suivants :
- **Environnement Python :** Python 3.x installé sur votre système.
- **Bibliothèque Aspose.Slides :** Installez Aspose.Slides pour Python via PIP. Une connaissance des concepts de base de la programmation Python est requise.

## Configuration d'Aspose.Slides pour Python
Pour créer des graphiques en forme de soleil, assurez-vous d'abord qu'Aspose.Slides est installé dans votre environnement :

```bash
pip install aspose.slides
```

### Acquisition de licence
Aspose propose une licence d'essai gratuite pour explorer toutes les fonctionnalités de ses bibliothèques. Obtenez cette licence temporaire auprès de [Page de licence temporaire d'Aspose](https://purchase.aspose.com/temporary-license/)Pour une utilisation à long terme, pensez à acheter un abonnement sur leur page d'achat.

Une fois installé, initialisez votre configuration Aspose.Slides en Python comme suit :

```python
import aspose.slides as slides

def init_aspose():
    # Initialiser un objet de présentation pour des opérations ultérieures
    with slides.Presentation() as pres:
        print("Aspose.Slides is ready to use!")
```

## Guide de mise en œuvre
### Création du graphique Sunburst
Décomposons les étapes nécessaires pour créer et configurer votre graphique Sunburst à l'aide d'Aspose.Slides.

#### Étape 1 : Initialiser un objet de présentation
Commencez par créer un nouvel objet de présentation, qui agit comme un conteneur pour vos diapositives et graphiques :

```python
def create_sunburst_chart():
    with slides.Presentation() as pres:
        # Cela crée un gestionnaire de contexte pour gérer le cycle de vie de la présentation.
```

#### Étape 2 : Ajouter le graphique Sunburst
Ajoutez un graphique en rayons de soleil aux coordonnées spécifiées dans votre première diapositive. Ajustez sa position et sa taille selon vos besoins :

```python
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.SUNBURST, 50, 50, 500, 400)
        
        # Paramètres : type de graphique, position x, position y, largeur, hauteur
```

#### Étape 3 : Effacer les données existantes
Avant de remplir votre graphique avec des données, effacez toutes les catégories et séries par défaut pour repartir à zéro :

```python
        chart.chart_data.categories.clear()
        chart.chart_data.series.clear()
        
        # Accéder au classeur pour manipuler les données du graphique
        wb = chart.chart_data.chart_data_workbook
        wb.clear(0)  # Efface toutes les cellules du classeur
```

#### Étape 4 : Configurer les catégories et les niveaux de regroupement
Définissez des catégories hiérarchiques en ajoutant des feuilles, des tiges et des branches. Utilisez des niveaux de regroupement pour organiser visuellement vos données :

```python
        # Configuration de la branche 1
        leaf = chart.chart_data.categories.add(wb.get_cell(0, "C1", "Leaf1"))
        leaf.grouping_levels.set_grouping_item(1, "Stem1")
        leaf.grouping_levels.set_grouping_item(2, "Branch1")

        # Ajouter des feuilles supplémentaires sous la branche 1
        chart.chart_data.categories.add(wb.get_cell(0, "C2", "Leaf2"))
```

Continuez ce modèle pour d’autres branches et feuilles si nécessaire.

#### Étape 5 : Ajouter une série de données
Créez une série de données et renseignez-la avec des valeurs. Cette étape relie vos catégories aux points de données correspondants :

```python
        series = chart.chart_data.series.add(slides.charts.ChartType.SUNBURST)
        series.labels.default_data_label_format.show_category_name = True
        
        # Ajout de points de données à la série
        series.data_points.add_data_point_for_sunburst_series(wb.get_cell(0, "D1", 4))
```

#### Étape 6 : Enregistrez votre présentation
Enfin, enregistrez votre présentation avec le graphique en forme de soleil nouvellement créé :

```python
        pres.save("YOUR_OUTPUT_DIRECTORY/charts_sunburst_chart_out.pptx", slides.export.SaveFormat.PPTX)
        
        # Assurez-vous de spécifier un chemin de répertoire de sortie valide
```

### Conseils de dépannage
- **Incohérence des données :** Si vos points de données ne correspondent pas aux catégories, vérifiez vos configurations de catégories et de séries.
- **Le graphique n'apparaît pas :** Vérifiez que la position et la taille du graphique sont dans les limites de la diapositive.

## Applications pratiques
Les graphiques Sunburst excellent dans divers scénarios :
1. **Hiérarchie organisationnelle :** Afficher les structures départementales ou les hiérarchies de gestion de projet.
2. **Analyse des catégories de produits :** Affichez les données de vente sur différentes catégories de produits.
3. **Représentation des données géographiques :** Visualisez la répartition de la population dans les régions et sous-régions.

Ces cas d’utilisation démontrent la flexibilité des graphiques en forme de soleil pour représenter intuitivement des informations hiérarchiques complexes.

## Considérations relatives aux performances
Optimisez les performances de votre graphique Sunburst en :
- Réduire les points de données inutiles pour améliorer la clarté.
- Utilisation de techniques efficaces de gestion de la mémoire fournies par Aspose.Slides pour Python.

Le respect de ces bonnes pratiques garantit un fonctionnement fluide et un rendu graphique réactif.

## Conclusion
Vous maîtrisez désormais la création et la configuration de graphiques en rayons de soleil avec Aspose.Slides en Python. Cette puissante fonctionnalité peut transformer vos présentations, rendant les données complexes plus accessibles et attrayantes. Poursuivez vos expérimentations en intégrant des fonctionnalités supplémentaires à Aspose.Slides pour améliorer vos applications.

**Prochaines étapes :** Explorez le vaste [Documentation Aspose.Slides](https://reference.aspose.com/slides/python-net/) pour des fonctionnalités plus avancées et des options de personnalisation.

## Section FAQ
**Q1 : Comment personnaliser les couleurs de mon tableau Sunburst ?**
A1 : Utilisez le `fill_format` propriété sur chaque point de données pour définir des couleurs personnalisées, améliorant ainsi l'attrait visuel.

**Q2 : Puis-je exporter le graphique sous forme d'image ?**
A2 : Oui, Aspose.Slides prend en charge l’exportation de diapositives et de graphiques vers différents formats tels que JPEG ou PNG.

**Q3 : Que faire si mon graphique ne s’affiche pas correctement dans PowerPoint ?**
A3 : Assurez-vous que les valeurs de vos séries de données sont correctement mappées aux catégories. Revérifiez l'exactitude des niveaux de regroupement.

**Q4 : Est-il possible d'animer le graphique en forme de soleil ?**
A4 : Bien qu’Aspose.Slides prenne en charge les animations, elles doivent être configurées manuellement après la création du graphique dans PowerPoint.

**Q5 : Comment puis-je gérer de grands ensembles de données avec Aspose.Slides ?**
A5 : Optimisez en divisant les données en morceaux gérables et en tirant parti de la gestion efficace de la mémoire de Python.

## Ressources
- **Documentation:** [Documentation Python d'Aspose.Slides](https://reference.aspose.com/slides/python-net/)
- **Télécharger:** [Dernières sorties](https://releases.aspose.com/slides/python-net/)
- **Achat:** [Acheter Aspose.Slides](https://purchase.aspose.com/buy)
- **Essai gratuit :** [Essayez Aspose.Slides gratuitement](https://releases.aspose.com/slides/python-net/)
- **Licence temporaire :** [Demander une licence temporaire](https://purchase.aspose.com/temporary-license/)
- **Soutien:** [Forum d'assistance Aspose](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}