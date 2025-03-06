---
title: Ajouter une image à l'intérieur des cellules du tableau dans Java PowerPoint
linktitle: Ajouter une image à l'intérieur des cellules du tableau dans Java PowerPoint
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment ajouter des images à l'intérieur des cellules d'un tableau dans des présentations Java PowerPoint avec ce guide détaillé étape par étape utilisant Aspose.Slides pour Java.
weight: 10
url: /fr/java/java-powerpoint-table-manipulation/add-image-inside-table-cells-java-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Introduction
Si vous souhaitez améliorer vos présentations Java PowerPoint en incorporant des images dans les cellules d'un tableau, vous êtes au bon endroit ! Aujourd'hui, nous allons plonger dans un guide détaillé, étape par étape, utilisant Aspose.Slides pour Java. Ce didacticiel vous guidera tout au long du processus, garantissant que même un novice puisse le suivre et obtenir des résultats époustouflants.
## Conditions préalables
Avant de commencer, assurons-nous que vous disposez de tout ce dont vous avez besoin :
1.  Kit de développement Java (JDK) : assurez-vous que JDK est installé sur votre ordinateur. Vous pouvez le télécharger depuis[Le site d'Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides pour Java : téléchargez la bibliothèque Aspose.Slides à partir du[site web](https://releases.aspose.com/slides/java/).
3. Environnement de développement intégré (IDE) : nous vous recommandons d'utiliser IntelliJ IDEA ou Eclipse pour le développement Java.
4. Fichier image : préparez un fichier image que vous souhaitez intégrer dans les cellules de votre tableau PowerPoint.
Maintenant que vous disposez de tous les prérequis, passons à l’importation des packages nécessaires et à l’écriture du code.
## Importer des packages
Tout d’abord, importez les packages requis dans votre projet Java. Ces packages vous permettront d'utiliser les fonctionnalités fournies par Aspose.Slides et la gestion des images de Java.
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
Décomposons l'exemple en plusieurs étapes pour le rendre plus facile à suivre.
## Étape 1 : configurer la présentation
Commencez par configurer l’objet de présentation et accédez à la première diapositive.
```java
// Définissez le chemin d'accès à votre répertoire de documents
String dataDir = "Your Document Directory";
// Instancier l'objet de classe Présentation
Presentation presentation = new Presentation();
```
Cet extrait de code initialise une nouvelle présentation PowerPoint et la prépare à d'autres modifications.
## Étape 2 : accéder à la première diapositive
Accédez ensuite à la première diapositive de la présentation. Cette diapositive sera le canevas sur lequel nous ajouterons le tableau.
```java
try {
    // Accédez à la première diapositive
    ISlide slide = presentation.getSlides().get_Item(0);
```
## Étape 3 : Définir les dimensions du tableau
Définissez les largeurs des colonnes et les hauteurs des lignes du tableau. Cette étape est cruciale pour garantir que les cellules de votre tableau ont les bonnes dimensions.
```java
    // Définir des colonnes avec des largeurs et des lignes avec des hauteurs
    double[] columns = {150, 150, 150, 150};
    double[] rows = {100, 100, 100, 100, 90};
```
## Étape 4 : Ajouter un tableau à la diapositive
Ajoutez la forme du tableau à la diapositive en utilisant les dimensions spécifiées.
```java
    // Ajouter une forme de tableau à la diapositive
    ITable table = slide.getShapes().addTable(50, 50, columns, rows);
```
## Étape 5 : Charger l'image
Chargez l'image que vous souhaitez intégrer dans la cellule du tableau. Assurez-vous que le fichier image est disponible dans votre répertoire spécifié.
```java
    // Créez un objet BufferedImage pour contenir le fichier image
    BufferedImage image = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
    // Créez un objet IPPImage à l'aide de l'objet bitmap
    IPPImage imgx = presentation.getImages().addImage(image);
```
## Étape 6 : Ajouter une image à la cellule du tableau
Il est maintenant temps d'ajouter l'image à la première cellule du tableau. Configurez le format de remplissage et définissez les propriétés de l'image.
```java
    // Ajouter une image à la première cellule du tableau
    table.get_Item(0, 0).getCellFormat().getFillFormat().setFillType(FillType.Picture);
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Stretch);
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().getPicture().setImage(imgx);
```
## Étape 7 : Ajuster le recadrage de l'image
Ajustez le recadrage de l’image pour qu’il s’adapte parfaitement à la cellule si nécessaire. Cette étape garantit que votre image est parfaite.
```java
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().setCropRight(20);
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().setCropLeft(20);
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().setCropTop(20);
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().setCropBottom(20);
```
## Étape 8 : Enregistrez la présentation
Enfin, enregistrez la présentation modifiée dans le répertoire de votre choix.
```java
    // Enregistrez le PPTX sur le disque
    presentation.save(dataDir + "Image_In_TableCell_out.pptx", SaveFormat.Pptx);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (presentation != null) presentation.dispose();
}
```

## Conclusion
Voilà! En suivant ces étapes, vous pouvez ajouter avec succès des images à l'intérieur des cellules d'un tableau dans une présentation Java PowerPoint à l'aide d'Aspose.Slides. Ce guide couvre tout, de la configuration de votre environnement à l'enregistrement de la présentation finale. J'espère que ce didacticiel vous aidera à créer des présentations plus attrayantes visuellement.
## FAQ
### Qu’est-ce qu’Aspose.Slides pour Java ?
Aspose.Slides for Java est une API puissante pour créer, modifier et gérer des présentations PowerPoint dans des applications Java.
### Existe-t-il un essai gratuit disponible pour Aspose.Slides ?
 Oui, vous pouvez obtenir un[essai gratuit](https://releases.aspose.com/) pour essayer Aspose.Slides avant d’acheter.
### Puis-je utiliser n’importe quel format d’image avec Aspose.Slides ?
Aspose.Slides prend en charge divers formats d'image, notamment JPEG, PNG, BMP, etc.
### Où puis-je trouver une documentation plus détaillée ?
 Vous pouvez vous référer au[Documentation](https://reference.aspose.com/slides/java/) pour des informations plus détaillées et des exemples.
### Comment puis-je acheter Aspose.Slides pour Java ?
 Vous pouvez l'acheter auprès du[Site Aspose](https://purchase.aspose.com/buy).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
