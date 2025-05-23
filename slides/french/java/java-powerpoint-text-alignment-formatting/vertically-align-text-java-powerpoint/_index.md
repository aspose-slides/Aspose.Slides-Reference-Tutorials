---
"description": "Découvrez comment aligner verticalement du texte dans des présentations PowerPoint Java à l'aide d'Aspose.Slides pour une mise en forme transparente des diapositives."
"linktitle": "Aligner verticalement le texte dans Java PowerPoint"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Aligner verticalement le texte dans Java PowerPoint"
"url": "/fr/java/java-powerpoint-text-alignment-formatting/vertically-align-text-java-powerpoint/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aligner verticalement le texte dans Java PowerPoint

## Introduction
Dans ce tutoriel, vous apprendrez à aligner verticalement du texte dans les cellules d'un tableau PowerPoint avec Aspose.Slides pour Java. L'alignement vertical du texte est un aspect crucial de la conception des diapositives, garantissant une présentation soignée et professionnelle de votre contenu. Aspose.Slides offre de puissantes fonctionnalités pour manipuler et mettre en forme vos présentations par programmation, vous offrant ainsi un contrôle total sur chaque aspect de vos diapositives.
## Prérequis
Avant de plonger dans ce tutoriel, assurez-vous de disposer des prérequis suivants :
- Connaissances de base de la programmation Java.
- JDK (Java Development Kit) installé sur votre machine.
- Bibliothèque Aspose.Slides pour Java. Vous pouvez la télécharger ici. [ici](https://releases.aspose.com/slides/java/).
- IDE (environnement de développement intégré) tel que IntelliJ IDEA ou Eclipse installé.

## Importer des packages
Avant de poursuivre le didacticiel, assurez-vous d'importer les packages Aspose.Slides nécessaires dans votre fichier Java :
```java
import com.aspose.slides.*;
import java.awt.*;
```
## Étape 1 : Configurez votre projet Java
Assurez-vous d'avoir configuré un nouveau projet Java dans votre IDE préféré et ajouté la bibliothèque Aspose.Slides au chemin de génération de votre projet.
## Étape 2 : Initialiser l’objet Présentation
Créer une instance de `Presentation` cours pour commencer à travailler avec une nouvelle présentation PowerPoint :
```java
Presentation presentation = new Presentation();
```
## Étape 3 : Accéder à la première diapositive
Récupérez la première diapositive de la présentation pour y ajouter du contenu :
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
Définir le contenu du texte pour des lignes spécifiques du tableau :
```java
tbl.getRows().get_Item(1).get_Item(0).getTextFrame().setText("10");
tbl.getRows().get_Item(2).get_Item(0).getTextFrame().setText("20");
tbl.getRows().get_Item(3).get_Item(0).getTextFrame().setText("30");
```
## Étape 6 : Accéder au cadre de texte et formater le texte
Accédez au cadre de texte et formatez le texte dans une cellule spécifique :
```java
ITextFrame txtFrame = tbl.get_Item(0, 0).getTextFrame();
IParagraph paragraph = txtFrame.getParagraphs().get_Item(0);
IPortion portion = paragraph.getPortions().get_Item(0);
portion.setText("Text here");
portion.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
portion.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```
## Étape 7 : Aligner le texte verticalement
Définir l'alignement vertical du texte dans la cellule :
```java
ICell cell = tbl.get_Item(0, 0);
cell.setTextAnchorType(TextAnchorType.Center);
cell.setTextVerticalType(TextVerticalType.Vertical270);
```
## Étape 8 : Enregistrer la présentation
Enregistrez la présentation modifiée à un emplacement spécifié sur votre disque :
```java
String dataDir = "Your Document Directory";
presentation.save(dataDir + "Vertical_Align_Text_out.pptx", SaveFormat.Pptx);
```
## Étape 9 : Nettoyer les ressources
Jeter le `Presentation` objet de libération de ressources :
```java
if (presentation != null) presentation.dispose();
```

## Conclusion
En suivant ces étapes, vous pouvez aligner verticalement le texte des cellules de tableau de vos présentations PowerPoint Java avec Aspose.Slides. Cette fonctionnalité améliore l'attrait visuel et la clarté de vos diapositives, garantissant ainsi une présentation professionnelle de votre contenu.

## FAQ
### Puis-je aligner verticalement du texte dans d’autres formes que des tableaux ?
Oui, Aspose.Slides fournit des méthodes pour aligner verticalement du texte dans diverses formes, y compris des zones de texte et des espaces réservés.
### Aspose.Slides prend-il également en charge l'alignement horizontal du texte ?
Oui, vous pouvez aligner le texte horizontalement à l’aide de différentes options d’alignement fournies par Aspose.Slides.
### Aspose.Slides est-il compatible avec toutes les versions de PowerPoint ?
Aspose.Slides prend en charge la génération de présentations compatibles avec toutes les principales versions de Microsoft PowerPoint.
### Où puis-je trouver plus d'exemples et de documentation pour Aspose.Slides ?
Visitez le [Documentation Aspose.Slides](https://reference.aspose.com/slides/java/) pour des guides complets, des références API et des exemples de code.
### Comment puis-je obtenir de l'aide pour Aspose.Slides ?
Pour une assistance technique et un soutien communautaire, visitez le [Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}