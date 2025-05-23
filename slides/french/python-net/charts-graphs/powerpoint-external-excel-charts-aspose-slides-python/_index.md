---
"date": "2025-04-23"
"description": "Apprenez à intégrer des graphiques Excel dynamiques à vos présentations PowerPoint avec Aspose.Slides pour Python. Créez facilement des diapositives basées sur des données pour un usage professionnel et pédagogique."
"title": "Créez des présentations PowerPoint avec des graphiques Excel externes à l'aide d'Aspose.Slides pour Python"
"url": "/fr/python-net/charts-graphs/powerpoint-external-excel-charts-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Créer une présentation PowerPoint avec des graphiques Excel externes à l'aide d'Aspose.Slides pour Python

## Comment intégrer des graphiques Excel dans des présentations PowerPoint avec Aspose.Slides pour Python

### Introduction
Créer des présentations dynamiques est essentiel pour les réunions d'affaires, les conférences et les projets personnels. L'intégration fluide de sources de données externes, comme des fichiers Excel, dans les présentations est un défi courant pour les développeurs. Ce tutoriel aborde ce problème en montrant comment utiliser ces outils. **Aspose.Slides pour Python** pour créer des présentations PowerPoint avec des graphiques provenant d'un classeur externe.

À la fin de ce guide, vous apprendrez :
- Comment copier des fichiers de classeur externes à l'aide de Python
- Comment créer et configurer une présentation dans Aspose.Slides
- Comment configurer des graphiques qui extraient des données directement à partir de classeurs Excel

Commençons d’abord par les prérequis !

## Prérequis

### Bibliothèques, versions et dépendances requises
Pour suivre ce tutoriel, vous aurez besoin de :
- **Python** installé sur votre machine (version 3.6 ou ultérieure)
- Le `shutil` bibliothèque pour les opérations sur les fichiers (intégrée à Python)
- **Aspose.Slides pour Python**une bibliothèque puissante pour créer et modifier des présentations PowerPoint

### Configuration requise pour l'environnement
Assurez-vous que les répertoires nécessaires sont configurés :
1. Un répertoire source contenant votre classeur Excel (`charts_external_workbook.xlsx`)
2. Un répertoire de sortie où les fichiers copiés et la présentation générée seront enregistrés

### Prérequis en matière de connaissances
Vous devez avoir des connaissances de base en programmation Python, y compris la gestion des fichiers et l'utilisation des bibliothèques.

## Configuration d'Aspose.Slides pour Python
Pour démarrer avec Aspose.Slides, vous devrez l'installer via pip :
```bash
pip install aspose.slides
```

