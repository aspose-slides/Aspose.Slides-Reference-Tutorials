---
"date": "2025-04-16"
"description": "Découvrez comment définir les attributs de langue du texte dans les formes avec Aspose.Slides pour .NET. Ce guide explique comment ajouter des formes automatiques, définir des identifiants de langue et enregistrer des présentations."
"title": "Comment définir la langue des formes PowerPoint avec Aspose.Slides pour .NET"
"url": "/fr/net/shapes-text-frames/set-language-in-shapes-with-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment définir la langue des formes PowerPoint avec Aspose.Slides pour .NET

Dans le monde des présentations numériques, garantir l'accessibilité et la mise en forme correcte de votre contenu dans différentes langues peut s'avérer complexe. Avec Aspose.Slides pour .NET, vous pouvez facilement définir les attributs de langue du texte des formes de vos diapositives PowerPoint. Cette fonctionnalité est particulièrement utile pour la préparation de documents multilingues ou la cohérence des communications internationales.

**Ce que vous apprendrez :**
- Ajout de formes automatiques et insertion de texte dans celles-ci.
- Définition de l'ID de langue pour les parties de texte à l'aide d'Aspose.Slides.
- Enregistrement de présentations avec des configurations personnalisées.

Voyons comment vous pouvez implémenter cette fonctionnalité de manière transparente.

## Prérequis

Avant de commencer, assurez-vous d’avoir les éléments suivants :

- **Bibliothèques et dépendances**: Vous devez avoir installé Aspose.Slides pour .NET. Cette bibliothèque est essentielle pour manipuler des présentations PowerPoint en C#.
  
- **Configuration de l'environnement**:Un environnement de développement avec .NET Core ou .NET Framework est requis.

- **Prérequis en matière de connaissances**:Une connaissance des concepts de base de la programmation C# et une compréhension des principes de la programmation orientée objet seront utiles.

## Configuration d'Aspose.Slides pour .NET

Pour commencer, vous devez installer la bibliothèque Aspose.Slides. Vous pouvez le faire de l'une des manières suivantes :

**.NET CLI**
```shell
dotnet add package Aspose.Slides
```

**Gestionnaire de paquets**
```powershell
Install-Package Aspose.Slides
```

**Interface utilisateur du gestionnaire de packages NuGet**
Recherchez « Aspose.Slides » et installez la dernière version.

### Acquisition de licence

Vous pouvez commencer avec un essai gratuit en téléchargeant une licence temporaire à partir de [ici](https://purchase.aspose.com/temporary-license/)Pour une utilisation continue, pensez à acheter une licence via [ce lien](https://purchase.aspose.com/buy).

Une fois votre configuration prête, initialisez Aspose.Slides dans votre projet :

```csharp
using Aspose.Slides;
```

## Guide de mise en œuvre

Maintenant que nous sommes configurés, implémentons la fonctionnalité permettant de définir la langue du texte de forme.

### Présentation des fonctionnalités : Définition de la langue du texte de forme

Cette fonctionnalité vous permet de spécifier la langue du texte d'une forme PowerPoint. En définissant l'ID de langue, vous garantissez que la vérification orthographique et les autres fonctionnalités spécifiques à la langue sont correctement appliquées.

#### Étape 1 : Initialiser la présentation

Commencez par créer une instance du `Presentation` classe.

```csharp
using (Presentation pres = new Presentation())
{
    // Votre code ici
}
```

Cela initialise un nouvel objet de présentation PowerPoint que nous allons manipuler.

#### Étape 2 : Ajouter une forme automatique et un cadre de texte

Ajoutez une forme rectangulaire à votre diapositive et insérez-y du texte :

```csharp
IAutoShape shape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 50, 50, 200, 50);
shape.AddTextFrame("Text to apply spellcheck language");
```

Ici, `AddAutoShape` Ajoute un rectangle à la première diapositive. Les paramètres définissent sa position et sa taille.

#### Étape 3 : définir l’ID de langue

Définissez la langue de la partie texte dans la forme :

```csharp
shape.TextFrame.Paragraphs[0].Portions[0].PortionFormat.LanguageId = "en-EN";
```

Cela attribue l'anglais (Royaume-Uni) comme langue pour la vérification orthographique.

#### Étape 4 : Enregistrer la présentation

Enfin, enregistrez votre présentation dans un chemin spécifié :

```csharp
pres.Save("YOUR_OUTPUT_DIRECTORY\	est1.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}