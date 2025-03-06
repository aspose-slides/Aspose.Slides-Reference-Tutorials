---
title: Définir les valeurs de hauteur de police locale dans PowerPoint à l'aide de Java
linktitle: Définir les valeurs de hauteur de police locale dans PowerPoint à l'aide de Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment ajuster la hauteur des polices dans les présentations PowerPoint à l'aide de Java avec Aspose.Slides. Améliorez facilement la mise en forme du texte dans vos diapositives.
weight: 17
url: /fr/java/java-powerpoint-text-font-customization/set-local-font-height-values-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introduction
Dans ce didacticiel, vous apprendrez à manipuler les hauteurs de police à différents niveaux dans les présentations PowerPoint à l'aide d'Aspose.Slides pour Java. Le contrôle de la taille des polices est crucial pour créer des présentations visuellement attrayantes et structurées. Nous passerons en revue des exemples étape par étape pour illustrer comment définir la hauteur de police pour différents éléments de texte.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
- Kit de développement Java (JDK) installé sur votre système
-  Aspose.Slides pour la bibliothèque Java. Vous pouvez le télécharger[ici](https://releases.aspose.com/slides/java/).
- Une compréhension de base de la programmation Java et des présentations PowerPoint
## Importer des packages
Assurez-vous d'inclure les packages Aspose.Slides nécessaires dans votre fichier Java :
```java
import com.aspose.slides.*;
```
## Étape 1 : initialiser un objet de présentation
Tout d’abord, créez un nouvel objet de présentation PowerPoint :
```java
Presentation pres = new Presentation();
```
## Étape 2 : ajouter une forme et un cadre de texte
Ajoutez une forme automatique avec un cadre de texte à la première diapositive :
```java
IAutoShape newShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 400, 75, false);
newShape.addTextFrame("");
```
## Étape 3 : Créer des portions de texte
Définissez des portions de texte avec différentes hauteurs de police :
```java
IPortion portion0 = new Portion("Sample text with first portion");
IPortion portion1 = new Portion(" and second portion.");
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion0);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion1);
```
## Étape 4 : Définir les hauteurs de police
Définissez les hauteurs de police à différents niveaux :
```java
pres.getDefaultTextStyle().getLevel(0).getDefaultPortionFormat().setFontHeight(24);
newShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().getDefaultPortionFormat().setFontHeight(40);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(55);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(1).getPortionFormat().setFontHeight(18);
```
## Étape 5 : Enregistrez la présentation
Enregistrez la présentation modifiée dans un fichier :
```java
pres.save("YourOutputDirectory/SetLocalFontHeightValues.pptx", SaveFormat.Pptx);
```

## Conclusion
Ce didacticiel a montré comment ajuster la hauteur des polices dans les diapositives PowerPoint par programme à l'aide d'Aspose.Slides pour Java. En manipulant les tailles de police à différents niveaux (à l’échelle de la présentation, paragraphe et partie), vous pouvez obtenir un contrôle précis sur le formatage du texte dans vos présentations.
## FAQ
### Qu’est-ce qu’Aspose.Slides pour Java ?
Aspose.Slides pour Java est une API puissante permettant de manipuler des présentations PowerPoint par programme.
### Où puis-je trouver de la documentation pour Aspose.Slides pour Java ?
 Vous pouvez trouver la documentation[ici](https://reference.aspose.com/slides/java/).
### Puis-je essayer Aspose.Slides pour Java avant d’acheter ?
 Oui, vous pouvez bénéficier d'un essai gratuit[ici](https://releases.aspose.com/).
### Comment puis-je obtenir de l’assistance pour Aspose.Slides pour Java ?
 Pour obtenir de l'aide, visitez le[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).
### Où puis-je acheter une licence pour Aspose.Slides pour Java ?
 Vous pouvez acheter une licence[ici](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
