---
title: Définir le format de remplissage des puces dans SmartArt à l'aide de Java
linktitle: Définir le format de remplissage des puces dans SmartArt à l'aide de Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment définir le format de remplissage des puces dans SmartArt à l'aide de Java avec Aspose.Slides. Guide étape par étape pour une manipulation efficace des présentations.
type: docs
weight: 18
url: /fr/java/java-powerpoint-smartart-manipulation/set-bullet-fill-format-smartart-java/
---
## Introduction
Dans le domaine de la programmation Java, la manipulation efficace des présentations est une exigence courante, notamment lorsqu'il s'agit d'éléments SmartArt. Aspose.Slides pour Java apparaît comme un outil puissant pour de telles tâches, offrant un éventail de fonctionnalités pour gérer les présentations par programme. Dans ce didacticiel, nous approfondirons le processus de définition du format de remplissage des puces dans SmartArt à l'aide de Java avec Aspose.Slides, étape par étape.
## Conditions préalables
Avant de commencer ce didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :
### Kit de développement Java (JDK)
 Vous devez avoir JDK installé sur votre système. Vous pouvez le télécharger depuis le[site web](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) et suivez les instructions d'installation.
### Aspose.Slides pour Java
 Téléchargez et installez Aspose.Slides pour Java à partir du[lien de téléchargement](https://releases.aspose.com/slides/java/). Suivez les instructions d'installation fournies dans la documentation de votre système d'exploitation spécifique.

## Importer des packages
Pour commencer, importez les packages nécessaires dans votre projet Java :
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
#Décomposons l'exemple fourni en plusieurs étapes pour une compréhension claire de la façon de définir le format de remplissage des puces dans SmartArt à l'aide de Java avec Aspose.Slides.
## Étape 1 : Créer un objet de présentation
```java
Presentation presentation = new Presentation();
```
Tout d’abord, créez une nouvelle instance de la classe Présentation, qui représente une présentation PowerPoint.
## Étape 2 : Ajouter un SmartArt
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 500, 400, SmartArtLayoutType.VerticalPictureList);
```
Ensuite, ajoutez une forme SmartArt à la diapositive. Cette ligne de code initialise une nouvelle forme SmartArt avec des dimensions et une disposition spécifiées.
## Étape 3 : accéder au nœud SmartArt
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
Maintenant, accédez au premier nœud (ou à tout nœud souhaité) dans la forme SmartArt pour modifier ses propriétés.
## Étape 4 : Définir le format de remplissage des puces
```java
if (node.getBulletFillFormat() != null) {
    BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
    IPPImage image = presentation.getImages().addImage(img);
    node.getBulletFillFormat().setFillType(FillType.Picture);
    node.getBulletFillFormat().getPictureFillFormat().getPicture().setImage(image);
    node.getBulletFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Stretch);
}
```
Ici, nous vérifions si le format de remplissage des puces est pris en charge. Si tel est le cas, nous chargeons un fichier image et le définissons comme remplissage de puces pour le nœud SmartArt.
## Étape 5 : Enregistrer la présentation
```java
presentation.save(dataDir + "out.pptx", SaveFormat.Pptx);
```
Enfin, enregistrez la présentation modifiée dans un emplacement spécifié.

## Conclusion
Toutes nos félicitations! Vous avez appris avec succès comment définir le format de remplissage des puces dans SmartArt à l'aide de Java avec Aspose.Slides. Cette fonctionnalité ouvre un monde de possibilités pour des présentations dynamiques et visuellement attrayantes dans les applications Java.
## FAQ
### Puis-je utiliser Aspose.Slides pour Java pour créer des présentations à partir de zéro ?
Absolument! Aspose.Slides fournit des API complètes pour créer, modifier et manipuler des présentations entièrement via du code.
### Aspose.Slides est-il compatible avec différentes versions de PowerPoint ?
Oui, Aspose.Slides garantit la compatibilité avec différentes versions de Microsoft PowerPoint, permettant une intégration transparente dans votre flux de travail.
### Puis-je personnaliser les éléments SmartArt au-delà du format de remplissage à puces ?
En effet, Aspose.Slides vous permet de personnaliser tous les aspects des formes SmartArt, notamment la mise en page, le style, le contenu, etc.
### Existe-t-il une version d’essai disponible pour Aspose.Slides pour Java ?
 Oui, vous pouvez explorer les fonctionnalités d’Aspose.Slides avec un essai gratuit. Téléchargez-le simplement depuis le[site web](https://releases.aspose.com/slides/java/) et commencez à explorer.
### Où puis-je trouver de l’assistance pour Aspose.Slides pour Java ?
 Pour toute question ou assistance, vous pouvez visiter le forum Aspose.Slides à l'adresse[ce lien](https://forum.aspose.com/c/slides/11).