---
title: Ajouter des puces de paragraphe dans PowerPoint à l'aide de Java
linktitle: Ajouter des puces de paragraphe dans PowerPoint à l'aide de Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment ajouter des puces de paragraphe dans les diapositives PowerPoint à l'aide d'Aspose.Slides pour Java. Ce didacticiel vous guide étape par étape avec des exemples de code.
type: docs
weight: 15
url: /fr/java/java-powerpoint-text-paragraph-management/add-paragraph-bullets-powerpoint-java/
---
## Introduction
L'ajout de puces de paragraphe améliore la lisibilité et la structure des présentations PowerPoint. Aspose.Slides pour Java fournit des outils robustes pour manipuler les présentations par programmation, notamment la possibilité de formater le texte avec différents styles de puces. Dans ce didacticiel, vous apprendrez à intégrer des puces dans des diapositives PowerPoint à l'aide de code Java, en tirant parti d'Aspose.Slides.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
- Connaissance de base de la programmation Java.
- JDK (Java Development Kit) installé sur votre système.
-  Aspose.Slides pour la bibliothèque Java. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/slides/java/).

## Importer des packages
Pour commencer, importez les packages Aspose.Slides nécessaires dans votre projet Java :
```java
import com.aspose.slides.*;
import java.awt.*;
import java.io.File;
```
## Étape 1 : Configurez votre projet
Tout d’abord, créez un nouveau projet Java et ajoutez la bibliothèque Aspose.Slides for Java au chemin de génération de votre projet.
## Étape 2 : initialiser une présentation
Initialiser un objet de présentation (`Presentation`) pour commencer à travailler avec des diapositives.
```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
// Création d'une instance de présentation
Presentation pres = new Presentation();
```
## Étape 3 : Accédez à la diapositive et au cadre de texte
Accédez à la diapositive (`ISlide`et son cadre de texte (`ITextFrame`) où vous souhaitez ajouter des puces.
```java
// Accéder à la première diapositive
ISlide slide = pres.getSlides().get_Item(0);
// Ajout et accès à Autoshape
IAutoShape aShp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
// Accéder au cadre de texte de la forme automatique créée
ITextFrame txtFrm = aShp.getTextFrame();
```
## Étape 4 : Créer et formater des paragraphes avec des puces
Créer des paragraphes (`Paragraph`) et définissez leurs styles de puces, leur indentation et leur texte.
```java
// Créer un paragraphe
Paragraph para = new Paragraph();
para.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para.getParagraphFormat().getBullet().setChar((char) 8226);
para.setText("Welcome to Aspose.Slides");
para.getParagraphFormat().setIndent(25);
txtFrm.getParagraphs().add(para);
// Créer un autre paragraphe
Paragraph para2 = new Paragraph();
para2.getParagraphFormat().getBullet().setType(BulletType.Numbered);
para2.getParagraphFormat().getBullet().setNumberedBulletStyle(NumberedBulletStyle.BulletCircleNumWDBlackPlain);
para2.setText("This is numbered bullet");
para2.getParagraphFormat().setIndent(25);
txtFrm.getParagraphs().add(para2);
```
## Étape 5 : Enregistrez la présentation
Enregistrez la présentation modifiée dans un fichier PowerPoint (`PPTX`).
```java
// Écrire la présentation sous forme de fichier PPTX
pres.save(dataDir + "Bullet_out.pptx", SaveFormat.Pptx);
```
## Étape 6 : Nettoyer les ressources
Supprimez l’objet de présentation pour libérer des ressources.
```java
// Supprimer l'objet de présentation
if (pres != null) {
    pres.dispose();
}
```

## Conclusion
L'ajout de puces de paragraphe dans PowerPoint à l'aide d'Aspose.Slides pour Java est simple grâce aux exemples de code fournis. Personnalisez les styles de puces et le formatage en fonction de vos besoins de présentation.

## FAQ
### Puis-je personnaliser les couleurs des puces ?
Oui, vous pouvez définir des couleurs personnalisées pour les puces à l'aide de l'API Aspose.Slides.
### Comment ajouter des puces imbriquées ?
L'imbrication des puces implique l'ajout de paragraphes dans les paragraphes, en ajustant l'indentation en conséquence.
### Puis-je créer différents styles de puces pour différentes diapositives ?
Oui, vous pouvez appliquer des styles de puces uniques à différentes diapositives par programmation.
### Aspose.Slides est-il compatible avec Java 11 ?
Oui, Aspose.Slides prend en charge Java 11 et les versions supérieures.
### Où puis-je trouver plus d’exemples et de documentation ?
 Visite[Aspose.Slides pour Java Documentation](https://reference.aspose.com/slides/java/) pour des guides et des exemples complets.