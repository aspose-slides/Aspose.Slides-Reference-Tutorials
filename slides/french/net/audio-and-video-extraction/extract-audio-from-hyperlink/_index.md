---
title: Extraire l'audio des hyperliens PowerPoint avec Aspose.Slides
linktitle: Extraire l'audio d'un lien hypertexte
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Extrayez l'audio des hyperliens dans les présentations PowerPoint à l'aide d'Aspose.Slides pour .NET. Améliorez vos projets multimédias sans effort.
type: docs
weight: 12
url: /fr/net/audio-and-video-extraction/extract-audio-from-hyperlink/
---

Dans le monde des présentations multimédias, l'audio joue un rôle essentiel dans l'amélioration de l'impact global de vos diapositives. Avez-vous déjà rencontré une présentation PowerPoint avec des hyperliens audio et vous êtes-vous demandé comment extraire l'audio pour d'autres utilisations ? Avec Aspose.Slides pour .NET, vous pouvez réaliser cette tâche sans effort. Dans ce guide étape par étape, nous vous guiderons tout au long du processus d'extraction audio d'un lien hypertexte dans une présentation PowerPoint.

## Conditions préalables

Avant de plonger dans le processus d’extraction, assurez-vous d’avoir les conditions préalables suivantes en place :

### 1. Aspose.Slides pour la bibliothèque .NET

La bibliothèque Aspose.Slides pour .NET doit être installée dans votre environnement de développement. Si ce n'est pas déjà fait, vous pouvez le télécharger sur le site Web à l'adresse[Documentation Aspose.Slides pour .NET](https://reference.aspose.com/slides/net/).

### 2. Présentation PowerPoint avec hyperliens audio

Assurez-vous d'avoir une présentation PowerPoint (PPTX) contenant des hyperliens avec l'audio associé. Ce sera la source à partir de laquelle vous extrairez l’audio.

## Importation d'espaces de noms

Tout d’abord, importons les espaces de noms nécessaires dans votre projet C# pour utiliser efficacement Aspose.Slides pour .NET. Ces espaces de noms sont essentiels pour travailler avec des présentations PowerPoint et extraire l'audio des hyperliens.

```csharp
using System;
using System.IO;
using Aspose.Slides;
```

Maintenant que nos prérequis sont en place et que les espaces de noms requis sont importés, décomposons le processus d'extraction en plusieurs étapes.

## Étape 1 : Définir le répertoire des documents

 Commencez par spécifier le répertoire où se trouve votre présentation PowerPoint. Vous pouvez remplacer`"Your Document Directory"` avec le chemin réel vers votre répertoire de documents.

```csharp
string dataDir = "Your Document Directory";
```

## Étape 2 : Charger la présentation PowerPoint

 Chargez la présentation PowerPoint (PPTX) qui contient le lien hypertexte audio à l'aide d'Aspose.Slides. Remplacer`"HyperlinkSound.pptx"`avec le nom de fichier réel de votre présentation.

```csharp
string pptxFile = Path.Combine(dataDir, "HyperlinkSound.pptx");

using (Presentation pres = new Presentation(pptxFile))
{
    // Continuer à l'étape suivante.
}
```

## Étape 3 : Obtenez le son du lien hypertexte

Obtenez le lien hypertexte de la première forme à partir de la diapositive PowerPoint. Si le lien hypertexte a un son associé, nous procéderons à son extraction.

```csharp
IHyperlink link = pres.Slides[0].Shapes[0].HyperlinkClick;

if (link.Sound != null)
{
    // Continuer à l'étape suivante.
}
```

## Étape 4 : Extraire l'audio du lien hypertexte

Si le lien hypertexte est associé à un son, nous pouvons l'extraire sous forme de tableau d'octets et l'enregistrer en tant que fichier multimédia.

```csharp
// Extrait le son du lien hypertexte dans un tableau d'octets
byte[] audioData = link.Sound.BinaryData;

// Spécifiez le chemin où vous souhaitez enregistrer l'audio extrait
string outMediaPath = Path.Combine(dataDir, "HyperlinkSound.mpg");

// Enregistrez l'audio extrait dans un fichier multimédia
File.WriteAllBytes(outMediaPath, audioData);
```

Toutes nos félicitations! Vous avez réussi à extraire l'audio d'un lien hypertexte dans une présentation PowerPoint à l'aide d'Aspose.Slides pour .NET. Cet audio extrait peut désormais être utilisé à d’autres fins dans vos projets multimédia.

## Conclusion

Aspose.Slides pour .NET fournit une solution puissante et conviviale pour extraire l'audio des hyperliens dans les présentations PowerPoint. Avec les étapes décrites dans ce guide, vous pouvez améliorer sans effort vos projets multimédia en réutilisant le contenu audio de vos présentations.

### Foire aux questions (FAQ)

### Aspose.Slides pour .NET est-il une bibliothèque gratuite ?
 Non, Aspose.Slides pour .NET est une bibliothèque commerciale, mais vous pouvez explorer ses fonctionnalités et sa documentation en téléchargeant un essai gratuit sur[ici](https://releases.aspose.com/).

### Puis-je extraire l’audio des hyperliens dans d’anciens formats PowerPoint comme PPT ?
Oui, Aspose.Slides pour .NET prend en charge les formats PPTX et PPT pour extraire l'audio des hyperliens.

### Existe-t-il un forum communautaire pour le support Aspose.Slides ?
 Oui, vous pouvez obtenir de l'aide et partager vos expériences avec Aspose.[Forum communautaire Aspose.Slides](https://forum.aspose.com/).

### Puis-je acheter une licence temporaire pour Aspose.Slides pour un projet à court terme ?
Oui, vous pouvez obtenir une licence temporaire pour Aspose.Slides pour .NET afin de répondre aux besoins de votre projet à court terme en visitant[ce lien](https://purchase.aspose.com/temporary-license/).

### Existe-t-il d'autres formats audio pris en charge pour l'extraction, en dehors du MPG ?
Aspose.Slides pour .NET vous permet d'extraire de l'audio dans différents formats, sans se limiter au MPG. Vous pouvez le convertir dans votre format préféré après l'extraction.
