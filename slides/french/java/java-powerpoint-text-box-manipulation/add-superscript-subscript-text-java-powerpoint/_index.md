---
title: Ajouter du texte en exposant et en indice dans Java PowerPoint
linktitle: Ajouter du texte en exposant et en indice dans Java PowerPoint
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment ajouter du texte en exposant et en indice dans des présentations Java PowerPoint à l'aide d'Aspose.Slides pour Java. Parfait pour améliorer vos diapositives.
weight: 13
url: /fr/java/java-powerpoint-text-box-manipulation/add-superscript-subscript-text-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter du texte en exposant et en indice dans Java PowerPoint

## Introduction
La création de présentations PowerPoint attrayantes et informatives nécessite souvent l’utilisation de fonctionnalités de formatage telles que le texte en exposant et en indice. Ce didacticiel vous guidera tout au long du processus d'incorporation de texte en exposant et en indice dans vos présentations Java PowerPoint à l'aide d'Aspose.Slides pour Java.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
- Kit de développement Java (JDK) installé sur votre système.
-  Aspose.Slides pour la bibliothèque Java. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/slides/java/).
- Un environnement de développement intégré (IDE) tel qu'IntelliJ IDEA ou Eclipse configuré pour le développement Java.
- Familiarité de base avec la programmation Java et les présentations PowerPoint.

## Importer des packages
Tout d’abord, importez les packages nécessaires depuis Aspose.Slides pour Java :
```java
import com.aspose.slides.*;
```
## Étape 1 : Configurer la présentation
```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
## Étape 2 : accéder à la diapositive
```java
// Obtenez la première diapositive
ISlide slide = presentation.getSlides().get_Item(0);
```
## Étape 3 : Créer une zone de texte
```java
// Créer une forme automatique pour servir de zone de texte
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
ITextFrame textFrame = shape.getTextFrame();
textFrame.getParagraphs().clear();
```
## Étape 4 : ajouter du texte en exposant
```java
// Créer un paragraphe pour le texte principal
IParagraph mainParagraph = new Paragraph();
IPortion mainPortion = new Portion();
mainPortion.setText("SlideTitle");
mainParagraph.getPortions().add(mainPortion);
// Créer une partie pour le texte en exposant
IPortion superPortion = new Portion();
superPortion.getPortionFormat().setEscapement(30); // Définir l'échappement pour l'exposant
superPortion.setText("TM");
mainParagraph.getPortions().add(superPortion);
//Ajoutez le paragraphe principal avec l'exposant à la zone de texte
textFrame.getParagraphs().add(mainParagraph);
```
## Étape 5 : ajouter du texte en indice
```java
// Créer un autre paragraphe pour le texte en indice
IParagraph subscriptParagraph = new Paragraph();
IPortion subscriptPortion = new Portion();
subscriptPortion.setText("a");
subscriptParagraph.getPortions().add(subscriptPortion);
// Créer une partie pour le texte en indice
IPortion subPortion = new Portion();
subPortion.getPortionFormat().setEscapement(-25); // Définir l'échappement pour l'indice
subPortion.setText("i");
subscriptParagraph.getPortions().add(subPortion);
// Ajouter le paragraphe d'indice à la zone de texte
textFrame.getParagraphs().add(subscriptParagraph);
```
## Étape 6 : Enregistrez la présentation
```java
// Enregistrez la présentation
presentation.save(dataDir + "TestOut.pptx", SaveFormat.Pptx);
```

## Conclusion
Dans ce didacticiel, nous avons exploré comment améliorer vos présentations Java PowerPoint avec du texte en exposant et en indice à l'aide d'Aspose.Slides pour Java. En suivant ces étapes, vous pouvez créer des diapositives plus attrayantes et informatives qui communiquent efficacement votre contenu.

## FAQ
### Qu’est-ce qu’Aspose.Slides pour Java ?
Aspose.Slides pour Java est une bibliothèque robuste qui permet aux développeurs de créer, manipuler et convertir des présentations PowerPoint par programme.
### Où puis-je trouver plus de documentation sur Aspose.Slides pour Java ?
 Une documentation détaillée peut être trouvée[ici](https://reference.aspose.com/slides/java/).
### Comment puis-je obtenir une licence temporaire pour Aspose.Slides pour Java ?
 Vous pouvez obtenir une licence temporaire[ici](https://purchase.aspose.com/temporary-license/).
### Puis-je essayer Aspose.Slides pour Java gratuitement ?
 Oui, vous pouvez télécharger une version d'essai gratuite à partir de[ici](https://releases.aspose.com/).
### Où puis-je obtenir de l'aide pour Aspose.Slides pour Java ?
 Pour obtenir de l'aide et des discussions, visitez le[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
