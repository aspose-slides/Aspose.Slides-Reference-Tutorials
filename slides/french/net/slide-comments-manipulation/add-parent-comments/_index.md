---
title: Ajouter des commentaires parents à la diapositive à l'aide d'Aspose.Slides
linktitle: Ajouter des commentaires des parents à la diapositive
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Découvrez comment ajouter des commentaires et des réponses interactifs à vos présentations PowerPoint à l'aide d'Aspose.Slides pour .NET. Améliorez l’engagement et la collaboration.
weight: 12
url: /fr/net/slide-comments-manipulation/add-parent-comments/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


Cherchez-vous à améliorer vos présentations PowerPoint avec des fonctionnalités interactives ? Aspose.Slides pour .NET vous permet d'incorporer des commentaires et des réponses, créant ainsi une expérience dynamique et engageante pour votre public. Dans ce didacticiel étape par étape, nous allons vous montrer comment ajouter des commentaires parents aux diapositives à l'aide d'Aspose.Slides pour .NET. Plongeons et explorons cette fonctionnalité intéressante.

## Conditions préalables

Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :

1.  Aspose.Slides pour .NET : assurez-vous que Aspose.Slides pour .NET est installé. Vous pouvez le télécharger[ici](https://releases.aspose.com/slides/net/).

2. Visual Studio : vous aurez besoin de Visual Studio pour créer et exécuter votre application .NET.

3. Connaissance de base de C# : ce didacticiel suppose que vous possédez une compréhension de base de la programmation C#.

Maintenant que nous avons couvert les prérequis, procédons à l’importation des espaces de noms nécessaires.

## Importation d'espaces de noms

Tout d'abord, vous devrez importer les espaces de noms pertinents dans votre projet. Ces espaces de noms fournissent les classes et méthodes requises pour travailler avec Aspose.Slides pour .NET.

```csharp
using Aspose.Slides;
using Aspose.Slides.SlideComments;
```

Une fois les conditions préalables et les espaces de noms en place, décomposons le processus en plusieurs étapes pour ajouter des commentaires parents à une diapositive.

## Étape 1 : Créer une présentation

Pour commencer, vous devez créer une nouvelle présentation à l'aide d'Aspose.Slides pour .NET. Cette présentation sera la toile sur laquelle vous ajouterez vos commentaires.

```csharp
// Le chemin d'accès au répertoire de sortie.
string outPptxFile = "Output Path";

using (Presentation pres = new Presentation())
{
    // Votre code pour ajouter des commentaires ira ici.
    
    pres.Save(outPptxFile + "parent_comment.pptx", SaveFormat.Pptx);
}
```

 Dans le code ci-dessus, remplacez`"Output Path"` avec le chemin souhaité pour votre présentation de sortie.

## Étape 2 : ajouter des auteurs de commentaires

Avant d'ajouter des commentaires, vous devez définir les auteurs de ces commentaires. Dans cet exemple, nous avons deux auteurs, "Author_1" et "Author_2", chacun représenté par une instance de`ICommentAuthor`.

```csharp
// Ajouter un commentaire
ICommentAuthor author1 = pres.CommentAuthors.AddAuthor("Author_1", "A.A.");
IComment comment1 = author1.Comments.AddComment("comment1", pres.Slides[0], new PointF(10, 10), DateTime.Now);

// Ajouter une réponse pour le commentaire1
ICommentAuthor author2 = pres.CommentAuthors.AddAuthor("Autror_2", "B.B.");
IComment reply1 = author2.Comments.AddComment("reply 1 for comment 1", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply1.ParentComment = comment1;
```

Dans cette étape, nous créons deux auteurs de commentaires et ajoutons le commentaire initial et une réponse au commentaire.

## Étape 3 : ajouter plus de réponses

Pour créer une structure hiérarchique de commentaires, vous pouvez ajouter davantage de réponses aux commentaires existants. Ici, nous ajoutons une deuxième réponse à « comment1 ».

```csharp
// Ajouter une réponse pour le commentaire1
IComment reply2 = author2.Comments.AddComment("reply 2 for comment 1", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply2.ParentComment = comment1;
```

Cela établit un flux de conversation au sein de votre présentation.

## Étape 4 : ajouter des réponses imbriquées

Les commentaires peuvent également avoir des réponses imbriquées. Pour le démontrer, nous ajoutons une réponse à « réponse 2 pour le commentaire 1 », créant ainsi une sous-réponse.

```csharp
// Ajouter une réponse à la réponse
IComment subReply = author1.Comments.AddComment("subreply 3 for reply 2", pres.Slides[0], new PointF(10, 10), DateTime.Now);
subReply.ParentComment = reply2;
```

Cette étape met en évidence la polyvalence d'Aspose.Slides pour .NET dans la gestion des hiérarchies de commentaires.

## Étape 5 : Plus de commentaires et de réponses

Vous pouvez continuer à ajouter d'autres commentaires et réponses si nécessaire. Dans cet exemple, nous ajoutons deux commentaires supplémentaires et une réponse à l'un d'eux.

```csharp
IComment comment2 = author2.Comments.AddComment("comment 2", pres.Slides[0], new PointF(10, 10), DateTime.Now);
IComment comment3 = author2.Comments.AddComment("comment 3", pres.Slides[0], new PointF(10, 10), DateTime.Now);

IComment reply3 = author1.Comments.AddComment("reply 4 for comment 3", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply3.ParentComment = comment3;
```

Cette étape montre comment vous pouvez créer un contenu attrayant et interactif pour vos présentations.

## Étape 6 : Afficher la hiérarchie

Pour visualiser la hiérarchie des commentaires, vous pouvez l'afficher sur la console. Cette étape est facultative mais peut être utile pour le débogage et la compréhension de la structure.

```csharp
ISlide slide = pres.Slides[0];
var comments = slide.GetSlideComments(null);
for (int i = 0; i < comments.Length; i++)
{
    IComment comment = comments[i];
    while (comment.ParentComment != null)
    {
        Console.Write("\t");
        comment = comment.ParentComment;
    }

    Console.Write("{0} : {1}", comments[i].Author.Name, comments[i].Text);
    Console.WriteLine();
}
```

## Étape 7 : Supprimer les commentaires

Dans certains cas, vous devrez peut-être supprimer les commentaires et leurs réponses. L'extrait de code ci-dessous montre comment supprimer « comment1 » et toutes ses réponses.

```csharp
comment1.Remove();
pres.Save(outPptxFile + "remove_comment.pptx", SaveFormat.Pptx);
```

Cette étape est utile pour gérer et mettre à jour le contenu de votre présentation.

Avec ces étapes, vous pouvez créer des présentations avec des commentaires et des réponses interactifs à l'aide d'Aspose.Slides pour .NET. Que vous cherchiez à engager votre public ou à collaborer avec les membres de votre équipe, cette fonctionnalité offre un large éventail de possibilités.

## Conclusion

Aspose.Slides pour .NET fournit un ensemble d'outils puissants pour améliorer vos présentations PowerPoint. Avec la possibilité d'ajouter des commentaires et des réponses, vous pouvez créer un contenu dynamique et interactif qui captive votre public. Ce guide étape par étape vous a montré comment ajouter des commentaires parents aux diapositives, établir des hiérarchies et même supprimer des commentaires si nécessaire. En suivant ces étapes et en explorant la documentation Aspose.Slides[ici](https://reference.aspose.com/slides/net/), vous pouvez faire passer vos présentations au niveau supérieur.

## FAQ

### Puis-je ajouter des commentaires à des diapositives spécifiques de ma présentation ?
Oui, vous pouvez ajouter des commentaires à n'importe quelle diapositive de votre présentation en spécifiant la diapositive cible lors de la création d'un commentaire.

### Est-il possible de personnaliser l’apparence des commentaires dans la présentation ?
Aspose.Slides pour .NET vous permet de personnaliser l'apparence des commentaires, y compris leur texte, les informations sur l'auteur et leur position sur la diapositive.

### Puis-je exporter les commentaires et les réponses dans un fichier séparé ?
Oui, vous pouvez exporter les commentaires et les réponses vers un fichier de présentation distinct, comme démontré à l'étape 7.

### Aspose.Slides pour .NET est-il compatible avec les dernières versions de PowerPoint ?
Aspose.Slides for .NET est conçu pour fonctionner avec une large gamme de versions de PowerPoint, garantissant ainsi la compatibilité avec les dernières versions.

### Existe-t-il des options de licence disponibles pour Aspose.Slides pour .NET ?
 Oui, vous pouvez explorer les options de licence, y compris les licences temporaires, sur le site Web Aspose.[ici](https://purchase.aspose.com/buy) ou essayez l'essai gratuit[ici](https://releases.aspose.com/temporary-license/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
