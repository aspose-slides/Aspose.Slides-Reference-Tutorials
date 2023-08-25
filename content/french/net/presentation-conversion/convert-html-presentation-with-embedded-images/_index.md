---
title: Convertir une présentation HTML avec des images intégrées
linktitle: Convertir une présentation HTML avec des images intégrées
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Convertissez facilement des présentations HTML avec des images intégrées à l'aide d'Aspose.Slides pour .NET. Créez, personnalisez et enregistrez des fichiers PowerPoint en toute transparence.
type: docs
weight: 11
url: /fr/net/presentation-conversion/convert-html-presentation-with-embedded-images/
---
## Introduction à la conversion d'une présentation HTML avec des images intégrées 

Dans ce guide, nous allons parcourir le processus de conversion d'une présentation HTML avec des images intégrées au format de présentation PowerPoint (PPTX) à l'aide d'Aspose.Slides pour .NET. Aspose.Slides est une bibliothèque puissante qui vous permet de travailler avec des présentations PowerPoint par programme. 

## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants en place :
- Visual Studio ou tout autre environnement de développement .NET installé.
-  Aspose.Slides pour la bibliothèque .NET. Vous pouvez le télécharger depuis[ici](https://downloads.aspose.com/slides/net).
- Connaissance de base du développement C# et .NET.

## Pas

1. Créez un nouveau projet C# :
   Ouvrez votre Visual Studio et créez un nouveau projet C#.

2. Installez Aspose.Slides pour .NET :
   Installez la bibliothèque Aspose.Slides pour .NET dans votre projet à l'aide de NuGet Package Manager ou en ajoutant une référence à la DLL téléchargée.

3. Incluez les espaces de noms nécessaires :
   Dans votre fichier de code, incluez les espaces de noms nécessaires :
   ```csharp
   using Aspose.Slides;
   using Aspose.Slides.Export;
   using System.IO;
   ```

4. Charger le contenu HTML :
   Chargez le contenu HTML de la présentation dans une chaîne. Vous pouvez récupérer le code HTML à partir d'un fichier ou d'une source Web.
   ```csharp
   string htmlContent = File.ReadAllText("path_to_your_html_file.html");
   ```

5. Créez une nouvelle présentation :
    Créez une nouvelle instance du`Presentation` classe.
   ```csharp
   using Presentation presentation = new Presentation();
   ```

6. Ajoutez des diapositives avec du contenu HTML :
   Ajoutez des diapositives à la présentation et définissez le contenu HTML de chaque diapositive.
   ```csharp
   ISlideCollection slides = presentation.Slides;

   // Créer une diapositive
   ISlide slide = slides.AddEmptySlide();

   //Ajouter du contenu HTML à la diapositive
   IAutoShape textShape = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 50, 600, 400);
   textShape.TextFrame.Text = htmlContent;
   ```

7. Enregistrez la présentation :
   Enregistrez la présentation au format PPTX.
   ```csharp
   presentation.Save("output_presentation.pptx", SaveFormat.Pptx);
   ```

8. Exécutez l'application :
   Créez et exécutez votre application. Il convertira la présentation HTML avec des images intégrées en une présentation PowerPoint.

## Exemple de code

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
using System.IO;

namespace HTMLToPPTConversion
{
    class Program
    {
        static void Main(string[] args)
        {
            // Charger le contenu HTML à partir du fichier
            string htmlContent = File.ReadAllText("path_to_your_html_file.html");

            // Créer une nouvelle présentation
            using Presentation presentation = new Presentation();

            // Ajouter une diapositive avec du contenu HTML
            ISlide slide = presentation.Slides.AddEmptySlide();
            IAutoShape textShape = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 50, 600, 400);
            textShape.TextFrame.Text = htmlContent;

            // Enregistrez la présentation au format PPTX
            presentation.Save("output_presentation.pptx", SaveFormat.Pptx);
        }
    }
}
```

## Conclusion

La conversion de présentations HTML avec des images intégrées en PowerPoint est simplifiée avec Aspose.Slides pour .NET. Cette bibliothèque rationalise le processus et fournit des outils complets pour gérer la conversion avec précision.

## FAQ

### Comment puis-je inclure des images externes dans la présentation HTML ?

Si votre présentation HTML comprend des images externes, assurez-vous de fournir les URL correctes pour les images. Aspose.Slides gérera automatiquement l'intégration de ces images lorsque vous ajouterez le contenu HTML à la diapositive.

### Puis-je personnaliser l’apparence des diapositives converties ?

Oui, vous pouvez personnaliser l'apparence des diapositives converties à l'aide de diverses propriétés et méthodes fournies par la bibliothèque Aspose.Slides. Vous pouvez modifier les polices, les couleurs, les styles et bien plus encore.

### Où puis-je trouver la documentation complète d’Aspose.Slides pour .NET ?

 Vous pouvez trouver la documentation complète et la référence API pour Aspose.Slides pour .NET[ici](https://reference.aspose.com/slides/net).

### Où puis-je télécharger la dernière version d’Aspose.Slides pour .NET ?

 Vous pouvez télécharger la dernière version d'Aspose.Slides pour .NET à partir de la page des versions d'Aspose :[Téléchargez Aspose.Slides pour .NET](https://releases.aspose.com/slides/net).