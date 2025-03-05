---
title: Ajouter une image vidéo dans PowerPoint
linktitle: Ajouter une image vidéo dans PowerPoint
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment intégrer de manière transparente du contenu vidéo dans des présentations PowerPoint à l'aide d'Aspose.Slides pour Java. Vos diapositives avec des éléments multimédias pour engager votre public.
type: docs
weight: 17
url: /fr/java/java-powerpoint-shape-media-insertion/add-video-frame-powerpoint/
---
## Introduction
Dans ce didacticiel, nous vous guiderons tout au long du processus d'ajout d'une image vidéo à une présentation PowerPoint à l'aide d'Aspose.Slides pour Java. En suivant ces instructions étape par étape, vous serez en mesure d'intégrer facilement du contenu vidéo dans vos présentations.
## Conditions préalables
Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :
- Kit de développement Java (JDK) installé sur votre système
- Bibliothèque Aspose.Slides pour Java téléchargée et configurée dans votre projet Java
## Importer des packages
Tout d’abord, vous devez importer les packages nécessaires pour utiliser les fonctionnalités Aspose.Slides dans votre code Java. 
```java
import com.aspose.slides.*;

import java.io.File;
```
## Étape 1 : configurer le répertoire de documents
Assurez-vous d'avoir un répertoire configuré pour stocker vos fichiers PowerPoint.
```java
String dataDir = "Your Document Directory";
```
## Étape 2 : Créer un objet de présentation
 Instancier le`Presentation` classe pour représenter le fichier PowerPoint.
```java
Presentation pres = new Presentation();
```
## Étape 3 : Ajouter une image vidéo à la diapositive
Obtenez la première diapositive et ajoutez-y une image vidéo.
```java
ISlide sld = pres.getSlides().get_Item(0);
IVideoFrame vf = sld.getShapes().addVideoFrame(50, 150, 300, 150, dataDir + "video1.avi");
```
## Étape 4 : Définir le mode de lecture et le volume
Définissez le mode de lecture et le volume de l'image vidéo.
```java
vf.setPlayMode(VideoPlayModePreset.Auto);
vf.setVolume(AudioVolumeMode.Loud);
```
## Étape 5 : Enregistrer la présentation
Enregistrez le fichier PowerPoint modifié sur le disque.
```java
pres.save(dataDir + "VideoFrame_out.pptx", SaveFormat.Pptx);
```
## Conclusion
Toutes nos félicitations! Vous avez appris avec succès comment ajouter une image vidéo à une présentation PowerPoint à l'aide d'Aspose.Slides pour Java. Améliorez vos présentations en incorporant des éléments multimédias pour impliquer efficacement votre public.
## FAQ
### Puis-je ajouter des vidéos de n’importe quel format à la présentation PowerPoint ?
Aspose.Slides prend en charge divers formats vidéo tels que AVI, WMV, MP4, etc. Assurez-vous que le format est compatible avec PowerPoint.
### Aspose.Slides est-il compatible avec différentes versions de Java ?
Oui, Aspose.Slides pour Java est compatible avec les versions 6 et supérieures du JDK.
### Comment puis-je ajuster la taille et la position de l'image vidéo ?
 Vous pouvez personnaliser les dimensions et les coordonnées de l'image vidéo en modifiant les paramètres dans le`addVideoFrame` méthode.
### Puis-je contrôler les paramètres de lecture de la vidéo ?
Oui, vous pouvez définir le mode de lecture et le volume de l'image vidéo selon vos préférences.
### Où puis-je trouver plus d’assistance et de ressources pour Aspose.Slides ?
 Visiter le[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) pour obtenir de l'aide, de la documentation et le soutien de la communauté.