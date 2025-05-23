---
"description": "Apprenez à conserver les polices d'origine lors de la conversion de vos présentations au format HTML avec Aspose.Slides pour .NET. Assurez la cohérence des polices et un impact visuel optimal sans effort."
"linktitle": "Préserver les polices d'origine - Convertir une présentation en HTML"
"second_title": "API de traitement PowerPoint Aspose.Slides .NET"
"title": "Préserver les polices d'origine - Convertir une présentation en HTML"
"url": "/fr/net/presentation-conversion/preserving-original-fonts-convert-presentation-to-html/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Préserver les polices d'origine - Convertir une présentation en HTML


Dans ce guide complet, nous vous expliquerons comment conserver les polices d'origine lors de la conversion d'une présentation au format HTML avec Aspose.Slides pour .NET. Nous vous fournirons le code source C# nécessaire et vous expliquerons chaque étape en détail. À la fin de ce tutoriel, vous serez en mesure de garantir que les polices de votre document HTML converti restent fidèles à la présentation d'origine.

## 1. Introduction

Lors de la conversion de présentations PowerPoint en HTML, il est essentiel de conserver les polices d'origine pour garantir la cohérence visuelle de votre contenu. Aspose.Slides pour .NET offre une solution performante pour y parvenir. Dans ce tutoriel, nous vous guiderons à travers les étapes nécessaires pour conserver les polices d'origine pendant la conversion.

## 2. Prérequis

Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :

- Visual Studio installé sur votre machine.
- Bibliothèque Aspose.Slides pour .NET ajoutée à votre projet.

## 3. Configuration de votre projet

Pour commencer, créez un nouveau projet dans Visual Studio et ajoutez la bibliothèque Aspose.Slides pour .NET comme référence.

## 4. Chargement de la présentation

Utilisez le code suivant pour charger votre présentation PowerPoint :

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation("input.pptx"))
{
    // Votre code ici
}
```

Remplacer `"Your Document Directory"` avec le chemin vers votre fichier de présentation.

## 5. Exclusion des polices par défaut

Pour exclure les polices par défaut comme Calibri et Arial, utilisez le code suivant :

```csharp
string[] fontNameExcludeList = { "Calibri", "Arial" };
```

Vous pouvez personnaliser cette liste selon vos besoins.

## 6. Intégration de toutes les polices

Nous allons ensuite intégrer toutes les polices dans le document HTML. Cela garantit la préservation des polices d'origine. Utilisez le code suivant :

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);

HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(embedFontsController)
};
```

## 7. Enregistrer au format HTML

Maintenant, enregistrez la présentation en tant que document HTML avec des polices intégrées :

```csharp
pres.Save("output.html", SaveFormat.Html, htmlOptionsEmbed);
```

Remplacer `"output.html"` avec le nom de fichier de sortie souhaité.

## 8. Conclusion

Dans ce tutoriel, nous avons montré comment conserver les polices d'origine lors de la conversion d'une présentation PowerPoint en HTML avec Aspose.Slides pour .NET. En suivant ces étapes, vous pouvez garantir que votre document HTML converti conserve l'intégrité visuelle de la présentation d'origine.

## 9. FAQ

### Q1 : Puis-je personnaliser la liste des polices exclues ?

Oui, vous pouvez. Modifiez le `fontNameExcludeList` tableau pour inclure ou exclure des polices spécifiques selon vos besoins.

### Q2 : Que faire si je ne souhaite pas intégrer toutes les polices ?

Si vous souhaitez intégrer uniquement des polices spécifiques, vous pouvez modifier le code en conséquence. Consultez la documentation d'Aspose.Slides pour .NET pour plus de détails.

### Q3 : Existe-t-il des exigences de licence pour utiliser Aspose.Slides pour .NET ?

Oui, vous aurez peut-être besoin d'une licence valide pour utiliser Aspose.Slides pour .NET dans vos projets. Consultez le site web d'Aspose pour plus d'informations sur les licences.

### Q4 : Puis-je convertir d’autres formats de fichiers en HTML à l’aide d’Aspose.Slides pour .NET ?

Aspose.Slides pour .NET est principalement destiné aux présentations PowerPoint. Pour convertir d'autres formats de fichiers en HTML, vous devrez peut-être explorer d'autres produits Aspose adaptés à ces formats.

### Q5 : Où puis-je accéder à des ressources et à un soutien supplémentaires ?

Vous trouverez davantage de documentation, de tutoriels et d'assistance sur le site web d'Aspose. Visitez [Documentation Aspose.Slides pour .NET](https://reference.aspose.com/slides/net/) pour des informations détaillées.


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}