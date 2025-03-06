---
title: Ajouter une image vidéo à partir d'une source Web dans PowerPoint
linktitle: Ajouter une image vidéo à partir d'une source Web dans PowerPoint
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment améliorer vos présentations PowerPoint en ajoutant des images vidéo à partir de sources Web à l'aide d'Aspose.Slides pour Java.
weight: 18
url: /fr/java/java-powerpoint-shape-media-insertion/add-video-frame-web-source-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Introduction
Dans ce didacticiel, nous apprendrons comment ajouter une image vidéo provenant d'une source Web, telle que YouTube, à une présentation PowerPoint à l'aide d'Aspose.Slides pour Java. En suivant ces instructions étape par étape, vous serez en mesure d'améliorer vos présentations en incorporant des éléments multimédias attrayants.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les prérequis suivants :
- Connaissance de base de la programmation Java.
- JDK (Java Development Kit) installé sur votre système.
-  Bibliothèque Aspose.Slides pour Java téléchargée et ajoutée à votre projet Java. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/slides/java/).
- Une connexion Internet active pour accéder à la source Web (par exemple, YouTube).

## Importer des packages
Tout d'abord, importez les packages nécessaires dans votre projet Java :
```java
import com.aspose.slides.IVideoFrame;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.VideoPlayModePreset;

import java.io.ByteArrayOutputStream;
import java.io.IOException;
import java.io.InputStream;
import java.net.URL;
import java.net.URLConnection;
```
## Étape 1 : Créer un objet de présentation PowerPoint
Initialisez un objet Présentation, qui représente une présentation PowerPoint :
```java
Presentation pres = new Presentation();
```
## Étape 2 : ajouter une image vidéo
Maintenant, ajoutons une image vidéo à la présentation. Ce cadre contiendra la vidéo de la source Web. Nous utiliserons la méthode addVideoFrame :
```java
IVideoFrame videoFrame = pres.getSlides().get_Item(0).getShapes().addVideoFrame(10, 10, 427, 240, "https://www.youtube.com/embed/VIDEO_ID");
```
Remplacez "VIDEO_ID" par l'ID de la vidéo YouTube que vous souhaitez intégrer.
## Étape 3 : Définir le mode de lecture vidéo
Définissez le mode de lecture de l'image vidéo. Dans cet exemple, nous le définirons sur Auto :
```java
videoFrame.setPlayMode(VideoPlayModePreset.Auto);
```
## Étape 4 : Charger la vignette
Pour améliorer l'attrait visuel, nous chargerons la vignette de la vidéo. Cette étape consiste à récupérer l'image miniature à partir de la source Web :
```java
String thumbnailUri = "https://www.youtube.com/watch?v=VIDEO_ID" ;
URL url = new URL(thumbnailUri);
URLConnection connection = url.openConnection();
connection.setConnectTimeout(5000);
connection.setReadTimeout(10000);
try (InputStream input = connection.getInputStream();
     ByteArrayOutputStream output = new ByteArrayOutputStream()) {
    byte[] buffer = new byte[8192];
    for (int count; (count = input.read(buffer)) > 0;) {
        output.write(buffer, 0, count);
    }
    output.toByteArray();
    videoFrame.getPictureFormat().getPicture().setImage(pres.getImages().addImage(output.toByteArray()));
}
```
## Étape 5 : Enregistrez la présentation
Enfin, enregistrez la présentation modifiée :
```java
pres.save("YOUR_DIRECTORY/AddVideoFrameFromWebSource_out.pptx", SaveFormat.Pptx);
```
Remplacez "YOUR_DIRECTORY" par le répertoire dans lequel vous souhaitez enregistrer la présentation.

## Conclusion
Toutes nos félicitations! Vous avez appris avec succès comment ajouter une image vidéo à partir d'une source Web dans PowerPoint à l'aide d'Aspose.Slides pour Java. L'intégration d'éléments multimédias tels que des vidéos peut améliorer considérablement l'impact et l'engagement de vos présentations.
## FAQ
### Puis-je ajouter des vidéos provenant de sources autres que YouTube ?
Oui, vous pouvez ajouter des vidéos provenant de diverses sources Web à condition qu'elles fournissent un lien intégrable.
### Ai-je besoin d’une connexion Internet pour lire la vidéo intégrée ?
Oui, une connexion Internet active est requise pour diffuser la vidéo à partir de la source Web.
### Puis-je personnaliser l’apparence de l’image vidéo ?
Absolument! Aspose.Slides offre de nombreuses options pour personnaliser l'apparence et le comportement des images vidéo.
### Aspose.Slides est-il compatible avec toutes les versions de PowerPoint ?
Aspose.Slides prend en charge une large gamme de versions de PowerPoint, garantissant la compatibilité entre différentes plates-formes.
### Où puis-je trouver plus de ressources et d’assistance pour Aspose.Slides ?
 Vous pouvez visiter le[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) pour obtenir de l'aide, de la documentation et le soutien de la communauté.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
