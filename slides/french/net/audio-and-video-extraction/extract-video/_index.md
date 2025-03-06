---
title: Comment extraire une vidéo d'une diapositive à l'aide d'Aspose.Slides pour .NET
linktitle: Extraire la vidéo de la diapositive
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Découvrez comment extraire des vidéos de diapositives PowerPoint à l'aide d'Aspose.Slides pour .NET. Ce guide étape par étape simplifie le processus pour vous.
weight: 14
url: /fr/net/audio-and-video-extraction/extract-video/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


Aspose.Slides for .NET est une bibliothèque puissante qui vous permet de travailler avec des présentations PowerPoint dans un environnement .NET. L'une des fonctionnalités utiles qu'il offre est la possibilité d'extraire des vidéos à partir de diapositives. Dans ce guide étape par étape, nous allons vous montrer comment extraire une vidéo d'une diapositive PowerPoint à l'aide d'Aspose.Slides pour .NET.

## Conditions préalables

Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :

-  Aspose.Slides pour .NET : Vous devez avoir installé Aspose.Slides pour .NET. Vous pouvez l'obtenir auprès du[site web](https://purchase.aspose.com/buy).

- Une présentation PowerPoint : préparez une présentation PowerPoint (par exemple, Video.pptx) contenant la vidéo que vous souhaitez extraire.

## Importer des espaces de noms

Vous devez importer les espaces de noms nécessaires pour travailler avec Aspose.Slides pour .NET. Voici comment procéder :

```csharp
using Aspose.Slides;
using Aspose.Slides.Video;
```

Maintenant, décomposons le processus d'extraction d'une vidéo à partir d'une diapositive en plusieurs étapes.

## Étape 1 : Définir le répertoire des documents

```csharp
string dataDir = "Your Document Directory";
```

 Remplacer`"Your Document Directory"` avec le chemin d'accès au répertoire où se trouve votre présentation PowerPoint.

## Étape 2 : Charger la présentation

```csharp
Presentation presentation = new Presentation(dataDir + "Video.pptx");
```

Ce code initialise un objet Présentation, représentant votre fichier de présentation PowerPoint.

## Étape 3 : Parcourir les diapositives et les formes

```csharp
foreach (ISlide slide in presentation.Slides)
{
    foreach (IShape shape in presentation.Slides[0].Shapes)
    {
```

Ici, nous parcourons chaque diapositive de la présentation, puis parcourons les formes de la première diapositive (modifions si nécessaire).

## Étape 4 : Vérifiez si la forme est une image vidéo

```csharp
if (shape is VideoFrame)
{
    IVideoFrame vf = shape as IVideoFrame;
    String type = vf.EmbeddedVideo.ContentType;
```

Cette étape vérifie si la forme sur la diapositive est une image vidéo.

## Étape 5 : Extraire les données vidéo

```csharp
int ss = type.LastIndexOf('/');
type = type.Remove(0, type.LastIndexOf('/') + 1);
Byte[] buffer = vf.EmbeddedVideo.BinaryData;
```

Ce code extrait des informations sur la vidéo, notamment son type de contenu et ses données binaires.

## Étape 6 : Enregistrez la vidéo

```csharp
using (FileStream stream = new FileStream(dataDir + "NewVideo_out." + type, FileMode.Create, FileAccess.Write, FileShare.Read))
{
    stream.Write(buffer, 0, buffer.Length);
}
```

Enfin, cette étape enregistre la vidéo dans un nouveau fichier dans le répertoire spécifié.

Une fois ces étapes terminées, vous aurez réussi à extraire une vidéo d'une diapositive PowerPoint à l'aide d'Aspose.Slides pour .NET.

## Conclusion

Aspose.Slides pour .NET simplifie le processus de travail avec des présentations PowerPoint, vous permettant d'effectuer facilement des tâches telles que l'extraction de vidéos à partir de diapositives. En suivant ce guide étape par étape et en utilisant la bibliothèque Aspose.Slides, vous pouvez améliorer vos applications .NET avec de puissantes fonctionnalités PowerPoint.

## Foire aux questions (FAQ)

### Qu’est-ce qu’Aspose.Slides pour .NET ?
Aspose.Slides for .NET est une bibliothèque qui permet aux applications .NET de fonctionner avec des présentations PowerPoint, notamment la création, la modification et l'extraction de contenu.

### Où puis-je trouver la documentation d’Aspose.Slides pour .NET ?
 Vous pouvez trouver la documentation[ici](https://reference.aspose.com/slides/net/).

### Aspose.Slides pour .NET est-il disponible pour un essai gratuit ?
 Oui, vous pouvez obtenir une version d'essai gratuite auprès de[ici](https://releases.aspose.com/).

### Comment puis-je obtenir une licence temporaire pour Aspose.Slides pour .NET ?
 Vous pouvez demander une licence temporaire auprès de[ce lien](https://purchase.aspose.com/temporary-license/).

### Où puis-je obtenir de l’assistance pour Aspose.Slides pour .NET ?
 Vous pouvez trouver de l'aide sur le[Forum Aspose.Slides](https://forum.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
