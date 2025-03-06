---
title: Convertir une présentation entière en HTML avec des fichiers multimédias dans des diapositives Java
linktitle: Convertir une présentation entière en HTML avec des fichiers multimédias dans des diapositives Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment convertir des présentations au format HTML avec des fichiers multimédias à l'aide de Java Slides. Suivez notre guide étape par étape avec l'API Aspose.Slides pour Java.
weight: 30
url: /fr/java/presentation-conversion/convert-whole-presentation-html-media-files-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Introduction à la conversion d'une présentation entière en HTML avec des fichiers multimédias dans des diapositives Java

À l’ère numérique d’aujourd’hui, la nécessité de convertir des présentations dans différents formats, notamment HTML, est une exigence courante. Les développeurs Java se retrouvent souvent confrontés à ce défi. Heureusement, avec l'API Aspose.Slides pour Java, cette tâche peut être accomplie efficacement. Dans ce guide étape par étape, nous explorerons comment convertir une présentation entière en HTML tout en préservant les fichiers multimédias à l'aide de Java Slides.

## Conditions préalables

Avant de nous plonger dans l’aspect codage, assurons-nous que tout est correctement configuré :

- Kit de développement Java (JDK) : assurez-vous que le JDK est installé sur votre système.
-  Aspose.Slides pour Java : vous devrez installer l'API Aspose.Slides pour Java. Vous pouvez le télécharger[ici](https://releases.aspose.com/slides/java/).

## Étape 1 : Importer les packages nécessaires

Pour commencer, vous devez importer les packages nécessaires. Ces packages fourniront les classes et méthodes requises pour notre tâche.

```java
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.SlideImageFormat;
import com.aspose.slides.SVGOptions;
import com.aspose.slides.VideoPlayerHtmlController;
```

## Étape 2 : Spécifiez le répertoire de documents

 Définissez le chemin d'accès à votre répertoire de documents où se trouve le fichier de présentation. Remplacer`"Your Document Directory"` avec le chemin réel.

```java
String dataDir = "Your Document Directory";
```

## Étape 3 : initialiser la présentation

 Chargez la présentation que vous souhaitez convertir en HTML. Assurez-vous de remplacer`"presentationWith.pptx"` avec le nom de fichier de votre présentation.

```java
Presentation pres = new Presentation("presentationWith.pptx");
```

## Étape 4 : Créer le contrôleur HTML

 Nous allons créer un`VideoPlayerHtmlController` pour gérer le processus de conversion. Remplacez l'URL par l'adresse Web souhaitée.

```java
VideoPlayerHtmlController controller = new VideoPlayerHtmlController(
    "", htmlDocumentFileName, "http://www.exemple.com/");
```

## Étape 5 : Configurer les options HTML et SVG

Configurez les options HTML et SVG pour la conversion. C'est ici que vous pouvez personnaliser le formatage selon vos besoins.

```java
HtmlOptions htmlOptions = new HtmlOptions(controller);
SVGOptions svgOptions = new SVGOptions(controller);
htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(controller));
htmlOptions.setSlideImageFormat(SlideImageFormat.svg(svgOptions));
```

## Étape 6 : Enregistrez la présentation au format HTML

Il est maintenant temps d'enregistrer la présentation sous forme de fichier HTML, y compris les fichiers multimédias.

```java
pres.save(htmlDocumentFileName, SaveFormat.Html, htmlOptions);
```

## Code source complet pour convertir une présentation entière en HTML avec des fichiers multimédias dans des diapositives Java

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
String htmlDocumentFileName = "presentationWithVideo.html";
Presentation pres = new Presentation("presentationWith.pptx");
try
{
	VideoPlayerHtmlController controller = new VideoPlayerHtmlController(
			"", htmlDocumentFileName, "http://www.exemple.com/");
	HtmlOptions htmlOptions = new HtmlOptions(controller);
	SVGOptions svgOptions = new SVGOptions(controller);
	htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(controller));
	htmlOptions.setSlideImageFormat(SlideImageFormat.svg(svgOptions));
	pres.save(htmlDocumentFileName, SaveFormat.Html, htmlOptions);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusion

Dans ce didacticiel, nous avons parcouru le processus de conversion d'une présentation entière en HTML avec des fichiers multimédias à l'aide de Java Slides et de l'API Aspose.Slides pour Java. En suivant ces étapes, vous pouvez transformer efficacement vos présentations dans un format adapté au Web, en préservant tous les éléments multimédias essentiels.

## FAQ

### Comment puis-je installer Aspose.Slides pour Java ?

 Pour installer Aspose.Slides pour Java, visitez la page de téléchargement à l'adresse[ici](https://releases.aspose.com/slides/java/) et suivez les instructions d'installation fournies.

### Puis-je personnaliser davantage la sortie HTML ?

 Oui, vous pouvez personnaliser la sortie HTML en fonction de vos besoins. Le`HtmlOptions` La classe fournit divers paramètres pour contrôler le processus de conversion, y compris des options de formatage et de mise en page.

### Aspose.Slides pour Java prend-il en charge d’autres formats de sortie ?

Oui, Aspose.Slides pour Java prend en charge divers formats de sortie, notamment PDF, PPTX, etc. Vous pouvez explorer ces options dans la documentation.

### Aspose.Slides pour Java est-il adapté aux projets commerciaux ?

Oui, Aspose.Slides pour Java est une solution robuste et commercialement viable pour gérer les tâches liées à la présentation dans les applications Java. Il est largement utilisé dans les projets au niveau de l’entreprise.

### Comment puis-je accéder à la présentation HTML convertie ?

 Une fois la conversion terminée, vous pouvez accéder à la présentation HTML en localisant le fichier spécifié dans le`htmlDocumentFileName` variable.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
