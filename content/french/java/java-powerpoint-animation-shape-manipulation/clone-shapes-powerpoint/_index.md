---
title: Cloner des formes dans PowerPoint
linktitle: Cloner des formes dans PowerPoint
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment cloner des formes dans des présentations PowerPoint à l'aide d'Aspose.Slides pour Java. Rationalisez votre flux de travail avec ce didacticiel facile à suivre.
type: docs
weight: 16
url: /fr/java/java-powerpoint-animation-shape-manipulation/clone-shapes-powerpoint/
---
## Introduction
Dans ce didacticiel, nous verrons comment cloner des formes dans des présentations PowerPoint à l'aide d'Aspose.Slides pour Java. Le clonage de formes vous permet de dupliquer des formes existantes dans une présentation, ce qui peut être particulièrement utile pour créer des mises en page cohérentes ou répéter des éléments sur des diapositives.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les prérequis suivants :
1.  Kit de développement Java (JDK) : assurez-vous que le kit de développement Java est installé sur votre système. Vous pouvez télécharger et installer la dernière version à partir du[site web](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Bibliothèque Aspose.Slides pour Java : téléchargez et incluez la bibliothèque Aspose.Slides pour Java dans votre projet Java. Vous pouvez trouver le lien de téléchargement[ici](https://releases.aspose.com/slides/java/).

## Importer des packages
Pour commencer, vous devrez importer les packages nécessaires dans votre projet Java. Ces packages fournissent les fonctionnalités requises pour travailler avec des présentations PowerPoint à l'aide d'Aspose.Slides pour Java.
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
```
## Étape 1 : Charger la présentation
 Tout d'abord, vous devez charger la présentation PowerPoint contenant les formes que vous souhaitez cloner. Utilisez le`Presentation` classe pour charger la présentation source.
```java
String dataDir = "Your Document Directory";
Presentation srcPres = new Presentation(dataDir + "SourceFrame.pptx");
```
## Étape 2 : cloner les formes
Vous allez ensuite cloner les formes de la présentation source et les ajouter à une nouvelle diapositive dans la même présentation. Cela implique d'accéder aux formes source, de créer une nouvelle diapositive, puis d'ajouter les formes clonées à la nouvelle diapositive.
```java
IShapeCollection sourceShapes = srcPres.getSlides().get_Item(0).getShapes();
ILayoutSlide blankLayout = srcPres.getMasters().get_Item(0).getLayoutSlides().getByType(SlideLayoutType.Blank);
ISlide destSlide = srcPres.getSlides().addEmptySlide(blankLayout);
IShapeCollection destShapes = destSlide.getShapes();
destShapes.addClone(sourceShapes.get_Item(1), 50, 150 + sourceShapes.get_Item(0).getHeight());
destShapes.addClone(sourceShapes.get_Item(2));
destShapes.insertClone(0, sourceShapes.get_Item(0), 50, 150);
```
## Étape 3 : Enregistrez la présentation
Enfin, enregistrez la présentation modifiée avec les formes clonées dans un nouveau fichier.
```java
srcPres.save(dataDir + "CloneShape_out.pptx", SaveFormat.Pptx);
```

## Conclusion
Le clonage de formes dans des présentations PowerPoint à l'aide d'Aspose.Slides pour Java est un processus simple qui peut vous aider à rationaliser votre flux de travail de création de présentation. En suivant les étapes décrites dans ce didacticiel, vous pouvez facilement dupliquer des formes existantes et les personnaliser selon vos besoins.

## FAQ
### Puis-je cloner des formes sur différentes diapositives ?
Oui, vous pouvez cloner des formes de n'importe quelle diapositive de la présentation et les ajouter à une autre diapositive à l'aide d'Aspose.Slides pour Java.
### Y a-t-il des limites au clonage de formes ?
Bien qu'Aspose.Slides pour Java offre des capacités de clonage robustes, les formes ou animations complexes peuvent ne pas être parfaitement répliquées.
### Puis-je modifier les formes clonées après les avoir ajoutées à une diapositive ?
Absolument, une fois les formes clonées et ajoutées à une diapositive, vous pouvez modifier leurs propriétés, leur style et leur contenu selon vos besoins.
### Aspose.Slides pour Java prend-il en charge le clonage d'autres éléments que les formes ?
Oui, vous pouvez cloner des diapositives, du texte, des images et d'autres éléments dans une présentation PowerPoint à l'aide d'Aspose.Slides pour Java.
### Existe-t-il une version d’essai disponible pour Aspose.Slides pour Java ?
 Oui, vous pouvez télécharger une version d'essai gratuite d'Aspose.Slides pour Java à partir du[site web](https://releases.aspose.com/slides/java/).