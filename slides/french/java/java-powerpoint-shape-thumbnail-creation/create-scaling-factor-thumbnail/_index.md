---
"description": "Apprenez à créer des miniatures avec facteur d'échelle en Java avec Aspose.Slides pour Java. Guide facile à suivre avec des instructions étape par étape."
"linktitle": "Créer une miniature de facteur d'échelle"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Créer une miniature de facteur d'échelle"
"url": "/fr/java/java-powerpoint-shape-thumbnail-creation/create-scaling-factor-thumbnail/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Créer une miniature de facteur d'échelle

## Introduction
Dans ce tutoriel, nous vous guiderons dans la création d'une miniature de facteur d'échelle avec Aspose.Slides pour Java. Suivez ces instructions étape par étape pour obtenir le résultat souhaité.
## Prérequis
Avant de commencer, assurez-vous de disposer des prérequis suivants :
- Java Development Kit (JDK) installé sur votre système.
- Bibliothèque Aspose.Slides pour Java téléchargée et configurée dans votre projet Java.
- Compréhension de base du langage de programmation Java.

## Importer des packages
Tout d’abord, importez les packages nécessaires pour travailler avec Aspose.Slides dans votre code Java. 
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ShapeThumbnailBounds;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```

Décomposons maintenant l’exemple fourni en plusieurs étapes :
## Étape 1 : Définir le répertoire du document
Définissez le chemin d’accès à votre répertoire de documents où se trouve le fichier de présentation PowerPoint.
```java
String dataDir = "Your Document Directory";
```
Remplacer `"Your Document Directory"` avec le chemin vers votre répertoire de documents actuel.
## Étape 2 : instancier l'objet de présentation
Créez une instance de la classe Presentation pour représenter le fichier de présentation PowerPoint.
```java
Presentation p = new Presentation(dataDir + "HelloWorld.pptx");
```
Assurez-vous de remplacer `"HelloWorld.pptx"` avec le nom de votre fichier de présentation PowerPoint.
## Étape 3 : Créer une image à grande échelle
Générez une image à grande échelle de la diapositive souhaitée à partir de la présentation.
```java
BufferedImage bitmap = p.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail(ShapeThumbnailBounds.Shape, 1, 1);
```
Ce code récupère la vignette de la première forme sur la première diapositive de la présentation.
## Étape 4 : Enregistrer l'image
Enregistrez l'image générée sur le disque au format PNG.
```java
ImageIO.write(bitmap, ".png", new File(dataDir + "Scaling Factor Thumbnail_out.png"));
```
Assurez-vous de remplacer `"Scaling Factor Thumbnail_out.png"` avec le nom du fichier de sortie souhaité.

## Conclusion
En conclusion, vous avez créé avec succès une miniature de facteur d'échelle avec Aspose.Slides pour Java. En suivant les étapes fournies, vous pourrez facilement intégrer cette fonctionnalité à vos applications Java.
## FAQ
### Puis-je utiliser Aspose.Slides pour Java avec n'importe quel IDE Java ?
Oui, Aspose.Slides pour Java peut être utilisé avec n'importe quel environnement de développement intégré Java (IDE) tel qu'Eclipse, IntelliJ IDEA ou NetBeans.
### Existe-t-il un essai gratuit disponible pour Aspose.Slides pour Java ?
Oui, vous pouvez bénéficier d'un essai gratuit d'Aspose.Slides pour Java en visitant le [site web](https://releases.aspose.com/).
### Où puis-je trouver du support pour Aspose.Slides pour Java ?
Vous pouvez trouver du support pour Aspose.Slides pour Java sur le [Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).
### Comment puis-je acheter Aspose.Slides pour Java ?
Vous pouvez acheter Aspose.Slides pour Java auprès du [page d'achat](https://purchase.aspose.com/buy).
### Ai-je besoin d’une licence temporaire pour utiliser Aspose.Slides pour Java ?
Oui, vous pouvez obtenir un permis temporaire auprès du [page de licence temporaire](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}