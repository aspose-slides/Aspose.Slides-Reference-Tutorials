---
"description": "Apprenez à convertir des diapositives PowerPoint individuelles en HTML étape par étape avec des exemples de code à l'aide d'Aspose.Slides pour Java."
"linktitle": "Convertir des diapositives individuelles dans Java Slides"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Convertir des diapositives individuelles dans Java Slides"
"url": "/fr/java/presentation-conversion/convert-individual-slide-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Convertir des diapositives individuelles dans Java Slides


## Introduction à la conversion de diapositives individuelles dans Java Slides

Dans ce tutoriel, nous allons vous expliquer comment convertir des diapositives individuelles d'une présentation PowerPoint en HTML avec Aspose.Slides pour Java. Ce guide étape par étape vous fournira le code source et les explications nécessaires pour réaliser cette tâche.

## Prérequis

Avant de commencer, assurez-vous d’avoir les éléments suivants :

- Bibliothèque Aspose.Slides pour Java installée.
- Un fichier de présentation PowerPoint (`Individual-Slide.pptx`) que vous souhaitez convertir.
- Configuration de l'environnement de développement Java.

## Étape 1 : Configurer le projet

1. Créez un projet Java dans votre environnement de développement préféré.
2. Ajoutez la bibliothèque Aspose.Slides pour Java à votre projet.

## Étape 2 : Importer les classes nécessaires

Dans votre classe Java, importez les classes requises et configurez la configuration initiale.

```java
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.INotesCommentsLayoutingOptions;
import com.aspose.slides.NotesPositions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.IHtmlFormattingController;
import com.aspose.slides.IHtmlGenerator;
import com.aspose.slides.ISlide;
import com.aspose.slides.IShape;
```

## Étape 3 : Définir la méthode de conversion principale

Créez une méthode pour convertir des diapositives individuelles. Assurez-vous de remplacer `"Your Document Directory"` avec le chemin réel vers votre répertoire de documents.

```java
public static void convertIndividualSlides() {
    String dataDir = "Your Document Directory";
    Presentation presentation = new Presentation(dataDir + "Individual-Slide.pptx");
    try {
        HtmlOptions htmlOptions = new HtmlOptions();
        htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(new CustomFormattingController()));
        INotesCommentsLayoutingOptions notesOptions = htmlOptions.getNotesCommentsLayouting();
        notesOptions.setNotesPosition(NotesPositions.BottomFull);
        
        // Sauvegarde du fichier
        for (int i = 0; i < presentation.getSlides().size(); i++) {
            presentation.save(dataDir + "Individual-Slide" + (i + 1) + "_out.html", new int[]{i + 1}, SaveFormat.Html, htmlOptions);
        }
    } finally {
        if (presentation != null) presentation.dispose();
    }
}
```

## Étape 4 : implémenter le CustomFormattingController

Créer le `CustomFormattingController` classe pour gérer le formatage personnalisé pendant la conversion.

```java
public static class CustomFormattingController implements IHtmlFormattingController {
    public void writeDocumentStart(IHtmlGenerator generator, IPresentation presentation) {
    }
    
    public void writeDocumentEnd(IHtmlGenerator generator, IPresentation presentation) {
    }
    
    public void writeSlideStart(IHtmlGenerator generator, ISlide slide) {
        generator.addHtml(String.format(SlideHeader, generator.getSlideIndex() + 1));
    }
    
    public void writeSlideEnd(IHtmlGenerator generator, ISlide slide) {
        generator.addHtml(SlideFooter);
    }
    
    public void writeShapeStart(IHtmlGenerator generator, IShape shape) {
    }
    
    public void writeShapeEnd(IHtmlGenerator generator, IShape shape) {
    }
    
    private static String SlideHeader = "<div class=\"slide\" name=\"slide\" id=\"slide{0}\">";
    private static String SlideFooter = "</div>";
}
```

## Étape 5 : Exécuter la conversion

Enfin, appelez le `convertIndividualSlides` méthode pour exécuter le processus de conversion.

```java
public static void main(String[] args) {
    convertIndividualSlides();
}
```

## Code source complet pour convertir des diapositives individuelles en diapositives Java

```java
	String dataDir = "Your Document Directory";
	Presentation presentation = new Presentation(dataDir + "Individual-Slide.pptx");
	try
	{
		HtmlOptions htmlOptions = new HtmlOptions();
		htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(new CustomFormattingController()));
		INotesCommentsLayoutingOptions notesOptions = htmlOptions.getNotesCommentsLayouting();
		notesOptions.setNotesPosition(NotesPositions.BottomFull);
		// Sauvegarde du fichier              
		for (int i = 0; i < presentation.getSlides().size(); i++)
			presentation.save(dataDir + "Individual Slide" + i + 1 + "_out.html", new int[]{i + 1}, SaveFormat.Html, htmlOptions);
	}
	finally
	{
		if (presentation != null) presentation.dispose();
	}
}
public static class CustomFormattingController implements IHtmlFormattingController
{
	public void writeDocumentStart(IHtmlGenerator generator, IPresentation presentation)
	{
	}
	public void writeDocumentEnd(IHtmlGenerator generator, IPresentation presentation)
	{
	}
	public void writeSlideStart(IHtmlGenerator generator, ISlide slide)
	{
		generator.addHtml(String.format(SlideHeader, generator.getSlideIndex() + 1));
	}
	public void writeSlideEnd(IHtmlGenerator generator, ISlide slide)
	{
		generator.addHtml(SlideFooter);
	}
	public void writeShapeStart(IHtmlGenerator generator, IShape shape)
	{
	}
	public void writeShapeEnd(IHtmlGenerator generator, IShape shape)
	{
	}
	private static String SlideHeader = "<div class=\"slide\" name=\"slide\" id=\"slide{0}\">";
	private static String SlideFooter = "</div>";
```

## Conclusion

Vous avez réussi à convertir des diapositives individuelles d'une présentation PowerPoint en HTML avec Aspose.Slides pour Java. Ce tutoriel vous a fourni le code et les étapes nécessaires pour réaliser cette tâche. N'hésitez pas à personnaliser le rendu et la mise en forme selon vos besoins.

## FAQ

### Comment puis-je personnaliser davantage la sortie HTML ?

Vous pouvez personnaliser la sortie HTML en modifiant le `CustomFormattingController` classe. Ajustez le `writeSlideStart` et `writeSlideEnd` méthodes pour modifier la structure et le style HTML des diapositives.

### Puis-je convertir plusieurs présentations PowerPoint en une seule fois ?

Oui, vous pouvez modifier le code pour parcourir plusieurs fichiers de présentation et les convertir individuellement en appelant la commande `convertIndividualSlides` méthode pour chaque présentation.

### Comment gérer la mise en forme supplémentaire des formes et du texte dans les diapositives ?

Vous pouvez prolonger le `CustomFormattingController` classe pour gérer le formatage spécifique à la forme en implémentant le `writeShapeStart` et `writeShapeEnd` méthodes et en appliquant une logique de formatage personnalisée en leur sein.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}