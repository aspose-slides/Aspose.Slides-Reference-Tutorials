---
title: Exporter des formes au format SVG à partir d'une présentation
linktitle: Exporter des formes au format SVG à partir d'une présentation
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Découvrez comment exporter des formes d'une présentation PowerPoint au format SVG à l'aide d'Aspose.Slides pour .NET. Guide étape par étape avec code source inclus. Extrayez efficacement des formes pour diverses applications.
type: docs
weight: 16
url: /fr/net/presentation-manipulation/export-shapes-to-svg-format-from-presentation/
---
Ce guide vous guidera tout au long du processus d'exportation de formes d'une présentation au format SVG à l'aide de la bibliothèque Aspose.Slides pour .NET. Aspose.Slides est une API puissante qui vous permet de travailler avec des fichiers Microsoft PowerPoint par programme. Dans ce didacticiel, vous apprendrez à extraire des formes d'une présentation et à les enregistrer au format SVG en utilisant C#.

## Conditions préalables

Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :

- Visual Studio installé
- Compréhension de base de la programmation C#
-  Aspose.Slides pour la bibliothèque .NET. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/slides/net/).

## Guide étape par étape

Suivez ces étapes pour exporter des formes au format SVG à partir d'une présentation :

### 1. Créer un nouveau projet

Ouvrez Visual Studio et créez un nouveau projet C#.

### 2. Ajouter une référence à Aspose.Slides

Dans votre projet, cliquez avec le bouton droit sur « Références » dans l'Explorateur de solutions, puis cliquez sur « Ajouter une référence ». Parcourez et sélectionnez la DLL Aspose.Slides que vous avez téléchargée.

### 3. Chargez la présentation

```csharp
using Aspose.Slides;

// Charger la présentation
Presentation presentation = new Presentation("presentation.pptx");
```

### 4. Parcourir les formes

```csharp
foreach (IShape shape in presentation.Slides[0].Shapes)
{
    // Vérifiez si la forme est une forme de groupe
    if (shape is IGroupShape groupShape)
    {
        foreach (IShape groupChildShape in groupShape.Shapes)
        {
            // Exporter la forme au format SVG
            string svgFileName = $"shape_{groupChildShape.Id}.svg";
            groupChildShape.WriteAsSvg(svgFileName);
        }
    }
    else
    {
        // Exporter la forme au format SVG
        string svgFileName = $"shape_{shape.Id}.svg";
        shape.WriteAsSvg(svgFileName);
    }
}
```

### 5. Enregistrez les fichiers SVG

```csharp
presentation.Save("output.pptx", SaveFormat.Pptx); // Enregistrer les modifications apportées à la présentation
```

## FAQ

### Comment puis-je installer Aspose.Slides pour .NET ?

 Vous pouvez télécharger la bibliothèque Aspose.Slides pour .NET à partir de[ici](https://releases.aspose.com/slides/net/). Suivez les instructions d'installation fournies dans la documentation.

### Comment charger une présentation PowerPoint à l’aide d’Aspose.Slides ?

 Vous pouvez charger une présentation en utilisant le`Presentation`constructeur de classe. Fournissez le chemin d'accès au fichier PowerPoint en tant que paramètre.

### Comment exporter une forme au format SVG ?

 Vous pouvez utiliser le`WriteAsSvg` méthode sur un`IShape` objet pour l’exporter au format SVG. Vous devez spécifier le nom du fichier pour la sortie SVG.

## Conclusion

Dans ce didacticiel, vous avez appris à exporter des formes d'une présentation PowerPoint au format SVG à l'aide de la bibliothèque Aspose.Slides pour .NET. Cela peut être utile lorsque vous devez extraire des formes individuelles pour les utiliser dans d'autres applications ou plates-formes prenant en charge les graphiques SVG. Aspose.Slides fournit un moyen simple et efficace d'y parvenir par programmation.

 Pour plus de détails et de fonctionnalités avancées, reportez-vous au[Aspose.Slides pour la référence de l'API .NET](https://reference.aspose.com/slides/net/).