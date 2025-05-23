---
"date": "2025-04-23"
"description": "Apprenez à automatiser vos présentations PowerPoint avec Aspose.Slides pour Python. Ce guide explique la configuration, la création de diapositives, l'ajout de formes et l'enregistrement de votre présentation en toute simplicité."
"title": "Créer des présentations PowerPoint avec Aspose.Slides pour Python &#58; guide complet"
"url": "/fr/python-net/getting-started/create-powerpoint-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment créer et enregistrer une présentation PowerPoint avec Aspose.Slides pour Python

## Introduction

Vous souhaitez automatiser la création de présentations PowerPoint avec Python ? Que vous génériez des rapports, des diaporamas ou tout autre support de présentation par programmation, maîtriser cette tâche peut vous faire gagner un temps considérable. Ce tutoriel vous guidera dans la création d'une présentation PowerPoint avec Aspose.Slides pour Python, l'ajout d'une forme automatique (comme une ligne) et son enregistrement en toute simplicité.

**Ce que vous apprendrez :**
- Comment configurer votre environnement pour utiliser Aspose.Slides.
- Le processus de création d'une présentation PowerPoint en Python.
- Ajout de formes aux diapositives par programmation.
- Sauvegardez facilement vos présentations.

Commençons d’abord par les prérequis afin que vous soyez prêt à commencer à coder !

## Prérequis

Avant de commencer, assurez-vous d’avoir les éléments suivants :

1. **Bibliothèques requises**:Vous aurez besoin du `aspose.slides` bibliothèque pour ce tutoriel.
2. **Version Python**:Python 3.x est recommandé (assurez-vous de la compatibilité avec Aspose.Slides).
3. **Configuration de l'environnement**:
   - Installez Python et configurez un environnement virtuel si vous le souhaitez.

4. **Prérequis en matière de connaissances**:
   - Compréhension de base de la programmation Python.
   - Connaissance de la gestion des fichiers en Python.

Une fois votre configuration prête, procédons à l'installation d'Aspose.Slides pour Python.

## Configuration d'Aspose.Slides pour Python

### Installation

Vous pouvez facilement installer Aspose.Slides via pip :

```bash
pip install aspose.slides
```

### Étapes d'acquisition de licence

Aspose.Slides propose un essai gratuit, des licences temporaires et des options d'achat :
- **Essai gratuit**:Pour tester les capacités de la bibliothèque sans limitations.
- **Permis temporaire**:Obtenez ceci à des fins d'évaluation sur votre machine locale.
- **Achat**:Pour une utilisation commerciale à long terme.

Visite [Achat Aspose](https://purchase.aspose.com/buy) Pour explorer ces options, après avoir obtenu une licence, vous pouvez l'installer dans votre code :

```python
import aspose.slides as slides

# Appliquer la licence (en supposant que vous disposez du fichier .lic)
license = slides.License()
license.set_license("path_to_your_licence_file.lic")
```

## Guide de mise en œuvre

Passons maintenant à la création et à l’enregistrement d’une présentation.

### Créer une nouvelle présentation

L’objectif principal de ce didacticiel est de démontrer comment créer une présentation PowerPoint à partir de zéro à l’aide de Python.

#### Aperçu

Nous allons commencer par initialiser le `Presentation` objet qui représente notre fichier de présentation.

```python
import aspose.slides as slides

# Instanciez un objet Presentation qui représente un fichier de présentation avec slides.Presentation() comme présentation :
    # Obtenir la première diapositive (diapositive par défaut ajoutée par Aspose.Slides)
slide = presentation.slides[0]

    # Ajouter une forme automatique de type ligne à la diapositive
slide.shapes.add_auto_shape(slides.ShapeType.LINE, 50, 150, 300, 0)

    # Enregistrer la présentation au format PPTX
presentation.save("YOUR_OUTPUT_DIRECTORY/create_new_presentation_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}