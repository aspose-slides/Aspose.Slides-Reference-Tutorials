---
title: Définir le remplacement des polices dans Java PowerPoint
linktitle: Définir le remplacement des polices dans Java PowerPoint
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment définir des polices de secours dans Java PowerPoint à l'aide d'Aspose.Slides for Java pour garantir un affichage de texte cohérent.
weight: 16
url: /fr/java/java-powerpoint-text-font-customization/set-font-fallback-java-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Introduction
Dans ce didacticiel, nous aborderons les subtilités de la définition des polices de remplacement dans les présentations Java PowerPoint à l'aide d'Aspose.Slides pour Java. Les polices de secours sont cruciales pour garantir que le texte de vos présentations s'affiche correctement sur différents appareils et systèmes d'exploitation, même lorsque les polices requises ne sont pas disponibles.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
- Kit de développement Java (JDK) installé sur votre système.
-  Aspose.Slides pour la bibliothèque Java. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/slides/java/).
- Compréhension de base du langage de programmation Java.
- Environnement de développement intégré (IDE) tel qu'IntelliJ IDEA ou Eclipse.

## Importer des packages
Tout d’abord, incluez les packages Aspose.Slides pour Java nécessaires dans votre classe Java :
```java
import com.aspose.slides.FontFallBackRule;
import com.aspose.slides.IFontFallBackRule;
```
## Étape 1 : initialiser les règles de secours des polices
Pour définir des polices de secours, vous devez définir des règles qui spécifient les plages Unicode et les polices de secours correspondantes. Voici comment initialiser ces règles :
```java
long startUnicodeIndex = 0x0B80;
long endUnicodeIndex = 0x0BFF;
IFontFallBackRule firstRule = new FontFallBackRule(startUnicodeIndex, endUnicodeIndex, "Vijaya");
IFontFallBackRule secondRule = new FontFallBackRule(0x3040, 0x309F, "MS Mincho, MS Gothic");
String[] fontNames = new String[]{"Segoe UI Emoji, Segoe UI Symbol", "Arial"};
IFontFallBackRule thirdRule = new FontFallBackRule(0x1F300, 0x1F64F, fontNames);
```
## Étape 2 : appliquer les règles de remplacement des polices
Ensuite, vous appliquez ces règles à la présentation ou à la diapositive pour laquelle les polices de remplacement doivent être définies. Vous trouverez ci-dessous un exemple d'application de ces règles à une diapositive dans une présentation PowerPoint :
```java
// En supposant que la diapositive soit votre objet Slide
slide.getFontsManager().setFontFallBackRules(new IFontFallBackRule[]{firstRule, secondRule, thirdRule});
```

## Conclusion
La définition de polices de remplacement dans les présentations Java PowerPoint à l'aide d'Aspose.Slides pour Java est essentielle pour garantir un affichage de texte cohérent dans différents environnements. En définissant des règles de secours comme démontré dans ce didacticiel, vous pouvez gérer les situations dans lesquelles des polices spécifiques ne sont pas disponibles, tout en préservant l'intégrité de vos présentations.

## FAQ
### Que sont les polices de remplacement dans les présentations PowerPoint ?
Les polices de secours garantissent que le texte s'affiche correctement en remplaçant les polices disponibles par celles qui ne sont pas installées.
### Comment puis-je télécharger Aspose.Slides pour Java ?
 Vous pouvez télécharger Aspose.Slides pour Java à partir de[ici](https://releases.aspose.com/slides/java/).
### Aspose.Slides pour Java est-il compatible avec tous les IDE Java ?
Oui, Aspose.Slides pour Java est compatible avec les IDE Java populaires tels que IntelliJ IDEA et Eclipse.
### Puis-je obtenir des licences temporaires pour les produits Aspose ?
Oui, des licences temporaires pour les produits Aspose peuvent être obtenues auprès de[ici](https://purchase.aspose.com/temporary-license/).
### Où puis-je trouver de l’assistance pour Aspose.Slides pour Java ?
 Pour obtenir une assistance relative à Aspose.Slides pour Java, visitez le[Forum Aspose](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
