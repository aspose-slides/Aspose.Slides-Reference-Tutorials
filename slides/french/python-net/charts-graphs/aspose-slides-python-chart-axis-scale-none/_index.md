---
"date": "2025-04-23"
"description": "Découvrez comment personnaliser les échelles des axes des graphiques à l’aide d’Aspose.Slides en Python, avec des étapes détaillées et des exemples de code."
"title": "Comment définir l'échelle des axes d'un graphique sur AUCUNE dans Aspose.Slides pour Python (graphiques et diagrammes)"
"url": "/fr/python-net/charts-graphs/aspose-slides-python-chart-axis-scale-none/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment définir l'échelle de l'axe du graphique sur AUCUNE avec Aspose.Slides Python
## Introduction
Créer des graphiques visuellement attrayants nécessite souvent d'affiner l'échelle des axes. Ce tutoriel montre comment définir l'échelle des unités principales de l'axe horizontal. `NONE` pour un graphique utilisant Aspose.Slides en Python, parfait pour personnaliser la visualisation des données dans vos présentations.
**Ce que vous apprendrez :**
- Configurer Aspose.Slides pour Python.
- Créez et personnalisez des graphiques avec des configurations d’axes spécifiques.
- Enregistrez les présentations par programmation.
- Résoudre les problèmes courants lors de l’utilisation des axes de graphique.

## Prérequis
Avant de commencer, assurez-vous d'avoir les éléments suivants :
### Bibliothèques requises
- **Aspose.Slides pour Python**:Installer via pip. Nécessite Python 3.x ou version ultérieure.
### Configuration de l'environnement
- Installer Python depuis [python.org](https://www.python.org/).
- Utilisez un éditeur de code comme VSCode ou PyCharm.
### Prérequis en matière de connaissances
- Compréhension de base de la programmation Python.
- La connaissance de la gestion des présentations et des graphiques est utile mais pas obligatoire.

## Configuration d'Aspose.Slides pour Python
Pour utiliser Aspose.Slides dans vos projets :
**Installation:**
```bash
pip install aspose.slides
```
### Étapes d'acquisition de licence
- **Essai gratuit**: Téléchargez la version d'essai pour tester les fonctionnalités.
- **Permis temporaire**:Obtenez une licence temporaire pour des tests prolongés.
- **Achat**: Achetez une licence complète pour un accès à long terme.

**Initialisation de base :**
```python
import aspose.slides as slides
```
Cela importe toutes les fonctionnalités d'Aspose.Slides.

## Guide de mise en œuvre
### Création d'un graphique avec une échelle d'axe personnalisée
#### Aperçu
Nous allons créer un graphique de type ZONE et définir l'échelle de son unité principale sur l'axe horizontal `NONE`.
**Étape 1 : Initialiser la présentation**
Commencez par créer une nouvelle instance de présentation :
```python
with slides.Presentation() as pres:
    # D'autres opérations seront réalisées ici.
```
Ce gestionnaire de contexte assure une gestion efficace des ressources.
#### Étape 2 : Ajouter un graphique
Ajoutez un graphique de type ZONE à votre diapositive à des coordonnées et des dimensions spécifiques :
```python
chart = pres.slides[0].shapes.add_chart(slides.charts.ChartType.AREA, 10, 10, 400, 300, True)
```
Cela ajoute un graphique de taille 400x300 pixels à la position (10, 10) sur la première diapositive.
#### Étape 3 : définissez l'échelle de l'axe sur AUCUN
Modifier l'échelle de l'unité principale de l'axe horizontal :
```python
chart.axes.horizontal_axis.major_unit_scale = slides.charts.TimeUnitType.NONE
```
La définition de cette propriété supprime les intervalles de mise à l'échelle prédéfinis le long de l'axe des x.
#### Étape 4 : Enregistrer la présentation
Enregistrez vos modifications dans un fichier au format PPTX :
```python
pres.save("YOUR_OUTPUT_DIRECTORY/charts_time_unit_type_enum_out.pptx", slides.export.SaveFormat.PPTX)
```
Cela enregistre votre graphique personnalisé dans un nouveau fichier de présentation.
### Conseils de dépannage
- Assurer la `aspose.slides` Le paquet est correctement installé. Utilisez `pip show aspose.slides` à vérifier.
- Vérifiez si le répertoire de sortie existe et dispose des autorisations d’écriture appropriées.

## Applications pratiques
La définition des échelles d'axe peut être utile dans :
1. **Rapports financiers**:Concentrez-vous sur des périodes ou des points de données spécifiques sans intervalles prédéfinis.
2. **Présentations scientifiques**:Contrôle précis de la visualisation des données pour les résultats de recherche.
3. **Analyse marketing**: Mettez en évidence les indicateurs clés en supprimant les mises à l’échelle gênantes.

## Considérations relatives aux performances
Lorsque vous travaillez avec Aspose.Slides :
- Utiliser les gestionnaires de contexte (`with` (déclarations) pour gérer efficacement les ressources.
- Gérez efficacement les données en Python pour minimiser la consommation de mémoire.
- Mettez à jour régulièrement les versions de la bibliothèque pour améliorer les performances et corriger les bogues.

## Conclusion
Vous avez appris à personnaliser l'échelle des axes des graphiques avec Aspose.Slides pour Python, améliorant ainsi la clarté de vos présentations. Explorez d'autres fonctionnalités, comme les commandes d'animation, pour améliorer encore vos présentations.
**Prochaines étapes :**
Implémentez cette solution dans un projet pour améliorer la présentation des données !

## Section FAQ
1. **Comment mettre à jour Aspose.Slides ?**
   - Utiliser `pip install --upgrade aspose.slides`.
2. **Puis-je définir les échelles des axes horizontaux et verticaux sur AUCUN ?**
   - Oui, utilisez `chart.axes.vertical_axis.major_unit_scale = slides.charts.TimeUnitType.NONE`.
3. **Que faire si mon graphique ne s'enregistre pas correctement ?**
   - Vérifiez les chemins d’accès aux fichiers et assurez-vous que votre répertoire de sortie est accessible en écriture.
4. **Existe-t-il un moyen de prévisualiser les modifications avant de les enregistrer ?**
   - Aspose.Slides ne fournit pas d'aperçu direct, mais itère avec des scripts plus petits jusqu'à ce qu'il soit satisfait.
5. **Comment gérer les différents types de graphiques ?**
   - Remplacer `ChartType.AREA` avec d'autres types comme `Bar`, `Line`, etc., selon les besoins.

## Ressources
- [Documentation Aspose.Slides](https://reference.aspose.com/slides/python-net/)
- [Télécharger Aspose.Slides pour Python](https://releases.aspose.com/slides/python-net/)
- [Acheter une licence](https://purchase.aspose.com/buy)
- [Essai gratuit](https://releases.aspose.com/slides/python-net/)
- [Permis temporaire](https://purchase.aspose.com/temporary-license/)
- [Forum d'assistance Aspose](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}