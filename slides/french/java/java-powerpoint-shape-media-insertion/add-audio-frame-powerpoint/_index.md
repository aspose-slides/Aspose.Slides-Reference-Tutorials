---
"description": "Apprenez à ajouter des cadres audio à vos présentations PowerPoint avec Aspose.Slides pour Java. Améliorez vos présentations avec des éléments audio captivants en toute simplicité."
"linktitle": "Ajouter un cadre audio dans PowerPoint"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Ajouter un cadre audio dans PowerPoint"
"url": "/fr/java/java-powerpoint-shape-media-insertion/add-audio-frame-powerpoint/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter un cadre audio dans PowerPoint

## Introduction
Enrichir vos présentations avec des éléments audio peut considérablement améliorer leur impact et leur implication. Avec Aspose.Slides pour Java, l'intégration de cadres audio dans vos présentations PowerPoint devient un processus fluide. Ce tutoriel vous guidera pas à pas pour ajouter des cadres audio à vos présentations avec Aspose.Slides pour Java.
## Prérequis
Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :
1. Kit de développement Java (JDK) : assurez-vous que Java est installé sur votre système.
2. Bibliothèque Aspose.Slides pour Java : Téléchargez et installez la bibliothèque Aspose.Slides pour Java. Vous pouvez la télécharger depuis le [Documentation Aspose.Slides pour Java](https://reference.aspose.com/slides/java/).
3. Fichier audio : préparez le fichier audio (par exemple, au format WAV) que vous souhaitez ajouter à votre présentation.
## Importer des packages
Importez les packages nécessaires dans votre projet Java :
```java
import com.aspose.slides.*;

import java.io.File;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
```
## Étape 1 : Configurez votre répertoire de projet
Assurez-vous d'avoir configuré une structure de répertoires pour votre projet. Sinon, créez-en une pour organiser efficacement vos fichiers.
```java
String dataDir = "Your Document Directory";
boolean isExists = new File(dataDir).exists();
if (!isExists)
    new File(dataDir).mkdirs();
```
## Étape 2 : instancier la classe de présentation
Instancier le `Presentation` classe pour représenter la présentation PowerPoint.
```java
Presentation pres = new Presentation();
```
## Étape 3 : Récupérez la diapositive et chargez le fichier audio
Récupérez la première diapositive et chargez le fichier audio depuis votre répertoire.
```java
ISlide sld = pres.getSlides().get_Item(0);
FileInputStream fstr = new FileInputStream(dataDir + "sampleaudio.wav");
```
## Étape 4 : Ajouter une image audio
Ajoutez le cadre audio à la diapositive.
```java
IAudioFrame audioFrame = sld.getShapes().addAudioFrameEmbedded(50, 150, 100, 100, fstr);
```
## Étape 5 : Définir les propriétés audio
Définissez des propriétés telles que la lecture sur plusieurs diapositives, le rembobinage audio, le mode de lecture et le volume.
```java
audioFrame.setPlayAcrossSlides(true);
audioFrame.setRewindAudio(true);
audioFrame.setPlayMode(AudioPlayModePreset.Auto);
audioFrame.setVolume(AudioVolumeMode.Loud);
```
## Étape 6 : Enregistrer la présentation
Enregistrez la présentation modifiée avec le cadre audio ajouté.
```java
pres.save(dataDir + "AudioFrameEmbed_out.pptx", SaveFormat.Pptx);
```

## Conclusion
Intégrer des éléments audio à vos présentations PowerPoint peut améliorer leur efficacité et captiver votre public. Avec Aspose.Slides pour Java, l'ajout d'images audio devient un jeu d'enfant, vous permettant de créer des présentations dynamiques et captivantes en toute simplicité.

## FAQ
### Puis-je ajouter des fichiers audio de différents formats à ma présentation ?
Oui, Aspose.Slides pour Java prend en charge divers formats audio, notamment WAV, MP3, etc.
### Est-il possible de régler le timing de la lecture audio dans les diapositives ?
Absolument. Vous pouvez synchroniser la lecture audio avec des transitions de diapositives spécifiques grâce à Aspose.Slides pour Java.
### Aspose.Slides pour Java prend-il en charge la compatibilité multiplateforme ?
Oui, vous pouvez créer des présentations PowerPoint avec des cadres audio intégrés compatibles sur différentes plates-formes.
### Puis-je personnaliser l’apparence du lecteur audio dans la présentation ?
Aspose.Slides pour Java offre de nombreuses options de personnalisation, vous permettant d'adapter l'apparence du lecteur audio à vos préférences.
### Existe-t-il une version d'essai disponible pour Aspose.Slides pour Java ?
Oui, vous pouvez accéder à un essai gratuit d'Aspose.Slides pour Java à partir de leur [site web](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}