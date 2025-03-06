---
title: Propriétés de police dans PowerPoint avec Java
linktitle: Propriétés de police dans PowerPoint avec Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Apprenez à manipuler les propriétés de police dans les présentations PowerPoint à l'aide de Java avec Aspose.Slides pour Java. Personnalisez facilement les polices avec ce guide étape par étape.
weight: 11
url: /fr/java/java-powerpoint-font-management/font-properties-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Propriétés de police dans PowerPoint avec Java

## Introduction
Dans ce didacticiel, nous allons explorer comment manipuler les propriétés des polices dans les présentations PowerPoint à l'aide de Java, en particulier avec Aspose.Slides pour Java. Nous vous guiderons à travers chaque étape, depuis l'importation des packages nécessaires jusqu'à l'enregistrement de votre présentation modifiée. Allons-y !
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
1.  Kit de développement Java (JDK) : assurez-vous que JDK est installé sur votre système. Vous pouvez le télécharger depuis[ici](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides pour Java JAR : téléchargez la bibliothèque Aspose.Slides pour Java à partir de[ici](https://releases.aspose.com/slides/java/).
3. Environnement de développement intégré (IDE) : vous pouvez utiliser n'importe quel IDE Java de votre choix, tel que IntelliJ IDEA, Eclipse ou NetBeans.

## Importer des packages
Tout d'abord, importons les packages nécessaires pour travailler avec Aspose.Slides pour Java :
```java
import com.aspose.slides.*;
import java.awt.*;
```
## Étape 1 : Instancier un objet de présentation
 Commencez par créer un`Presentation` objet qui représente votre fichier PowerPoint :
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "FontProperties.pptx");
```
## Étape 2 : accéder aux diapositives et aux espaces réservés
Passons maintenant aux diapositives et aux espaces réservés de votre présentation :
```java
ISlide slide = pres.getSlides().get_Item(0);
ITextFrame tf1 = ((IAutoShape) slide.getShapes().get_Item(0)).getTextFrame();
ITextFrame tf2 = ((IAutoShape) slide.getShapes().get_Item(1)).getTextFrame();
```
## Étape 3 : accéder aux paragraphes et aux portions
Ensuite, nous accéderons aux paragraphes et aux portions dans les cadres de texte :
```java
IParagraph para1 = tf1.getParagraphs().get_Item(0);
IParagraph para2 = tf2.getParagraphs().get_Item(0);
IPortion port1 = para1.getPortions().get_Item(0);
IPortion port2 = para2.getPortions().get_Item(0);
```
## Étape 4 : Définir de nouvelles polices
Définissez les polices que vous souhaitez utiliser pour les portions :
```java
FontData fd1 = new FontData("Elephant");
FontData fd2 = new FontData("Castellar");
```
## Étape 5 : Définir les propriétés de la police
Définissez diverses propriétés de police telles que le gras, l'italique et la couleur :
```java
port1.getPortionFormat().setLatinFont(fd1);
port2.getPortionFormat().setLatinFont(fd2);
port1.getPortionFormat().setFontBold(NullableBool.True);
port2.getPortionFormat().setFontBold(NullableBool.True);
port1.getPortionFormat().setFontItalic(NullableBool.True);
port2.getPortionFormat().setFontItalic(NullableBool.True);
port1.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
port1.getPortionFormat().getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Purple));
port2.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
port2.getPortionFormat().getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Peru));
```
## Étape 6 : Enregistrez la présentation modifiée
Enfin, enregistrez votre présentation modifiée sur le disque :
```java
pres.save(dataDir + "WelcomeFont_out.pptx", SaveFormat.Pptx);
```

## Conclusion
La manipulation des propriétés de police dans les présentations PowerPoint à l'aide de Java est facilitée avec Aspose.Slides pour Java. En suivant les étapes décrites dans ce didacticiel, vous pouvez personnaliser les polices pour améliorer l'attrait visuel de vos diapositives.
## FAQ
### Puis-je utiliser des polices personnalisées avec Aspose.Slides pour Java ?
 Oui, vous pouvez utiliser des polices personnalisées en spécifiant le nom de la police lors de la définition du`FontData`.
### Comment puis-je modifier la taille de la police du texte dans une diapositive PowerPoint ?
 Vous pouvez ajuster la taille de la police en définissant le`FontHeight` propriété du`PortionFormat`.
### Aspose.Slides pour Java prend-il en charge l’ajout d’effets de texte ?
Oui, Aspose.Slides pour Java propose diverses options d'effets de texte pour améliorer vos présentations.
### Existe-t-il une version d’essai disponible pour Aspose.Slides pour Java ?
 Oui, vous pouvez télécharger une version d'essai gratuite à partir de[ici](https://releases.aspose.com/).
### Où puis-je trouver plus d’assistance et de ressources pour Aspose.Slides pour Java ?
 Vous pouvez visiter le forum Aspose.Slides[ici](https://forum.aspose.com/c/slides/11) pour le support et la documentation[ici](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
