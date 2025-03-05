---
title: Convertir une diapositive individuelle dans des diapositives Java
linktitle: Convertir une diapositive individuelle dans des diapositives Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Apprenez à convertir des diapositives PowerPoint individuelles en HTML étape par étape avec des exemples de code utilisant Aspose.Slides pour Java.
type: docs
weight: 12
url: /fr/java/presentation-conversion/convert-individual-slide-java-slides/
---

## Introduction à la conversion de diapositives individuelles dans des diapositives Java

Dans ce didacticiel, nous passerons en revue le processus de conversion de diapositives individuelles d'une présentation PowerPoint en HTML à l'aide d'Aspose.Slides pour Java. Ce guide étape par étape vous fournira le code source et des explications pour vous aider à réaliser cette tâche.

## Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Aspose.Slides pour la bibliothèque Java installée.
- Un fichier de présentation PowerPoint (`Individual-Slide.pptx`) que vous souhaitez convertir.
- Environnement de développement Java mis en place.

## Étape 1 : Configurer le projet

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

 Créez une méthode pour effectuer la conversion de diapositives individuelles. Assurez-vous de remplacer`"Your Document Directory"` avec le chemin réel vers votre répertoire de documents.

```java
public static void convertIndividualSlides() {
    String dataDir = "Your Document Directory";
    Presentation presentation = new Presentation(dataDir + "Individual-Slide.pptx");
    try {
        HtmlOptions htmlOptions = new HtmlOptions();
        htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(new CustomFormattingController()));
        INotesCommentsLayoutingOptions notesOptions = htmlOptions.getNotesCommentsLayouting();
        notesOptions.setNotesPosition(NotesPositions.BottomFull);
        
        // Enregistrement du fichier
        for (int i = 0; i < presentation.getSlides().size(); i++) {
            presentation.save(dataDir + "Individual-Slide" + (i + 1) + "_out.html", new int[]{i + 1}, SaveFormat.Html, htmlOptions);
        }
    } finally {
        if (presentation != null) presentation.dispose();
    }
}
```

## Étape 4 : implémenter le CustomFormattingController

 Créer le`CustomFormattingController` classe pour gérer le formatage personnalisé lors de la conversion.

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

 Enfin, appelez le`convertIndividualSlides` méthode pour exécuter le processus de conversion.

```java
public static void main(String[] args) {
    convertIndividualSlides();
}
```

## Code source complet pour convertir une diapositive individuelle en diapositives Java

```java
	String dataDir = "Your Document Directory";
	Presentation presentation = new Presentation(dataDir + "Individual-Slide.pptx");
	try
	{
		HtmlOptions htmlOptions = new HtmlOptions();
		htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(new CustomFormattingController()));
		INotesCommentsLayoutingOptions notesOptions = htmlOptions.getNotesCommentsLayouting();
		notesOptions.setNotesPosition(NotesPositions.BottomFull);
		// Enregistrement du fichier
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

Vous avez réussi à convertir des diapositives individuelles d'une présentation PowerPoint en HTML à l'aide d'Aspose.Slides pour Java. Ce didacticiel vous a fourni le code et les étapes nécessaires pour réaliser cette tâche. N'hésitez pas à personnaliser la sortie et le formatage selon vos besoins spécifiques.

## FAQ

### Comment puis-je personnaliser davantage la sortie HTML ?

 Vous pouvez personnaliser la sortie HTML en modifiant le`CustomFormattingController` classe. Ajuste le`writeSlideStart` et`writeSlideEnd` méthodes pour modifier la structure et le style HTML des diapositives.

### Puis-je convertir plusieurs présentations PowerPoint en une seule fois ?

 Oui, vous pouvez modifier le code pour parcourir plusieurs fichiers de présentation et les convertir individuellement en appelant le`convertIndividualSlides` méthode pour chaque présentation.

### Comment gérer une mise en forme supplémentaire pour les formes et le texte dans les diapositives ?

 Vous pouvez prolonger le`CustomFormattingController` classe pour gérer le formatage spécifique à la forme en implémentant la`writeShapeStart` et`writeShapeEnd` méthodes et en leur appliquant une logique de formatage personnalisée.