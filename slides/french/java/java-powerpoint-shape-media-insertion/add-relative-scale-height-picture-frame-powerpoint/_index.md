---
title: Ajouter un cadre photo à hauteur d'échelle relative dans PowerPoint
linktitle: Ajouter un cadre photo à hauteur d'échelle relative dans PowerPoint
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment ajouter des cadres photo à hauteur d'échelle relative dans des présentations PowerPoint à l'aide d'Aspose.Slides pour Java, améliorant ainsi votre contenu visuel.
weight: 15
url: /fr/java/java-powerpoint-shape-media-insertion/add-relative-scale-height-picture-frame-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introduction
Dans ce didacticiel, vous apprendrez à ajouter un cadre d'image avec une hauteur d'échelle relative dans des présentations PowerPoint à l'aide d'Aspose.Slides pour Java.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
1. Kit de développement Java (JDK) installé sur votre système.
2. Bibliothèque Aspose.Slides pour Java téléchargée et ajoutée à votre projet Java.

## Importer des packages
Pour commencer, importez les packages nécessaires dans votre projet Java :
```java
import com.aspose.slides.*;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Étape 1 : Configurez votre projet
Tout d’abord, assurez-vous d’avoir un répertoire configuré pour votre projet et que votre environnement Java est correctement configuré.
## Étape 2 : Instancier un objet de présentation
Créez un nouvel objet de présentation à l'aide d'Aspose.Slides :
```java
Presentation presentation = new Presentation();
```
## Étape 3 : Charger l'image à ajouter
Chargez l'image que vous souhaitez ajouter à la présentation :
```java
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage image = presentation.getImages().addImage(img);
```
## Étape 4 : ajouter un cadre photo à la diapositive
Ajoutez un cadre photo à une diapositive dans la présentation :
```java
IPictureFrame pf = presentation.getSlides().get_Item(0).getShapes().addPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
## Étape 5 : Définir la largeur et la hauteur de l'échelle relative
Définissez la largeur et la hauteur de l'échelle relative du cadre photo :
```java
pf.setRelativeScaleHeight(0.8f);
pf.setRelativeScaleWidth(1.35f);
```
## Étape 6 : Enregistrer la présentation
Enregistrez la présentation avec le cadre photo ajouté :
```java
presentation.save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```

## Conclusion
En suivant ces étapes, vous pouvez facilement ajouter un cadre d'image avec une hauteur d'échelle relative dans les présentations PowerPoint à l'aide d'Aspose.Slides pour Java. Expérimentez avec différentes valeurs d'échelle pour obtenir l'apparence souhaitée pour vos images.

## FAQ
### Puis-je ajouter plusieurs cadres photo à une seule diapositive en utilisant cette méthode ?
Oui, vous pouvez ajouter plusieurs cadres photo à une diapositive en répétant le processus pour chaque image.
### Aspose.Slides pour Java est-il compatible avec toutes les versions de PowerPoint ?
Aspose.Slides pour Java est compatible avec différentes versions de PowerPoint, garantissant une flexibilité dans la création de présentations.
### Puis-je personnaliser la position et la taille du cadre photo ?
 Absolument, vous pouvez ajuster les paramètres de position et de taille dans le`addPictureFrame` méthode adaptée à vos besoins.
### Aspose.Slides pour Java prend-il en charge d'autres formats d'image que JPEG ?
Oui, Aspose.Slides pour Java prend en charge divers formats d'image, notamment PNG, GIF, BMP, etc.
### Existe-t-il un forum communautaire ou un canal d'assistance disponible pour les utilisateurs d'Aspose.Slides ?
Oui, vous pouvez visiter le forum Aspose.Slides pour toute question, discussion ou assistance concernant la bibliothèque.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
