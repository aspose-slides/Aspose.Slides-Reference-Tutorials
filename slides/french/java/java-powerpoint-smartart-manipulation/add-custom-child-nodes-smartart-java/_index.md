---
"description": "Apprenez à ajouter des nœuds enfants personnalisés à SmartArt dans vos présentations PowerPoint en Java avec Aspose.Slides. Améliorez vos diapositives avec des graphismes professionnels en toute simplicité."
"linktitle": "Ajouter des nœuds enfants personnalisés dans SmartArt à l'aide de Java"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Ajouter des nœuds enfants personnalisés dans SmartArt à l'aide de Java"
"url": "/fr/java/java-powerpoint-smartart-manipulation/add-custom-child-nodes-smartart-java/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter des nœuds enfants personnalisés dans SmartArt à l'aide de Java

## Introduction
SmartArt est une fonctionnalité puissante de PowerPoint qui permet aux utilisateurs de créer rapidement et facilement des graphiques de qualité professionnelle. Dans ce tutoriel, nous allons apprendre à ajouter des nœuds enfants personnalisés à SmartArt en Java avec Aspose.Slides.
## Prérequis
Avant de commencer, assurez-vous d’avoir les éléments suivants :
1. Kit de développement Java (JDK) : assurez-vous que Java est installé sur votre système.
2. Aspose.Slides pour Java : téléchargez et installez Aspose.Slides pour Java depuis [ici](https://releases.aspose.com/slides/java/).

## Importer des packages
Pour commencer, importez les packages nécessaires dans votre projet Java :
```java
import com.aspose.slides.*;
```
## Étape 1 : Charger la présentation
Chargez la présentation PowerPoint à l'endroit où vous souhaitez ajouter des nœuds enfants personnalisés au SmartArt :
```java
String dataDir = "Your Document Directory";
// Charger la présentation souhaitée
Presentation pres = new Presentation(dataDir + "YourPresentation.pptx");
```
## Étape 2 : ajouter SmartArt à la diapositive
Maintenant, ajoutons SmartArt à la diapositive :
```java
ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(20, 20, 600, 500, SmartArtLayoutType.OrganizationChart);
```
## Étape 3 : Déplacer la forme SmartArt
Déplacez la forme SmartArt vers une nouvelle position :
```java
ISmartArtNode node = smart.getAllNodes().get_Item(1);
ISmartArtShape shape = node.getShapes().get_Item(1);
shape.setX(shape.getX() + (shape.getWidth() * 2));
shape.setY(shape.getY() - (shape.getHeight() / 2));
```
## Étape 4 : modifier la largeur de la forme
Modifier la largeur de la forme SmartArt :
```java
node = smart.getAllNodes().get_Item(2);
shape = node.getShapes().get_Item(1);
shape.setWidth(shape.getWidth() + (shape.getWidth() / 2));
```
## Étape 5 : Modifier la hauteur de la forme
Modifier la hauteur de la forme SmartArt :
```java
node = smart.getAllNodes().get_Item(3);
shape = node.getShapes().get_Item(1);
shape.setHeight(shape.getHeight() + (shape.getHeight() / 2));
```
## Étape 6 : faire pivoter la forme
Faire pivoter la forme SmartArt :
```java
node = smart.getAllNodes().get_Item(4);
shape = node.getShapes().get_Item(1);
shape.setRotation(90);
```
## Étape 7 : Enregistrer la présentation
Enfin, enregistrez la présentation modifiée :
```java
pres.save(dataDir + "ModifiedPresentation.pptx", SaveFormat.Pptx);
```

## Conclusion
Dans ce tutoriel, nous avons appris à ajouter des nœuds enfants personnalisés à SmartArt en Java avec Aspose.Slides. En suivant ces étapes, vous pouvez enrichir vos présentations avec des graphiques personnalisés, les rendant ainsi plus attrayantes et professionnelles.
## FAQ
### Puis-je ajouter différents types de mises en page SmartArt à l’aide d’Aspose.Slides pour Java ?
Oui, Aspose.Slides pour Java prend en charge différentes mises en page SmartArt, vous permettant de choisir celle qui correspond le mieux à vos besoins de présentation.
### Aspose.Slides pour Java est-il compatible avec différentes versions de PowerPoint ?
Aspose.Slides pour Java est conçu pour fonctionner de manière transparente avec différentes versions de PowerPoint, garantissant la compatibilité et la cohérence entre les plates-formes.
### Puis-je personnaliser l’apparence des formes SmartArt par programmation ?
Absolument ! Avec Aspose.Slides pour Java, vous pouvez personnaliser par programmation l'apparence, la taille, la couleur et la disposition des formes SmartArt selon vos préférences de conception.
### Aspose.Slides pour Java fournit-il de la documentation et du support ?
Oui, vous pouvez trouver une documentation complète et accéder aux forums de support communautaire sur le site Web d'Aspose.
### Existe-t-il une version d'essai disponible pour Aspose.Slides pour Java ?
Oui, vous pouvez télécharger une version d'essai gratuite d'Aspose.Slides pour Java à partir du site Web pour explorer ses fonctionnalités et capacités avant de procéder à un achat. [ici](https://releases.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}