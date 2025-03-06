---
title: Ajouter une ligne simple à la diapositive
linktitle: Ajouter une ligne simple à la diapositive
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment ajouter une ligne simple à une diapositive PowerPoint par programme à l'aide d'Aspose.Slides pour Java. Boostez votre productivité avec ce guide étape par étape.
weight: 14
url: /fr/java/java-powerpoint-shape-media-insertion/add-plain-line-slide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introduction
Aspose.Slides for Java est une bibliothèque puissante qui permet aux développeurs Java de travailler avec des présentations PowerPoint par programme. Avec Aspose.Slides, vous pouvez créer, modifier et convertir facilement des fichiers PowerPoint, ce qui vous fait gagner du temps et des efforts. Dans ce didacticiel, nous vous guiderons tout au long du processus d'ajout d'une ligne simple à une diapositive dans une présentation PowerPoint à l'aide d'Aspose.Slides pour Java.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les prérequis suivants :
- Kit de développement Java (JDK) installé sur votre système
- Bibliothèque Aspose.Slides pour Java téléchargée et ajoutée à votre projet Java
- Connaissance de base du langage de programmation Java

## Importer des packages
Pour commencer, vous devez importer les packages nécessaires dans votre code Java. Voici comment procéder :
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.ShapeType;

import java.io.File;
```
## Étape 1 : configurer l'environnement
 Tout d’abord, créez un nouveau projet Java et ajoutez la bibliothèque Aspose.Slides for Java au chemin de classe de votre projet. Vous pouvez télécharger la bibliothèque depuis[ici](https://releases.aspose.com/slides/java/).
## Étape 2 : Créer une nouvelle présentation
 Ensuite, instanciez le`Presentation` classe pour créer une nouvelle présentation PowerPoint.
```java
Presentation pres = new Presentation();
```
## Étape 3 : ajouter une diapositive
Récupérez la première diapositive de la présentation et stockez-la dans une variable.
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Étape 4 : ajouter une forme de ligne
Maintenant, ajoutez une forme automatique de type ligne à la diapositive.
```java
slide.getShapes().addAutoShape(ShapeType.Line, 50, 150, 300, 0);
```
## Étape 5 : Enregistrez la présentation
Enfin, enregistrez la présentation sur le disque.
```java
pres.save("Your Document Directory/LineShape1_out.pptx", SaveFormat.Pptx);
```

## Conclusion
Toutes nos félicitations! Vous avez ajouté avec succès une ligne simple à une diapositive dans une présentation PowerPoint à l'aide d'Aspose.Slides pour Java. Avec Aspose.Slides, vous pouvez facilement manipuler des fichiers PowerPoint par programme, ouvrant ainsi un monde de possibilités pour vos applications Java.

## FAQ
### Puis-je personnaliser les propriétés de la forme de la ligne ?
Oui, vous pouvez personnaliser diverses propriétés telles que la couleur de la ligne, la largeur, le style, etc. à l'aide de l'API Aspose.Slides.
### Aspose.Slides est-il compatible avec différentes versions de PowerPoint ?
Oui, Aspose.Slides prend en charge divers formats PowerPoint, notamment PPT, PPTX et autres, garantissant la compatibilité entre les différentes versions.
### Aspose.Slides prend-il en charge l'ajout d'autres formes que les lignes ?
Absolument! Aspose.Slides propose une large gamme de types de formes, notamment des rectangles, des cercles, des flèches, etc.
### Puis-je ajouter du texte à la diapositive avec la forme de la ligne ?
Oui, vous pouvez ajouter du texte, des images et d'autres contenus à la diapositive à l'aide de l'API Aspose.Slides.
### Existe-t-il un essai gratuit disponible pour Aspose.Slides ?
 Oui, vous pouvez télécharger un essai gratuit d’Aspose.Slides à partir de[ici](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
