---
"description": "Apprenez à exporter des présentations au format XAML avec Aspose.Slides pour .NET. Créez du contenu interactif en toute simplicité !"
"linktitle": "Exporter la présentation au format XAML"
"second_title": "API de traitement PowerPoint Aspose.Slides .NET"
"title": "Exporter la présentation au format XAML"
"url": "/fr/net/presentation-conversion/export-presentation-to-xaml-format/"
"weight": 27
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Exporter la présentation au format XAML


Dans le monde du développement logiciel, il est essentiel de disposer d'outils permettant de simplifier les tâches complexes. Aspose.Slides pour .NET est l'un de ces outils qui vous permet de travailler avec des présentations PowerPoint par programmation. Dans ce tutoriel pas à pas, nous allons découvrir comment exporter une présentation au format XAML avec Aspose.Slides pour .NET. 

## Introduction à Aspose.Slides pour .NET

Avant de commencer ce tutoriel, présentons brièvement Aspose.Slides pour .NET. Cette puissante bibliothèque permet aux développeurs de créer, modifier, convertir et gérer des présentations PowerPoint sans utiliser Microsoft PowerPoint. Avec Aspose.Slides pour .NET, vous pouvez automatiser diverses tâches liées aux présentations PowerPoint et ainsi optimiser votre processus de développement.

## Prérequis

Pour suivre ce tutoriel, vous aurez besoin des éléments suivants :

1. Aspose.Slides pour .NET : assurez-vous que la bibliothèque Aspose.Slides pour .NET est installée et prête à être utilisée dans votre projet .NET.

2. Présentation source : Vous disposez d'une présentation PowerPoint (PPTX) que vous souhaitez exporter au format XAML. Assurez-vous de connaître le chemin d'accès à cette présentation.

3. Répertoire de sortie : choisissez un répertoire dans lequel vous souhaitez enregistrer les fichiers XAML générés.

## Étape 1 : Configurez votre projet

Dans cette première étape, nous allons configurer notre projet et vérifier que tous les composants nécessaires sont prêts. Assurez-vous d'avoir ajouté une référence à la bibliothèque Aspose.Slides pour .NET dans votre projet.

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
// Présentation du chemin vers la source
string presentationFileName = Path.Combine(dataDir, "XamlEtalon.pptx");
```

Remplacer `"Your Document Directory"` avec le chemin d'accès au répertoire contenant votre présentation PowerPoint source. Indiquez également le répertoire de sortie où seront enregistrés les fichiers XAML générés.

## Étape 2 : Exporter la présentation au format XAML

Passons maintenant à l'exportation de la présentation PowerPoint au format XAML. Nous utiliserons Aspose.Slides pour .NET. 

```csharp
using (Presentation pres = new Presentation(presentationFileName))
{
    // Créer des options de conversion
    XamlOptions xamlOptions = new XamlOptions();
    xamlOptions.ExportHiddenSlides = true;

    // Définissez votre propre service d'économie de production
    NewXamlSaver newXamlSaver = new NewXamlSaver();
    xamlOptions.OutputSaver = newXamlSaver;

    // Convertir des diapositives
    pres.Save(xamlOptions);

    // Enregistrer les fichiers XAML dans un répertoire de sortie
    foreach (var pair in newXamlSaver.Results)
    {
        File.AppendAllText(Path.Combine(outPath, pair.Key), pair.Value);
    }
}
```

Dans cet extrait de code, nous chargeons la présentation source, créons des options de conversion XAML et définissons un service de sauvegarde de sortie personnalisé à l'aide de `NewXamlSaver`Nous enregistrons ensuite les fichiers XAML dans le répertoire de sortie spécifié.

## Étape 3 : Classe de sauvegarde XAML personnalisée

Pour implémenter l'économiseur XAML personnalisé, nous allons créer une classe nommée `NewXamlSaver` qui met en œuvre le `IXamlOutputSaver` interface.

```csharp
class NewXamlSaver : IXamlOutputSaver
{
    private Dictionary<string, string> m_result = new Dictionary<string, string>();

    public Dictionary<string, string> Results
    {
        get { return m_result; }
    }

    public void Save(string path, byte[] data)
    {
        string name = Path.GetFileName(path);
        Results[name] = Encoding.UTF8.GetString(data);
    }
}
```

Cette classe gérera l'enregistrement des fichiers XAML dans le répertoire de sortie.

## Conclusion

Félicitations ! Vous avez appris à exporter une présentation PowerPoint au format XAML avec Aspose.Slides pour .NET. Cette compétence peut s'avérer précieuse pour les projets impliquant la manipulation de présentations.

N'hésitez pas à explorer davantage de fonctionnalités et de capacités d'Aspose.Slides pour .NET pour améliorer vos tâches d'automatisation PowerPoint.

## FAQ

1. ### Qu'est-ce qu'Aspose.Slides pour .NET ?
Aspose.Slides pour .NET est une bibliothèque .NET permettant de travailler avec des présentations PowerPoint par programmation.

2. ### Où puis-je obtenir Aspose.Slides pour .NET ?
Vous pouvez télécharger Aspose.Slides pour .NET à partir de [ici](https://purchase.aspose.com/buy).

3. ### Existe-t-il un essai gratuit disponible ?
Oui, vous pouvez obtenir un essai gratuit d'Aspose.Slides pour .NET [ici](https://releases.aspose.com/).

4. ### Comment puis-je obtenir une licence temporaire pour Aspose.Slides pour .NET ?
Vous pouvez obtenir un permis temporaire [ici](https://purchase.aspose.com/temporary-license/).

5. ### Où puis-je obtenir de l'aide pour Aspose.Slides pour .NET ?
Vous pouvez trouver du soutien et des discussions communautaires [ici](https://forum.aspose.com/).

Pour plus de tutoriels et de ressources, visitez le [Documentation de l'API Aspose.Slides](https://reference.aspose.com/slides/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}