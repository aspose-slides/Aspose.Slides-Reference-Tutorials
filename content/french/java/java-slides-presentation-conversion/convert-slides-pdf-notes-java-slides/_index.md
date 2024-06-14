---
title: Convertir des diapositives en PDF avec des notes dans Java Slides
linktitle: Convertir des diapositives en PDF avec des notes dans Java Slides
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment convertir des diapositives PowerPoint en PDF avec des notes en Java à l'aide d'Aspose.Slides pour Java. Guide étape par étape pour les développeurs Java. Améliorez le partage de vos présentations.
type: docs
weight: 19
url: /fr/java/presentation-conversion/convert-slides-pdf-notes-java-slides/
---

## Introduction à la conversion de diapositives en PDF avec Notes en Java

Dans le monde des présentations numériques, la possibilité de convertir des diapositives en PDF accompagnées de notes est une fonctionnalité précieuse. Les développeurs Java peuvent y parvenir en utilisant la bibliothèque Aspose.Slides pour Java, qui fournit un ensemble d'outils robustes pour travailler avec des présentations PowerPoint par programmation. Dans ce guide étape par étape, nous explorerons comment convertir des diapositives en PDF avec des notes à l'aide de Java et Aspose.Slides pour Java.

## Conditions préalables

Avant de plonger dans le code, assurez-vous que les conditions préalables suivantes sont en place :

- Kit de développement Java (JDK) installé sur votre système.
-  Aspose.Slides pour la bibliothèque Java. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/slides/java/).

Maintenant que nous avons notre plan, passons à la mise en œuvre étape par étape.
## Étape 1 : Mise en place du projet

Tout d’abord, créez un projet Java et ajoutez la bibliothèque Aspose.Slides for Java aux dépendances de votre projet.

## Étape 2 : chargement de la présentation

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
```

## Étape 3 : Création d'une nouvelle présentation

```java
Presentation auxPresentation = new Presentation();
```

## Étape 4 : Copier les diapositives

```java
ISlide slide = presentation.getSlides().get_Item(0);
auxPresentation.getSlides().insertClone(0, slide);
```

## Étape 5 : Ajustement de la taille de la diapositive

```java
auxPresentation.getSlideSize().setSize(612F, 792F, SlideSizeScaleType.EnsureFit);
```

## Étape 6 : Configuration des options PDF

```java
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
options.setNotesPosition(NotesPositions.BottomFull);
```

## Étape 7 : Enregistrer au format PDF

```java
auxPresentation.save(dataDir + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## Code source complet pour convertir des diapositives en PDF avec des notes dans les diapositives Java

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
// Instancier un objet Présentation qui représente un fichier de présentation
Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
try
{
	Presentation auxPresentation = new Presentation();
	try
	{
		ISlide slide = presentation.getSlides().get_Item(0);
		auxPresentation.getSlides().insertClone(0, slide);
		// Définition du type et de la taille des diapositives
		//auxPresentation.getSlideSize().setSize(presentation.getSlideSize().getSize().getWidth(), présentation.getSlideSize().getSize().getHeight(),SlideSizeScaleType.EnsureFit);
		auxPresentation.getSlideSize().setSize(612F, 792F, SlideSizeScaleType.EnsureFit);
		PdfOptions pdfOptions = new PdfOptions();
		INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
		options.setNotesPosition(NotesPositions.BottomFull);
		auxPresentation.save(dataDir + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
	}
	finally
	{
		if (auxPresentation != null) auxPresentation.dispose();
	}
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusion

Dans ce didacticiel, nous avons appris à convertir des diapositives en PDF avec des notes en Java à l'aide d'Aspose.Slides pour Java. Nous avons couvert la configuration du projet, le chargement de la présentation, la création d'une nouvelle présentation, la copie des diapositives, l'ajustement de la taille des diapositives, la configuration des options PDF et enfin, l'enregistrement de la présentation au format PDF avec des notes.

## FAQ

### Comment installer Aspose.Slides pour Java ?

Pour installer Aspose.Slides pour Java, procédez comme suit :
1.  Téléchargez la bibliothèque depuis[ici](https://releases.aspose.com/slides/java/).
2. Ajoutez le fichier JAR au chemin de classe de votre projet Java.

### Puis-je personnaliser la position des notes dans le PDF généré ?

 Oui, vous pouvez personnaliser la position des notes en modifiant le`NotesPositions` énumération dans les options PDF. Dans ce tutoriel, nous l'avons défini sur`BottomFull`, mais vous pouvez également explorer d'autres options.

### Existe-t-il des conditions de licence pour utiliser Aspose.Slides pour Java ?

Oui, Aspose.Slides pour Java est une bibliothèque commerciale et vous devrez peut-être acquérir une licence pour l'utiliser en production. Visitez le site Web Aspose pour plus de détails sur les licences.

### Puis-je convertir plusieurs diapositives à la fois ?

Certainement! Vous pouvez parcourir les diapositives de votre présentation et les cloner dans la nouvelle présentation, ce qui vous permet de convertir plusieurs diapositives au format PDF avec des notes en une seule fois.

### Où puis-je trouver plus de documentation sur Aspose.Slides pour Java ?

 Vous pouvez trouver une documentation détaillée pour Aspose.Slides pour Java sur le site :[Référence de l'API Aspose.Slides pour Java](https://reference.aspose.com/slides/java/).