---
"description": "Apprenez à intégrer facilement du contenu vidéo à vos présentations PowerPoint avec Aspose.Slides pour Java. Ajoutez des éléments multimédias à vos diapositives pour captiver votre public."
"linktitle": "Ajouter une image vidéo dans PowerPoint"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Ajouter une image vidéo dans PowerPoint"
"url": "/fr/java/java-powerpoint-shape-media-insertion/add-video-frame-powerpoint/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter une image vidéo dans PowerPoint

## Introduction
Dans ce tutoriel, nous vous guiderons dans l'ajout d'une image vidéo à une présentation PowerPoint avec Aspose.Slides pour Java. En suivant ces instructions étape par étape, vous pourrez intégrer facilement du contenu vidéo à vos présentations.
## Prérequis
Avant de commencer, assurez-vous de disposer des conditions préalables suivantes :
- Java Development Kit (JDK) installé sur votre système
- Bibliothèque Aspose.Slides pour Java téléchargée et configurée dans votre projet Java
## Importer des packages
Tout d’abord, vous devez importer les packages nécessaires pour utiliser les fonctionnalités d’Aspose.Slides dans votre code Java. 
```java
import com.aspose.slides.*;

import java.io.File;
```
## Étape 1 : Configurer le répertoire de documents
Assurez-vous d’avoir un répertoire configuré pour stocker vos fichiers PowerPoint.
```java
String dataDir = "Your Document Directory";
```
## Étape 2 : Créer un objet de présentation
Instancier le `Presentation` classe pour représenter le fichier PowerPoint.
```java
Presentation pres = new Presentation();
```
## Étape 3 : Ajouter une image vidéo à la diapositive
Prenez la première diapositive et ajoutez-y une image vidéo.
```java
ISlide sld = pres.getSlides().get_Item(0);
IVideoFrame vf = sld.getShapes().addVideoFrame(50, 150, 300, 150, dataDir + "video1.avi");
```
## Étape 4 : définir le mode de lecture et le volume
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
Félicitations ! Vous avez appris à ajouter une image vidéo à une présentation PowerPoint avec Aspose.Slides pour Java. Améliorez vos présentations en intégrant des éléments multimédias pour captiver efficacement votre public.
## FAQ
### Puis-je ajouter des vidéos de n’importe quel format à la présentation PowerPoint ?
Aspose.Slides prend en charge divers formats vidéo tels que AVI, WMV, MP4, etc. Assurez-vous que le format est compatible avec PowerPoint.
### Aspose.Slides est-il compatible avec différentes versions de Java ?
Oui, Aspose.Slides pour Java est compatible avec les versions JDK 6 et supérieures.
### Comment puis-je ajuster la taille et la position de l'image vidéo ?
Vous pouvez personnaliser les dimensions et les coordonnées de l'image vidéo en modifiant les paramètres dans le `addVideoFrame` méthode.
### Puis-je contrôler les paramètres de lecture de la vidéo ?
Oui, vous pouvez définir le mode de lecture et le volume de l'image vidéo selon vos préférences.
### Où puis-je trouver plus d'assistance et de ressources pour Aspose.Slides ?
Visitez le [Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) pour obtenir de l'aide, de la documentation et du soutien communautaire.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}