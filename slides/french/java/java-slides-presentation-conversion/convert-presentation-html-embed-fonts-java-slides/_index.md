---
title: Conversion d'une présentation en HTML avec intégration de toutes les polices dans les diapositives Java
linktitle: Conversion d'une présentation en HTML avec intégration de toutes les polices dans les diapositives Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment convertir des présentations au format HTML avec des polices intégrées à l'aide d'Aspose.Slides pour Java. Ce guide étape par étape garantit un formatage cohérent pour un partage fluide.
weight: 13
url: /fr/java/presentation-conversion/convert-presentation-html-embed-fonts-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Introduction à la conversion d'une présentation en HTML avec intégration de toutes les polices dans les diapositives Java

À l'ère numérique d'aujourd'hui, la conversion de présentations au format HTML est devenue essentielle pour partager des informations de manière transparente sur diverses plates-formes. Lorsque vous travaillez avec Java Slides, il est essentiel de vous assurer que toutes les polices utilisées dans votre présentation sont intégrées afin de conserver un formatage cohérent. Dans ce guide étape par étape, nous vous guiderons tout au long du processus de conversion d'une présentation en HTML tout en intégrant toutes les polices à l'aide d'Aspose.Slides pour Java. Commençons!

## Conditions préalables

Avant de plonger dans le code et le processus de conversion, assurez-vous que les conditions préalables suivantes sont en place :

- Kit de développement Java (JDK) installé sur votre système.
-  Aspose.Slides pour l'API Java, que vous pouvez télécharger à partir de[ici](https://releases.aspose.com/slides/java/).
-  Un dossier de présentation (par exemple,`presentation.pptx`) que vous souhaitez convertir en HTML.

## Étape 1 : Configuration de l'environnement Java

Assurez-vous que Java et Aspose.Slides pour Java API sont correctement installés sur votre système. Vous pouvez vous référer à la documentation pour les instructions d'installation.

## Étape 2 : Chargement du fichier de présentation

Dans votre code Java, vous devez charger le fichier de présentation que vous souhaitez convertir. Remplacer`"Your Document Directory"` avec le chemin réel vers votre fichier de présentation.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "presentation.pptx");
```

## Étape 3 : intégration de toutes les polices dans la présentation

Pour intégrer toutes les polices utilisées dans la présentation, vous pouvez utiliser l'extrait de code suivant. Cela garantit que la sortie HTML inclura toutes les polices nécessaires pour un rendu cohérent.

```java
try
{
    // Exclure les polices de présentation par défaut
    String[] fontNameExcludeList = {  };
    LinkAllFontsHtmlController linkcont = new LinkAllFontsHtmlController(fontNameExcludeList, "C:\\Windows\\Fonts\\");
    HtmlOptions htmlOptionsEmbed = new HtmlOptions();
    htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(linkcont));
    pres.save("Your Output Directory" + "pres.html", SaveFormat.Html, htmlOptionsEmbed);
}
finally
{
    if (pres != null) pres.dispose();
}
```

## Étape 4 : Conversion de la présentation en HTML

Maintenant que nous avons intégré toutes les polices, il est temps de convertir la présentation en HTML. Le code fourni à l'étape 3 gérera cette conversion.

## Étape 5 : enregistrement du fichier HTML

La dernière étape consiste à enregistrer le fichier HTML avec les polices intégrées. Le fichier HTML sera enregistré dans le répertoire spécifié, garantissant que toutes les polices sont incluses.

C'est ça! Vous avez réussi à convertir une présentation en HTML tout en incorporant toutes les polices à l'aide d'Aspose.Slides pour Java.

## Code source complet

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "presentation.pptx");
try
{
	// exclure les polices de présentation par défaut
	String[] fontNameExcludeList = {  };
	LinkAllFontsHtmlController linkcont = new LinkAllFontsHtmlController(fontNameExcludeList, "C:\\Windows\\Fonts\\");
	HtmlOptions htmlOptionsEmbed = new HtmlOptions();
	htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(linkcont));
	pres.save("Your Output Directory" + "pres.html", SaveFormat.Html, htmlOptionsEmbed);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusion

La conversion de présentations au format HTML avec des polices intégrées est cruciale pour maintenir un formatage cohérent sur différentes plates-formes. Avec Aspose.Slides pour Java, ce processus devient simple et efficace. Vous pouvez désormais partager vos présentations au format HTML sans vous soucier des polices manquantes.

## FAQ

### Comment puis-je vérifier si toutes les polices sont intégrées dans la sortie HTML ?

Vous pouvez inspecter le code source du fichier HTML et rechercher des références de police. Toutes les polices utilisées dans la présentation doivent être référencées dans le fichier HTML.

### Puis-je personnaliser davantage la sortie HTML, comme le style et la mise en page ?

 Oui, vous pouvez personnaliser la sortie HTML en modifiant le`HtmlOptions` et le modèle HTML utilisé pour le formatage. Aspose.Slides pour Java offre une flexibilité à cet égard.

### Existe-t-il des limitations lors de l’intégration de polices en HTML ?

Bien que l'intégration de polices garantisse un rendu cohérent, gardez à l'esprit que cela peut augmenter la taille du fichier de sortie HTML. Assurez-vous d'optimiser la présentation pour équilibrer la qualité et la taille du fichier.

### Puis-je convertir des présentations au contenu complexe en HTML en utilisant cette méthode ?

Oui, cette méthode fonctionne pour les présentations au contenu complexe, comprenant des images, des animations et des éléments multimédias. Aspose.Slides pour Java gère la conversion efficacement.

### Où puis-je trouver plus de ressources et de documentation pour Aspose.Slides pour Java ?

 Vous pouvez accéder à une documentation et à des ressources complètes pour Aspose.Slides pour Java à l'adresse[Aspose.Slides pour les références de l'API Java](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
