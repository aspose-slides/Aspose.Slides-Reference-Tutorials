---
title: Ajout de cadres d'objets OLE à la présentation avec Aspose.Slides
linktitle: Ajout de cadres d'objets OLE à la présentation avec Aspose.Slides
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Apprenez à améliorer les présentations PowerPoint avec du contenu dynamique ! Suivez notre guide étape par étape en utilisant Aspose.Slides pour .NET. Boostez l’engagement maintenant !
weight: 15
url: /fr/net/shape-effects-and-manipulation-in-slides/adding-ole-object-frames/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Introduction
Dans ce didacticiel, nous aborderons le processus d'ajout de cadres d'objets OLE (Object Linking and Embedding) aux diapositives de présentation à l'aide d'Aspose.Slides pour .NET. Aspose.Slides est une bibliothèque puissante qui permet aux développeurs de travailler avec des fichiers PowerPoint par programme. Suivez ce guide étape par étape pour intégrer de manière transparente des objets OLE dans vos diapositives de présentation, améliorant ainsi vos fichiers PowerPoint avec un contenu dynamique et interactif.
## Conditions préalables
Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :
1.  Bibliothèque Aspose.Slides pour .NET : assurez-vous que la bibliothèque Aspose.Slides pour .NET est installée. Vous pouvez le télécharger depuis le[Aspose.Slides pour la documentation .NET](https://reference.aspose.com/slides/net/).
2. Répertoire de documents : créez un répertoire sur votre système pour stocker les fichiers nécessaires. Vous pouvez définir le chemin d'accès à ce répertoire dans l'extrait de code fourni.
## Importer des espaces de noms
Pour commencer, importez les espaces de noms nécessaires dans votre projet :
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.DOM.Ole;
using Aspose.Slides.Export;
```
## Étape 1 : configurer la présentation
```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "Your Document Directory";
// Créez un répertoire s'il n'est pas déjà présent.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
// Instancier la classe de présentation qui représente le PPTX
using (Presentation pres = new Presentation())
{
    // Accédez à la première diapositive
    ISlide sld = pres.Slides[0];
    
    // Passez aux étapes suivantes...
}
```
## Étape 2 : charger un objet OLE (fichier Excel) dans Stream
```csharp
// Charger un fichier Excel à diffuser
MemoryStream mstream = new MemoryStream();
using (FileStream fs = new FileStream(dataDir + "book1.xlsx", FileMode.Open, FileAccess.Read))
{
    byte[] buf = new byte[4096];
    while (true)
    {
        int bytesRead = fs.Read(buf, 0, buf.Length);
        if (bytesRead <= 0)
            break;
        mstream.Write(buf, 0, bytesRead);
    }
}
```
## Étape 3 : Créer un objet de données pour l'intégration
```csharp
// Créer un objet de données à intégrer
IOleEmbeddedDataInfo dataInfo = new OleEmbeddedDataInfo(mstream.ToArray(), "xlsx");
```
## Étape 4 : ajouter une forme de cadre d'objet OLE
```csharp
//Ajouter une forme de cadre d'objet OLE
IOleObjectFrame oleObjectFrame = sld.Shapes.AddOleObjectFrame(0, 0, pres.SlideSize.Size.Width,
    pres.SlideSize.Size.Height, dataInfo);
```
## Étape 5 : Enregistrez la présentation
```csharp
// Écrivez le PPTX sur le disque
pres.Save(dataDir + "OleEmbed_out.pptx", SaveFormat.Pptx);
```
Vous avez maintenant ajouté avec succès un cadre d'objet OLE à votre diapositive de présentation à l'aide d'Aspose.Slides pour .NET.
## Conclusion
Dans ce didacticiel, nous avons exploré l'intégration transparente des cadres d'objets OLE dans les diapositives PowerPoint à l'aide d'Aspose.Slides pour .NET. Cette fonctionnalité améliore vos présentations en permettant l'intégration dynamique de divers objets, tels que des feuilles Excel, offrant ainsi une expérience utilisateur plus interactive.
## FAQ
### Q : Puis-je intégrer des objets autres que des feuilles Excel à l’aide d’Aspose.Slides pour .NET ?
R : Oui, Aspose.Slides prend en charge l'intégration de divers objets OLE, notamment les documents Word et les fichiers PDF.
### Q : Comment gérer les erreurs lors du processus d’incorporation d’objets OLE ?
R : Assurez-vous d'une gestion appropriée des exceptions dans votre code pour résoudre tout problème pouvant survenir lors du processus d'intégration.
### Q : Aspose.Slides est-il compatible avec les derniers formats de fichiers PowerPoint ?
: Oui, Aspose.Slides prend en charge les derniers formats de fichiers PowerPoint, y compris PPTX.
### Q : Puis-je personnaliser l’apparence du cadre d’objet OLE intégré ?
R : Absolument, vous pouvez ajuster la taille, la position et d’autres propriétés du cadre d’objet OLE selon vos préférences.
### Q : Où puis-je demander de l'aide si je rencontre des difficultés lors de la mise en œuvre ?
 R : Visitez le[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) pour le soutien et les conseils de la communauté.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
