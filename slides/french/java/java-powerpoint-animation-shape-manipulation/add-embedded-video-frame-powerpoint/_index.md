---
"description": "Apprenez à intégrer des images vidéo dans PowerPoint avec Aspose.Slides pour Java grâce à ce tutoriel étape par étape. Améliorez facilement vos présentations."
"linktitle": "Ajouter une image vidéo intégrée dans PowerPoint"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Ajouter une image vidéo intégrée dans PowerPoint"
"url": "/fr/java/java-powerpoint-animation-shape-manipulation/add-embedded-video-frame-powerpoint/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter une image vidéo intégrée dans PowerPoint

## Introduction
Ajouter des vidéos à vos présentations PowerPoint peut les rendre plus attrayantes et informatives. Grâce à Aspose.Slides pour Java, vous pouvez facilement intégrer des vidéos directement dans vos diapositives. Dans ce tutoriel, nous vous guiderons pas à pas pour vous aider à comprendre chaque partie du code et son fonctionnement. Que vous soyez un développeur expérimenté ou débutant, ce guide vous aidera à enrichir vos présentations avec des vidéos intégrées.
## Prérequis
Avant de plonger dans le code, assurez-vous de disposer des prérequis suivants :
1. Kit de développement Java (JDK) : assurez-vous que JDK est installé sur votre machine.
2. Aspose.Slides pour Java : téléchargez et installez la bibliothèque Aspose.Slides pour Java.
3. Environnement de développement intégré (IDE) : utilisez un IDE comme IntelliJ IDEA ou Eclipse pour une meilleure expérience de développement.
4. Fichier vidéo : vous disposez d’un fichier vidéo que vous souhaitez intégrer dans votre présentation PowerPoint.
## Importer des packages
Tout d'abord, vous devrez importer les packages nécessaires pour utiliser Aspose.Slides. Ces importations vous permettront de gérer vos diapositives, vidéos et fichiers de présentation.
```java
import com.aspose.slides.*;

import java.io.File;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
```
## Étape 1 : Configurez votre environnement
Avant de commencer à coder, assurez-vous que votre environnement est correctement configuré. Cela implique de créer les répertoires nécessaires et de préparer le fichier vidéo.
```java
// Le chemin vers le répertoire des documents.
String dataDir = "Your Document Directory";
String videoDir = "Path to Your Video Directory";
String resultPath = "Path to Save Result" + "VideoFrame_out.pptx";
// Créez un répertoire s'il n'est pas déjà présent.
boolean isExists = new File(dataDir).exists();
if (!isExists) new File(dataDir).mkdirs();
```
## Étape 2 : instancier la classe de présentation
Créer une instance de `Presentation` classe. Cette classe représente votre fichier PowerPoint.
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
## Étape 4 : Ajouter la vidéo à la présentation
Intégrez le fichier vidéo à la présentation. Assurez-vous que le chemin d'accès à la vidéo est correctement spécifié.
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
## Étape 6 : Configurer les propriétés de l'image vidéo
Définissez la vidéo sur l'image vidéo et configurez ses paramètres de lecture tels que le mode de lecture et le volume.
```java
// Définir la vidéo sur l'image vidéo
vf.setEmbeddedVideo(vid);
// Définir le mode de lecture et le volume de la vidéo
vf.setPlayMode(VideoPlayModePreset.Auto);
vf.setVolume(AudioVolumeMode.Loud);
```
## Étape 7 : Enregistrer la présentation
Enregistrez la présentation avec la vidéo intégrée dans le répertoire spécifié.
```java
// Écrire le fichier PPTX sur le disque
pres.save(resultPath, SaveFormat.Pptx);
```
## Étape 8 : Nettoyer les ressources
Enfin, supprimez l’objet de présentation pour libérer des ressources.
```java
// Éliminer l'objet de présentation
if (pres != null) pres.dispose();
```
## Conclusion
Intégrer une vidéo dans vos présentations PowerPoint avec Aspose.Slides pour Java est un processus simple. En suivant les étapes décrites dans ce guide, vous pouvez enrichir vos présentations avec du contenu vidéo captivant. N'oubliez pas : c'est en forgeant qu'on devient forgeron ! Essayez donc d'intégrer différentes vidéos et d'ajuster leurs propriétés pour trouver celle qui répond le mieux à vos besoins.
## FAQ
### Puis-je intégrer plusieurs vidéos dans une seule diapositive ?
Oui, vous pouvez intégrer plusieurs vidéos dans une seule diapositive en ajoutant plusieurs images vidéo.
### Comment puis-je contrôler la lecture de la vidéo ?
Vous pouvez contrôler la lecture à l'aide du `setPlayMode` et `setVolume` méthodes de la `IVideoFrame` classe.
### Quels formats vidéo sont pris en charge par Aspose.Slides ?
Aspose.Slides prend en charge divers formats vidéo, notamment MP4, AVI et WMV.
### Ai-je besoin d'une licence pour utiliser Aspose.Slides ?
Oui, vous avez besoin d'une licence valide pour utiliser Aspose.Slides. Vous pouvez obtenir une licence temporaire pour l'évaluation.
### Puis-je personnaliser la taille et la position de l'image vidéo ?
Oui, vous pouvez personnaliser la taille et la position en définissant les paramètres appropriés lors de l'ajout de l'image vidéo.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}