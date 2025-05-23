---
"date": "2025-04-23"
"description": "Découvrez comment automatiser la création de graphiques SmartArt dans les présentations PowerPoint à l’aide d’Aspose.Slides pour Python, notamment l’extraction et l’enregistrement efficaces des miniatures."
"title": "Comment créer et récupérer des miniatures SmartArt avec Aspose.Slides pour Python"
"url": "/fr/python-net/smart-art-diagrams/aspose-slides-python-smartart-thumbnails/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment créer et récupérer des miniatures SmartArt avec Aspose.Slides pour Python

## Introduction

Créer des présentations visuellement attrayantes est essentiel pour capter l'attention de votre public. Un moyen efficace d'améliorer vos diapositives consiste à intégrer des graphiques dynamiques comme SmartArt dans vos présentations PowerPoint. Si vous cherchez une méthode automatisée pour générer ces visuels et en extraire des vignettes, ce guide sur « Aspose.Slides Python » vous sera précieux.

Grâce à Aspose.Slides pour Python, vous pouvez facilement créer des graphiques SmartArt, accéder à des nœuds spécifiques du graphique, récupérer les miniatures de ces nœuds et enregistrer ces images pour vos projets. Ce tutoriel vous guidera pas à pas.

**Ce que vous apprendrez :**
- Comment installer et configurer Aspose.Slides pour Python.
- Création d’un graphique SmartArt dans une présentation PowerPoint.
- Accéder aux nœuds dans un graphique SmartArt.
- Extraction et enregistrement d'une miniature d'image à partir d'un nœud spécifique.

Examinons les prérequis avant de commencer.

## Prérequis

Avant de commencer, assurez-vous d’avoir les éléments suivants à portée de main :

- **Bibliothèques requises :** Vous aurez besoin d'Aspose.Slides pour Python. Assurez-vous que votre environnement prend en charge Python 3.x.
- **Configuration requise pour l'environnement :** Une installation fonctionnelle de Python et un IDE ou un éditeur de texte approprié comme VSCode ou PyCharm.
- **Prérequis en matière de connaissances :** Compréhension de base de la programmation Python, y compris les définitions de fonctions et les opérations sur les fichiers.

## Configuration d'Aspose.Slides pour Python

Tout d'abord, vous devez installer la bibliothèque Aspose.Slides. Cela se fait facilement avec pip :

```bash
pip install aspose.slides
```

Une fois l'installation terminée, obtenez une licence pour explorer toutes les fonctionnalités sans restriction. Vous pouvez commencer par un essai gratuit, demander une licence temporaire ou l'acheter pour une utilisation à long terme.

Pour initialiser Aspose.Slides dans votre environnement Python, importez la bibliothèque au début de votre script :

```python
import aspose.slides as slides
```

## Guide de mise en œuvre

Décomposons le processus en étapes claires pour créer et récupérer une miniature SmartArt.

### Étape 1 : Créer une nouvelle instance de présentation

Commencez par créer une instance de présentation. Ce sera le conteneur dans lequel vous ajouterez votre graphique SmartArt.

```python
with slides.Presentation() as pres:
```

En utilisant `with` garantit que les ressources sont correctement gérées, en enregistrant et en fermant automatiquement le fichier à la sortie.

### Étape 2 : ajouter SmartArt à la première diapositive

Nous allons maintenant ajouter un graphique SmartArt à notre première diapositive. Voici comment procéder :

```python
smart = pres.slides[0].shapes.add_smart_art(10, 10, 400, 300,
    slides.smartart.SmartArtLayoutType.BASIC_CYCLE)
```

Cela ajoute une disposition de cycle de base pour le graphique SmartArt à la position (10, 10) avec des dimensions de 400x300 pixels.

### Étape 3 : Accéder au deuxième nœud

Accédez à des nœuds spécifiques de votre SmartArt. Dans cet exemple, nous accédons au deuxième nœud :

```python
node = smart.nodes[1]
```

Les nœuds sont indexés à partir de zéro ; par conséquent, `nodes[1]` fait référence au deuxième nœud de la liste.

### Étape 4 : Récupérer la miniature de l'image

Pour obtenir une miniature d’image de la forme dans le nœud sélectionné :

```python
image = node.shapes[0].get_image()
```

Cela récupère l'image de la première forme sous forme de miniature à partir du nœud SmartArt spécifié.

### Étape 5 : Enregistrer l’image récupérée

Enfin, enregistrez cette miniature à l'emplacement souhaité au format JPEG :

```python
image.save("YOUR_OUTPUT_DIRECTORY/shapes_create_smartart_thumbnail_out.jpeg\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}