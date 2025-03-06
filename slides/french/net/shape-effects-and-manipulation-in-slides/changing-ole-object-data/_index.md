---
title: Modification des données d'objet OLE dans la présentation avec Aspose.Slides
linktitle: Modification des données d'objet OLE dans la présentation avec Aspose.Slides
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Découvrez la puissance d'Aspose.Slides pour .NET pour modifier facilement les données des objets OLE. Améliorez vos présentations avec du contenu dynamique.
weight: 25
url: /fr/net/shape-effects-and-manipulation-in-slides/changing-ole-object-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introduction
Créer des présentations PowerPoint dynamiques et interactives est une exigence courante dans le monde numérique d'aujourd'hui. Aspose.Slides for .NET est un outil puissant pour y parvenir, une bibliothèque robuste qui permet aux développeurs de manipuler et d'améliorer les présentations PowerPoint par programmation. Dans ce didacticiel, nous aborderons le processus de modification des données d'objet OLE (Object Linking and Embedding) dans les diapositives de présentation à l'aide d'Aspose.Slides.
## Conditions préalables
Avant de commencer à travailler avec Aspose.Slides pour .NET, assurez-vous que les conditions préalables suivantes sont remplies :
1. Environnement de développement : configurez un environnement de développement avec .NET installé.
2.  Bibliothèque Aspose.Slides : téléchargez et installez la bibliothèque Aspose.Slides pour .NET. Vous pouvez trouver la bibliothèque[ici](https://releases.aspose.com/slides/net/).
3. Compréhension de base : Familiarisez-vous avec les concepts de base de la programmation C# et des présentations PowerPoint.
## Importer des espaces de noms
Dans votre projet C#, importez les espaces de noms nécessaires pour utiliser les fonctionnalités Aspose.Slides :
```csharp
using System.IO;
using Aspose.Cells;
using Aspose.Slides;
using Aspose.Slides.DOM.Ole;
using SaveFormat = Aspose.Slides.Export.SaveFormat;
```
## Étape 1 : Configurez votre projet
Commencez par créer un nouveau projet C# et importez la bibliothèque Aspose.Slides. Assurez-vous que votre projet est correctement configuré et que les dépendances requises sont en place.
## Étape 2 : accéder à la présentation et à la diapositive
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx"))
{
    ISlide slide = pres.Slides[0];
```
## Étape 3 : Localiser l'objet OLE
Parcourez toutes les formes de la diapositive pour trouver le cadre de l'objet OLE :
```csharp
OleObjectFrame ole = null;
foreach (IShape shape in slide.Shapes)
{
    if (shape is OleObjectFrame)
    {
        ole = (OleObjectFrame)shape;
    }
}
```
## Étape 4 : Lire et modifier les données du classeur
```csharp
if (ole != null)
{
    using (MemoryStream msln = new MemoryStream(ole.EmbeddedData.EmbeddedFileData))
    {
        // Lecture des données d'objet dans le classeur
        Workbook Wb = new Workbook(msln);
        using (MemoryStream msout = new MemoryStream())
        {
            // Modification des données du classeur
            Wb.Worksheets[0].Cells[0, 4].PutValue("E");
            Wb.Worksheets[0].Cells[1, 4].PutValue(12);
            Wb.Worksheets[0].Cells[2, 4].PutValue(14);
            Wb.Worksheets[0].Cells[3, 4].PutValue(15);
            OoxmlSaveOptions so1 = new OoxmlSaveOptions(Aspose.Cells.SaveFormat.Xlsx);
            Wb.Save(msout, so1);
            // Modification des données d'un objet frame Ole
            IOleEmbeddedDataInfo newData = new OleEmbeddedDataInfo(msout.ToArray(), ole.EmbeddedData.EmbeddedFileExtension);
            ole.SetEmbeddedData(newData);
        }
    }
}
```
## Étape 5 : Enregistrez la présentation
```csharp
pres.Save(dataDir + "OleEdit_out.pptx", SaveFormat.Pptx);
```
## Conclusion
En suivant ces étapes, vous pouvez modifier de manière transparente les données des objets OLE dans les diapositives de présentation à l'aide d'Aspose.Slides pour .NET. Cela ouvre un monde de possibilités pour créer des présentations dynamiques et personnalisées adaptées à vos besoins spécifiques.
## Questions fréquemment posées
### Qu’est-ce qu’Aspose.Slides pour .NET ?
Aspose.Slides for .NET est une bibliothèque puissante qui permet aux développeurs de travailler avec des présentations PowerPoint par programme, permettant une manipulation et une amélioration faciles.
### Où puis-je trouver la documentation Aspose.Slides ?
 La documentation d'Aspose.Slides pour .NET peut être trouvée[ici](https://reference.aspose.com/slides/net/).
### Comment télécharger Aspose.Slides pour .NET ?
 Vous pouvez télécharger la bibliothèque à partir de la page de version[ici](https://releases.aspose.com/slides/net/).
### Existe-t-il un essai gratuit disponible pour Aspose.Slides ?
 Oui, vous pouvez accéder à l'essai gratuit[ici](https://releases.aspose.com/).
### Où puis-je obtenir de l’assistance pour Aspose.Slides pour .NET ?
 Pour obtenir de l'aide et des discussions, visitez le[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
