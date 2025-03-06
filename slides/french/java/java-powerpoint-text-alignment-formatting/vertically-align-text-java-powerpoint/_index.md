---
title: Aligner verticalement le texte dans Java PowerPoint
linktitle: Aligner verticalement le texte dans Java PowerPoint
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment aligner verticalement le texte dans les présentations Java PowerPoint à l'aide d'Aspose.Slides pour un formatage transparent des diapositives.
weight: 10
url: /fr/java/java-powerpoint-text-alignment-formatting/vertically-align-text-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aligner verticalement le texte dans Java PowerPoint

## Introduction
Dans ce didacticiel, vous apprendrez à aligner verticalement le texte dans les cellules d'un tableau dans une présentation PowerPoint à l'aide d'Aspose.Slides pour Java. L'alignement vertical du texte est un aspect crucial de la conception des diapositives, car il garantit que votre contenu est présenté de manière soignée et professionnelle. Aspose.Slides fournit des fonctionnalités puissantes pour manipuler et formater des présentations par programme, vous donnant un contrôle total sur chaque aspect de vos diapositives.
## Conditions préalables
Avant de vous lancer dans ce didacticiel, assurez-vous d'avoir les prérequis suivants :
- Connaissance de base de la programmation Java.
- JDK (Java Development Kit) installé sur votre machine.
-  Aspose.Slides pour la bibliothèque Java. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/slides/java/).
- IDE (Integrated Development Environment) tel qu'IntelliJ IDEA ou Eclipse installé.

## Importer des packages
Avant de poursuivre le didacticiel, assurez-vous d'importer les packages Aspose.Slides nécessaires dans votre fichier Java :
```java
import com.aspose.slides.*;
import java.awt.*;
```
## Étape 1 : Configurez votre projet Java
Assurez-vous d'avoir configuré un nouveau projet Java dans votre IDE préféré et ajouté la bibliothèque Aspose.Slides au chemin de construction de votre projet.
## Étape 2 : initialiser l'objet Présentation
 Créez une instance du`Presentation` classe pour commencer à travailler avec une nouvelle présentation PowerPoint :
```java
Presentation presentation = new Presentation();
```
## Étape 3 : Accédez à la première diapositive
Obtenez la première diapositive de la présentation pour y ajouter du contenu :
```java
ISlide slide = presentation.getSlides().get_Item(0);
```
## Étape 4 : Définir les dimensions du tableau et ajouter un tableau
Définissez les largeurs de colonnes et les hauteurs de lignes de votre tableau, puis ajoutez la forme du tableau à la diapositive :
```java
double[] dblCols = {120, 120, 120, 120};
double[] dblRows = {100, 100, 100, 100};
ITable tbl = slide.getShapes().addTable(100, 50, dblCols, dblRows);
```
## Étape 5 : Définir le contenu du texte dans les cellules du tableau
Définissez le contenu du texte pour des lignes spécifiques du tableau :
```java
tbl.getRows().get_Item(1).get_Item(0).getTextFrame().setText("10");
tbl.getRows().get_Item(2).get_Item(0).getTextFrame().setText("20");
tbl.getRows().get_Item(3).get_Item(0).getTextFrame().setText("30");
```
## Étape 6 : Accédez au cadre de texte et formatez le texte
Accédez au cadre de texte et formatez le texte dans une cellule spécifique :
```java
ITextFrame txtFrame = tbl.get_Item(0, 0).getTextFrame();
IParagraph paragraph = txtFrame.getParagraphs().get_Item(0);
IPortion portion = paragraph.getPortions().get_Item(0);
portion.setText("Text here");
portion.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
portion.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```
## Étape 7 : aligner le texte verticalement
Définissez l'alignement vertical du texte dans la cellule :
```java
ICell cell = tbl.get_Item(0, 0);
cell.setTextAnchorType(TextAnchorType.Center);
cell.setTextVerticalType(TextVerticalType.Vertical270);
```
## Étape 8 : Enregistrez la présentation
Enregistrez la présentation modifiée dans un emplacement spécifié sur votre disque :
```java
String dataDir = "Your Document Directory";
presentation.save(dataDir + "Vertical_Align_Text_out.pptx", SaveFormat.Pptx);
```
## Étape 9 : Ressources de nettoyage
 Jetez le`Presentation` s'opposer à la libération des ressources :
```java
if (presentation != null) presentation.dispose();
```

## Conclusion
En suivant ces étapes, vous pouvez efficacement aligner verticalement le texte dans les cellules du tableau de vos présentations Java PowerPoint à l'aide d'Aspose.Slides. Cette fonctionnalité améliore l'attrait visuel et la clarté de vos diapositives, garantissant ainsi que votre contenu est présenté de manière professionnelle.

## FAQ
### Puis-je aligner verticalement du texte sous d’autres formes que les tableaux ?
Oui, Aspose.Slides fournit des méthodes pour aligner verticalement du texte sous diverses formes, y compris des zones de texte et des espaces réservés.
### Aspose.Slides prend-il également en charge l'alignement du texte horizontalement ?
Oui, vous pouvez aligner le texte horizontalement en utilisant différentes options d'alignement fournies par Aspose.Slides.
### Aspose.Slides est-il compatible avec toutes les versions de PowerPoint ?
Aspose.Slides prend en charge la génération de présentations compatibles avec toutes les versions majeures de Microsoft PowerPoint.
### Où puis-je trouver plus d’exemples et de documentation pour Aspose.Slides ?
 Visiter le[Documentation Aspose.Slides](https://reference.aspose.com/slides/java/) pour des guides complets, des références API et des exemples de code.
### Comment puis-je obtenir de l'aide pour Aspose.Slides ?
 Pour une assistance technique et un soutien communautaire, visitez le[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
