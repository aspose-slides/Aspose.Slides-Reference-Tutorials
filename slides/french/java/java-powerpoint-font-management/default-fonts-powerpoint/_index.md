---
title: Polices par défaut dans PowerPoint avec Aspose.Slides pour Java
linktitle: Polices par défaut dans PowerPoint avec Aspose.Slides pour Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment définir les polices par défaut dans les présentations PowerPoint à l'aide d'Aspose.Slides pour Java. Assurez la cohérence et améliorez l’attrait visuel sans effort.
weight: 11
url: /fr/java/java-powerpoint-font-management/default-fonts-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introduction
La création de présentations PowerPoint avec des polices personnalisées est une exigence courante dans de nombreux projets. Aspose.Slides pour Java fournit une solution transparente pour gérer les polices par défaut, garantissant ainsi la cohérence entre différents environnements. Dans ce didacticiel, nous vous guiderons tout au long du processus de définition des polices par défaut dans les présentations PowerPoint à l'aide d'Aspose.Slides pour Java.
## Conditions préalables
Avant de commencer, assurez-vous d'avoir les prérequis suivants :
1. Kit de développement Java (JDK) : assurez-vous que JDK est installé sur votre système.
2.  Aspose.Slides pour Java : téléchargez et installez Aspose.Slides pour Java à partir du[page de téléchargement](https://releases.aspose.com/slides/java/).
3. Connaissances de base de Java : Familiarité avec les principes fondamentaux du langage de programmation Java.

## Importer des packages
Commencez par importer les packages nécessaires dans votre projet Java :
```java
import com.aspose.slides.LoadFormat;
import com.aspose.slides.LoadOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Étape 1 : définir les polices par défaut
Définissez le chemin d'accès à votre répertoire de documents et créez des options de chargement pour spécifier les polices régulières et asiatiques par défaut :
```java
String dataDir = "Your Document Directory";
LoadOptions loadOptions = new LoadOptions(LoadFormat.Auto);
loadOptions.setDefaultRegularFont("Wingdings");
loadOptions.setDefaultAsianFont("Wingdings");
```
## Étape 2 : Charger la présentation
Chargez la présentation PowerPoint en utilisant les options de chargement définies :
```java
Presentation pptx = new Presentation(dataDir + "DefaultFonts.pptx", loadOptions);
```
## Étape 3 : Générer des sorties
Générez diverses sorties telles que des vignettes de diapositives, des fichiers PDF et XPS :
```java
try {
    // Générer une miniature de diapositive
    BufferedImage image = pptx.getSlides().get_Item(0).getThumbnail(1, 1);
    ImageIO.write(image, ".png", new File(dataDir + "output_out.png"));
    // Générer un PDF
    pptx.save(dataDir + "output_out.pdf", SaveFormat.Pdf);
    // Générer du XPS
    pptx.save(dataDir + "output_out.xps", SaveFormat.Xps);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pptx != null) pptx.dispose();
}
```

## Conclusion
La définition des polices par défaut dans les présentations PowerPoint à l'aide d'Aspose.Slides pour Java est simple et efficace. En suivant les étapes décrites dans ce didacticiel, vous pouvez garantir la cohérence des styles de police sur différentes plates-formes et environnements, améliorant ainsi l'attrait visuel de vos présentations.
## FAQ
### Puis-je utiliser des polices personnalisées avec Aspose.Slides pour Java ?
Oui, vous pouvez spécifier des polices personnalisées dans vos présentations à l'aide d'Aspose.Slides pour Java.
### Aspose.Slides pour Java est-il compatible avec toutes les versions de PowerPoint ?
Aspose.Slides for Java prend en charge une large gamme de versions de PowerPoint, garantissant ainsi la compatibilité entre différents environnements.
### Comment puis-je obtenir de l’assistance pour Aspose.Slides pour Java ?
 Vous pouvez obtenir une assistance pour Aspose.Slides pour Java via le[Forums Aspose](https://forum.aspose.com/c/slides/11).
### Puis-je essayer Aspose.Slides pour Java avant d’acheter ?
 Oui, vous pouvez explorer Aspose.Slides pour Java grâce à un essai gratuit disponible sur[releases.aspose.com](https://releases.aspose.com/).
### Où puis-je obtenir une licence temporaire pour Aspose.Slides pour Java ?
 Vous pouvez obtenir une licence temporaire pour Aspose.Slides pour Java auprès du[page d'achat](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
