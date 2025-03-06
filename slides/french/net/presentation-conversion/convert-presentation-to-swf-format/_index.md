---
title: Convertir la présentation au format SWF
linktitle: Convertir la présentation au format SWF
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Découvrez comment convertir des présentations PowerPoint au format SWF à l'aide d'Aspose.Slides pour .NET. Créez du contenu dynamique sans effort !
weight: 28
url: /fr/net/presentation-conversion/convert-presentation-to-swf-format/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Convertir la présentation au format SWF


À l’ère numérique d’aujourd’hui, les présentations multimédias constituent un moyen de communication puissant. Parfois, vous souhaiterez peut-être partager vos présentations de manière plus dynamique, par exemple en les convertissant au format SWF (Shockwave Flash). Ce guide vous guidera tout au long du processus de conversion d'une présentation au format SWF à l'aide d'Aspose.Slides pour .NET.

## Ce dont vous aurez besoin

Avant de plonger dans le didacticiel, assurez-vous d'avoir les éléments suivants :

-  Aspose.Slides pour .NET : si vous ne l'avez pas déjà, vous pouvez[Télécharger les ici](https://releases.aspose.com/slides/net/).

- Un fichier de présentation : vous aurez besoin d'un fichier de présentation PowerPoint que vous souhaitez convertir au format SWF.

## Étape 1 : Configurez votre environnement

Pour commencer, créez un répertoire pour votre projet. Appelons-le « Votre répertoire de projets ». Dans ce répertoire, vous devrez placer le code source suivant :

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

// Instancier un objet Présentation qui représente un fichier de présentation
using (Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx"))
{
    SwfOptions swfOptions = new SwfOptions();
    swfOptions.ViewerIncluded = false;

    INotesCommentsLayoutingOptions notesOptions = swfOptions.NotesCommentsLayouting;
    notesOptions.NotesPosition = NotesPositions.BottomFull;

    // Enregistrer les pages de présentation et de notes
    presentation.Save(dataDir + "SaveAsSwf_out.swf", SaveFormat.Swf, swfOptions);
    swfOptions.ViewerIncluded = true;
    presentation.Save(dataDir + "SaveNotes_out.swf", SaveFormat.Swf, swfOptions);
}
```

 Assurez-vous de remplacer`"Your Document Directory"` et`"Your Output Directory"` avec les chemins réels où se trouve votre fichier de présentation et où vous souhaitez enregistrer les fichiers SWF.

## Étape 2 : chargement de la présentation

Dans cette étape, nous chargeons la présentation PowerPoint à l'aide d'Aspose.Slides :

```csharp
using (Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx"))
```

 Remplacer`"HelloWorld.pptx"` avec le nom de votre fichier de présentation.

## Étape 3 : Configurer les options de conversion SWF

Nous configurons les options de conversion SWF pour personnaliser la sortie :

```csharp
SwfOptions swfOptions = new SwfOptions();
swfOptions.ViewerIncluded = false;

INotesCommentsLayoutingOptions notesOptions = swfOptions.NotesCommentsLayouting;
notesOptions.NotesPosition = NotesPositions.BottomFull;
```

Vous pouvez ajuster ces options en fonction de vos besoins.

## Étape 4 : Enregistrer au format SWF

Maintenant, nous enregistrons la présentation sous forme de fichier SWF :

```csharp
presentation.Save(dataDir + "SaveAsSwf_out.swf", SaveFormat.Swf, swfOptions);
```

Cette ligne enregistrera la présentation principale sous forme de fichier SWF.

## Étape 5 : Enregistrer avec Notes

Si vous souhaitez inclure des notes, utilisez ce code :

```csharp
swfOptions.ViewerIncluded = true;
presentation.Save(dataDir + "SaveNotes_out.swf", SaveFormat.Swf, swfOptions);
```

Ce code enregistre la présentation avec des notes au format SWF.

## Conclusion

Toutes nos félicitations! Vous avez converti avec succès une présentation PowerPoint au format SWF à l'aide d'Aspose.Slides pour .NET. Cela peut être particulièrement utile lorsque vous devez partager vos présentations en ligne ou les intégrer dans des pages Web.

 Pour plus d’informations et une documentation détaillée, vous pouvez visiter le[Aspose.Slides pour référence .NET](https://reference.aspose.com/slides/net/).

## FAQ

### Qu’est-ce que le format SWF ?
SWF (Shockwave Flash) est un format multimédia utilisé pour les animations, les jeux et le contenu interactif sur le Web.

### L’utilisation d’Aspose.Slides pour .NET est-elle gratuite ?
 Aspose.Slides pour .NET propose un essai gratuit, mais pour bénéficier de toutes les fonctionnalités, vous devrez peut-être acheter une licence. Vous pouvez vérifier les détails des prix et des licences[ici](https://purchase.aspose.com/buy).

### Puis-je essayer Aspose.Slides pour .NET avant d’acheter une licence ?
 Oui, vous pouvez obtenir un essai gratuit d'Aspose.Slides pour .NET[ici](https://releases.aspose.com/).

### Ai-je besoin de compétences en programmation pour utiliser Aspose.Slides pour .NET ?
Oui, vous devez avoir des connaissances en programmation C# pour utiliser efficacement Aspose.Slides.

### Où puis-je obtenir de l’assistance pour Aspose.Slides pour .NET ?
 Si vous avez des questions ou avez besoin d'aide, vous pouvez visiter le[Forum Aspose.Slides pour .NET](https://forum.aspose.com/)pour le soutien et l’aide de la communauté.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
