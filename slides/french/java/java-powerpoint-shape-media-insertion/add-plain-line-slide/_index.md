---
"description": "Apprenez à ajouter une ligne simple à une diapositive PowerPoint par programmation avec Aspose.Slides pour Java. Boostez votre productivité grâce à ce guide étape par étape."
"linktitle": "Ajouter une ligne simple à la diapositive"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Ajouter une ligne simple à la diapositive"
"url": "/fr/java/java-powerpoint-shape-media-insertion/add-plain-line-slide/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter une ligne simple à la diapositive

## Introduction
Aspose.Slides pour Java est une bibliothèque puissante qui permet aux développeurs Java de travailler avec des présentations PowerPoint par programmation. Avec Aspose.Slides, vous pouvez créer, modifier et convertir facilement des fichiers PowerPoint, vous faisant gagner du temps et de l'énergie. Dans ce tutoriel, nous vous expliquerons comment ajouter une ligne simple à une diapositive de présentation PowerPoint avec Aspose.Slides pour Java.
## Prérequis
Avant de commencer, assurez-vous de disposer des prérequis suivants :
- Java Development Kit (JDK) installé sur votre système
- Bibliothèque Aspose.Slides pour Java téléchargée et ajoutée à votre projet Java
- Connaissances de base du langage de programmation Java

## Importer des packages
Pour commencer, vous devez importer les packages nécessaires dans votre code Java. Voici comment procéder :
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.ShapeType;

import java.io.File;
```
## Étape 1 : Configurer l’environnement
Commencez par créer un projet Java et ajoutez la bibliothèque Aspose.Slides pour Java à son classpath. Vous pouvez télécharger la bibliothèque ici. [ici](https://releases.aspose.com/slides/java/).
## Étape 2 : Créer une nouvelle présentation
Ensuite, instanciez le `Presentation` classe pour créer une nouvelle présentation PowerPoint.
```java
Presentation pres = new Presentation();
```
## Étape 3 : Ajouter une diapositive
Obtenez la première diapositive de la présentation et stockez-la dans une variable.
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Étape 4 : ajouter une forme de ligne
Ajoutez maintenant une forme automatique de type ligne à la diapositive.
```java
slide.getShapes().addAutoShape(ShapeType.Line, 50, 150, 300, 0);
```
## Étape 5 : Enregistrer la présentation
Enfin, enregistrez la présentation sur le disque.
```java
pres.save("Your Document Directory/LineShape1_out.pptx", SaveFormat.Pptx);
```

## Conclusion
Félicitations ! Vous avez réussi à ajouter une ligne simple à une diapositive de votre présentation PowerPoint avec Aspose.Slides pour Java. Avec Aspose.Slides, vous pouvez facilement manipuler des fichiers PowerPoint par programmation, ouvrant ainsi un monde de possibilités pour vos applications Java.

## FAQ
### Puis-je personnaliser les propriétés de la forme de la ligne ?
Oui, vous pouvez personnaliser diverses propriétés telles que la couleur de la ligne, la largeur, le style et bien plus encore à l'aide de l'API Aspose.Slides.
### Aspose.Slides est-il compatible avec différentes versions de PowerPoint ?
Oui, Aspose.Slides prend en charge divers formats PowerPoint, notamment PPT, PPTX et autres, garantissant la compatibilité entre différentes versions.
### Aspose.Slides prend-il en charge l'ajout d'autres formes en plus des lignes ?
Absolument ! Aspose.Slides propose une large gamme de formes, notamment des rectangles, des cercles, des flèches, etc.
### Puis-je ajouter du texte à la diapositive avec la forme de la ligne ?
Oui, vous pouvez ajouter du texte, des images et d’autres contenus à la diapositive à l’aide de l’API Aspose.Slides.
### Existe-t-il un essai gratuit disponible pour Aspose.Slides ?
Oui, vous pouvez télécharger une version d'essai gratuite d'Aspose.Slides à partir de [ici](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}