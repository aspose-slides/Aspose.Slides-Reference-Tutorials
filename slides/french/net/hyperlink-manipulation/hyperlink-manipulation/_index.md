---
title: Manipulation des liens hypertextes dans Aspose.Slides
linktitle: Manipulation des liens hypertextes dans Aspose.Slides
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Découvrez comment ajouter et supprimer des hyperliens dans Aspose.Slides pour .NET. Améliorez facilement vos présentations avec des liens interactifs.
weight: 10
url: /fr/net/hyperlink-manipulation/hyperlink-manipulation/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


Les hyperliens sont des éléments essentiels dans les présentations, car ils constituent un moyen pratique de naviguer entre les diapositives ou d'accéder à des ressources externes. Aspose.Slides pour .NET offre des fonctionnalités puissantes pour ajouter et supprimer des hyperliens dans vos diapositives de présentation. Dans ce didacticiel, nous vous guiderons tout au long du processus de manipulation des liens hypertexte à l'aide d'Aspose.Slides pour .NET. Nous aborderons l'ajout d'hyperliens à une diapositive et la suppression d'hyperliens d'une diapositive. Alors, plongeons-nous !

## Conditions préalables

Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :

1.  Aspose.Slides pour .NET : vous devez avoir installé et configuré la bibliothèque Aspose.Slides pour .NET. Vous pouvez trouver la documentation[ici](https://reference.aspose.com/slides/net/) et téléchargez-le depuis[ce lien](https://releases.aspose.com/slides/net/).

2. Votre répertoire de documents : vous avez besoin d'un répertoire dans lequel vous stockerez vos fichiers de présentation. Assurez-vous de spécifier le chemin d'accès à ce répertoire dans votre code.

3. Connaissance de base de C# : ce didacticiel suppose que vous possédez une compréhension de base de la programmation C#.

Maintenant que vous avez mis en place vos prérequis, passons au guide étape par étape pour la manipulation des liens hypertexte à l'aide d'Aspose.Slides pour .NET.

## Ajouter des hyperliens à une diapositive

### Étape 1 : initialiser la présentation

Pour commencer, vous devez initialiser une présentation à l'aide d'Aspose.Slides. Vous pouvez le faire avec le code suivant :

```csharp
using (Presentation presentation = new Presentation())
{
    // Votre code ici
}
```

### Étape 2 : Ajouter un cadre de texte

Maintenant, ajoutons un cadre de texte à une diapositive. Ce code crée une forme rectangulaire avec du texte :

```csharp
IAutoShape shape1 = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 600, 50, false);
shape1.AddTextFrame("Aspose: File Format APIs");
```

### Étape 3 : ajouter un lien hypertexte

Ensuite, vous allez ajouter un lien hypertexte vers le texte dans la forme que vous avez créée. Voici comment procéder :

```csharp
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick = new Hyperlink("https://www.aspose.com/");
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick.Tooltip = "More than 70% Fortune 100 companies trust Aspose APIs";
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.FontHeight = 32;
```

### Étape 4 : Enregistrer la présentation

Enfin, enregistrez votre présentation avec le lien hypertexte ajouté :

```csharp
presentation.Save("presentation-out.pptx", SaveFormat.Pptx);
```

Toutes nos félicitations! Vous avez ajouté avec succès un lien hypertexte à une diapositive à l'aide d'Aspose.Slides pour .NET.

## Supprimer les hyperliens d'une diapositive

### Étape 1 : initialiser la présentation

Pour supprimer les hyperliens d'une diapositive, vous devez ouvrir une présentation existante :

```csharp
string dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "Hyperlink.pptx");
```

### Étape 2 : Supprimer les hyperliens

Maintenant, supprimez tous les hyperliens de la présentation en utilisant le code suivant :

```csharp
presentation.HyperlinkQueries.RemoveAllHyperlinks();
```

### Étape 3 : Enregistrer la présentation

Après avoir supprimé les hyperliens, enregistrez la présentation :

```csharp
presentation.Save(dataDir + "RemovedHyperlink_out.pptx", SaveFormat.Pptx);
```

Et c'est tout! Vous avez réussi à supprimer les liens hypertexte d’une diapositive à l’aide d’Aspose.Slides pour .NET.

En conclusion, Aspose.Slides for .NET offre un moyen efficace de manipuler les hyperliens dans vos présentations, vous permettant de créer des diapositives interactives et attrayantes. Que vous souhaitiez ajouter des hyperliens vers des ressources externes ou les supprimer, Aspose.Slides simplifie le processus et améliore vos capacités de création de présentations.

 Merci de nous avoir rejoint dans ce didacticiel sur la manipulation des liens hypertexte dans Aspose.Slides pour .NET. Si vous avez des questions ou avez besoin d'aide supplémentaire, n'hésitez pas à explorer le[Documentation Aspose.Slides](https://reference.aspose.com/slides/net/) ou contactez la communauté Aspose sur le[forum d'entraide](https://forum.aspose.com/).

---

## Conclusion

Dans ce didacticiel, nous avons appris à manipuler les hyperliens dans les présentations à l'aide d'Aspose.Slides pour .NET. Nous avons couvert à la fois l'ajout et la suppression de liens hypertexte, vous permettant de créer des présentations dynamiques et interactives. Aspose.Slides simplifie le processus, facilitant l'amélioration de vos diapositives avec des hyperliens vers des ressources externes.

Avez-vous d'autres questions sur l'utilisation d'Aspose.Slides ou sur d'autres aspects de la conception de présentations ? Consultez la FAQ ci-dessous pour plus d’informations.

## FAQ (Foire aux questions)

### Quels sont les principaux avantages de l’utilisation d’Aspose.Slides pour .NET ?
Aspose.Slides pour .NET offre un large éventail de fonctionnalités pour créer, manipuler et convertir des présentations. Il fournit un ensemble complet d'outils pour ajouter du contenu, des animations et des interactions à vos diapositives.

### Puis-je ajouter des hyperliens vers des objets autres que du texte dans Aspose.Slides ?
Oui, Aspose.Slides vous permet d'ajouter des hyperliens vers divers objets, notamment des formes, des images et du texte, vous offrant ainsi une flexibilité dans la création de présentations interactives.

### Aspose.Slides est-il compatible avec différents formats de fichiers PowerPoint ?
Absolument. Aspose.Slides prend en charge divers formats PowerPoint, notamment PPT, PPTX, PPS, etc. Il assure la compatibilité avec les différentes versions de Microsoft PowerPoint.

### Où puis-je trouver des ressources supplémentaires et une assistance pour Aspose.Slides ?
 Pour une documentation détaillée et le soutien de la communauté, visitez le[Documentation Aspose.Slides](https://reference.aspose.com/slides/net/) et le[Forum d'assistance Aspose](https://forum.aspose.com/).

### Comment puis-je obtenir une licence temporaire pour Aspose.Slides ?
 Si vous avez besoin d'une licence temporaire pour Aspose.Slides, vous pouvez en obtenir une[ici](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
