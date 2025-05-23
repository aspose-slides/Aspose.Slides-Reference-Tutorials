---
"description": "Convertissez des présentations PowerPoint en HTML tout en préservant les polices d'origine à l'aide d'Aspose.Slides pour Java."
"linktitle": "Conversion d'une présentation au format HTML avec conservation des polices d'origine dans les diapositives Java"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Conversion d'une présentation au format HTML avec conservation des polices d'origine dans les diapositives Java"
"url": "/fr/java/presentation-conversion/convert-presentation-html-preserve-fonts-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Conversion d'une présentation au format HTML avec conservation des polices d'origine dans les diapositives Java


## Introduction à la conversion d'une présentation au format HTML avec conservation des polices d'origine dans les diapositives Java

Dans ce tutoriel, nous découvrirons comment convertir une présentation PowerPoint (PPTX) en HTML tout en préservant les polices d'origine grâce à Aspose.Slides pour Java. Cela garantira que le code HTML obtenu sera fidèle à l'apparence de la présentation d'origine.

## Étape 1 : Configuration du projet
Avant de plonger dans le code, assurons-nous que vous disposez de la configuration nécessaire :

1. Téléchargez Aspose.Slides pour Java : si vous ne l’avez pas déjà fait, téléchargez et incluez la bibliothèque Aspose.Slides pour Java dans votre projet.

2. Créez un projet Java : configurez un projet Java dans votre IDE préféré et assurez-vous d'avoir un dossier « lib » dans lequel vous pouvez placer le fichier JAR Aspose.Slides.

3. Importer les classes requises : importez les classes nécessaires au début de votre fichier Java :

```java
import com.aspose.slides.EmbedAllFontsHtmlController;
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## Étape 2 : Conversion de la présentation en HTML avec les polices d'origine

Maintenant, convertissons une présentation PowerPoint en HTML tout en préservant les polices d'origine :

```java
// Le chemin vers le répertoire des documents.
String dataDir = "Your Document Directory";

// Charger la présentation
Presentation pres = new Presentation("input.pptx");

try {
    // Exclure les polices de présentation par défaut telles que Calibri et Arial
    String[] fontNameExcludeList = {"Calibri", "Arial"};
    EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
    
    // Créez des options HTML et définissez le formateur HTML personnalisé
    HtmlOptions htmlOptionsEmbed = new HtmlOptions();
    htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
    
    // Enregistrer la présentation au format HTML
    pres.save("output.html", SaveFormat.Html, htmlOptionsEmbed);
} finally {
    // Éliminer l'objet de présentation
    if (pres != null) pres.dispose();
}
```

Dans cet extrait de code :

- Nous chargeons la présentation PowerPoint d'entrée en utilisant `Presentation`.

- Nous définissons une liste de polices (`fontNameExcludeList`) que nous souhaitons exclure de l'intégration dans le code HTML. Ceci est utile pour exclure les polices courantes comme Calibri et Arial afin de réduire la taille du fichier.

- Nous créons une instance de `EmbedAllFontsHtmlController` et lui transmettre la liste d'exclusion des polices.

- Nous créons `HtmlOptions` et définissez un formateur HTML personnalisé à l'aide de `HtmlFormatter.createCustomFormatter(embedFontsController)`.

- Enfin, nous enregistrons la présentation au format HTML avec les options spécifiées.

## Code source complet pour la conversion d'une présentation en HTML avec conservation des polices d'origine dans les diapositives Java

```java
// Le chemin vers le répertoire des documents.
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

Dans ce tutoriel, vous avez appris à convertir une présentation PowerPoint en HTML tout en préservant les polices d'origine grâce à Aspose.Slides pour Java. Cette fonctionnalité est utile pour préserver la fidélité visuelle de vos présentations lors de leur partage sur le Web.

## FAQ

### Comment télécharger Aspose.Slides pour Java ?

Vous pouvez télécharger Aspose.Slides pour Java depuis le site web d'Aspose. Visitez [ici](https://downloads.aspose.com/slides/java/) pour obtenir la dernière version.

### Puis-je personnaliser la liste des polices exclues ?

Oui, vous pouvez personnaliser le `fontNameExcludeList` tableau pour inclure ou exclure des polices spécifiques selon vos besoins.

### Cette méthode fonctionne-t-elle pour les anciens formats PowerPoint comme PPT ?

Cet exemple de code est conçu pour les fichiers PPTX. Si vous devez convertir d'anciens fichiers PPT, vous devrez peut-être apporter des modifications au code.

### Comment puis-je personnaliser davantage la sortie HTML ?

Vous pouvez explorer le `HtmlOptions` classe permettant de personnaliser divers aspects de la sortie HTML, tels que la taille des diapositives, la qualité de l'image, etc.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}