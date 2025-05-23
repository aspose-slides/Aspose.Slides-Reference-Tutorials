---
"description": "Apprenez à ajouter et supprimer des hyperliens dans Aspose.Slides pour .NET. Améliorez facilement vos présentations avec des liens interactifs."
"linktitle": "Manipulation des hyperliens dans Aspose.Slides"
"second_title": "API de traitement PowerPoint Aspose.Slides .NET"
"title": "Manipulation des hyperliens dans Aspose.Slides"
"url": "/fr/net/hyperlink-manipulation/hyperlink-manipulation/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Manipulation des hyperliens dans Aspose.Slides


Les hyperliens sont des éléments essentiels des présentations, car ils permettent de naviguer facilement entre les diapositives ou d'accéder à des ressources externes. Aspose.Slides pour .NET offre de puissantes fonctionnalités pour ajouter et supprimer des hyperliens dans vos diapositives de présentation. Dans ce tutoriel, nous vous guiderons dans la manipulation des hyperliens avec Aspose.Slides pour .NET. Nous aborderons l'ajout et la suppression d'hyperliens dans une diapositive. Alors, c'est parti !

## Prérequis

Avant de commencer, assurez-vous de disposer des conditions préalables suivantes :

1. Aspose.Slides pour .NET : la bibliothèque Aspose.Slides pour .NET doit être installée et configurée. Vous trouverez la documentation. [ici](https://reference.aspose.com/slides/net/) et téléchargez-le depuis [ce lien](https://releases.aspose.com/slides/net/).

2. Votre répertoire de documents : vous avez besoin d'un répertoire où stocker vos fichiers de présentation. Assurez-vous de spécifier le chemin d'accès à ce répertoire dans votre code.

3. Connaissances de base de C# : ce didacticiel suppose que vous avez une compréhension de base de la programmation C#.

Maintenant que vous avez mis en place vos prérequis, passons au guide étape par étape pour la manipulation des hyperliens à l'aide d'Aspose.Slides pour .NET.

## Ajout d'hyperliens à une diapositive

### Étape 1 : Initialiser la présentation

Pour commencer, vous devez initialiser une présentation avec Aspose.Slides. Pour ce faire, utilisez le code suivant :

```csharp
using (Presentation presentation = new Presentation())
{
    // Votre code ici
}
```

### Étape 2 : Ajouter un cadre de texte

Ajoutons maintenant un cadre de texte à une diapositive. Ce code crée une forme rectangulaire avec du texte :

```csharp
IAutoShape shape1 = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 600, 50, false);
shape1.AddTextFrame("Aspose: File Format APIs");
```

### Étape 3 : Ajouter un lien hypertexte

Ensuite, vous ajouterez un lien hypertexte au texte de la forme créée. Voici comment procéder :

```csharp
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick = new Hyperlink("https://www.aspose.com/");
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick.Tooltip = "More than 70% Fortune 100 companies trust Aspose APIs";
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.FontHeight = 32;
```

### Étape 4 : Enregistrer la présentation

Enfin, enregistrez votre présentation avec l’hyperlien ajouté :

```csharp
presentation.Save("presentation-out.pptx", SaveFormat.Pptx);
```

Félicitations ! Vous avez ajouté un lien hypertexte à une diapositive avec Aspose.Slides pour .NET.

## Suppression des hyperliens d'une diapositive

### Étape 1 : Initialiser la présentation

Pour supprimer les hyperliens d’une diapositive, vous devez ouvrir une présentation existante :

```csharp
string dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "Hyperlink.pptx");
```

### Étape 2 : supprimer les hyperliens

Maintenant, supprimez tous les hyperliens de la présentation à l’aide du code suivant :

```csharp
presentation.HyperlinkQueries.RemoveAllHyperlinks();
```

### Étape 3 : Enregistrer la présentation

Après avoir supprimé les hyperliens, enregistrez la présentation :

```csharp
presentation.Save(dataDir + "RemovedHyperlink_out.pptx", SaveFormat.Pptx);
```

Et voilà ! Vous avez réussi à supprimer les hyperliens d'une diapositive avec Aspose.Slides pour .NET.

En conclusion, Aspose.Slides pour .NET offre un moyen efficace de manipuler les hyperliens dans vos présentations, vous permettant de créer des diapositives interactives et attrayantes. Que vous souhaitiez ajouter ou supprimer des hyperliens vers des ressources externes, Aspose.Slides simplifie le processus et optimise vos capacités de création de présentations.

Merci de nous avoir rejoint pour ce tutoriel sur la manipulation des hyperliens dans Aspose.Slides pour .NET. Si vous avez des questions ou besoin d'aide, n'hésitez pas à consulter le [Documentation Aspose.Slides](https://reference.aspose.com/slides/net/) ou contactez la communauté Aspose sur le [forum d'assistance](https://forum.aspose.com/).

---

## Conclusion

Dans ce tutoriel, nous avons appris à manipuler les hyperliens dans les présentations avec Aspose.Slides pour .NET. Nous avons abordé l'ajout et la suppression d'hyperliens, vous permettant ainsi de créer des présentations dynamiques et interactives. Aspose.Slides simplifie le processus et permet d'enrichir facilement vos diapositives avec des hyperliens vers des ressources externes.

Vous avez d'autres questions sur Aspose.Slides ou sur d'autres aspects de la conception de présentations ? Consultez la FAQ ci-dessous pour en savoir plus.

## FAQ (Foire aux questions)

### Quels sont les principaux avantages de l’utilisation d’Aspose.Slides pour .NET ?
Aspose.Slides pour .NET offre un large éventail de fonctionnalités pour créer, manipuler et convertir des présentations. Il propose un ensemble complet d'outils pour ajouter du contenu, des animations et des interactions à vos diapositives.

### Puis-je ajouter des hyperliens à des objets autres que du texte dans Aspose.Slides ?
Oui, Aspose.Slides vous permet d'ajouter des hyperliens vers divers objets, notamment des formes, des images et du texte, vous offrant ainsi une flexibilité dans la création de présentations interactives.

### Aspose.Slides est-il compatible avec différents formats de fichiers PowerPoint ?
Absolument. Aspose.Slides prend en charge différents formats PowerPoint, notamment PPT, PPTX, PPS, etc. Il assure la compatibilité avec différentes versions de Microsoft PowerPoint.

### Où puis-je trouver des ressources et une assistance supplémentaires pour Aspose.Slides ?
Pour une documentation approfondie et un soutien communautaire, visitez le [Documentation Aspose.Slides](https://reference.aspose.com/slides/net/) et le [Forum d'assistance Aspose](https://forum.aspose.com/).

### Comment puis-je obtenir une licence temporaire pour Aspose.Slides ?
Si vous avez besoin d'une licence temporaire pour Aspose.Slides, vous pouvez en obtenir une [ici](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}