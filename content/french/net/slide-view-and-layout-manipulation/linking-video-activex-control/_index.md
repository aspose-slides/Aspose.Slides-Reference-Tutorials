---
title: Lier une vidéo via le contrôle ActiveX dans PowerPoint
linktitle: Lier la vidéo via le contrôle ActiveX
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Découvrez comment lier des vidéos à des diapositives PowerPoint à l'aide d'Aspose.Slides pour .NET. Ce guide étape par étape comprend le code source et des conseils pour créer des présentations interactives et attrayantes avec des vidéos liées.
type: docs
weight: 12
url: /fr/net/slide-view-and-layout-manipulation/linking-video-activex-control/
---
Lier une vidéo via un contrôle ActiveX dans une présentation à l'aide d'Aspose.Slides pour .NET

Dans Aspose.Slides pour .NET, vous pouvez lier par programme une vidéo à une diapositive de présentation à l'aide du contrôle ActiveX. Cela vous permet de créer des présentations interactives où le contenu vidéo peut être lu directement dans la diapositive. Dans ce guide étape par étape, nous vous guiderons tout au long du processus de liaison d'une vidéo à une diapositive de présentation à l'aide d'Aspose.Slides pour .NET.

## Conditions préalables:
- Visual Studio (ou tout autre environnement de développement .NET)
-  Aspose.Slides pour la bibliothèque .NET. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/slides/net/).

## Étape 1 : Créer un nouveau projet
Créez un nouveau projet dans votre environnement de développement .NET préféré (par exemple, Visual Studio) et ajoutez des références à la bibliothèque Aspose.Slides pour .NET.

## Étape 2 : Importer les espaces de noms nécessaires
Dans votre projet, importez les espaces de noms nécessaires pour travailler avec Aspose.Slides :

```csharp
using Aspose.Slides;
using Aspose.Slides.ActiveXControls;
```

## Étape 3 : Charger la présentation
Chargez la présentation PowerPoint à l'endroit où vous souhaitez ajouter la vidéo liée :

```csharp
string presentationPath = "path_to_your_presentation.pptx";
using (Presentation presentation = new Presentation(presentationPath))
{
    // Votre code pour ajouter la vidéo liée ira ici
}
```

## Étape 4 : ajouter un contrôle ActiveX
 Créez une instance du`IOleObjectFrame` interface pour ajouter le contrôle ActiveX à la diapositive :

```csharp
ISlide slide = presentation.Slides[0]; // Choisissez la diapositive où vous souhaitez ajouter la vidéo
IOleObjectFrame oleObjectFrame = slide.Shapes.AddOleObjectFrame(0, 0, 640, 480, "Video", "ShockwaveFlash.ShockwaveFlash.10");
```

Dans le code ci-dessus, nous ajoutons un cadre de contrôle ActiveX de dimensions 640x480 à la diapositive. Nous spécifions le ProgID pour le contrôle ShockwaveFlash ActiveX, qui est couramment utilisé pour l'intégration de vidéos.

## Étape 5 : Définir les propriétés du contrôle ActiveX
Définissez les propriétés du contrôle ActiveX pour spécifier la source vidéo liée :

```csharp
oleObjectFrame.ObjectData = Encoding.UTF8.GetBytes("YourVideoPathHere"); // Remplacer par le chemin réel du fichier vidéo
oleObjectFrame.AlternativeText = "Linked Video";
```

 Remplacer`"YourVideoPathHere"` avec le chemin réel de votre fichier vidéo. Le`AlternativeText` La propriété fournit une description de la vidéo liée.

## Étape 6 : Enregistrer la présentation
Enregistrez la présentation modifiée :

```csharp
string outputPresentationPath = "output_presentation.pptx";
presentation.Save(outputPresentationPath, SaveFormat.Pptx);
```

## FAQ :

### Comment puis-je spécifier la taille et la position de la vidéo liée sur la diapositive ?
 Vous pouvez ajuster les dimensions et la position du cadre de contrôle ActiveX à l'aide des paramètres du`AddOleObjectFrame`méthode. Les quatre arguments numériques représentent respectivement les coordonnées X et Y du coin supérieur gauche ainsi que la largeur et la hauteur du cadre.

### Puis-je lier des vidéos de différents formats en utilisant cette approche ?
Oui, vous pouvez lier des vidéos de différents formats tant que le contrôle ActiveX approprié est disponible pour ce format. Par exemple, le contrôle ShockwaveFlash ActiveX utilisé dans ce guide convient aux vidéos Flash (SWF). Pour d'autres formats, vous devrez peut-être utiliser des ProgID différents.

### Y a-t-il une limite à la taille de la vidéo liée ?
La taille de la vidéo liée peut affecter la taille globale et les performances de votre présentation. Il est recommandé d'optimiser vos vidéos pour la lecture sur le Web avant de les lier à la présentation.

### Conclusion:
En suivant les étapes décrites dans ce guide, vous pouvez facilement lier une vidéo via un contrôle ActiveX dans une présentation à l'aide d'Aspose.Slides pour .NET. Cette fonctionnalité vous permet de créer des présentations attrayantes et interactives qui intègrent du contenu multimédia de manière transparente.

 Pour plus de détails et d'options avancées, vous pouvez vous référer au[Aspose.Slides pour la documentation .NET](https://reference.aspose.com/slides/net/).