### Étapes d'acquisition de licence
Aspose propose différentes options de licence, allant d'un essai gratuit à des licences temporaires et complètes. Commencez par demander une licence. [licence d'essai gratuite](https://purchase.aspose.com/temporary-license/) pour explorer ses fonctionnalités.

#### Initialisation et configuration de base
Une fois installé, vous pouvez importer Aspose.Slides dans votre script :
```python
import aspose.slides as slides
```

Cela ouvre la voie à l’intégration transparente de sources de données externes dans les présentations.

## Guide de mise en œuvre

### Fonctionnalité : Copier un classeur externe
**Aperçu:**
Tout d'abord, nous allons montrer comment copier un fichier de classeur externe d'un répertoire source vers un répertoire de sortie cible à l'aide de Python. `shutil` module. Cela garantit que votre présentation a accès aux données nécessaires.

#### Étape 1 : Importer les bibliothèques requises
```python
import shutil
```

#### Étape 2 : Définir les chemins d’accès aux fichiers et copier le classeur
```python
external_workbook_file_name = "charts_external_workbook.xlsx"
source_path = "YOUR_DOCUMENT_DIRECTORY/" + external_workbook_file_name
output_path = "YOUR_OUTPUT_DIRECTORY/" + external_workbook_file_name
shutil.copyfile(source_path, output_path)
```
Cet extrait copie `charts_external_workbook.xlsx` de votre répertoire de documents vers le répertoire de sortie.

### Fonctionnalité : Créer une présentation et définir un classeur externe pour les données du graphique
**Aperçu:**
Nous allons ensuite créer une présentation et définir un classeur externe comme source de données pour un graphique avec Aspose.Slides. Cela vous permettra de visualiser des données Excel directement dans des diapositives PowerPoint.

#### Étape 1 : Importer Aspose.Slides
```python
import aspose.slides as slides
```

#### Étape 2 : Définir la fonction de création de présentation
```python
def create_presentation_with_external_chart():
    with slides.Presentation() as pres:
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.PIE, 50, 50, 400, 600, False)
        
        chart_data = chart.chart_data
        chart_data.set_external_workbook("YOUR_OUTPUT_DIRECTORY/charts_external_workbook.xlsx")
        
        series = chart_data.series.add(chart_data.chart_data_workbook.get_cell(0, "B1"), slides.charts.ChartType.PIE)
        
        # Ajouter des points de données pour la série de secteurs à partir de cellules de classeur externes
        series.data_points.add_data_point_for_pie_series(chart_data.chart_data_workbook.get_cell(0, "B2"))
        series.data_points.add_data_point_for_pie_series(chart_data.chart_data_workbook.get_cell(0, "B3"))
        series.data_points.add_data_point_for_pie_series(chart_data.chart_data_workbook.get_cell(0, "B4"))

        chart_data.categories.add(chart_data.chart_data_workbook.get_cell(0, "A2"))
        chart_data.categories.add(chart_data.chart_data_workbook.get_cell(0, "A3"))
        chart_data.categories.add(chart_data.chart_data_workbook.get_cell(0, "A4"))
        
        pres.save("YOUR_OUTPUT_DIRECTORY/charts_set_external_workbook_out.pptx", slides.export.SaveFormat.PPTX)
```

#### Explication:
- **Créer une présentation**:Nous commençons par ouvrir un nouvel objet de présentation.
- **Ajouter un graphique**:Un graphique à secteurs est ajouté à la première diapositive aux coordonnées et dimensions spécifiées.
- **Définir un classeur externe**: Le chemin du classeur est défini de sorte qu'Aspose.Slides sache d'où extraire les données.
- **Ajouter des séries et des points de données**:Nous configurons des séries avec des cellules spécifiques du classeur externe, permettant des mises à jour dynamiques.

#### Conseils de dépannage :
- Assurez-vous que les chemins d'accès aux fichiers sont corrects ; sinon, vous rencontrerez des erreurs de fichier introuvable.
- Vérifiez que les références de cellule dans votre fichier Excel correspondent à celles utilisées dans votre code pour éviter les problèmes de désalignement des données.

## Applications pratiques
Voici quelques applications pratiques de l’intégration d’Aspose.Slides avec des classeurs externes :
1. **Rapports financiers**:Mettez à jour automatiquement les graphiques dans les présentations trimestrielles en fonction des dernières feuilles de calcul financières.
2. **Présentations basées sur les données**:Intégrez de manière transparente des analyses en temps réel dans les argumentaires de vente ou les mises à jour de projets.
3. **Matériel pédagogique**:Les enseignants peuvent utiliser les données de performance des élèves mises à jour pour créer des rapports personnalisés.
4. **Systèmes de rapports automatisés**: Mettre en œuvre des systèmes automatisés qui génèrent et distribuent des présentations en fonction de nouvelles entrées de données.

## Considérations relatives aux performances
### Optimisation des performances
- Utilisez des chemins de fichiers efficaces et assurez-vous que votre classeur n'est pas excessivement volumineux pour des temps d'accès plus rapides.
- Limitez le nombre de diapositives avec des sources de données externes pour réduire le temps de traitement.

### Directives d'utilisation des ressources
- Surveillez régulièrement l’utilisation de la mémoire, en particulier lorsque vous traitez de grands ensembles de données ou plusieurs présentations simultanément.

### Meilleures pratiques pour la gestion de la mémoire
- Éliminez les objets correctement à l'aide des gestionnaires de contexte (`with` (déclarations) pour libérer rapidement les ressources après utilisation.

## Conclusion
En intégrant Aspose.Slides pour Python à votre flux de travail, vous pouvez créer facilement des présentations PowerPoint dynamiques et basées sur les données. Ce tutoriel a abordé les bases de la copie de classeurs externes et de la configuration de graphiques avec des sources de données dynamiques. Pour approfondir vos compétences, explorez les fonctionnalités supplémentaires d'Aspose.Slides, telles que les transitions entre diapositives ou les effets d'animation.

Prêt à aller plus loin ? Essayez d'appliquer ces techniques à votre prochain projet !

## Section FAQ
1. **Comment installer Aspose.Slides pour Python ?**
   - Utilisez la commande pip : `pip install aspose.slides`.
2. **Puis-je utiliser Aspose.Slides avec d’autres sources de données en plus d’Excel ?**
   - Oui, Aspose.Slides prend en charge divers formats de données, bien que ce didacticiel se concentre sur les classeurs Excel.
3. **Que faire si mon graphique ne s’affiche pas correctement dans la présentation ?**
   - Vérifiez vos références de cellule et assurez-vous que le classeur externe est accessible au moment de l’exécution.
4. **Comment puis-je obtenir une licence temporaire pour Aspose.Slides ?**
   - Visite [Page de licence d'Aspose](https://purchase.aspose.com/temporary-license/) pour demander un permis temporaire.
5. **Existe-t-il des limitations à l’utilisation des fonctionnalités d’essai gratuites d’Aspose.Slides ?**
   - L'essai gratuit peut comporter certaines restrictions d'utilisation, telles que le filigrane dans les fichiers exportés.

## Ressources
- [Documentation Aspose.Slides](https://reference.aspose.com/slides/python-net/)
- [Télécharger Aspose.Slides pour Python](https://releases.aspose.com/slides/python-net/)
- [Acheter une licence](https://purchase.aspose.com/slides)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}