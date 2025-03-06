---
title: Ajouter une image vidéo intégrée dans PowerPoint
linktitle: Ajouter une image vidéo intégrée dans PowerPoint
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment intégrer des images vidéo dans PowerPoint à l'aide d'Aspose.Slides pour Java avec ce didacticiel étape par étape. Améliorez facilement vos présentations.
weight: 21
url: /fr/java/java-powerpoint-animation-shape-manipulation/add-embedded-video-frame-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter une image vidéo intégrée dans PowerPoint

## Introduction
L'ajout de vidéos à vos présentations PowerPoint peut les rendre plus attrayantes et informatives. En utilisant Aspose.Slides pour Java, vous pouvez facilement intégrer des vidéos directement dans vos diapositives. Dans ce didacticiel, nous vous guiderons pas à pas tout au long du processus, en nous assurant que vous comprenez chaque partie du code et son fonctionnement. Que vous soyez un développeur chevronné ou débutant, ce guide vous aidera à enrichir vos présentations avec des vidéos intégrées.
## Conditions préalables
Avant de plonger dans le code, assurez-vous d'avoir les conditions préalables suivantes en place :
1. Kit de développement Java (JDK) : assurez-vous que JDK est installé sur votre ordinateur.
2. Aspose.Slides pour Java : téléchargez et installez la bibliothèque Aspose.Slides pour Java.
3. Environnement de développement intégré (IDE) : utilisez un IDE comme IntelliJ IDEA ou Eclipse pour une meilleure expérience de développement.
4. Fichier vidéo : disposez d'un fichier vidéo que vous souhaitez intégrer dans votre présentation PowerPoint.
## Importer des packages
Tout d’abord, vous devrez importer les packages nécessaires pour travailler avec Aspose.Slides. Ces importations vous aideront à gérer les diapositives, les vidéos et les fichiers de présentation.
```java
import com.aspose.slides.*;

import java.io.File;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
```
## Étape 1 : Configurez votre environnement
Avant de commencer le codage, assurez-vous que votre environnement est correctement configuré. Cela implique de créer les répertoires nécessaires et de préparer le fichier vidéo.
```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
String videoDir = "Path to Your Video Directory";
String resultPath = "Path to Save Result" + "VideoFrame_out.pptx";
// Créez un répertoire s'il n'est pas déjà présent.
boolean isExists = new File(dataDir).exists();
if (!isExists) new File(dataDir).mkdirs();
```
## Étape 2 : Instancier un cours de présentation
 Créez une instance du`Presentation` classe. Cette classe représente votre fichier PowerPoint.
```java
// Instancier la classe de présentation qui représente le PPTX
Presentation pres = new Presentation();
```
## Étape 3 : Obtenez la première diapositive
Accédez à la première diapositive de la présentation où vous intégrerez la vidéo.
```java
// Obtenez la première diapositive
ISlide sld = pres.getSlides().get_Item(0);
```
## Étape 4 : ajouter la vidéo à la présentation
Intégrez le fichier vidéo dans la présentation. Assurez-vous que le chemin vidéo est correctement spécifié.
```java
// Intégrer une vidéo dans la présentation
IVideo vid = pres.getVideos().addVideo(new FileInputStream(videoDir + "Wildlife.mp4"), LoadingStreamBehavior.ReadStreamAndRelease);
```
## Étape 5 : Ajouter une image vidéo à la diapositive
Créez une image vidéo sur la diapositive et définissez ses dimensions et sa position.
```java
// Ajouter une image vidéo
IVideoFrame vf = sld.getShapes().addVideoFrame(50, 150, 300, 350, vid);
```
## Étape 6 : Configurer les propriétés de l'image vidéo
Réglez la vidéo sur l'image vidéo et configurez ses paramètres de lecture tels que le mode de lecture et le volume.
```java
// Définir la vidéo sur l'image vidéo
vf.setEmbeddedVideo(vid);
// Définir le mode de lecture et le volume de la vidéo
vf.setPlayMode(VideoPlayModePreset.Auto);
vf.setVolume(AudioVolumeMode.Loud);
```
## Étape 7 : Enregistrez la présentation
Enregistrez la présentation avec la vidéo intégrée dans le répertoire spécifié.
```java
// Écrivez le fichier PPTX sur le disque
pres.save(resultPath, SaveFormat.Pptx);
```
## Étape 8 : Nettoyer les ressources
Enfin, supprimez l’objet de présentation pour libérer des ressources.
```java
// Supprimer l'objet de présentation
if (pres != null) pres.dispose();
```
## Conclusion
L'intégration d'une vidéo dans vos présentations PowerPoint à l'aide d'Aspose.Slides pour Java est un processus simple. En suivant les étapes décrites dans ce guide, vous pouvez améliorer vos présentations avec un contenu vidéo attrayant. N'oubliez pas que la pratique rend parfait, alors essayez d'intégrer différentes vidéos et d'ajuster leurs propriétés pour voir ce qui fonctionne le mieux pour vos besoins.
## FAQ
### Puis-je intégrer plusieurs vidéos dans une seule diapositive ?
Oui, vous pouvez intégrer plusieurs vidéos dans une seule diapositive en ajoutant plusieurs images vidéo.
### Comment puis-je contrôler la lecture de la vidéo ?
 Vous pouvez contrôler la lecture à l'aide du`setPlayMode` et`setVolume` méthodes du`IVideoFrame` classe.
### Quels formats vidéo sont pris en charge par Aspose.Slides ?
Aspose.Slides prend en charge divers formats vidéo, notamment MP4, AVI et WMV.
### Ai-je besoin d’une licence pour utiliser Aspose.Slides ?
Oui, vous avez besoin d'une licence valide pour utiliser Aspose.Slides. Vous pouvez obtenir une licence temporaire pour évaluation.
### Puis-je personnaliser la taille et la position de l'image vidéo ?
Oui, vous pouvez personnaliser la taille et la position en définissant les paramètres appropriés lors de l'ajout de l'image vidéo.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
