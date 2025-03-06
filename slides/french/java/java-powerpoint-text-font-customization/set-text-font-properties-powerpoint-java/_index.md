---
title: Définir les propriétés de la police de texte dans PowerPoint avec Java
linktitle: Définir les propriétés de la police de texte dans PowerPoint avec Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment définir les propriétés de police de texte dans PowerPoint à l'aide d'Aspose.Slides pour Java. Guide simple étape par étape pour les développeurs Java.#Apprenez à manipuler les propriétés de la police de texte PowerPoint à l'aide d'Aspose.Slides pour Java avec ce didacticiel étape par étape pour les développeurs Java.
weight: 18
url: /fr/java/java-powerpoint-text-font-customization/set-text-font-properties-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introduction
Dans ce didacticiel, vous apprendrez à utiliser Aspose.Slides for Java pour définir par programme diverses propriétés de police de texte dans une présentation PowerPoint. Nous aborderons la définition du type de police, du style (gras, italique), du soulignement, de la taille et de la couleur du texte dans les diapositives.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
- JDK installé sur votre système.
-  Aspose.Slides pour la bibliothèque Java. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/slides/java/).
- Connaissance de base de la programmation Java.
- Configuration d'un environnement de développement intégré (IDE) tel qu'IntelliJ IDEA ou Eclipse.
## Importer des packages
Tout d’abord, assurez-vous d’avoir importé les classes Aspose.Slides nécessaires :
```java
import com.aspose.slides.*;
import java.awt.*;
```
## Étape 1 : Configurez votre projet Java
Créez un nouveau projet Java dans votre IDE et ajoutez la bibliothèque Aspose.Slides au chemin de construction de votre projet.
## Étape 2 : initialiser l'objet de présentation
 Instancier un`Presentation` objet pour travailler avec des fichiers PowerPoint :
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
## Étape 3 : accéder à la diapositive et ajouter une forme automatique
Obtenez la première diapositive et ajoutez-y une forme automatique (rectangle) :
```java
ISlide slide = presentation.getSlides().get_Item(0);
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 50, 50, 200, 50);
```
## Étape 4 : définir le texte sur la forme automatique
Définissez le contenu du texte sur la forme automatique :
```java
ITextFrame textFrame = shape.getTextFrame();
textFrame.setText("Aspose TextBox");
```
## Étape 5 : Définir les propriétés de la police
Accédez à la partie du texte et définissez diverses propriétés de police :
```java
IPortion portion = textFrame.getParagraphs().get_Item(0).getPortions().get_Item(0);
// Définir la famille de polices
portion.getPortionFormat().setLatinFont(new FontData("Times New Roman"));
// Mettre en gras
portion.getPortionFormat().setFontBold(NullableBool.True);
// Mettre en italique
portion.getPortionFormat().setFontItalic(NullableBool.True);
// Définir le soulignement
portion.getPortionFormat().setFontUnderline(TextUnderlineType.Single);
// Définir la taille de la police
portion.getPortionFormat().setFontHeight(25);
// Définir la couleur de la police
portion.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
portion.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
```
## Étape 6 : Enregistrer la présentation
Enregistrez la présentation modifiée dans un fichier :
```java
presentation.save(dataDir + "SetTextFontProperties_out.pptx", SaveFormat.Pptx);
```
## Étape 7 : Ressources de nettoyage
Supprimez l’objet Présentation pour libérer des ressources :
```java
if (presentation != null) {
    presentation.dispose();
}
```

## Conclusion
Dans ce didacticiel, vous avez appris à utiliser Aspose.Slides for Java pour personnaliser dynamiquement les propriétés de police de texte dans les diapositives PowerPoint. En suivant ces étapes, vous pouvez formater efficacement le texte pour répondre à des exigences de conception spécifiques par programmation.
## FAQ
### Puis-je appliquer ces modifications de police au texte existant dans une diapositive PowerPoint ?
 Oui, vous pouvez modifier le texte existant en accédant à son`Portion` et appliquer les propriétés de police souhaitées.
### Comment puis-je changer la couleur de la police en un dégradé ou un motif de remplissage ?
 Au lieu de`SolidFillColor` , utiliser`GradientFillColor` ou`PatternedFillColor` par conséquent.
### Aspose.Slides est-il compatible avec les modèles PowerPoint (.potx) ?
Oui, vous pouvez utiliser Aspose.Slides pour travailler avec des modèles PowerPoint.
### Aspose.Slides prend-il en charge l'exportation au format PDF ?
Oui, Aspose.Slides permet d'exporter des présentations vers différents formats, dont PDF.
### Où puis-je trouver plus d’aide et de support pour Aspose.Slides ?
 Visite[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) pour le soutien et les conseils de la communauté.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
