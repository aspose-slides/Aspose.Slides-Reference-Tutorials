---
title: Définir l'ajustement automatique du cadre de texte dans Java PowerPoint
linktitle: Définir l'ajustement automatique du cadre de texte dans Java PowerPoint
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment définir l'ajustement automatique des blocs de texte dans Java PowerPoint à l'aide d'Aspose.Slides pour Java. Créez des présentations dynamiques sans effort.
weight: 14
url: /fr/java/java-powerpoint-text-font-customization/set-autofit-text-frame-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introduction
Dans le développement d’applications Java, la création par programme de présentations PowerPoint dynamiques et visuellement attrayantes est une exigence courante. Aspose.Slides pour Java fournit un ensemble puissant d'API pour y parvenir sans effort. Une fonctionnalité essentielle consiste à définir l'ajustement automatique des blocs de texte, garantissant que le texte s'ajuste parfaitement dans les formes sans ajustements manuels. Ce didacticiel vous guidera tout au long du processus, étape par étape, en tirant parti d'Aspose.Slides for Java pour automatiser l'ajustement du texte dans les diapositives PowerPoint.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous d'avoir configuré les conditions préalables suivantes :
- Kit de développement Java (JDK) installé sur votre système
- Bibliothèque Aspose.Slides pour Java téléchargée et référencée dans votre projet Java
- Environnement de développement intégré (IDE) tel qu'IntelliJ IDEA ou Eclipse
### Importer des packages
Tout d'abord, assurez-vous d'importer les classes Aspose.Slides nécessaires dans votre projet Java :
```java
import com.aspose.slides.*;
import java.awt.*;
```
## Étape 1 : Créer une nouvelle présentation
Commencez par créer une nouvelle instance de présentation PowerPoint dans laquelle vous ajouterez des diapositives et des formes.
```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
// Créer une instance de la classe Présentation
Presentation presentation = new Presentation();
```
## Étape 2 : accédez à la diapositive pour ajouter des formes
Accédez à la première diapositive de la présentation dans laquelle vous souhaitez ajouter une forme avec du texte à ajustement automatique.
```java
// Accédez à la première diapositive
ISlide slide = presentation.getSlides().get_Item(0);
```
## Étape 3 : ajouter une forme automatique (rectangle)
Ajoutez une forme automatique (rectangle) à la diapositive à des coordonnées et dimensions spécifiques.
```java
// Ajouter une forme automatique de type Rectangle
IAutoShape ashp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 350, 350);
```
## Étape 4 : ajouter un TextFrame au rectangle
Ajoutez un cadre de texte à la forme du rectangle.
```java
// Ajouter TextFrame au rectangle
ashp.addTextFrame(" ");
ashp.getFillFormat().setFillType(FillType.NoFill);
```
## Étape 5 : Définir l'ajustement automatique pour le cadre de texte
Définissez les propriétés d'ajustement automatique du cadre de texte afin d'ajuster le texte en fonction de la taille de la forme.
```java
// Accéder au bloc de texte
ITextFrame txtFrame = ashp.getTextFrame();
txtFrame.getTextFrameFormat().setAutofitType(TextAutofitType.Shape);
```
## Étape 6 : Ajouter du texte au cadre de texte
Ajoutez du contenu textuel au cadre de texte dans la forme.
```java
// Créer l'objet Paragraphe pour le bloc de texte
IParagraph para = txtFrame.getParagraphs().get_Item(0);
// Créer un objet Portion pour le paragraphe
IPortion portion = para.getPortions().get_Item(0);
portion.setText("A quick brown fox jumps over the lazy dog. A quick brown fox jumps over the lazy dog.");
portion.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
portion.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```
## Étape 7 : Enregistrez la présentation
Enregistrez la présentation modifiée avec le cadre de texte d'ajustement automatique.
```java
// Enregistrer la présentation
presentation.save(dataDir + "formatText_out.pptx", SaveFormat.Pptx);
```

## Conclusion
Dans ce didacticiel, vous avez appris à définir l'ajustement automatique des blocs de texte dans les présentations Java PowerPoint à l'aide d'Aspose.Slides pour Java. En suivant ces étapes, vous pouvez automatiser l'ajustement du texte dans les formes, améliorant ainsi la lisibilité et l'esthétique de vos présentations par programmation.

## FAQ
### Qu’est-ce qu’Aspose.Slides pour Java ?
Aspose.Slides for Java est une API Java robuste qui permet aux développeurs de créer, lire, manipuler et convertir des présentations PowerPoint.
### Comment télécharger Aspose.Slides pour Java ?
 Vous pouvez télécharger Aspose.Slides pour Java à partir de[ici](https://releases.aspose.com/slides/java/).
### Puis-je essayer Aspose.Slides pour Java gratuitement ?
 Oui, vous pouvez obtenir un essai gratuit d'Aspose.Slides pour Java à partir de[ici](https://releases.aspose.com/).
### Où puis-je trouver de la documentation pour Aspose.Slides pour Java ?
 Vous pouvez trouver une documentation détaillée pour Aspose.Slides pour Java[ici](https://reference.aspose.com/slides/java/).
### Comment puis-je obtenir de l’assistance pour Aspose.Slides pour Java ?
 Vous pouvez obtenir une assistance communautaire et professionnelle pour Aspose.Slides for Java à partir de[ici](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
