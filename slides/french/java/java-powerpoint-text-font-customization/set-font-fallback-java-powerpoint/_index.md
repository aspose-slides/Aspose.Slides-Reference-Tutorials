---
"description": "Découvrez comment définir des polices de secours dans Java PowerPoint à l’aide d’Aspose.Slides pour Java pour garantir un affichage de texte cohérent."
"linktitle": "Définir la police de secours dans Java PowerPoint"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Définir la police de secours dans Java PowerPoint"
"url": "/fr/java/java-powerpoint-text-font-customization/set-font-fallback-java-powerpoint/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Définir la police de secours dans Java PowerPoint

## Introduction
Dans ce tutoriel, nous explorerons les subtilités de la configuration des polices de secours dans les présentations PowerPoint Java à l'aide d'Aspose.Slides pour Java. Les polices de secours sont essentielles pour garantir l'affichage correct du texte de vos présentations sur différents appareils et systèmes d'exploitation, même lorsque les polices requises ne sont pas disponibles.
## Prérequis
Avant de commencer, assurez-vous d’avoir les éléments suivants :
- Java Development Kit (JDK) installé sur votre système.
- Bibliothèque Aspose.Slides pour Java. Vous pouvez la télécharger ici. [ici](https://releases.aspose.com/slides/java/).
- Compréhension de base du langage de programmation Java.
- Environnement de développement intégré (IDE) tel qu'IntelliJ IDEA ou Eclipse.

## Importer des packages
Tout d’abord, incluez les packages Aspose.Slides pour Java nécessaires dans votre classe Java :
```java
import com.aspose.slides.FontFallBackRule;
import com.aspose.slides.IFontFallBackRule;
```
## Étape 1 : Initialiser les règles de secours des polices
Pour définir des polices de secours, vous devez définir des règles spécifiant les plages Unicode et les polices de secours correspondantes. Voici comment initialiser ces règles :
```java
long startUnicodeIndex = 0x0B80;
long endUnicodeIndex = 0x0BFF;
IFontFallBackRule firstRule = new FontFallBackRule(startUnicodeIndex, endUnicodeIndex, "Vijaya");
IFontFallBackRule secondRule = new FontFallBackRule(0x3040, 0x309F, "MS Mincho, MS Gothic");
String[] fontNames = new String[]{"Segoe UI Emoji, Segoe UI Symbol", "Arial"};
IFontFallBackRule thirdRule = new FontFallBackRule(0x1F300, 0x1F64F, fontNames);
```
## Étape 2 : Appliquer les règles de secours des polices
Appliquez ensuite ces règles à la présentation ou à la diapositive où les polices de secours doivent être définies. Voici un exemple d'application de ces règles à une diapositive de présentation PowerPoint :
```java
// En supposant que la diapositive soit votre objet Slide
slide.getFontsManager().setFontFallBackRules(new IFontFallBackRule[]{firstRule, secondRule, thirdRule});
```

## Conclusion
Définir des polices de secours dans les présentations PowerPoint Java avec Aspose.Slides pour Java est essentiel pour garantir un affichage cohérent du texte dans différents environnements. En définissant des règles de secours, comme illustré dans ce tutoriel, vous pouvez gérer les situations où certaines polices ne sont pas disponibles, préservant ainsi l'intégrité de vos présentations.

## FAQ
### Quelles sont les polices de secours dans les présentations PowerPoint ?
Les polices de secours garantissent que le texte s'affiche correctement en remplaçant les polices disponibles par celles qui ne sont pas installées.
### Comment puis-je télécharger Aspose.Slides pour Java ?
Vous pouvez télécharger Aspose.Slides pour Java à partir de [ici](https://releases.aspose.com/slides/java/).
### Aspose.Slides pour Java est-il compatible avec tous les IDE Java ?
Oui, Aspose.Slides pour Java est compatible avec les IDE Java populaires comme IntelliJ IDEA et Eclipse.
### Puis-je obtenir des licences temporaires pour les produits Aspose ?
Oui, des licences temporaires pour les produits Aspose peuvent être obtenues auprès de [ici](https://purchase.aspose.com/temporary-license/).
### Où puis-je trouver du support pour Aspose.Slides pour Java ?
Pour obtenir de l'aide concernant Aspose.Slides pour Java, visitez le [Forum Aspose](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}