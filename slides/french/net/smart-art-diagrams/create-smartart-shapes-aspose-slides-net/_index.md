---
"date": "2025-04-16"
"description": "Apprenez à créer des graphiques SmartArt dynamiques dans PowerPoint avec Aspose.Slides pour .NET. Améliorez vos présentations grâce à ce guide complet."
"title": "Créer des formes SmartArt dans PowerPoint à l'aide d'Aspose.Slides pour .NET &#58; un guide étape par étape"
"url": "/fr/net/smart-art-diagrams/create-smartart-shapes-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment créer des formes SmartArt dans PowerPoint avec Aspose.Slides pour .NET : guide étape par étape

## Introduction

Améliorez vos présentations PowerPoint en intégrant des graphiques SmartArt dynamiques en C#. Avec Aspose.Slides pour .NET, créez et gérez facilement des formes SmartArt dans vos diapositives. Ce guide vous guidera pas à pas dans la configuration et l'implémentation de SmartArt avec Aspose.Slides pour .NET.

**Ce que vous apprendrez :**
- Configurer votre environnement avec Aspose.Slides pour .NET
- Créer une forme SmartArt dans une diapositive PowerPoint
- Gérer efficacement les répertoires dans votre code

## Prérequis (H2)

Pour mettre en œuvre cette solution avec succès, assurez-vous d'avoir :
- **Bibliothèques requises**:Aspose.Slides pour .NET (version 21.11 ou ultérieure recommandée)
- **Environnement de développement**: .NET Core ou .NET Framework
- **Connaissances de base**: Familiarité avec C# et les opérations du système de fichiers

## Configuration d'Aspose.Slides pour .NET (H2)

### Installation

Commencez par installer Aspose.Slides en utilisant l’une des méthodes suivantes :

**.NET CLI**
```bash
dotnet add package Aspose.Slides
```

**Console du gestionnaire de packages dans Visual Studio**
```powershell
Install-Package Aspose.Slides
```

**Interface utilisateur du gestionnaire de packages NuGet**
1. Ouvrez le gestionnaire de packages NuGet.
2. Recherchez « Aspose.Slides » et installez la dernière version.

### Acquisition de licence
- **Essai gratuit**: Téléchargez une licence temporaire à partir de [ici](https://purchase.aspose.com/temporary-license/) pour évaluer toutes les capacités d'Aspose.Slides.
- **Achat**: Pour une utilisation continue, achetez une licence via [ce lien](https://purchase.aspose.com/buy).

Une fois que vous avez votre fichier de licence, initialisez-le dans votre application comme suit :
```csharp
License license = new License();
license.SetLicense("Aspose.Slides.lic");
```

## Guide de mise en œuvre (H2)

### Fonctionnalité : Créer une forme SmartArt (H2)

Cette fonctionnalité vous permet d’ajouter des graphiques SmartArt visuellement attrayants à vos diapositives PowerPoint par programmation.

#### Aperçu du processus (H3)
Nous commencerons par configurer un répertoire, créer un objet de présentation, puis ajouter une forme SmartArt.

#### Procédure pas à pas du code (H3)
1. **Gestion des répertoires**
   Assurez-vous que votre répertoire de documents existe ou créez-le si nécessaire :
   ```csharp
   string dataDir = "YOUR_DOCUMENT_DIRECTORY"; // Définir le chemin du répertoire du document cible
   bool isExists = Directory.Exists(dataDir); // Vérifiez si le répertoire existe
   if (!isExists) 
       Directory.CreateDirectory(dataDir); // Créer le répertoire s'il n'existe pas
   ```

2. **Créer une nouvelle présentation**
   Initialiser une nouvelle présentation et accéder à sa première diapositive :
   ```csharp
   using (Presentation pres = new Presentation())
   {
       ISlide slide = pres.Slides[0]; // Accéder à la première diapositive
   ```
   
3. **Ajout de SmartArt à la diapositive**
   Ajoutez une forme SmartArt aux coordonnées spécifiées avec les dimensions et le type de mise en page souhaités :
   ```csharp
   // Ajouter une forme SmartArt à l'aide de la disposition BasicBlockList
   ISmartArt smart = slide.Shapes.AddSmartArt(0, 0, 400, 400, SmartArtLayoutType.BasicBlockList);
   ```

4. **Enregistrer la présentation**
   Enfin, enregistrez votre présentation dans le répertoire souhaité :
   ```csharp
   pres.Save(dataDir + "SimpleSmartArt_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}