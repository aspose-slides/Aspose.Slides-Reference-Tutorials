---
title: Convertir des présentations en HTML avec des polices intégrées
linktitle: Convertir des présentations en HTML avec des polices intégrées
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Convertissez des présentations PowerPoint en HTML avec des polices intégrées à l'aide d'Aspose.Slides pour .NET. Conservez l’originalité en toute transparence.
type: docs
weight: 13
url: /fr/net/presentation-conversion/convert-presentations-to-html-with-embedded-fonts/
---

À l’ère numérique d’aujourd’hui, le partage de présentations et de documents en ligne est devenu une pratique courante. Cependant, un défi qui se pose souvent est de garantir que vos polices s'affichent correctement lors de la conversion de présentations au format HTML. Ce didacticiel étape par étape vous guidera tout au long du processus d'utilisation d'Aspose.Slides pour .NET pour convertir des présentations au format HTML avec des polices intégrées, garantissant ainsi que vos documents ressemblent exactement à ce que vous souhaitiez.

## Introduction à Aspose.Slides pour .NET

Avant de plonger dans le didacticiel, présentons brièvement Aspose.Slides pour .NET. Il s'agit d'une bibliothèque puissante qui permet aux développeurs de travailler avec des présentations PowerPoint dans des applications .NET. Avec Aspose.Slides, vous pouvez créer, modifier et convertir des fichiers PowerPoint par programme.

## Conditions préalables

Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :

-  Aspose.Slides pour .NET : la bibliothèque Aspose.Slides doit être installée dans votre projet. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/slides/net/).

## Étape 1 : Configurez votre projet

1. Créez un nouveau projet ou ouvrez-en un existant dans votre environnement de développement .NET préféré.

2. Ajoutez une référence à la bibliothèque Aspose.Slides dans votre projet.

3. Importez les espaces de noms nécessaires dans votre code :

   ```csharp
   using Aspose.Slides;
   ```

## Étape 2 : Chargez votre présentation

 Pour commencer, vous devez charger la présentation que vous souhaitez convertir en HTML. Remplacer`"Your Document Directory"` avec le répertoire réel où se trouve votre fichier de présentation.

```csharp
string dataDir = "Your Document Directory";
using (Presentation pres = new Presentation(dataDir + "presentation.pptx"))
{
    // Votre code va ici
}
```

## Étape 3 : exclure les polices de présentation par défaut

Au cours de cette étape, vous pouvez spécifier toutes les polices de présentation par défaut que vous souhaitez exclure de l'intégration. Cela peut aider à optimiser la taille du fichier HTML résultant.

```csharp
string[] fontNameExcludeList = { };
```

## Étape 4 : Choisissez un contrôleur HTML

Vous disposez désormais de deux options pour intégrer des polices dans le HTML :

### Option 1 : Incorporer toutes les polices

 Pour intégrer toutes les polices utilisées dans la présentation, utilisez le`EmbedAllFontsHtmlController`.

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
```

### Option 2 : lier toutes les polices

 Pour créer un lien vers toutes les polices utilisées dans la présentation, utilisez le`LinkAllFontsHtmlController`. Vous devez spécifier le répertoire où se trouvent les polices sur votre système.

```csharp
LinkAllFontsHtmlController linkcont = new LinkAllFontsHtmlController(fontNameExcludeList, @"C:\Windows\Fonts\");
```

## Étape 5 : Définir les options HTML

 Créé un`HtmlOptions` objet et définissez le formateur HTML sur celui que vous avez sélectionné à l’étape précédente.

```csharp
HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(linkcont) // Utilisez embedFontsController pour intégrer toutes les polices
};
```

## Étape 6 : Enregistrer au format HTML

 Enfin, enregistrez la présentation sous forme de fichier HTML. Vous pouvez choisir soit`SaveFormat.Html` ou`SaveFormat.Html5` en fonction de vos besoins.

```csharp
pres.Save("pres.html", SaveFormat.Html, htmlOptionsEmbed);
```

## Conclusion

Toutes nos félicitations! Vous avez converti avec succès votre présentation en HTML avec des polices intégrées à l'aide d'Aspose.Slides pour .NET. Cela garantit que vos polices s'afficheront correctement lors du partage de vos présentations en ligne.

Désormais, vous pouvez facilement partager vos présentations magnifiquement formatées en toute confiance, sachant que votre public les verra exactement comme vous le souhaitiez.

 Pour plus d'informations et des références API détaillées, consultez le[Aspose.Slides pour la documentation .NET](https://reference.aspose.com/slides/net/).

## FAQ

### 1. Puis-je convertir des présentations PowerPoint en HTML à l'aide d'Aspose.Slides pour .NET en mode batch ?

Oui, vous pouvez convertir par lots plusieurs présentations en HTML à l'aide d'Aspose.Slides pour .NET en parcourant vos fichiers de présentation et en appliquant le processus de conversion à chacun.

### 2. Existe-t-il un moyen de personnaliser l’apparence de la sortie HTML ?

Certainement! Aspose.Slides pour .NET propose diverses options pour personnaliser l'apparence et le formatage de la sortie HTML, telles que l'ajustement des couleurs, des polices et de la mise en page.

### 3. Existe-t-il des limites à l'intégration de polices dans HTML à l'aide d'Aspose.Slides pour .NET ?

Bien qu'Aspose.Slides pour .NET offre d'excellentes capacités d'intégration de polices, gardez à l'esprit que la taille de vos fichiers HTML peut augmenter lors de l'intégration de polices. Assurez-vous d'optimiser vos choix de polices pour l'utilisation du Web.

### 4. Puis-je convertir des présentations PowerPoint vers d'autres formats avec Aspose.Slides pour .NET ?

Oui, Aspose.Slides pour .NET prend en charge un large éventail de formats de sortie, notamment PDF, images, etc. Vous pouvez facilement convertir vos présentations au format de votre choix.

### 5. Où puis-je trouver des ressources supplémentaires et une assistance pour Aspose.Slides pour .NET ?

 Vous pouvez accéder à une multitude de ressources, y compris de la documentation, sur le[Aspose.Slides pour la référence de l'API .NET](https://reference.aspose.com/slides/net/).
