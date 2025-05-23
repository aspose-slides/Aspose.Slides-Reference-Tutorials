---
"description": "Convertissez facilement vos diapositives de présentation avec notes au format PDF grâce à Aspose.Slides pour .NET. Préservez le contenu et le contexte en toute transparence."
"linktitle": "Convertir des diapositives en PDF avec des notes"
"second_title": "API de traitement PowerPoint Aspose.Slides .NET"
"title": "Convertir des diapositives en PDF avec des notes"
"url": "/fr/net/presentation-conversion/convert-slides-to-pdf-with-notes/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Convertir des diapositives en PDF avec des notes


# Rédigez un guide étape par étape sur la conversion de diapositives au format PDF avec des notes à l'aide d'Aspose.Slides pour .NET.

Vous cherchez un moyen fiable de convertir vos diapositives PowerPoint au format PDF tout en préservant toutes vos notes importantes ? Ne cherchez plus ! Dans ce tutoriel complet, nous vous guiderons pas à pas dans l'utilisation d'Aspose.Slides pour .NET.

## 1. Introduction

Convertir des diapositives PowerPoint en PDF avec des annotations peut s'avérer un outil précieux pour partager des présentations tout en préservant le contexte et les commentaires importants. Aspose.Slides pour .NET offre une solution performante pour cette tâche.

## 2. Configuration de votre environnement

Avant de commencer le codage, assurez-vous de disposer de l'environnement nécessaire. Vous aurez besoin de :

- Visual Studio ou votre environnement de développement .NET préféré.
- Bibliothèque Aspose.Slides pour .NET installée.
- Une présentation PowerPoint avec des notes que vous souhaitez convertir.

## 3. Chargement de la présentation

Dans votre code C#, vous devez charger la présentation PowerPoint à convertir. Voici comment procéder :

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
```

## 4. Clonage de la diapositive

Pour vous assurer que votre PDF inclut toutes les diapositives et notes nécessaires, vous pouvez les cloner à partir de la présentation originale. Voici comment :

```csharp
Presentation auxPresentation = new Presentation();
ISlide slide = presentation.Slides[0];
auxPresentation.Slides.InsertClone(0, slide);
```

## 5. Réglage de la taille des diapositives

Vous pouvez ajuster la taille des diapositives à votre PDF. Aspose.Slides pour .NET vous permet de le faire facilement :

```csharp
auxPresentation.SlideSize.SetSize(612F, 792F, SlideSizeScaleType.EnsureFit);
```

## 6. Configuration des options PDF

Pour contrôler la manière dont vos notes seront affichées dans le PDF, vous pouvez configurer les options PDF :

```csharp
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.NotesCommentsLayouting;
options.NotesPosition = NotesPositions.BottomFull;
```

## 7. Enregistrer au format PDF avec des notes

Enfin, vous pouvez enregistrer votre présentation au format PDF avec des notes :

```csharp
auxPresentation.Save(outPath + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## 8. Conclusion

Félicitations ! Vous avez réussi à convertir vos diapositives PowerPoint au format PDF tout en conservant toutes les notes importantes. Aspose.Slides pour .NET simplifie et optimise ce processus.

## 9. FAQ

### Q1 : Puis-je personnaliser la mise en page des notes dans le PDF ?

Oui, vous pouvez personnaliser la mise en page des notes à l'aide du `INotesCommentsLayoutingOptions` dans les options PDF.

### Q2 : Aspose.Slides pour .NET prend-il en charge d’autres formats de sortie en plus du PDF ?

Oui, Aspose.Slides pour .NET prend en charge divers formats de sortie, notamment PPTX, DOCX, etc.

### Q3 : Existe-t-il une version d’essai disponible pour Aspose.Slides pour .NET ?

Oui, vous pouvez obtenir un essai gratuit d'Aspose.Slides pour .NET sur [https://releases.aspose.com/](https://releases.aspose.com/).

### Q4 : Où puis-je obtenir de l’aide pour Aspose.Slides pour .NET ?

Vous pouvez trouver du soutien et des discussions communautaires sur [https://forum.aspose.com/](https://forum.aspose.com/).

### Q5 : Puis-je acheter une licence temporaire pour Aspose.Slides pour .NET ?

Oui, vous pouvez acheter une licence temporaire sur [https://purchase.aspose.com/temporary-license/](https://purchase.aspose.com/temporary-license/).

En conclusion, avec Aspose.Slides pour .NET, vous pouvez facilement convertir des diapositives PowerPoint au format PDF en conservant les notes. C'est un outil précieux pour les professionnels qui doivent partager des présentations avec leurs collègues et clients tout en préservant le contexte important.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}