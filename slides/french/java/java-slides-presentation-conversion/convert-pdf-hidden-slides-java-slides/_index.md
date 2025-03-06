---
title: Convertir en PDF avec des diapositives masquées dans Java Slides
linktitle: Convertir en PDF avec des diapositives masquées dans Java Slides
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment convertir des présentations PowerPoint en PDF avec des diapositives masquées à l'aide d'Aspose.Slides pour Java. Suivez notre guide étape par étape avec le code source pour une génération transparente de PDF.
weight: 27
url: /fr/java/presentation-conversion/convert-pdf-hidden-slides-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Introduction à la conversion d'une présentation PowerPoint en PDF avec des diapositives masquées à l'aide d'Aspose.Slides pour Java

Dans ce guide étape par étape, vous apprendrez comment convertir une présentation PowerPoint en PDF tout en préservant les diapositives masquées à l'aide d'Aspose.Slides pour Java. Les diapositives masquées sont celles qui ne sont pas affichées lors d'une présentation normale mais qui peuvent être incluses dans la sortie PDF. Nous vous fournirons le code source et des instructions détaillées pour réaliser cette tâche.

## Conditions préalables

Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :

1.  Bibliothèque Aspose.Slides pour Java : assurez-vous que la bibliothèque Aspose.Slides pour Java est configurée dans votre projet Java. Vous pouvez le télécharger depuis le[Documentation Aspose.Slides pour Java](https://reference.aspose.com/slides/java/).

2. Environnement de développement Java : vous devez disposer d'un environnement de développement Java installé sur votre système.

## Étape 1 : Importer Aspose.Slides pour Java

Tout d'abord, vous devez importer la bibliothèque Aspose.Slides dans votre projet Java. Assurez-vous d'avoir ajouté la bibliothèque au chemin de construction de votre projet.

```java
import com.aspose.slides.*;
```

## Étape 2 : Charger la présentation PowerPoint

 Vous commencerez par charger la présentation PowerPoint que vous souhaitez convertir en PDF. Remplacer`"Your Document Directory"` et`"HiddingSlides.pptx"` avec le chemin de fichier approprié.

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
```

## Étape 3 : Configurer les options PDF

Configurez les options PDF pour inclure les diapositives masquées dans la sortie PDF. Vous pouvez le faire en définissant le`setShowHiddenSlides` propriété du`PdfOptions` classe à`true`.

```java
// Instancier la classe PdfOptions
PdfOptions pdfOptions = new PdfOptions();
// Spécifiez que le document généré doit inclure des diapositives masquées
pdfOptions.setShowHiddenSlides(true);
```

## Étape 4 : Enregistrez la présentation au format PDF

 Maintenant, enregistrez la présentation dans un fichier PDF avec les options spécifiées. Remplacer`"PDFWithHiddenSlides_out.pdf"` avec le nom de fichier de sortie souhaité.

```java
// Enregistrez la présentation au format PDF avec les options spécifiées
presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## Étape 5 : Ressources de nettoyage

Assurez-vous de libérer les ressources utilisées par la présentation lorsque vous avez terminé.

```java
finally
{
    if (presentation != null) presentation.dispose();
}
```

## Code source complet pour convertir en PDF avec des diapositives masquées dans les diapositives Java

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
try
{
	// Instancier la classe PdfOptions
	PdfOptions pdfOptions = new PdfOptions();
	// Spécifiez que le document généré doit inclure des diapositives masquées
	pdfOptions.setShowHiddenSlides(true);
	// Enregistrez la présentation au format PDF avec les options spécifiées
	presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusion

Dans ce guide complet, vous avez appris à convertir une présentation PowerPoint en PDF tout en préservant les diapositives masquées à l'aide d'Aspose.Slides pour Java. Nous vous avons fourni un didacticiel étape par étape ainsi que le code source nécessaire pour réaliser cette tâche de manière transparente.

## FAQ

### Comment puis-je masquer des diapositives dans une présentation PowerPoint ?

Pour masquer une diapositive dans une présentation PowerPoint, procédez comme suit :
1. Sélectionnez la diapositive que vous souhaitez masquer dans la vue Trieuse de diapositives.
2. Faites un clic droit sur la diapositive sélectionnée.
3. Choisissez "Masquer la diapositive" dans le menu contextuel.

### Puis-je afficher par programme les diapositives masquées dans Aspose.Slides pour Java ?

 Oui, vous pouvez afficher par programme les diapositives masquées dans Aspose.Slides pour Java en définissant l'option`Hidden` propriété du`Slide` classe à`false`. Voici un exemple :

```java
Slide slide = presentation.getSlides().get_Item(slideIndex); // Remplacez slideIndex par l'index de la diapositive masquée
slide.setHidden(false);
```

### Comment télécharger Aspose.Slides pour Java ?

 Vous pouvez télécharger Aspose.Slides pour Java à partir du site Web Aspose. Visiter le[Page de téléchargement d'Aspose.Slides pour Java](https://releases.aspose.com/slides/java/) pour obtenir la dernière version.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
