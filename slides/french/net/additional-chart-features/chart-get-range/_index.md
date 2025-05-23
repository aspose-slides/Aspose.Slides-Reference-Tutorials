---
"description": "Apprenez à extraire la plage de données d'un graphique à partir de présentations PowerPoint avec Aspose.Slides pour .NET. Un guide étape par étape pour les développeurs."
"linktitle": "Obtenir la plage de données du graphique"
"second_title": "API de traitement PowerPoint Aspose.Slides .NET"
"title": "Comment obtenir une plage de données de graphique dans Aspose.Slides pour .NET"
"url": "/fr/net/additional-chart-features/chart-get-range/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Comment obtenir une plage de données de graphique dans Aspose.Slides pour .NET


Vous souhaitez extraire la plage de données d'un graphique de votre présentation PowerPoint avec Aspose.Slides pour .NET ? Vous êtes au bon endroit. Ce guide étape par étape vous guidera pas à pas pour obtenir la plage de données de votre graphique. Aspose.Slides pour .NET est une bibliothèque puissante qui vous permet de travailler avec des documents PowerPoint par programmation. Obtenir la plage de données d'un graphique n'est qu'une des nombreuses tâches qu'elle peut vous aider à accomplir.

## Prérequis

Avant de nous plonger dans le processus d'obtention de la plage de données du graphique dans Aspose.Slides pour .NET, assurez-vous que les conditions préalables suivantes sont en place :

1. Aspose.Slides pour .NET : Aspose.Slides pour .NET doit être installé dans votre projet. Si ce n'est pas déjà fait, vous pouvez le télécharger depuis [ici](https://releases.aspose.com/slides/net/).

2. Environnement de développement : vous devez disposer d’un environnement de développement configuré, qui peut être Visual Studio ou tout autre IDE de votre choix.

Maintenant, commençons.

## Importer des espaces de noms

La première étape consiste à importer les espaces de noms nécessaires. Cela permet à votre code d'accéder aux classes et méthodes nécessaires à l'utilisation d'Aspose.Slides. Voici comment procéder :

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
using System;
```

Maintenant que vous avez importé les espaces de noms requis, vous êtes prêt à passer à l'exemple de code.

Nous allons décomposer l’exemple que vous avez fourni en plusieurs étapes pour vous guider tout au long du processus d’obtention de la plage de données du graphique.

## Étape 1 : Créer un objet de présentation

La première étape consiste à créer un objet de présentation. Cet objet représente votre présentation PowerPoint.

```csharp
using (Presentation pres = new Presentation())
{
    // Votre code va ici
}
```

## Étape 2 : Ajouter un graphique à une diapositive

À cette étape, vous devez ajouter un graphique à une diapositive de votre présentation. Vous pouvez spécifier le type de graphique, sa position et sa taille sur la diapositive.

```csharp
IChart chart = pres.Slides[0].Shapes.AddChart(ChartType.ClusteredColumn, 10, 10, 400, 300);
```

## Étape 3 : Obtenir la plage de données du graphique

Il est maintenant temps d'obtenir la plage de données du graphique. Il s'agit des données sur lesquelles le graphique est basé, et vous pouvez les extraire sous forme de chaîne.

```csharp
string result = chart.ChartData.GetRange();
```

## Étape 4 : Afficher le résultat

Enfin, vous pouvez afficher la plage de données de graphique obtenue en utilisant `Console.WriteLine`.

```csharp
Console.WriteLine("GetRange result: {0}", result);
```

Et voilà ! Vous avez récupéré avec succès la plage de données du graphique de votre présentation PowerPoint avec Aspose.Slides pour .NET.

## Conclusion

Dans ce tutoriel, nous avons abordé le processus d'extraction de la plage de données d'un graphique à partir d'une présentation PowerPoint avec Aspose.Slides pour .NET. En respectant les conditions préalables et en suivant le guide étape par étape, vous pourrez facilement extraire les données nécessaires de vos présentations par programmation.

Si vous avez des questions ou avez besoin d'aide supplémentaire, n'hésitez pas à visiter Aspose.Slides pour .NET [documentation](https://reference.aspose.com/slides/net/) ou contactez la communauté Aspose sur leur [forum d'assistance](https://forum.aspose.com/).

## Questions fréquemment posées

### Aspose.Slides pour .NET est-il compatible avec les dernières versions de Microsoft PowerPoint ?
Aspose.Slides pour .NET est conçu pour fonctionner avec différents formats de fichiers PowerPoint, y compris les plus récents. Consultez la documentation pour plus de détails.

### Puis-je manipuler d’autres éléments dans une présentation PowerPoint à l’aide d’Aspose.Slides pour .NET ?
Oui, vous pouvez travailler avec des diapositives, des formes, du texte, des images et d’autres éléments dans une présentation PowerPoint.

### Existe-t-il une version d'essai gratuite disponible pour Aspose.Slides pour .NET ?
Oui, vous pouvez télécharger une version d'essai gratuite à partir de [ici](https://releases.aspose.com/).

### Comment puis-je obtenir une licence temporaire pour Aspose.Slides pour .NET ?
Vous pouvez demander une licence temporaire auprès de [ici](https://purchase.aspose.com/temporary-license/).

### Quels types d’options d’assistance sont disponibles pour les utilisateurs d’Aspose.Slides pour .NET ?
Vous pouvez obtenir du soutien et de l'aide de la communauté Aspose sur leur [forum d'assistance](https://forum.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}