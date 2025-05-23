---
"description": "Apprenez à convertir des présentations PowerPoint en PDF avec diapositives masquées grâce à Aspose.Slides pour Java. Suivez notre guide étape par étape avec code source pour une génération PDF fluide."
"linktitle": "Convertir en PDF avec des diapositives masquées dans Java Slides"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Convertir en PDF avec des diapositives masquées dans Java Slides"
"url": "/fr/java/presentation-conversion/convert-pdf-hidden-slides-java-slides/"
"weight": 27
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Convertir en PDF avec des diapositives masquées dans Java Slides


## Introduction à la conversion d'une présentation PowerPoint en PDF avec diapositives masquées à l'aide d'Aspose.Slides pour Java

Dans ce guide étape par étape, vous apprendrez à convertir une présentation PowerPoint en PDF tout en conservant les diapositives masquées grâce à Aspose.Slides pour Java. Les diapositives masquées sont celles qui ne sont pas affichées lors d'une présentation standard, mais qui peuvent être incluses dans le PDF. Nous vous fournirons le code source et des instructions détaillées pour réaliser cette tâche.

## Prérequis

Avant de commencer, assurez-vous de disposer des prérequis suivants :

1. Bibliothèque Aspose.Slides pour Java : Assurez-vous que la bibliothèque Aspose.Slides pour Java est configurée dans votre projet Java. Vous pouvez la télécharger depuis le [Documentation Aspose.Slides pour Java](https://reference.aspose.com/slides/java/).

2. Environnement de développement Java : vous devez disposer d’un environnement de développement Java installé sur votre système.

## Étape 1 : Importer Aspose.Slides pour Java

Tout d'abord, vous devez importer la bibliothèque Aspose.Slides dans votre projet Java. Assurez-vous d'avoir ajouté la bibliothèque au chemin de compilation de votre projet.

```java
import com.aspose.slides.*;
```

## Étape 2 : Charger la présentation PowerPoint

Commencez par charger la présentation PowerPoint que vous souhaitez convertir en PDF. Remplacez `"Your Document Directory"` et `"HiddingSlides.pptx"` avec le chemin de fichier approprié.

```java
// Le chemin vers le répertoire des documents.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
```

## Étape 3 : Configurer les options PDF

Configurez les options PDF pour inclure les diapositives masquées dans la sortie PDF. Pour ce faire, définissez l'option `setShowHiddenSlides` propriété de la `PdfOptions` classe à `true`.

```java
// Instancier la classe PdfOptions
PdfOptions pdfOptions = new PdfOptions();
// Spécifiez que le document généré doit inclure des diapositives masquées
pdfOptions.setShowHiddenSlides(true);
```

## Étape 4 : Enregistrer la présentation au format PDF

Enregistrez maintenant la présentation au format PDF avec les options spécifiées. Remplacer `"PDFWithHiddenSlides_out.pdf"` avec le nom de fichier de sortie souhaité.

```java
// Enregistrer la présentation au format PDF avec les options spécifiées
presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## Étape 5 : Nettoyer les ressources

Assurez-vous de libérer les ressources utilisées par la présentation lorsque vous avez terminé.

```java
finally
{
    if (presentation != null) presentation.dispose();
}
```

## Code source complet pour la conversion en PDF avec diapositives masquées dans Java Slides

```java
// Le chemin vers le répertoire des documents.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
try
{
	// Instancier la classe PdfOptions
	PdfOptions pdfOptions = new PdfOptions();
	// Spécifiez que le document généré doit inclure des diapositives masquées
	pdfOptions.setShowHiddenSlides(true);
	// Enregistrer la présentation au format PDF avec les options spécifiées
	presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusion

Dans ce guide complet, vous avez appris à convertir une présentation PowerPoint en PDF tout en conservant les diapositives masquées grâce à Aspose.Slides pour Java. Nous vous proposons un tutoriel étape par étape ainsi que le code source nécessaire pour réaliser cette tâche en toute simplicité.

## FAQ

### Comment puis-je masquer des diapositives dans une présentation PowerPoint ?

Pour masquer une diapositive dans une présentation PowerPoint, procédez comme suit :
1. Sélectionnez la diapositive que vous souhaitez masquer dans la vue Trieuse de diapositives.
2. Cliquez avec le bouton droit sur la diapositive sélectionnée.
3. Choisissez « Masquer la diapositive » dans le menu contextuel.

### Puis-je afficher par programmation les diapositives masquées dans Aspose.Slides pour Java ?

Oui, vous pouvez afficher par programmation les diapositives masquées dans Aspose.Slides pour Java en définissant le `Hidden` propriété de la `Slide` classe à `false`Voici un exemple :

```java
Slide slide = presentation.getSlides().get_Item(slideIndex); // Remplacez slideIndex par l'index de la diapositive masquée
slide.setHidden(false);
```

### Comment télécharger Aspose.Slides pour Java ?

Vous pouvez télécharger Aspose.Slides pour Java depuis le site web d'Aspose. Visitez le [Page de téléchargement d'Aspose.Slides pour Java](https://releases.aspose.com/slides/java/) pour obtenir la dernière version.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}