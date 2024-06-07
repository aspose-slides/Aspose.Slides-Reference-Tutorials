---
title: Créer une vignette de facteur d'échelle
linktitle: Créer une vignette de facteur d'échelle
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment créer des vignettes de facteurs de mise à l'échelle en Java à l'aide d'Aspose.Slides pour Java. Guide facile à suivre avec des instructions étape par étape.
type: docs
weight: 12
url: /fr/java/java-powerpoint-shape-thumbnail-creation/create-scaling-factor-thumbnail/
---
## Introduction
Dans ce didacticiel, nous vous guiderons tout au long du processus de création d'une vignette de facteur de mise à l'échelle à l'aide d'Aspose.Slides pour Java. Suivez ces instructions étape par étape pour obtenir le résultat souhaité.
## Conditions préalables
Avant de commencer, assurez-vous de disposer des conditions préalables suivantes :
- Kit de développement Java (JDK) installé sur votre système.
- Bibliothèque Aspose.Slides pour Java téléchargée et configurée dans votre projet Java.
- Compréhension de base du langage de programmation Java.

## Importer des packages
Tout d’abord, importez les packages nécessaires pour travailler avec Aspose.Slides dans votre code Java. 
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ShapeThumbnailBounds;
import com.aspose.slides.examples.RunExamples;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```

Maintenant, décomposons l'exemple fourni en plusieurs étapes :
## Étape 1 : Définir le répertoire des documents
Définissez le chemin d'accès à votre répertoire de documents où se trouve le fichier de présentation PowerPoint.
```java
String dataDir = "Your Document Directory";
```
 Remplacer`"Your Document Directory"` avec le chemin d'accès à votre répertoire de documents actuel.
## Étape 2 : instancier l'objet de présentation
Créez une instance de la classe Présentation pour représenter le fichier de présentation PowerPoint.
```java
Presentation p = new Presentation(dataDir + "HelloWorld.pptx");
```
 Assurez-vous de remplacer`"HelloWorld.pptx"` avec le nom de votre fichier de présentation PowerPoint.
## Étape 3 : Créer une image à grande échelle
Générez une image à grande échelle de la diapositive souhaitée à partir de la présentation.
```java
BufferedImage bitmap = p.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail(ShapeThumbnailBounds.Shape, 1, 1);
```
Ce code récupère la vignette de la première forme de la première diapositive de la présentation.
## Étape 4 : Enregistrez l'image
Enregistrez l'image générée sur le disque au format PNG.
```java
ImageIO.write(bitmap, ".png", new File(dataDir + "Scaling Factor Thumbnail_out.png"));
```
 Assurez-vous de remplacer`"Scaling Factor Thumbnail_out.png"` avec le nom du fichier de sortie souhaité.

## Conclusion
En conclusion, vous avez réussi à créer une vignette de facteur de mise à l'échelle à l'aide d'Aspose.Slides pour Java. En suivant les étapes fournies, vous pouvez facilement intégrer cette fonctionnalité dans vos applications Java.
## FAQ
### Puis-je utiliser Aspose.Slides pour Java avec n’importe quel IDE Java ?
Oui, Aspose.Slides pour Java peut être utilisé avec n'importe quel environnement de développement intégré (IDE) Java tel qu'Eclipse, IntelliJ IDEA ou NetBeans.
### Existe-t-il un essai gratuit disponible pour Aspose.Slides pour Java ?
 Oui, vous pouvez bénéficier d'un essai gratuit d'Aspose.Slides pour Java en visitant le[site web](https://releases.aspose.com/).
### Où puis-je trouver de l’assistance pour Aspose.Slides pour Java ?
 Vous pouvez trouver une assistance pour Aspose.Slides pour Java sur le[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).
### Comment puis-je acheter Aspose.Slides pour Java ?
 Vous pouvez acheter Aspose.Slides pour Java sur le site[page d'achat](https://purchase.aspose.com/buy).
### Ai-je besoin d’une licence temporaire pour utiliser Aspose.Slides pour Java ?
 Oui, vous pouvez obtenir une licence temporaire auprès du[page de licence temporaire](https://purchase.aspose.com/temporary-license/).