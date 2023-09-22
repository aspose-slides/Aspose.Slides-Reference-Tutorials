---
title: Convertir une présentation HTML avec des images intégrées
linktitle: Convertir une présentation HTML avec des images intégrées
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Convertissez facilement des présentations HTML avec des images intégrées à l'aide d'Aspose.Slides pour .NET. Créez, personnalisez et enregistrez des fichiers PowerPoint en toute transparence.
type: docs
weight: 11
url: /fr/net/presentation-conversion/convert-html-presentation-with-embedded-images/
---

## 1. Introduction

Aspose.Slides pour .NET offre un moyen pratique de convertir des présentations PowerPoint au format HTML5 tout en préservant les images intégrées. Cela peut être incroyablement utile pour afficher vos présentations sur des sites Web ou dans des applications Web.

## 2. Conditions préalables

Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :

- Visual Studio ou tout environnement de développement C#.
- Aspose.Slides pour la bibliothèque .NET.
- Un exemple de présentation PowerPoint avec des images intégrées.
- Connaissance de base de la programmation C#.

## 3. Mise en place de votre projet

Commencez par créer un nouveau projet C# dans votre environnement de développement préféré. Assurez-vous que la bibliothèque Aspose.Slides for .NET est correctement référencée dans votre projet.

## 4. Chargement de la présentation source

```csharp
string dataDir = "Your Document Directory";
string presentationName = Path.Combine(dataDir, "PresentationDemo.pptx");

using (Presentation pres = new Presentation(presentationName))
{
    // Votre code pour traiter la présentation va ici
}
```

## 5. Configuration des options de conversion HTML

 Pour configurer les options de conversion HTML, vous pouvez utiliser le`Html5Options` classe. Voici un exemple de la façon de définir certaines options :

```csharp
Html5Options options = new Html5Options()
{
    EmbedImages = false, // Ne pas enregistrer les images dans le document HTML5
    OutputPath = "Your Output Directory" // Définir le chemin des images externes
};
```

## 6. Création du répertoire de sortie

Avant d'enregistrer la présentation au format HTML5, il est conseillé de créer le répertoire de sortie s'il n'existe pas déjà :

```csharp
string outFilePath = Path.Combine(outPath, "HTMLConversion");

if (!Directory.Exists(outFilePath))
{
    Directory.CreateDirectory(outFilePath);
}
```

## 7. Enregistrement de la présentation au format HTML5

Maintenant, enregistrons la présentation au format HTML5 :

```csharp
pres.Save(Path.Combine(outFilePath, "pres.html"), SaveFormat.Html5, options);
```

## 8. Conclusion

Toutes nos félicitations! Vous avez converti avec succès une présentation PowerPoint avec des images intégrées au format HTML5 à l'aide d'Aspose.Slides pour .NET. Cela peut être un outil précieux pour partager vos présentations en ligne.

## 9. FAQ

**Q1: Can I customize the appearance of the HTML5 presentation?**
Oui, vous pouvez personnaliser l'apparence en modifiant les fichiers HTML et CSS générés par Aspose.Slides.

**Q2: Does Aspose.Slides for .NET support other output formats?**
Oui, il prend en charge divers formats de sortie, notamment PDF, images, etc.

**Q3: Are there any limitations to converting presentations with embedded images?**
Bien qu'Aspose.Slides pour .NET soit puissant, vous pouvez rencontrer certaines limitations avec des présentations très complexes.

**Q4: Is Aspose.Slides for .NET compatible with the latest PowerPoint versions?**
Oui, il est compatible avec les fichiers PowerPoint de différentes versions, y compris les dernières.

**Q5: Where can I find more documentation and resources for Aspose.Slides for .NET?**
 Pour une documentation et des ressources complètes, visitez le[Aspose.Slides pour la documentation .NET](https://reference.aspose.com/slides/net/).