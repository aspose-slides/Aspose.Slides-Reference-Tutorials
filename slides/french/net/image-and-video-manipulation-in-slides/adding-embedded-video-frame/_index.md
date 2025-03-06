---
title: Aspose.Slides - Ajout de vidéos intégrées dans les présentations .NET
linktitle: Aspose.Slides - Ajout de vidéos intégrées dans les présentations .NET
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Améliorez vos présentations avec des vidéos intégrées à l'aide d'Aspose.Slides pour .NET. Suivez notre guide étape par étape pour une intégration transparente.
weight: 19
url: /fr/net/image-and-video-manipulation-in-slides/adding-embedded-video-frame/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introduction
Dans le monde dynamique des présentations, l’intégration d’éléments multimédias peut améliorer considérablement l’engagement. Aspose.Slides pour .NET fournit une solution puissante pour incorporer des images vidéo intégrées dans vos diapositives de présentation. Ce didacticiel vous guidera tout au long du processus, en décomposant chaque étape pour garantir une expérience fluide.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous d'avoir les éléments suivants :
-  Aspose.Slides pour la bibliothèque .NET : téléchargez et installez la bibliothèque à partir du[page de sortie](https://releases.aspose.com/slides/net/).
- Contenu multimédia : disposez d'un fichier vidéo (par exemple, "Wildlife.mp4") que vous souhaitez intégrer dans votre présentation.
## Importer des espaces de noms
Commencez par importer les espaces de noms nécessaires dans votre projet .NET :
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## Étape 1 : Configurer les répertoires
Assurez-vous que votre projet dispose des répertoires requis pour les documents et les fichiers multimédias :
```csharp
string dataDir = "Your Document Directory";
string videoDir = "Your Media Directory";
string resultPath = Path.Combine(dataDir, "VideoFrame_out.pptx");
// Créez un répertoire s'il n'est pas déjà présent.
bool IsExists = Directory.Exists(dataDir);
if (!IsExists)
    Directory.CreateDirectory(dataDir);
```
## Étape 2 : Instancier un cours de présentation
Créez une instance de la classe Présentation pour représenter le fichier PPTX :
```csharp
using (Presentation pres = new Presentation())
{
    // Obtenez la première diapositive
    ISlide sld = pres.Slides[0];
```
## Étape 3 : Intégrer la vidéo dans la présentation
Utilisez le code suivant pour intégrer une vidéo dans la présentation :
```csharp
IVideo vid = pres.Videos.AddVideo(new FileStream(videoDir + "Wildlife.mp4", FileMode.Open), LoadingStreamBehavior.ReadStreamAndRelease);
```
## Étape 4 : ajouter une image vidéo
Maintenant, ajoutez une image vidéo à la diapositive :
```csharp
IVideoFrame vf = sld.Shapes.AddVideoFrame(50, 150, 300, 350, vid);
```
## Étape 5 : Définir les propriétés de la vidéo
Réglez la vidéo sur l'image vidéo et configurez le mode de lecture et le volume :
```csharp
vf.EmbeddedVideo = vid;
vf.PlayMode = VideoPlayModePreset.Auto;
vf.Volume = AudioVolumeMode.Loud;
```
## Étape 6 : Enregistrez la présentation
Enfin, enregistrez le fichier PPTX sur le disque :
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
Répétez ces étapes pour chaque vidéo que vous souhaitez intégrer dans votre présentation.
## Conclusion
Toutes nos félicitations! Vous avez ajouté avec succès une image vidéo intégrée à votre présentation à l'aide d'Aspose.Slides pour .NET. Cette fonctionnalité dynamique peut élever vos présentations vers de nouveaux sommets, captivant votre public avec des éléments multimédias parfaitement intégrés dans vos diapositives.
## FAQ
### Puis-je intégrer des vidéos dans n’importe quelle diapositive de la présentation ?
 Oui, vous pouvez choisir n'importe quelle diapositive en modifiant l'index dans`pres.Slides[index]`.
### Quels formats vidéo sont pris en charge ?
Aspose.Slides prend en charge une variété de formats vidéo, notamment MP4, AVI et WMV.
### Puis-je personnaliser la taille et la position de l'image vidéo ?
 Absolument! Ajustez les paramètres dans`AddVideoFrame(x, y, width, height, video)` comme requis.
### Y a-t-il une limite au nombre de vidéos que je peux intégrer ?
Le nombre de vidéos intégrées est généralement limité par la capacité de votre logiciel de présentation.
### Comment puis-je demander de l’aide ou partager mon expérience ?
 Visiter le[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) pour le soutien et les discussions de la communauté.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
