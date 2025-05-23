---
"date": "2025-04-15"
"description": "Découvrez comment ajouter des cadres d'image avec une mise à l'échelle relative avec Aspose.Slides pour .NET. Ce guide couvre la configuration, la gestion des images et les techniques de mise à l'échelle."
"title": "Comment ajouter des cadres d'image avec une mise à l'échelle relative dans Aspose.Slides .NET ? Guide étape par étape"
"url": "/fr/net/images-multimedia/aspose-slides-net-picture-frame-relative-scaling/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment ajouter des cadres photo avec une mise à l'échelle relative dans Aspose.Slides .NET : guide étape par étape

## Introduction

Créer des présentations PowerPoint visuellement attrayantes est essentiel pour une communication efficace, qu'il s'agisse d'un pitch commercial ou d'une conférence pédagogique. Adapter les images à la mise en page de vos diapositives peut être fastidieux et chronophage. Avec Aspose.Slides pour .NET, vous pouvez facilement ajouter des cadres d'image avec une mise à l'échelle relative, garantissant ainsi que vos images conservent leurs proportions et s'intègrent parfaitement à vos diapositives.

Dans ce tutoriel, nous découvrirons comment utiliser Aspose.Slides pour .NET pour ajouter une image comme cadre et ajuster ses dimensions proportionnellement. Vous apprendrez les bases de la configuration d'Aspose.Slides dans votre environnement de développement et de l'implémentation de fonctionnalités de mise à l'échelle relative dans vos présentations. À la fin, vous obtiendrez une présentation non seulement professionnelle, mais également adaptable de manière dynamique aux différents paramètres d'affichage.

**Ce que vous apprendrez :**
- Configuration d'Aspose.Slides pour .NET
- Ajouter une image comme cadre photo à une diapositive PowerPoint
- Mise en œuvre d'une mise à l'échelle relative pour les cadres d'image
- Bonnes pratiques et conseils de dépannage

Plongeons dans les prérequis avant de commencer notre voyage avec Aspose.Slides.

## Prérequis

Avant de commencer, assurez-vous d’avoir les éléments suivants en place :

### Bibliothèques et dépendances requises

Pour implémenter cette fonctionnalité, vous devez avoir installé Aspose.Slides pour .NET. Cette bibliothèque permet une manipulation complète des présentations PowerPoint en C#.

### Configuration requise pour l'environnement

Assurez-vous que votre environnement de développement est configuré avec :
- Une version compatible de .NET (de préférence .NET Core ou .NET Framework 4.5 et supérieur)
- Un éditeur de code comme Visual Studio, Visual Studio Code ou tout autre IDE prenant en charge le développement .NET
- Accès à un répertoire de fichiers où vous pouvez enregistrer vos fichiers PowerPoint

### Prérequis en matière de connaissances

Une connaissance de la programmation C# est un atout, mais pas obligatoire. Des connaissances de base en gestion d'images et une compréhension des principes de la programmation orientée objet seront également utiles.

## Configuration d'Aspose.Slides pour .NET

Pour commencer à utiliser Aspose.Slides pour .NET, suivez les étapes d'installation ci-dessous :

**.NET CLI**
```bash
dotnet add package Aspose.Slides
```

**Gestionnaire de paquets**
```powershell
Install-Package Aspose.Slides
```

**Interface utilisateur du gestionnaire de packages NuGet**
Ouvrez votre projet dans Visual Studio, accédez au gestionnaire de packages NuGet et recherchez « Aspose.Slides » pour installer la dernière version.

### Étapes d'acquisition de licence

- **Essai gratuit**:Vous pouvez commencer par un essai gratuit qui vous permet de tester les fonctionnalités d'Aspose.Slides.
- **Permis temporaire**:Obtenez une licence temporaire pour une évaluation prolongée sans limitations.
- **Achat**:Pour un accès et une assistance complets, envisagez d'acheter une licence auprès d'Aspose.

#### Initialisation et configuration de base

Une fois installé, initialisez Aspose.Slides dans votre projet en ajoutant les directives using nécessaires :

```csharp
using Aspose.Slides;
```

## Guide de mise en œuvre

### Ajout d'un cadre photo avec mise à l'échelle relative

Dans cette section, nous allons vous expliquer comment ajouter une image en tant que cadre photo et définir sa mise à l'échelle relative.

#### Chargement de votre image

Commencez par charger l’image souhaitée dans la collection d’images de la présentation :

```csharp
string dataDir = @"YOUR_DOCUMENT_DIRECTORY";
IImage img = Images.FromFile(dataDir + "aspose-logo.jpg");
IPPImage image = presentation.Images.AddImage(img);
```

Cet extrait de code charge une image à partir d’un répertoire spécifié et l’ajoute à la présentation.

#### Ajout du cadre photo

Ensuite, ajoutez un cadre photo de type rectangle sur votre diapositive :

```csharp
IPictureFrame pf = presentation.Slides[0].Shapes.AddPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```

Ici, `ShapeType.Rectangle` spécifie la forme et les paramètres définissent sa position et sa taille initiale.

#### Réglage de l'échelle relative

Ajustez les dimensions proportionnellement en définissant la hauteur et la largeur de l'échelle relative :

```csharp
pf.RelativeScaleHeight = 0.8f; // Échelle à 80 % de la hauteur d'origine
pf.RelativeScaleWidth = 1.35f; // S'adapte à 135 % de la largeur d'origine
```

Cela garantit que votre image est correctement mise à l'échelle, en conservant un rapport hauteur/largeur cohérent.

#### Enregistrer votre présentation

Enfin, enregistrez la présentation avec le cadre photo modifié :

```csharp\presentation.Save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}