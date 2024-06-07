---
title: Créer une vignette de forme dans PowerPoint
linktitle: Créer une vignette de forme dans PowerPoint
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment générer des vignettes de formes dans des présentations PowerPoint à l'aide d'Aspose.Slides pour Java. Guide étape par étape fourni.
type: docs
weight: 14
url: /fr/java/java-powerpoint-shape-thumbnail-creation/create-shape-thumbnail-powerpoint/
---
## Introduction
Dans ce didacticiel, nous aborderons la création de vignettes de formes dans des présentations PowerPoint à l'aide d'Aspose.Slides pour Java. Aspose.Slides est une bibliothèque puissante qui permet aux développeurs de travailler avec des fichiers PowerPoint par programme, permettant l'automatisation de diverses tâches, notamment la génération de vignettes de formes.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les prérequis suivants :
- Connaissance de base de la programmation Java.
- Kit de développement Java (JDK) installé sur votre système.
-  Bibliothèque Aspose.Slides pour Java téléchargée et configurée dans votre projet. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/slides/java/).

## Importer des packages
Tout d'abord, vous devez importer les packages nécessaires dans votre code Java pour utiliser les fonctionnalités d'Aspose.Slides. Incluez les instructions d'importation suivantes au début de votre fichier Java :
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.examples.RunExamples;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Étape 1 : Définir le répertoire des documents
```java
String dataDir = "Your Document Directory";
```
 Remplacer`"Your Document Directory"` avec le chemin d'accès au répertoire contenant votre fichier PowerPoint.
## Étape 2 : Instancier un objet de présentation
```java
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
```
 Créez une nouvelle instance du`Presentation` classe, en passant le chemin d'accès à votre fichier PowerPoint en tant que paramètre.
## Étape 3 : générer une vignette de forme
```java
BufferedImage bitmap = presentation.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail();
```
Récupérez la vignette de la forme souhaitée dès la première diapositive de la présentation.
## Étape 4 : Enregistrer l'image miniature
```java
ImageIO.write(bitmap, ".png", new File(dataDir + "Shape_thumbnail_out.png"));
```
Enregistrez l'image miniature générée sur le disque au format PNG avec le nom de fichier spécifié.

## Conclusion
En conclusion, ce didacticiel a montré comment créer des vignettes de formes dans des présentations PowerPoint à l'aide d'Aspose.Slides pour Java. En suivant le guide étape par étape et en utilisant les extraits de code fournis, vous pouvez générer efficacement des vignettes de formes par programme.

## FAQ
### Puis-je créer des miniatures pour les formes de n’importe quelle diapositive de la présentation ?
Oui, vous pouvez modifier le code pour cibler les formes sur n'importe quelle diapositive en ajustant l'index de la diapositive en conséquence.
### Aspose.Slides prend-il en charge d'autres formats d'image pour enregistrer les vignettes ?
Oui, outre PNG, Aspose.Slides prend en charge l'enregistrement des vignettes dans divers formats d'image tels que JPEG, GIF et BMP.
### Aspose.Slides est-il adapté à un usage commercial ?
Oui, Aspose.Slides propose des licences commerciales pour les entreprises et les organisations. Vous pouvez acheter une licence auprès de[ici](https://purchase.aspose.com/buy).
### Puis-je essayer Aspose.Slides avant d’acheter ?
 Absolument! Vous pouvez télécharger une version d’essai gratuite d’Aspose.Slides à partir de[ici](https://releases.aspose.com/) pour évaluer ses caractéristiques et ses capacités.
### Où puis-je trouver de l’aide pour Aspose.Slides ?
 Si vous avez des questions ou avez besoin d'aide avec Aspose.Slides, vous pouvez visiter le[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) pour le soutien.