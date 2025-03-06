---
title: Faire pivoter le texte dans PowerPoint à l'aide de Java
linktitle: Faire pivoter le texte dans PowerPoint à l'aide de Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Apprenez à faire pivoter du texte dans PowerPoint à l'aide de Java avec Aspose.Slides. Tutoriel étape par étape pour les débutants et les utilisateurs avancés.
weight: 10
url: /fr/java/java-powerpoint-text-font-customization/rotate-text-powerpoint-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Introduction
Dans ce didacticiel, nous explorerons comment faire pivoter du texte dans des présentations PowerPoint par programmation à l'aide de Java et Aspose.Slides. La rotation du texte peut être une fonctionnalité utile lors de la conception de diapositives pour créer des présentations visuellement attrayantes.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
- Connaissance de base du langage de programmation Java.
- JDK installé sur votre système.
-  Aspose.Slides pour la bibliothèque Java. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/slides/java/).
- IDE (Integrated Development Environment) tel que IntelliJ IDEA ou Eclipse installé sur votre machine.
## Importer des packages
Tout d'abord, vous devez importer les classes Aspose.Slides nécessaires pour travailler avec des fichiers PowerPoint en Java :
```java
import com.aspose.slides.*;
import java.awt.*;
```
## Étape 1 : Configurez votre projet
Commencez par créer un nouveau projet Java dans votre IDE et ajoutez le fichier JAR Aspose.Slides au chemin de construction de votre projet.
## Étape 2 : initialiser les objets de présentation et de diapositive
```java
// Le chemin d'accès au répertoire dans lequel vous souhaitez enregistrer la présentation
String dataDir = "Your_Document_Directory/";
// Créer une instance de la classe Présentation
Presentation presentation = new Presentation();
// Obtenez la première diapositive
ISlide slide = presentation.getSlides().get_Item(0);
```
## Étape 3 : ajouter une forme rectangulaire
```java
// Ajouter une forme automatique de type Rectangle
IAutoShape ashp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 350, 350);
```
## Étape 4 : ajouter du texte à la forme du rectangle
```java
// Ajouter TextFrame au rectangle
ashp.addTextFrame(" ");
ashp.getFillFormat().setFillType(FillType.NoFill);
// Accéder au bloc de texte
ITextFrame txtFrame = ashp.getTextFrame();
txtFrame.getTextFrameFormat().setTextVerticalType(TextVerticalType.Vertical270);
```
## Étape 5 : Définir le contenu et le style du texte
```java
// Créer l'objet Paragraphe pour le bloc de texte
IParagraph para = txtFrame.getParagraphs().get_Item(0);
// Créer un objet Portion pour le paragraphe
IPortion portion = para.getPortions().get_Item(0);
portion.setText("A quick brown fox jumps over the lazy dog. A quick brown fox jumps over the lazy dog.");
portion.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
portion.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```
## Étape 6 : Enregistrez la présentation
```java
// Enregistrer la présentation
presentation.save(dataDir + "RotateText_out.pptx", SaveFormat.Pptx);
```

## Conclusion
Dans ce didacticiel, nous avons appris à faire pivoter du texte dans des présentations PowerPoint à l'aide de Java et Aspose.Slides. En suivant ces étapes, vous pouvez manipuler dynamiquement l'orientation du texte dans vos diapositives pour améliorer l'impact visuel.
## FAQ
### Puis-je faire pivoter le texte sous n’importe quel angle dans PowerPoint à l’aide d’Aspose.Slides pour Java ?
Oui, vous pouvez spécifier n’importe quel angle souhaité pour la rotation du texte par programmation.
### Aspose.Slides prend-il en charge d'autres options de formatage de texte telles que la taille et l'alignement de la police ?
Absolument, Aspose.Slides fournit des API complètes pour gérer diverses exigences de formatage de texte.
### Comment puis-je démarrer avec Aspose.Slides pour Java ?
 Vous pouvez télécharger un essai gratuit d’Aspose.Slides à partir de[ici](https://releases.aspose.com/) pour découvrir ses fonctionnalités.
### Où puis-je trouver plus de documentation et d’assistance pour Aspose.Slides ?
 Pour une documentation détaillée, visitez[Aspose.Slides pour Java Documentation](https://reference.aspose.com/slides/java/) . Vous pouvez également obtenir le soutien de la communauté sur[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).
### Comment puis-je obtenir une licence temporaire pour Aspose.Slides ?
 Vous pouvez obtenir une licence temporaire auprès de[ici](https://purchase.aspose.com/temporary-license/)pour évaluer Aspose.Slides sans limitations.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
