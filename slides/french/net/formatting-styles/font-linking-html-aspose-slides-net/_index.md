---
"date": "2025-04-15"
"description": "Découvrez comment garantir un rendu cohérent des polices lors de la conversion de présentations en HTML à l’aide d’Aspose.Slides pour .NET en incorporant directement les polices."
"title": "Comment lier des polices en HTML à l'aide d'Aspose.Slides pour .NET ? Guide étape par étape"
"url": "/fr/net/formatting-styles/font-linking-html-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment lier des polices en HTML avec Aspose.Slides pour .NET

## Introduction

Convertir des présentations en HTML tout en conservant un rendu de police cohérent sur toutes les plates-formes peut être un défi. **Aspose.Slides pour .NET** offre une solution transparente en vous permettant de lier toutes les polices utilisées dans une présentation directement dans la sortie HTML via des fichiers de polices intégrés.

Dans ce didacticiel, nous allons explorer comment implémenter la liaison de polices à l'aide d'Aspose.Slides pour .NET et garantir la cohérence de la conception sur différentes plates-formes. 

**Ce que vous apprendrez :**
- Configurer votre environnement avec Aspose.Slides pour .NET
- Lier les polices lors de la conversion HTML
- Écriture de contrôleurs personnalisés pour l'intégration de polices
- Applications pratiques et considérations de performance

Plongeons dans les étapes nécessaires pour y parvenir.

## Prérequis

Avant de commencer, assurez-vous d’avoir les éléments suivants :

### Bibliothèques et dépendances requises
- **Aspose.Slides pour .NET** bibliothèque : Le composant principal de notre implémentation.

### Configuration requise pour l'environnement
- Un environnement de développement avec .NET Framework ou .NET Core installé.

### Prérequis en matière de connaissances
- Compréhension de base de la programmation C#.
- Familiarité avec HTML et CSS, en particulier le `@font-face` règle.

## Configuration d'Aspose.Slides pour .NET

Pour utiliser Aspose.Slides dans votre projet .NET, vous devez installer la bibliothèque. Voici plusieurs méthodes :

### Utilisation de .NET CLI
```bash
dotnet add package Aspose.Slides
```

### Utilisation de la console du gestionnaire de packages
```powershell
Install-Package Aspose.Slides
```

### Via l'interface utilisateur du gestionnaire de packages NuGet
- Ouvrez votre projet dans Visual Studio.
- Accédez au « Gestionnaire de packages NuGet ».
- Recherchez « Aspose.Slides » et installez la dernière version.

### Étapes d'acquisition de licence
Vous pouvez obtenir une licence d'essai gratuite pour tester toutes les fonctionnalités sans limitations en suivant ces étapes :
1. **Essai gratuit**: Télécharger une licence temporaire [ici](https://releases.aspose.com/slides/net/).
2. **Permis temporaire**:Demander un accès prolongé [ici](https://purchase.aspose.com/temporary-license/).
3. **Achat**:Pour une fonctionnalité complète, achetez une licence [ici](https://purchase.aspose.com/buy).

### Initialisation et configuration de base
```csharp
// Créer une instance de la classe License
easpose.slides.License license = new aspose.slides.License();

// Appliquer la licence à partir du chemin du fichier
license.SetLicense("Aspose.Slides.lic");
```

## Guide de mise en œuvre

Maintenant, implémentons la liaison de police dans la conversion HTML en utilisant **Aspose.Slides pour .NET**.

### Présentation des fonctionnalités : Liaison des polices lors de la conversion HTML
Cette fonctionnalité garantit que toutes les polices utilisées dans une présentation sont directement liées au fichier HTML résultant en les intégrant. Cette méthode offre une solution robuste pour garantir la cohérence du design sur différents navigateurs et plateformes.

#### Étape 1 : Créer le contrôleur personnalisé
Créer une classe de contrôleur personnalisée `LinkAllFontsHtmlController` qui hérite de `EmbedAllFontsHtmlController`:
```csharp
using Aspose.Slides.Export;
using System.IO;

public class LinkAllFontsHtmlController : EmbedAllFontsHtmlController
{
    private readonly string m_basePath;

    public LinkAllFontsHtmlController(string[] fontNameExcludeList, string basePath)
        : base(fontNameExcludeList)
    {
        m_basePath = basePath; // Définissez le répertoire dans lequel les fichiers de polices seront stockés
    }
}
```
#### Étape 2 : Mettre en œuvre la méthode d’écriture des polices
Le `WriteFont` la méthode écrit les données de police dans un fichier et génère le code HTML correspondant pour l'intégration :
```csharp
public override void WriteFont(
    IHtmlGenerator generator,
    IFontData originalFont,
    IFontData substitutedFont,
    string fontStyle,
    string fontWeight,
    byte[] fontData)
{
    // Déterminez le nom de la police à utiliser, en privilégiant les polices de substitution si disponibles.
    string fontName = substitutedFont == null ? originalFont.FontName : substitutedFont.FontName;

    // Construisez un chemin de fichier pour le fichier de police .woff.
    string path = Path.Combine(m_basePath, $"{fontName}.woff`);
    
    // Écrivez les données de police dans le chemin de fichier spécifié.
    File.WriteAllBytes(path, fontData);

    // Générer un bloc de style HTML intégrant la police à l'aide de la règle @font-face.
    generator.AddHtml("<style>");
    generator.AddHtml("@font-face { ");
    generator.AddHtml($"font-family: '{fontName}'; ");
    generator.AddHtml($"src: url('{path}');");
    generator.AddHtml(\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}