---
title: Préserver les polices originales - Convertir la présentation en HTML
linktitle: Préserver les polices originales - Convertir la présentation en HTML
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Découvrez comment conserver les polices d'origine lors de la conversion de présentations au format HTML à l'aide d'Aspose.Slides pour .NET. Assurez la cohérence des polices et l’impact visuel sans effort.
type: docs
weight: 14
url: /fr/net/presentation-conversion/preserving-original-fonts-convert-presentation-to-html/
---

Dans ce guide complet, nous vous guiderons tout au long du processus de préservation des polices originales lors de la conversion d'une présentation en HTML à l'aide d'Aspose.Slides pour .NET. Nous vous fournirons le code source C# nécessaire et expliquerons chaque étape en détail. À la fin de ce didacticiel, vous serez en mesure de vous assurer que les polices de votre document HTML converti restent fidèles à la présentation originale.

## 1. Introduction

Lors de la conversion de présentations PowerPoint en HTML, il est crucial de conserver les polices d'origine pour garantir la cohérence visuelle de votre contenu. Aspose.Slides pour .NET fournit une solution puissante pour y parvenir. Dans ce didacticiel, nous vous guiderons à travers les étapes nécessaires pour conserver les polices d'origine pendant le processus de conversion.

## 2. Conditions préalables

Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :

- Visual Studio installé sur votre ordinateur.
- Bibliothèque Aspose.Slides pour .NET ajoutée à votre projet.

## 3. Mise en place de votre projet

Pour commencer, créez un nouveau projet dans Visual Studio et ajoutez la bibliothèque Aspose.Slides for .NET comme référence.

## 4. Chargement de la présentation

Utilisez le code suivant pour charger votre présentation PowerPoint :

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation("input.pptx"))
{
    // Votre code ici
}
```

 Remplacer`"Your Document Directory"` avec le chemin d'accès à votre fichier de présentation.

## 5. Exclusion des polices par défaut

Pour exclure les polices par défaut comme Calibri et Arial, utilisez le code suivant :

```csharp
string[] fontNameExcludeList = { "Calibri", "Arial" };
```

Vous pouvez personnaliser cette liste selon vos besoins.

## 6. Intégration de toutes les polices

Ensuite, nous intégrerons toutes les polices dans le document HTML. Cela garantit que les polices originales sont préservées. Utilisez le code suivant :

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);

HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(embedFontsController)
};
```

## 7. Enregistrement au format HTML

Maintenant, enregistrez la présentation en tant que document HTML avec des polices intégrées :

```csharp
pres.Save("output.html", SaveFormat.Html, htmlOptionsEmbed);
```

 Remplacer`"output.html"` avec le nom de fichier de sortie souhaité.

## 8. Conclusion

Dans ce didacticiel, nous avons montré comment conserver les polices d'origine lors de la conversion d'une présentation PowerPoint en HTML à l'aide d'Aspose.Slides pour .NET. En suivant ces étapes, vous pouvez vous assurer que votre document HTML converti conserve l'intégrité visuelle de la présentation originale.

## 9. FAQ

### Q1 : Puis-je personnaliser la liste des polices exclues ?

 Oui, vous pouvez. Modifier le`fontNameExcludeList`tableau pour inclure ou exclure des polices spécifiques en fonction de vos besoins.

### Q2 : Que faire si je ne souhaite pas intégrer toutes les polices ?

Si vous souhaitez intégrer uniquement des polices spécifiques, vous pouvez modifier le code en conséquence. Consultez la documentation Aspose.Slides pour .NET pour plus de détails.

### Q3 : Existe-t-il des conditions de licence pour utiliser Aspose.Slides pour .NET ?

Oui, vous aurez peut-être besoin d'une licence valide pour utiliser Aspose.Slides for .NET dans vos projets. Reportez-vous au site Web Aspose pour obtenir des informations sur les licences.

### Q4 : Puis-je convertir d'autres formats de fichiers en HTML à l'aide d'Aspose.Slides pour .NET ?

Aspose.Slides pour .NET se concentre principalement sur les présentations PowerPoint. Pour convertir d'autres formats de fichiers en HTML, vous devrez peut-être explorer d'autres produits Aspose adaptés à ces formats.

### Q5 : Où puis-je accéder à des ressources et à une assistance supplémentaires ?

 Vous pouvez trouver plus de documentation, de didacticiels et d'assistance sur le site Web Aspose. Visite[Documentation Aspose.Slides pour .NET](https://reference.aspose.com/slides/net/) pour des informations détaillées.
