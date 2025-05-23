---
"date": "2025-04-23"
"description": "Apprenez à automatiser la création et la mise en forme de formes rectangulaires dans PowerPoint avec Aspose.Slides pour Python. Améliorez vos compétences en présentation sans effort."
"title": "Automatiser les formes rectangulaires dans PowerPoint avec Aspose.Slides pour Python"
"url": "/fr/python-net/shapes-text/automate-rectangle-shapes-powerpoint-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment créer et formater une forme rectangulaire dans PowerPoint avec Aspose.Slides pour Python
## Introduction
Avez-vous déjà eu besoin d'ajouter rapidement des formes personnalisées à vos présentations PowerPoint, mais le manque d'automatisation vous a-t-il empêché de les utiliser ? Si vous en avez assez de formater manuellement des rectangles diapositive par diapositive, ce tutoriel est là pour vous aider. Grâce à « Aspose.Slides pour Python », nous automatiserons l'ajout et le style d'une forme rectangulaire en quelques lignes de code. À la fin de ce guide, vous maîtriserez :
- Créer une forme rectangulaire par programmation
- Application d'options de formatage telles que la couleur et le style de ligne
- Enregistrez votre présentation en toute simplicité
Plongeons dans la façon dont vous pouvez transformer votre processus de création de diapositives !
### Prérequis
Avant de commencer à coder, assurez-vous d’avoir les éléments suivants prêts :
- **Python** installé sur votre machine (la version 3.6 ou supérieure est recommandée)
- **Aspose.Slides pour Python** bibliothèque, qui nous permet de manipuler des présentations PowerPoint
- Compréhension de base des concepts de programmation Python et familiarité avec l'installation de packages à l'aide de pip
## Configuration d'Aspose.Slides pour Python
### Installation
Pour installer le package Aspose.Slides, ouvrez votre terminal ou votre invite de commande et exécutez :
```bash
pip install aspose.slides
```
Cette commande récupère et installe la dernière version d'Aspose.Slides pour Python à partir de PyPI.
### Acquisition de licence
Aspose.Slides est un produit commercial, mais vous pouvez commencer à l'utiliser grâce à une licence d'essai gratuite. Voici comment l'acquérir :
1. **Essai gratuit :** Visite [Essai gratuit d'Aspose](https://releases.aspose.com/slides/python-net/) et inscrivez-vous pour une évaluation.
2. **Licence temporaire :** Pour des tests plus approfondis sans limitations, demandez une licence temporaire à [Page de licence temporaire](https://purchase.aspose.com/temporary-license/).
3. **Achat:** Lorsque vous êtes prêt à passer en direct, achetez une licence via le [Page d'achat d'Aspose](https://purchase.aspose.com/buy).
Une fois acquise, suivez la documentation pour appliquer votre licence dans votre projet.
### Initialisation de base
Voici comment vous pouvez initialiser Aspose.Slides pour Python :
```python
import aspose.slides as slides
\# Initialiser la classe de présentation
with slides.Presentation() as pres:
    print("Presentation is ready!")
```
Cet extrait configure une nouvelle présentation et confirme qu'elle est prête à être manipulée.
## Guide de mise en œuvre
### Création de la forme rectangulaire
#### Aperçu
Dans cette section, nous nous concentrerons sur l’ajout d’une forme rectangulaire à une diapositive PowerPoint à l’aide d’Aspose.Slides pour Python.
#### Étapes pour créer la forme
1. **Ouvrir ou créer une présentation :**
   ```python
   import aspose.slides as slides
   
   with slides.Presentation() as pres:
       # Nous allons ajouter notre rectangle ici
   ```
2. **Accéder à la diapositive :**
   Récupérez la première diapositive où nous voulons ajouter la forme.
   ```python
   slide = pres.slides[0]
   ```
3. **Ajouter une forme rectangulaire :**
   Utilisez le `add_auto_shape` méthode pour créer un rectangle sur la diapositive.
   ```python
   shape = slide.shapes.add_auto_shape(slides.ShapeType.RECTANGLE, 50, 150, 150, 50)
   ```
   - Paramètres: `ShapeType.RECTANGLE`, position x (50), position y (150), largeur (150), hauteur (50).
### Formatage du rectangle
#### Aperçu
Ensuite, nous appliquerons la mise en forme à notre forme rectangulaire, y compris la couleur de remplissage et le style de ligne.
#### Étapes de formatage
1. **Couleur de remplissage :**
   Définissez un remplissage uni avec une couleur spécifique pour l'arrière-plan du rectangle.
   ```python
   shape.fill_format.fill_type = slides.FillType.SOLID
   shape.fill_format.solid_fill_color.color = drawing.Color.chocolate
   ```
2. **Style de ligne :**
   Personnalisez la ligne du rectangle, y compris sa couleur et sa largeur.
   ```python
   shape.line_format.fill_format.fill_type = slides.FillType.SOLID
   shape.line_format.fill_format.solid_fill_color.color = drawing.Color.black
   shape.line_format.width = 5
   ```
3. **Enregistrer la présentation :**
   Enfin, enregistrez la présentation dans un fichier.
   ```python
   pres.save("YOUR_OUTPUT_DIRECTORY/shapes_formatted_rectangle_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}