---
"date": "2025-04-23"
"description": "Apprenez à personnaliser les couleurs des hyperliens dans vos présentations PowerPoint avec Aspose.Slides pour Python. Améliorez efficacement vos diapositives avec des styles de liens personnalisés."
"title": "Comment définir les couleurs des hyperliens dans PowerPoint avec Aspose.Slides pour Python"
"url": "/fr/python-net/formatting-styles/aspose-slides-python-hyperlink-colors-powerpoint/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment définir les couleurs des hyperliens dans PowerPoint avec Aspose.Slides pour Python

## Introduction

Améliorer l'attrait visuel de vos présentations PowerPoint en personnalisant les couleurs des hyperliens est simple avec Aspose.Slides pour Python. Ce guide vous explique comment définir des hyperliens avec des couleurs spécifiques dans vos diapositives avec Python.

**Ce que vous apprendrez :**
- Comment définir une couleur d’hyperlien dans les formes de texte dans PowerPoint.
- Étapes impliquées dans la création d’une présentation visuellement attrayante.
- Principales fonctionnalités d’Aspose.Slides pour Python qui facilitent cette personnalisation.

Plongeons dans les prérequis nécessaires avant de commencer.

## Prérequis

Avant de commencer, assurez-vous que votre environnement est prêt avec les éléments suivants :
- **Bibliothèques et versions :** Installer `aspose.slides` bibliothèque. Assurez-vous que Python est installé sur votre machine.
- **Configuration requise pour l'environnement :** Ce tutoriel suppose une configuration de base de Python sur Windows, Mac ou Linux.
- **Prérequis en matière de connaissances :** Une connaissance de la programmation Python sera bénéfique.

## Configuration d'Aspose.Slides pour Python

Pour commencer à utiliser Aspose.Slides pour Python, installez le package via pip :

```bash
pip install aspose.slides
```

**Étapes d'acquisition de la licence :**
- **Essai gratuit :** Téléchargez une version d'essai à partir de [Page de sortie d'Aspose](https://releases.aspose.com/slides/python-net/).
- **Licence temporaire :** Demandez un permis temporaire sur le [page d'achat](https://purchase.aspose.com/temporary-license/) pour un accès étendu.
- **Achat:** Pour débloquer toutes les fonctionnalités sans limitations, pensez à acheter une licence auprès de [Page d'achat d'Aspose](https://purchase.aspose.com/buy).

**Initialisation de base :**
Une fois installé et licencié, importez Aspose.Slides dans votre script :

```python
import aspose.slides as slides
```

## Guide de mise en œuvre

Cette section vous guide dans la définition des couleurs des hyperliens dans une présentation PowerPoint.

### Définir la fonction de couleur du lien hypertexte

#### Aperçu

Personnalisez la couleur des hyperliens intégrés aux formes de texte avec Aspose.Slides pour Python. Cela améliore la lisibilité et l'attrait visuel.

##### Étape 1 : Créer une nouvelle présentation

Créer une instance d’une présentation :

```python
with slides.Presentation() as presentation:
    # Votre code ici
```

##### Étape 2 : ajouter une forme avec du texte

Ajoutez une forme rectangulaire à la première diapositive et insérez du texte qui inclut un lien hypertexte.

```python
shape1 = presentation.slides[0].shapes.add_auto_shape(
    slides.ShapeType.RECTANGLE, 100, 100, 450, 50, False)

shape1.add_text_frame("This is a sample of colored hyperlink.")
```

##### Étape 3 : définir les propriétés du lien hypertexte

Attribuez l'hyperlien et définissez sa couleur. `hyperlink_click` la propriété spécifie où le lien doit naviguer après avoir cliqué.

```python
shape1.text_frame.paragraphs[0].portions[0].portion_format.hyperlink_click = slides.Hyperlink(
    "https://www.aspose.com/")
# Définissez la source de couleur pour le lien hypertexte vers le format de portion et définissez le type de remplissage et la couleur.
shape1.text_frame.paragraphs[0].portions[0].portion_format.hyperlink_click.color_source = slides.HyperlinkColorSource.PORTION_FORMAT
shape1.text_frame.paragraphs[0].portions[0].portion_format.fill_format.fill_type = slides.FillType.SOLID
shape1.text_frame.paragraphs[0].portions[0].portion_format.fill_format.solid_fill_color.color = drawing.Color.red
```

##### Étape 4 : Enregistrer la présentation

Enregistrez votre présentation dans un répertoire spécifié :

```python\presentation.save("YOUR_OUTPUT_DIRECTORY/hyperlink_set_color_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}