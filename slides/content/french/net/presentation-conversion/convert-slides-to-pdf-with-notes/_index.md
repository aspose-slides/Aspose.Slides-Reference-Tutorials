---
title: Convertir des diapositives en PDF avec des notes
linktitle: Convertir des diapositives en PDF avec des notes
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Convertissez sans effort les diapositives de présentation avec les notes du présentateur au format PDF à l'aide d'Aspose.Slides pour .NET. Préservez le contenu et le contexte de manière transparente.
type: docs
weight: 18
url: /fr/net/presentation-conversion/convert-slides-to-pdf-with-notes/
---

# Rédigez un didacticiel étape par étape sur la conversion de diapositives en PDF avec des notes à l'aide d'Aspose.Slides pour .NET

Recherchez-vous un moyen fiable de convertir vos diapositives PowerPoint au format PDF tout en préservant toutes les notes importantes ? Cherchez pas plus loin! Dans ce didacticiel complet, nous vous guiderons tout au long du processus d'utilisation d'Aspose.Slides pour .NET pour réaliser cette tâche étape par étape.

## 1. Introduction

La conversion de diapositives PowerPoint en PDF avec des notes peut être un outil précieux pour partager des présentations tout en garantissant que le contexte et les commentaires importants sont conservés. Aspose.Slides pour .NET fournit une solution puissante pour cette tâche.

## 2. Configuration de votre environnement

Avant de plonger dans le processus de codage, assurez-vous d’avoir configuré l’environnement nécessaire. Tu auras besoin:

- Visual Studio ou votre environnement de développement .NET préféré.
- Aspose.Slides pour la bibliothèque .NET installée.
- Une présentation PowerPoint avec des notes que vous souhaitez convertir.

## 3. Chargement de la présentation

Dans votre code C#, vous devez charger la présentation PowerPoint que vous souhaitez convertir. Voici comment procéder :

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
```

## 4. Clonage de la diapositive

Pour vous assurer que votre PDF comprend toutes les diapositives nécessaires avec des notes, vous pouvez les cloner à partir de la présentation originale. Voici comment:

```csharp
Presentation auxPresentation = new Presentation();
ISlide slide = presentation.Slides[0];
auxPresentation.Slides.InsertClone(0, slide);
```

## 5. Ajustement de la taille de la diapositive

Vous souhaiterez peut-être ajuster la taille de la diapositive pour l'adapter à votre PDF. Aspose.Slides pour .NET vous permet de le faire facilement :

```csharp
auxPresentation.SlideSize.SetSize(612F, 792F, SlideSizeScaleType.EnsureFit);
```

## 6. Configuration des options PDF

Pour contrôler la façon dont vos notes seront affichées dans le PDF, vous pouvez configurer les options PDF :

```csharp
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.NotesCommentsLayouting;
options.NotesPosition = NotesPositions.BottomFull;
```

## 7. Enregistrement au format PDF avec Notes

Enfin, vous pouvez enregistrer votre présentation au format PDF avec des notes :

```csharp
auxPresentation.Save(outPath + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## 8. Conclusion

Toutes nos félicitations! Vous avez converti avec succès vos diapositives PowerPoint au format PDF tout en préservant toutes les notes importantes. Aspose.Slides pour .NET rend ce processus simple et efficace.

## 9. FAQ

### Q1 : Puis-je personnaliser la mise en page des notes dans le PDF ?

 Oui, vous pouvez personnaliser la disposition des notes à l'aide du`INotesCommentsLayoutingOptions` dans les options PDF.

### Q2 : Aspose.Slides pour .NET prend-il en charge d'autres formats de sortie que le PDF ?

Oui, Aspose.Slides pour .NET prend en charge divers formats de sortie, notamment PPTX, DOCX, etc.

### Q3 : Existe-t-il une version d’essai disponible pour Aspose.Slides pour .NET ?

 Oui, vous pouvez obtenir un essai gratuit d'Aspose.Slides pour .NET sur[https://releases.aspose.com/](https://releases.aspose.com/).

### Q4 : Où puis-je obtenir de l'aide pour Aspose.Slides pour .NET ?

 Vous pouvez trouver du soutien et des discussions communautaires sur[https://forum.aspose.com/](https://forum.aspose.com/).

### Q5 : Puis-je acheter une licence temporaire pour Aspose.Slides pour .NET ?

 Oui, vous pouvez acheter une licence temporaire à[https://purchase.aspose.com/temporary-license/](https://purchase.aspose.com/temporary-license/).

En conclusion, en utilisant Aspose.Slides pour .NET, vous pouvez facilement convertir des diapositives PowerPoint au format PDF avec les notes intactes. Il s'agit d'un outil précieux pour les professionnels qui ont besoin de partager des présentations avec des collègues et des clients tout en garantissant que le contexte important n'est pas perdu.