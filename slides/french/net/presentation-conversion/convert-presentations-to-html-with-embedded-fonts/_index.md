---
"description": "Convertissez vos présentations PowerPoint en HTML avec polices intégrées grâce à Aspose.Slides pour .NET. Préservez l'originalité de vos présentations."
"linktitle": "Convertir des présentations en HTML avec des polices intégrées"
"second_title": "API de traitement PowerPoint Aspose.Slides .NET"
"title": "Convertir des présentations en HTML avec des polices intégrées"
"url": "/fr/net/presentation-conversion/convert-presentations-to-html-with-embedded-fonts/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Convertir des présentations en HTML avec des polices intégrées


À l'ère du numérique, partager des présentations et des documents en ligne est devenu une pratique courante. Cependant, l'un des défis récurrents est de garantir l'affichage correct des polices lors de la conversion des présentations au format HTML. Ce tutoriel vous guidera pas à pas dans l'utilisation d'Aspose.Slides pour .NET pour convertir des présentations au format HTML avec polices intégrées, garantissant ainsi un rendu fidèle à vos attentes.

## Introduction à Aspose.Slides pour .NET

Avant de commencer ce tutoriel, présentons brièvement Aspose.Slides pour .NET. Cette puissante bibliothèque permet aux développeurs de travailler avec des présentations PowerPoint dans des applications .NET. Avec Aspose.Slides, vous pouvez créer, modifier et convertir des fichiers PowerPoint par programmation.

## Prérequis

Avant de commencer, assurez-vous de disposer des prérequis suivants :

- Aspose.Slides pour .NET : la bibliothèque Aspose.Slides doit être installée dans votre projet. Vous pouvez la télécharger ici. [ici](https://releases.aspose.com/slides/net/).

## Étape 1 : Configurez votre projet

1. Créez un nouveau projet ou ouvrez-en un existant dans votre environnement de développement .NET préféré.

2. Ajoutez une référence à la bibliothèque Aspose.Slides dans votre projet.

3. Importez les espaces de noms nécessaires dans votre code :

   ```csharp
   using Aspose.Slides;
   ```

## Étape 2 : chargez votre présentation

Pour commencer, vous devez charger la présentation que vous souhaitez convertir en HTML. Remplacer `"Your Document Directory"` avec le répertoire réel où se trouve votre fichier de présentation.

```csharp
string dataDir = "Your Document Directory";
using (Presentation pres = new Presentation(dataDir + "presentation.pptx"))
{
    // Votre code va ici
}
```

## Étape 3 : exclure les polices de présentation par défaut

À cette étape, vous pouvez spécifier les polices de présentation par défaut à exclure de l'incorporation. Cela permet d'optimiser la taille du fichier HTML obtenu.

```csharp
string[] fontNameExcludeList = { };
```

## Étape 4 : Choisir un contrôleur HTML

Vous disposez désormais de deux options pour intégrer des polices dans le code HTML :

### Option 1 : Intégrer toutes les polices

Pour intégrer toutes les polices utilisées dans la présentation, utilisez le `EmbedAllFontsHtmlController`.

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
```

### Option 2 : Lier toutes les polices

Pour créer un lien vers toutes les polices utilisées dans la présentation, utilisez le `LinkAllFontsHtmlController`Vous devez spécifier le répertoire dans lequel se trouvent les polices sur votre système.

```csharp
LinkAllFontsHtmlController linkcont = new LinkAllFontsHtmlController(fontNameExcludeList, @"C:\Windows\Fonts\");
```

## Étape 5 : Définir les options HTML

Créer un `HtmlOptions` objet et définissez le formateur HTML sur celui que vous avez sélectionné à l'étape précédente.

```csharp
HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(linkcont) // Utilisez embedFontsController pour intégrer toutes les polices
};
```

## Étape 6 : Enregistrer au format HTML

Enfin, enregistrez la présentation au format HTML. Vous pouvez choisir entre `SaveFoumat.Html` or `SaveFormat.Html5` en fonction de vos besoins.

```csharp
pres.Save("pres.html", SaveFormat.Html, htmlOptionsEmbed);
```

## Conclusion

Félicitations ! Vous avez converti votre présentation au format HTML avec polices intégrées grâce à Aspose.Slides pour .NET. Vos polices s'afficheront ainsi correctement lors du partage de vos présentations en ligne.

Désormais, vous pouvez facilement partager vos présentations magnifiquement formatées en toute confiance, sachant que votre public les verra exactement comme vous le souhaitiez.

Pour plus d'informations et des références API détaillées, consultez le [Aspose.Slides pour la documentation .NET](https://reference.aspose.com/slides/net/).

## FAQ

### 1. Puis-je convertir des présentations PowerPoint en HTML à l'aide d'Aspose.Slides pour .NET en mode batch ?

Oui, vous pouvez convertir par lots plusieurs présentations en HTML à l'aide d'Aspose.Slides pour .NET en parcourant vos fichiers de présentation et en appliquant le processus de conversion à chacun d'eux.

### 2. Existe-t-il un moyen de personnaliser l’apparence de la sortie HTML ?

Bien sûr ! Aspose.Slides pour .NET propose diverses options pour personnaliser l'apparence et la mise en forme du rendu HTML, comme le réglage des couleurs, des polices et de la mise en page.

### 3. Existe-t-il des limitations à l’intégration de polices dans HTML à l’aide d’Aspose.Slides pour .NET ?

Bien qu'Aspose.Slides pour .NET offre d'excellentes fonctionnalités d'intégration de polices, gardez à l'esprit que la taille de vos fichiers HTML peut augmenter lors de l'intégration de polices. Veillez à optimiser vos choix de polices pour une utilisation web.

### 4. Puis-je convertir des présentations PowerPoint vers d’autres formats avec Aspose.Slides pour .NET ?

Oui, Aspose.Slides pour .NET prend en charge un large éventail de formats de sortie, notamment les PDF, les images, etc. Vous pouvez facilement convertir vos présentations au format de votre choix.

### 5. Où puis-je trouver des ressources et une assistance supplémentaires pour Aspose.Slides pour .NET ?

Vous pouvez accéder à une multitude de ressources, y compris de la documentation, sur le [Référence de l'API Aspose.Slides pour .NET](https://reference.aspose.com/slides/net/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}