---
title: Conversion d'une présentation en HTML en préservant les polices originales dans les diapositives Java
linktitle: Conversion d'une présentation en HTML en préservant les polices originales dans les diapositives Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Convertissez des présentations PowerPoint en HTML tout en préservant les polices originales à l'aide d'Aspose.Slides pour Java.
type: docs
weight: 14
url: /fr/java/presentation-conversion/convert-presentation-html-preserve-fonts-java-slides/
---

## Introduction à la conversion d'une présentation en HTML en préservant les polices originales dans les diapositives Java

Dans ce didacticiel, nous explorerons comment convertir une présentation PowerPoint (PPTX) en HTML tout en préservant les polices d'origine à l'aide d'Aspose.Slides pour Java. Cela garantira que le HTML résultant ressemble étroitement à l’apparence de la présentation originale.

## Étape 1 : Mise en place du projet
Avant de plonger dans le code, assurons-nous que vous disposez de la configuration nécessaire :

1. Téléchargez Aspose.Slides pour Java : si vous ne l'avez pas déjà fait, téléchargez et incluez la bibliothèque Aspose.Slides pour Java dans votre projet.

2. Créez un projet Java : configurez un projet Java dans votre IDE préféré et assurez-vous de disposer d'un dossier "lib" dans lequel vous pouvez placer le fichier JAR Aspose.Slides.

3. Importer les classes requises : importez les classes nécessaires au début de votre fichier Java :

```java
import com.aspose.slides.EmbedAllFontsHtmlController;
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## Étape 2 : Conversion d'une présentation en HTML avec les polices originales

Maintenant, convertissons une présentation PowerPoint en HTML tout en préservant les polices d'origine :

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";

// Charger la présentation
Presentation pres = new Presentation("input.pptx");

try {
    // Exclure les polices de présentation par défaut comme Calibri et Arial
    String[] fontNameExcludeList = {"Calibri", "Arial"};
    EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
    
    // Créez des options HTML et définissez le formateur HTML personnalisé
    HtmlOptions htmlOptionsEmbed = new HtmlOptions();
    htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
    
    // Enregistrez la présentation au format HTML
    pres.save("output.html", SaveFormat.Html, htmlOptionsEmbed);
} finally {
    // Supprimer l'objet de présentation
    if (pres != null) pres.dispose();
}
```

Dans cet extrait de code :

-  Nous chargeons la présentation PowerPoint d'entrée en utilisant`Presentation`.

- Nous définissons une liste de polices (`fontNameExcludeList`que nous souhaitons exclure de l'intégration dans le HTML. Ceci est utile pour exclure les polices courantes telles que Calibri et Arial afin de réduire la taille du fichier.

-  Nous créons une instance de`EmbedAllFontsHtmlController` et transmettez-lui la liste d’exclusion de polices.

-  Nous créons`HtmlOptions` et définissez un formateur HTML personnalisé en utilisant`HtmlFormatter.createCustomFormatter(embedFontsController)`.

- Enfin, nous enregistrons la présentation au format HTML avec les options spécifiées.

## Code source complet pour convertir une présentation en HTML en préservant les polices originales dans les diapositives Java

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation("input.pptx");
try
{
	// exclure les polices de présentation par défaut
	String[] fontNameExcludeList = {"Calibri", "Arial"};
	EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
	HtmlOptions htmlOptionsEmbed = new HtmlOptions();
	htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
	pres.save("input-PFDinDisplayPro-Regular-installed.html", SaveFormat.Html, htmlOptionsEmbed);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusion

Dans ce didacticiel, vous avez appris à convertir une présentation PowerPoint en HTML tout en préservant les polices d'origine à l'aide d'Aspose.Slides pour Java. Ceci est utile lorsque vous souhaitez conserver la fidélité visuelle de vos présentations lors de leur partage sur le Web.

## FAQ

### Comment télécharger Aspose.Slides pour Java ?

 Vous pouvez télécharger Aspose.Slides pour Java à partir du site Web Aspose. Visite[ici](https://downloads.aspose.com/slides/java/) pour obtenir la dernière version.

### Puis-je personnaliser la liste des polices exclues ?

 Oui, vous pouvez personnaliser le`fontNameExcludeList` tableau pour inclure ou exclure des polices spécifiques selon vos besoins.

### Cette méthode fonctionne-t-elle pour les anciens formats PowerPoint comme PPT ?

Cet exemple de code est conçu pour les fichiers PPTX. Si vous devez convertir des fichiers PPT plus anciens, vous devrez peut-être apporter des modifications au code.

### Comment puis-je personnaliser davantage la sortie HTML ?

 Vous pouvez explorer le`HtmlOptions` classe pour personnaliser divers aspects de la sortie HTML, tels que la taille des diapositives, la qualité de l’image, etc.