---
title: Ajouter des polices intégrées dans PowerPoint à l'aide de Java
linktitle: Ajouter des polices intégrées dans PowerPoint à l'aide de Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment ajouter des polices intégrées aux présentations PowerPoint à l'aide de Java avec Aspose.Slides pour Java. Garantissez un affichage cohérent sur tous les appareils.
type: docs
weight: 10
url: /fr/java/java-powerpoint-font-management/add-embedded-fonts-powerpoint-java/
---
## Introduction
Dans ce didacticiel, nous vous guiderons tout au long du processus d'ajout de polices intégrées aux présentations PowerPoint à l'aide de Java, en tirant spécifiquement parti d'Aspose.Slides pour Java. Les polices intégrées garantissent que votre présentation apparaît cohérente sur différents appareils, même si la police d'origine n'est pas disponible. Passons aux étapes :
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
1. Kit de développement Java (JDK) : assurez-vous que Java est installé sur votre système.
2.  Bibliothèque Aspose.Slides pour Java : téléchargez et installez la bibliothèque Aspose.Slides pour Java. Vous pouvez l'obtenir de[ici](https://releases.aspose.com/slides/java/).

## Importer des packages
Importez les packages nécessaires dans votre projet Java :
```java
import com.aspose.slides.*;
```
## Étape 1 : Charger la présentation
Tout d’abord, chargez la présentation PowerPoint dans laquelle vous souhaitez ajouter des polices intégrées :
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "Fonts.pptx");
```
## Étape 2 : Charger la police source
Ensuite, chargez la police que vous souhaitez intégrer dans la présentation. Ici, nous utilisons Arial comme exemple :
```java
IFontData sourceFont = new FontData("Arial");
```
## Étape 3 : Ajouter des polices intégrées
Parcourez toutes les polices utilisées dans la présentation et ajoutez toutes les polices non intégrées :
```java
IFontData[] allFonts = presentation.getFontsManager().getFonts();
IFontData[] embeddedFonts = presentation.getFontsManager().getEmbeddedFonts();
for (IFontData font : allFonts) {
    boolean embeddedFontsContainsFont = false;
    for (int i = 0; i < embeddedFonts.length; i++) {
        if (embeddedFonts[i].equals(font)) {
            embeddedFontsContainsFont = true;
            break;
        }
    }
    if (!embeddedFontsContainsFont) {
        presentation.getFontsManager().addEmbeddedFont(font, EmbedFontCharacters.All);
        embeddedFonts = presentation.getFontsManager().getEmbeddedFonts();
    }
}
```
## Étape 4 : Enregistrez la présentation
Enfin, enregistrez la présentation avec les polices intégrées :
```java
presentation.save(dataDir + "AddEmbeddedFont_out.pptx", SaveFormat.Pptx);
```
Toutes nos félicitations! Vous avez intégré avec succès des polices dans votre présentation PowerPoint à l'aide de Java.

## Conclusion
L'ajout de polices intégrées à vos présentations PowerPoint garantit un affichage cohérent sur différents appareils, offrant ainsi une expérience visuelle transparente à votre public. Avec Aspose.Slides pour Java, le processus devient simple et efficace.
## FAQ
### Pourquoi les polices intégrées sont-elles importantes dans les présentations PowerPoint ?
Les polices intégrées garantissent que votre présentation conserve sa mise en forme et son style, même si les polices d'origine ne sont pas disponibles sur l'appareil de visualisation.
### Puis-je intégrer plusieurs polices dans une seule présentation à l’aide d’Aspose.Slides pour Java ?
Oui, vous pouvez intégrer plusieurs polices en parcourant toutes les polices utilisées dans la présentation et en incorporant celles qui ne sont pas intégrées.
### L'intégration de polices augmente-t-elle la taille du fichier de la présentation ?
Oui, l'intégration de polices peut légèrement augmenter la taille du fichier de la présentation, mais elle garantit un affichage cohérent sur différents appareils.
### Existe-t-il des limitations sur les types de polices pouvant être intégrées ?
Aspose.Slides pour Java prend en charge l'intégration des polices TrueType, qui couvrent un large éventail de polices couramment utilisées dans les présentations.
### Puis-je intégrer des polices par programme à l’aide d’Aspose.Slides pour Java ?
Oui, comme démontré dans ce didacticiel, vous pouvez intégrer des polices par programme à l'aide de l'API Aspose.Slides pour Java.