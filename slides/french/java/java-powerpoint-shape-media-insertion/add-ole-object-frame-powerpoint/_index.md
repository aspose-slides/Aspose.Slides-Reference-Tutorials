---
title: Ajouter un cadre d'objet OLE dans PowerPoint
linktitle: Ajouter un cadre d'objet OLE dans PowerPoint
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment intégrer de manière transparente des cadres d'objets OLE dans des présentations PowerPoint à l'aide d'Aspose.Slides pour Java.
weight: 13
url: /fr/java/java-powerpoint-shape-media-insertion/add-ole-object-frame-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter un cadre d'objet OLE dans PowerPoint

## Introduction
L'ajout d'un cadre d'objet OLE (Object Linking and Embedding) dans les présentations PowerPoint peut améliorer considérablement l'attrait visuel et la fonctionnalité de vos diapositives. Avec Aspose.Slides pour Java, ce processus devient rationalisé et efficace. Dans ce didacticiel, nous vous guiderons à travers les étapes nécessaires pour intégrer de manière transparente les cadres d'objets OLE dans vos présentations PowerPoint.
### Conditions préalables
Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :
1. Environnement de développement Java : assurez-vous que le kit de développement Java (JDK) est installé sur votre système.
2.  Aspose.Slides pour Java : téléchargez et installez Aspose.Slides pour Java à partir du site Web.[ici](https://releases.aspose.com/slides/java/).
3. Compréhension de base de la programmation Java : Familiarisez-vous avec les concepts et la syntaxe de la programmation Java.
## Importer des packages
Tout d'abord, vous devez importer les packages nécessaires pour exploiter les fonctionnalités d'Aspose.Slides pour Java. Voici comment procéder :
```java
import com.aspose.slides.*;

import java.io.ByteArrayOutputStream;
import java.io.File;
import java.io.FileInputStream;
import java.io.IOException;
```
## Étape 1 : Configurez votre environnement
Assurez-vous que votre projet est correctement configuré et que la bibliothèque Aspose.Slides est incluse dans votre chemin de classe.
## Étape 2 : initialiser l'objet de présentation
Créez un objet Présentation pour représenter le fichier PowerPoint avec lequel vous travaillez :
```java
String dataDir = "Your Document Directory";
String outPath = "Your Output Directory";
// Instancier la classe de présentation qui représente le PPTX
Presentation pres = new Presentation();
```
## Étape 3 : accéder à la diapositive et charger l'objet
Accédez à la diapositive dans laquelle vous souhaitez ajouter le cadre d'objet OLE et chargez le fichier objet :
```java
ISlide sld = pres.getSlides().get_Item(0);
// Charger un fichier à diffuser
FileInputStream fs = new FileInputStream(dataDir + "book1.xlsx");
ByteArrayOutputStream mstream = new ByteArrayOutputStream();
byte[] buf = new byte[4096];
while (true) {
    int bytesRead = fs.read(buf, 0, buf.length);
    if (bytesRead <= 0)
        break;
    mstream.write(buf, 0, bytesRead);
}
```
## Étape 4 : Créer un objet de données intégré
Créez un objet de données pour intégrer le fichier :
```java
IOleEmbeddedDataInfo dataInfo = new OleEmbeddedDataInfo(mstream.toByteArray(), "xlsx");
```
## Étape 5 : ajouter un cadre d'objet OLE
Ajoutez une forme de cadre d'objet OLE à la diapositive :
```java
IOleObjectFrame oleObjectFrame = sld.getShapes().addOleObjectFrame(0, 0, (float)pres.getSlideSize().getSize().getWidth(),
        (float)pres.getSlideSize().getSize().getHeight(), dataInfo);
```
## Étape 6 : Enregistrer la présentation
Enregistrez la présentation modifiée sur le disque :
```java
pres.save(outPath + "OleEmbed_out.pptx", SaveFormat.Pptx);
```

## Conclusion
Toutes nos félicitations! Vous avez appris avec succès comment ajouter un cadre d'objet OLE dans des présentations PowerPoint à l'aide d'Aspose.Slides pour Java. Cette fonctionnalité puissante vous permet d'intégrer différents types d'objets, améliorant ainsi l'interactivité et l'attrait visuel de vos diapositives.

## FAQ
### Puis-je intégrer des objets autres que des fichiers Excel à l’aide d’Aspose.Slides pour Java ?
Oui, vous pouvez intégrer différents types d'objets, notamment des documents Word, des fichiers PDF, etc.
### Aspose.Slides est-il compatible avec différentes versions de PowerPoint ?
Aspose.Slides offre une compatibilité avec une large gamme de versions de PowerPoint, garantissant une intégration transparente.
### Puis-je personnaliser l’apparence du cadre d’objet OLE ?
Absolument! Aspose.Slides offre des options étendues pour personnaliser l'apparence et le comportement des cadres d'objets OLE.
### Existe-t-il une version d’essai disponible pour Aspose.Slides pour Java ?
 Oui, vous pouvez télécharger une version d'essai gratuite à partir de[ici](https://releases.aspose.com/).
### Où puis-je trouver de l’assistance pour Aspose.Slides pour Java ?
 Vous pouvez demander de l'aide et de l'aide sur le forum Aspose.Slides[ici](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
