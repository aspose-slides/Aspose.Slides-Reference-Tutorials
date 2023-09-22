---
title: Ajout d'un décalage d'étirement vers la gauche pour le cadre photo dans Aspose.Slides
linktitle: Ajout d'un décalage d'étirement vers la gauche pour le cadre photo dans Aspose.Slides
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Découvrez comment ajouter un décalage d'étirement vers la gauche pour un cadre photo dans PowerPoint à l'aide d'Aspose.Slides pour .NET. Guide étape par étape avec un exemple complet de code source.
type: docs
weight: 14
url: /fr/net/shape-alignment-and-formatting-in-slides/adding-stretch-offset-left-picture-frame/
---

## Introduction à Aspose.Slides pour .NET

Aspose.Slides for .NET est une bibliothèque complète qui permet aux développeurs .NET de travailler avec des présentations PowerPoint sans avoir besoin de Microsoft Office. Il offre un large éventail de fonctionnalités, notamment la création, la modification et la manipulation de diapositives, de formes, de texte, d'images, etc.

## Conditions préalables

Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :

1. Visual Studio installé sur votre ordinateur.
2. Compréhension de base du framework C# et .NET.
3.  Aspose.Slides pour la bibliothèque .NET. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/slides/net/).

## Mise en place du projet

Commençons par configurer un nouveau projet C# dans Visual Studio :

1. Ouvrez Visual Studio.
2. Cliquez sur "Créer un nouveau projet".
3. Sélectionnez « Application console (.NET Framework/Core) ».
4. Choisissez un nom et un emplacement appropriés pour votre projet.
5. Cliquez sur "Créer".

Ensuite, ajoutez une référence à la bibliothèque Aspose.Slides for .NET dans votre projet. Cliquez avec le bouton droit sur « Références » dans l'Explorateur de solutions, choisissez « Gérer les packages NuGet », recherchez « Aspose.Slides » et installez le package.

## Ajout d'un décalage d'étirement vers la gauche pour le cadre photo

Pour ajouter un décalage d'étirement vers la gauche pour un cadre photo à l'aide d'Aspose.Slides pour .NET, procédez comme suit :

1.  Chargez le fichier de présentation en utilisant`Presentation` classe.
2. Localisez la diapositive contenant le cadre photo que vous souhaitez modifier.
3. Accédez à la forme du cadre photo en parcourant les formes de la diapositive.
4.  Appliquez le décalage d'étirement vers la gauche à l'aide de la touche`PictureFrame` classe.

## Exemple de code

```csharp
using Aspose.Slides;
using Aspose.Slides.ShapeManagers;

namespace PictureFrameStretchOffsetExample
{
    class Program
    {
        static void Main(string[] args)
        {
            // Charger la présentation
            using (Presentation presentation = new Presentation("sample.pptx"))
            {
                // Obtenez la première diapositive
                ISlide slide = presentation.Slides[0];

                // Parcourez les formes de la diapositive
                foreach (IShape shape in slide.Shapes)
                {
                    if (shape is IPictureFrame)
                    {
                        IPictureFrame pictureFrame = (IPictureFrame)shape;

                        // Appliquer un décalage d'étirement vers la gauche
                        pictureFrame.PictureFormat.StretchOffsetX = -10;
                    }
                }

                // Enregistrez la présentation modifiée
                presentation.Save("output.pptx", SaveFormat.Pptx);
            }
        }
    }
}
```

Dans cet exemple, nous chargeons une présentation, parcourons les formes de la première diapositive et si nous trouvons une forme de cadre photo, nous appliquons un décalage d'étirement de -10 vers la gauche.

## Tester l'application

Pour tester l'application, procédez comme suit :

1. Assurez-vous d'avoir un exemple de présentation PowerPoint (`sample.pptx`) avec au moins un cadre photo.
2. Exécutez l'application.
3.  La présentation modifiée avec le décalage d'étirement ajouté sera enregistrée sous`output.pptx`.

## Conclusion

Dans ce didacticiel, vous avez appris à ajouter un décalage d'étirement vers la gauche pour un cadre photo dans Aspose.Slides à l'aide de .NET. Aspose.Slides for .NET fournit un ensemble d'outils puissants pour manipuler par programmation les présentations PowerPoint, permettant aux développeurs de créer des diaporamas dynamiques et personnalisés de manière transparente.

## FAQ

### Comment puis-je installer Aspose.Slides pour .NET ?

 Vous pouvez télécharger Aspose.Slides pour .NET à partir du site Web[ici](https://releases.aspose.com/slides/net/).

### Puis-je utiliser Aspose.Slides pour d’autres tâches de manipulation PowerPoint ?

Absolument! Aspose.Slides pour .NET offre un large éventail de fonctionnalités, notamment la création, l'édition et la conversion de présentations PowerPoint. Vous pouvez explorer sa documentation pour plus de détails et d'exemples.

### Aspose.Slides est-il compatible avec différents formats PowerPoint ?

Oui, Aspose.Slides prend en charge divers formats PowerPoint, notamment PPTX, PPT, POTX, etc. Il prend également en charge la conversion entre différents formats.

### Comment puis-je personnaliser d’autres propriétés des formes dans une présentation ?

Vous pouvez accéder et modifier diverses propriétés des formes, notamment le texte, la position, la taille, le formatage, etc., à l'aide de la bibliothèque Aspose.Slides. Consultez la documentation pour obtenir des informations complètes et des exemples.

### Puis-je utiliser Aspose.Slides avec d’autres langages de programmation ?

Oui, Aspose.Slides fournit des bibliothèques pour divers langages de programmation, notamment Java, Python, etc. Vous pouvez choisir celui qui convient à votre environnement de développement.