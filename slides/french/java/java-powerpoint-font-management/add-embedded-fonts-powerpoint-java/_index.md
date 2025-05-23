---
"description": "Découvrez comment ajouter des polices intégrées à vos présentations PowerPoint avec Java grâce à Aspose.Slides pour Java. Assurez un affichage cohérent sur tous les appareils."
"linktitle": "Ajouter des polices intégrées dans PowerPoint à l'aide de Java"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Ajouter des polices intégrées dans PowerPoint à l'aide de Java"
"url": "/fr/java/java-powerpoint-font-management/add-embedded-fonts-powerpoint-java/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter des polices intégrées dans PowerPoint à l'aide de Java

## Introduction
Dans ce tutoriel, nous vous guiderons dans l'ajout de polices intégrées à vos présentations PowerPoint avec Java, et plus particulièrement avec Aspose.Slides pour Java. Les polices intégrées garantissent l'homogénéité de votre présentation sur différents appareils, même si la police d'origine n'est pas disponible. Découvrons les étapes :
## Prérequis
Avant de commencer, assurez-vous d’avoir les éléments suivants :
1. Kit de développement Java (JDK) : assurez-vous que Java est installé sur votre système.
2. Bibliothèque Aspose.Slides pour Java : Téléchargez et installez la bibliothèque Aspose.Slides pour Java. Vous pouvez l'obtenir ici. [ici](https://releases.aspose.com/slides/java/).

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
## Étape 2 : charger la police source
Ensuite, chargez la police que vous souhaitez intégrer à la présentation. Nous utilisons ici Arial comme exemple :
```java
IFontData sourceFont = new FontData("Arial");
```
## Étape 3 : ajouter des polices intégrées
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
## Étape 4 : Enregistrer la présentation
Enfin, enregistrez la présentation avec les polices intégrées :
```java
presentation.save(dataDir + "AddEmbeddedFont_out.pptx", SaveFormat.Pptx);
```
Félicitations ! Vous avez réussi à intégrer des polices dans votre présentation PowerPoint avec Java.

## Conclusion
L'ajout de polices intégrées à vos présentations PowerPoint garantit un affichage cohérent sur différents appareils, offrant ainsi une expérience visuelle fluide à votre public. Avec Aspose.Slides pour Java, ce processus devient simple et efficace.
## FAQ
### Pourquoi les polices intégrées sont-elles importantes dans les présentations PowerPoint ?
Les polices intégrées garantissent que votre présentation conserve sa mise en forme et son style, même si les polices d'origine ne sont pas disponibles sur l'appareil de visualisation.
### Puis-je intégrer plusieurs polices dans une seule présentation à l’aide d’Aspose.Slides pour Java ?
Oui, vous pouvez intégrer plusieurs polices en parcourant toutes les polices utilisées dans la présentation et en incorporant celles qui ne sont pas intégrées.
### L’intégration de polices augmente-t-elle la taille du fichier de la présentation ?
Oui, l’intégration de polices peut légèrement augmenter la taille du fichier de la présentation, mais elle garantit un affichage cohérent sur différents appareils.
### Existe-t-il des limitations concernant les types de polices pouvant être intégrées ?
Aspose.Slides pour Java prend en charge l'intégration de polices TrueType, qui couvrent une large gamme de polices couramment utilisées dans les présentations.
### Puis-je intégrer des polices par programmation à l'aide d'Aspose.Slides pour Java ?
Oui, comme démontré dans ce didacticiel, vous pouvez intégrer des polices par programmation à l’aide de l’API Aspose.Slides pour Java.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}