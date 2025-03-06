---
title: Guide d'intégration des objets OLE avec Aspose.Slides pour .NET
linktitle: Remplacement du titre de l'image du cadre d'objet OLE dans les diapositives de présentation
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Découvrez comment améliorer vos diapositives de présentation avec des objets OLE dynamiques à l'aide d'Aspose.Slides pour .NET. Suivez notre guide étape par étape pour une intégration transparente.
weight: 15
url: /fr/net/shape-alignment-and-formatting-in-slides/substituting-picture-title-ole-object-frame/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Guide d'intégration des objets OLE avec Aspose.Slides pour .NET

## Introduction
La création de diapositives de présentation dynamiques et attrayantes implique souvent l'incorporation de divers éléments multimédias. Dans ce didacticiel, nous allons explorer comment remplacer le titre d'image d'un cadre d'objet OLE (Object Linking and Embedding) dans les diapositives de présentation à l'aide de la puissante bibliothèque Aspose.Slides pour .NET. Aspose.Slides simplifie le processus de gestion des objets OLE, en fournissant aux développeurs les outils nécessaires pour améliorer facilement leurs présentations.
## Conditions préalables
Avant de plonger dans le guide étape par étape, assurez-vous que les conditions préalables suivantes sont en place :
-  Bibliothèque Aspose.Slides pour .NET : assurez-vous que la bibliothèque Aspose.Slides pour .NET est installée. Vous pouvez le télécharger depuis le[Documentation Aspose.Slides .NET](https://reference.aspose.com/slides/net/).
- Exemples de données : préparez un exemple de fichier Excel (par exemple, "ExcelObject.xlsx") que vous souhaitez intégrer en tant qu'objet OLE dans la présentation. De plus, disposez d'un fichier image (par exemple, "Image.png") qui servira d'icône pour l'objet OLE.
- Environnement de développement : configurez un environnement de développement avec les outils nécessaires, tels que Visual Studio ou tout autre IDE préféré pour le développement .NET.
## Importer des espaces de noms
Dans votre projet .NET, assurez-vous d'importer les espaces de noms requis pour travailler avec Aspose.Slides :
```csharp
using Aspose.Slides;
using Aspose.Slides.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Drawing;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Slides.DOM.Ole;
```
## Étape 1 : configurer le répertoire de documents
```csharp
string dataDir = "Your Document Directory";
```
Assurez-vous de remplacer « Votre répertoire de documents » par le chemin réel d'accès à votre répertoire de documents.
## Étape 2 : Définir les chemins des fichiers source OLE et des fichiers d'icônes
```csharp
string oleSourceFile = dataDir + "ExcelObject.xlsx";
string oleIconFile = dataDir + "Image.png";
```
Mettez à jour ces chemins avec les chemins réels vers votre exemple de fichier Excel et de fichier image.
## Étape 3 : Créer une instance de présentation
```csharp
using (Presentation pres = new Presentation())
{
    // Le code pour les étapes suivantes sera ici
}
```
 Initialisez une nouvelle instance du`Presentation` classe.
## Étape 4 : ajouter un cadre d'objet OLE
```csharp
ISlide slide = pres.Slides[0];
byte[] allbytes = File.ReadAllBytes(oleSourceFile);
IOleEmbeddedDataInfo dataInfo = new OleEmbeddedDataInfo(allbytes, "xlsx");
IOleObjectFrame oof = slide.Shapes.AddOleObjectFrame(20, 20, 50, 50, dataInfo);
oof.IsObjectIcon = true;
```
Ajoutez un cadre d'objet OLE à la diapositive, en spécifiant sa position et ses dimensions.
## Étape 5 : ajouter un objet image
```csharp
byte[] imgBuf = File.ReadAllBytes(oleIconFile);
using (MemoryStream ms = new MemoryStream(imgBuf))
{
    IPPImage image = pres.Images.AddImage(new Bitmap(ms));
}
```
Lisez le fichier image et ajoutez-le à la présentation en tant qu'objet image.
## Étape 6 : définir la légende sur l'icône OLE
```csharp
oof.SubstitutePictureTitle = "Caption example";
```
Définissez la légende souhaitée pour l'icône OLE.
## Conclusion
L'incorporation d'objets OLE dans vos diapositives de présentation à l'aide d'Aspose.Slides for .NET est un processus simple. Ce didacticiel vous a guidé à travers les étapes essentielles, depuis la configuration du répertoire de documents jusqu'à l'ajout et la personnalisation des objets OLE. Expérimentez avec différents types de fichiers et légendes pour améliorer l'attrait visuel de vos présentations.
## FAQ
### Puis-je intégrer d’autres types de fichiers en tant qu’objets OLE à l’aide d’Aspose.Slides ?
Oui, Aspose.Slides prend en charge l'intégration de différents types de fichiers, tels que des feuilles de calcul Excel, des documents Word, etc.
### L’icône de l’objet OLE est-elle personnalisable ?
Absolument. Vous pouvez remplacer l'icône par défaut par n'importe quelle image de votre choix pour mieux correspondre au thème de votre présentation.
### Aspose.Slides prend-il en charge les animations avec des objets OLE ?
Depuis la dernière version, Aspose.Slides se concentre sur l'incorporation et l'affichage d'objets OLE et ne gère pas directement les animations au sein des objets OLE.
### Puis-je manipuler des objets OLE par programme après les avoir ajoutés à une diapositive ?
Certainement. Vous disposez d'un contrôle programmatique total sur les objets OLE, vous permettant de modifier leurs propriétés et leur apparence selon vos besoins.
### Existe-t-il des limites à la taille des objets OLE incorporés ?
Bien qu’il existe des limites de taille, elles sont généralement généreuses. Il est recommandé de tester avec votre cas d'utilisation spécifique pour garantir des performances optimales.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
