---
title: Créer une vignette de note enfant SmartArt
linktitle: Créer une vignette de note enfant SmartArt
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Apprenez à créer des vignettes de notes enfants SmartArt en Java avec Aspose.Slides, améliorant ainsi vos présentations PowerPoint sans effort.
weight: 15
url: /fr/java/java-powerpoint-shape-thumbnail-creation/create-smartart-child-note-thumbnail/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introduction
Dans ce didacticiel, nous allons explorer comment créer des vignettes de notes enfants SmartArt en Java à l'aide d'Aspose.Slides. Aspose.Slides est une puissante API Java qui permet aux développeurs de travailler avec des présentations PowerPoint par programme, leur permettant ainsi de créer, modifier et manipuler facilement des diapositives.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :
1. Kit de développement Java (JDK) installé sur votre système.
2.  Bibliothèque Aspose.Slides pour Java téléchargée et configurée dans votre projet. Vous pouvez télécharger la bibliothèque depuis[ici](https://releases.aspose.com/slides/java/).

## Importer des packages
Assurez-vous d'importer les packages nécessaires dans votre classe Java :
```java
import com.aspose.slides.ISmartArt;
import com.aspose.slides.ISmartArtNode;
import com.aspose.slides.Presentation;
import com.aspose.slides.SmartArtLayoutType;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Étape 1 : Configurez votre projet
Assurez-vous d'avoir un projet Java installé et configuré avec la bibliothèque Aspose.Slides.
## Étape 2 : Créer une présentation
 Instancier le`Presentation` classe pour représenter le fichier PPTX :
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```
## Étape 3 : Ajouter un SmartArt
Ajoutez SmartArt à votre diapositive de présentation :
```java
ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
## Étape 4 : obtenir une référence de nœud
Obtenez la référence d'un nœud en utilisant son index :
```java
ISmartArtNode node = smart.getNodes().get_Item(1);
```
## Étape 5 : Obtenir une vignette
Récupérez l'image miniature du nœud SmartArt :
```java
BufferedImage bmp = node.getShapes().get_Item(0).getThumbnail();
```
## Étape 6 : Enregistrer la vignette
Enregistrez l'image miniature dans un fichier :
```java
ImageIO.write(bmp, "jpeg", new File(dataDir + "SmartArt_ChildNote_Thumbnail_out.jpeg"));
```
Répétez ces étapes pour chaque nœud SmartArt selon les besoins de votre présentation.

## Conclusion
Dans ce didacticiel, nous avons appris à créer des vignettes de notes enfants SmartArt en Java à l'aide d'Aspose.Slides. Grâce à ces connaissances, vous pouvez améliorer vos présentations PowerPoint par programmation, en ajoutant facilement des éléments visuellement attrayants.
## FAQ
### Puis-je utiliser Aspose.Slides pour manipuler des fichiers PowerPoint existants ?
Oui, Aspose.Slides vous permet de modifier des fichiers PowerPoint existants, notamment en ajoutant, supprimant ou modifiant des diapositives et leur contenu.
### Aspose.Slides prend-il en charge l’exportation de diapositives vers différents formats de fichiers ?
Absolument! Aspose.Slides prend en charge l'exportation de diapositives vers différents formats, notamment PDF, images et HTML, entre autres.
### Aspose.Slides est-il adapté à l’automatisation PowerPoint au niveau de l’entreprise ?
Oui, Aspose.Slides est conçu pour gérer les tâches d'automatisation PowerPoint au niveau de l'entreprise de manière efficace et fiable.
### Puis-je créer des diagrammes SmartArt complexes par programmation avec Aspose.Slides ?
Certainement! Aspose.Slides fournit une prise en charge complète pour la création et la manipulation de diagrammes SmartArt de complexité variable.
### Aspose.Slides offre-t-il un support technique aux développeurs ?
 Oui, Aspose.Slides fournit un support technique dédié aux développeurs via leur[forum](https://forum.aspose.com/c/slides/11) et d'autres chaînes.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
