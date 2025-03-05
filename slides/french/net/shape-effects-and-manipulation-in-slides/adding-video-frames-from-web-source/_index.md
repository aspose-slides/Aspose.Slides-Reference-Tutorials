---
title: Tutoriel d'intégration de cadres vidéo avec Aspose.Slides pour .NET
linktitle: Ajout d'images vidéo à partir d'une source Web dans des diapositives de présentation avec Aspose.Slides
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Découvrez comment intégrer de manière transparente des images vidéo dans des diapositives PowerPoint à l'aide d'Aspose.Slides pour .NET. Améliorez vos présentations avec le multimédia sans effort.
type: docs
weight: 20
url: /fr/net/shape-effects-and-manipulation-in-slides/adding-video-frames-from-web-source/
---
## Introduction
Dans le monde dynamique des présentations, l’intégration d’éléments multimédias peut améliorer considérablement l’engagement et transmettre des messages percutants. Un moyen efficace d’y parvenir consiste à intégrer des images vidéo dans des diapositives de présentation. Dans ce didacticiel, nous explorerons comment y parvenir de manière transparente à l'aide d'Aspose.Slides pour .NET. Aspose.Slides est une bibliothèque robuste qui permet aux développeurs de manipuler des présentations PowerPoint par programme, offrant des fonctionnalités étendues pour créer, éditer et améliorer des diapositives.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous d'avoir mis en place les éléments suivants :
1.  Aspose.Slides pour la bibliothèque .NET : téléchargez et installez la bibliothèque à partir du[Documentation Aspose.Slides pour .NET](https://reference.aspose.com/slides/net/).
2. Exemple de fichier vidéo : préparez un fichier vidéo que vous souhaitez intégrer à votre présentation. Vous pouvez utiliser l'exemple fourni avec une vidéo nommée "Wildlife.mp4".
## Importer des espaces de noms
Dans votre projet .NET, incluez les espaces de noms nécessaires pour exploiter les fonctionnalités d'Aspose.Slides :
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
Décomposons le processus d'intégration d'images vidéo dans des diapositives de présentation à l'aide d'Aspose.Slides for .NET en étapes gérables :
## Étape 1 : Configurer les répertoires
```csharp
string dataDir = "Your Document Directory";
string videoDir = "Your Media Directory";
string resultPath = Path.Combine(RunExamples.OutPath, "VideoFrame_out.pptx");
// Créez un répertoire s'il n'est pas déjà présent.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
Assurez-vous de remplacer « Votre répertoire de documents » et « Votre répertoire de médias » par les chemins appropriés dans votre projet.
## Étape 2 : Créer un objet de présentation
```csharp
using (Presentation pres = new Presentation())
{
    // Obtenez la première diapositive
    ISlide sld = pres.Slides[0];
```
Initialisez une nouvelle présentation et accédez à la première diapositive pour intégrer l'image vidéo.
## Étape 3 : Intégrer la vidéo dans la présentation
```csharp
IVideo vid = pres.Videos.AddVideo(new FileStream(videoDir + "Wildlife.mp4", FileMode.Open), LoadingStreamBehavior.ReadStreamAndRelease);
```
 Utiliser le`AddVideo` méthode pour intégrer la vidéo dans la présentation, en spécifiant le chemin du fichier et le comportement de chargement.
## Étape 4 : ajouter une image vidéo
```csharp
IVideoFrame vf = sld.Shapes.AddVideoFrame(50, 150, 300, 350, vid);
```
Créez une image vidéo sur la diapositive, en définissant sa position et ses dimensions.
## Étape 5 : Configurer les paramètres vidéo
```csharp
vf.EmbeddedVideo = vid;
vf.PlayMode = VideoPlayModePreset.Auto;
vf.Volume = AudioVolumeMode.Loud;
```
Associez l'image vidéo à la vidéo intégrée, définissez le mode de lecture et ajustez le volume selon vos préférences.
## Étape 6 : Enregistrer la présentation
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
Enregistrez la présentation modifiée avec l'image vidéo intégrée.
## Conclusion
Toutes nos félicitations! Vous avez appris avec succès comment intégrer des images vidéo dans des diapositives de présentation à l'aide d'Aspose.Slides pour .NET. Cette fonctionnalité ouvre des possibilités passionnantes pour créer des présentations dynamiques et engageantes qui captivent votre public.
## FAQ
### Puis-je intégrer des vidéos de différents formats à l’aide d’Aspose.Slides ?
Oui, Aspose.Slides prend en charge une variété de formats vidéo, garantissant ainsi la flexibilité de vos présentations.
### Comment puis-je contrôler les paramètres de lecture de la vidéo intégrée ?
 Ajuste le`PlayMode` et`Volume` propriétés de l’image vidéo pour personnaliser le comportement de lecture.
### Aspose.Slides est-il compatible avec les dernières versions de .NET ?
Aspose.Slides est régulièrement mis à jour pour maintenir la compatibilité avec les derniers frameworks .NET.
### Puis-je intégrer plusieurs vidéos dans une seule diapositive à l’aide d’Aspose.Slides ?
Oui, vous pouvez intégrer plusieurs vidéos en ajoutant des images vidéo supplémentaires à une diapositive.
### Où puis-je trouver de l'aide pour les requêtes liées à Aspose.Slides ?
 Visiter le[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) pour le soutien et les discussions de la communauté.