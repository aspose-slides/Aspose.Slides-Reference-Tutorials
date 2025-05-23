---
"date": "2025-04-16"
"description": "Apprenez à ajouter et supprimer des sous-titres vidéo avec Aspose.Slides pour .NET. Améliorez vos présentations avec du contenu accessible et engageant."
"title": "Ajouter et supprimer des sous-titres vidéo dans Aspose.Slides .NET - Un guide complet"
"url": "/fr/net/images-multimedia/aspose-slides-net-video-captions-add-remove/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Ajouter et supprimer des sous-titres vidéo dans Aspose.Slides .NET : guide complet

À l'ère du numérique, capter l'attention de votre public lors de vos présentations est plus important que jamais. L'ajout de sous-titres aux vidéos des diapositives peut considérablement améliorer l'engagement et l'accessibilité. Que vous soyez développeur ou concepteur de présentations, maîtriser la gestion des sous-titres vidéo avec Aspose.Slides pour .NET est essentiel.

## Ce que vous apprendrez
- Comment ajouter des légendes à un VideoFrame à l'aide d'Aspose.Slides pour .NET.
- Techniques d'extraction et de suppression des sous-titres vidéo des présentations.
- Applications concrètes de ces fonctionnalités.
- Conseils d’optimisation des performances lors de la gestion des données vidéo dans .NET.

Commençons par les prérequis dont vous avez besoin avant de plonger dans ce tutoriel !

## Prérequis

### Bibliothèques, versions et dépendances requises
Pour suivre ce guide, assurez-vous d'avoir :
- **Aspose.Slides pour .NET**:La bibliothèque principale utilisée pour manipuler les fichiers de présentation.
- **Kit de développement logiciel (SDK) .NET Core**Assurez-vous que votre environnement est configuré avec une version compatible du SDK .NET Core.

### Configuration requise pour l'environnement
Vous aurez besoin d'un IDE tel que Visual Studio ou VS Code, et une connaissance de la programmation C# est recommandée mais pas obligatoire.

### Prérequis en matière de connaissances
Une compréhension de base des opérations d'E/S de fichiers en C# sera bénéfique. Une connaissance des concepts de présentation (diapositives et cadres, par exemple) vous aidera également à mieux assimiler le contenu.

## Configuration d'Aspose.Slides pour .NET
L'ajout de sous-titres aux vidéos de présentation devient un jeu d'enfant avec Aspose.Slides pour .NET. Voici comment le configurer :

### Informations d'installation
Installez Aspose.Slides en utilisant l’une de ces méthodes :

**.NET CLI**
```bash
dotnet add package Aspose.Slides
```

**Console du gestionnaire de paquets**
```powershell
Install-Package Aspose.Slides
```

**Interface utilisateur du gestionnaire de packages NuGet**
Recherchez « Aspose.Slides » et installez directement la dernière version.

### Étapes d'acquisition de licence
- **Essai gratuit**: Commencez par télécharger un essai gratuit à partir de [Site Web d'Aspose](https://releases.aspose.com/slides/net/).
- **Permis temporaire**: Obtenez une licence temporaire si vous avez besoin de plus de temps pour évaluer.
- **Achat**: Pour une utilisation continue, achetez une licence via [Portail d'achat d'Aspose](https://purchase.aspose.com/buy).

### Initialisation et configuration de base
Une fois installée, importez la bibliothèque dans votre projet :

```csharp
using Aspose.Slides;
```

Initialiser un nouveau `Presentation` objet pour commencer à travailler avec des présentations.

## Guide de mise en œuvre
Cette section vous guidera dans l'ajout de sous-titres aux images vidéo, ainsi que dans leur extraction ou leur suppression. Chaque fonctionnalité est décrite en détail ci-dessous.

### Fonctionnalité 1 : Ajouter des sous-titres à une image vidéo

#### Aperçu
Cette fonctionnalité permet d'insérer des sous-titres à partir d'un fichier externe (comme VTT) dans une image vidéo, améliorant ainsi l'accessibilité pour votre public.

#### Étapes de mise en œuvre
**Étape 1 : Préparez vos fichiers**
Assurez-vous d'avoir la vidéo (`sample_bunny.mp4`) et les fichiers de pistes de légende (`bunny.vtt`).

```csharp
string mediaFile = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "sample_bunny.mp4");
string trackFile = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "bunny.vtt");
```

**Étape 2 : ajouter une vidéo à la présentation**
Créer un `Presentation` objet et ajoutez votre vidéo.

```csharp
using (Presentation pres = new Presentation())
{
    IVideo video = pres.Videos.AddVideo(File.ReadAllBytes(mediaFile));
    var videoFrame = pres.Slides[0].Shapes.AddVideoFrame(0, 0, 100, 100, video);
```

**Étape 3 : Ajouter une piste de sous-titres**
Joignez votre fichier de piste de sous-titres à l’image vidéo.

```csharp
videoFrame.CaptionTracks.Add("New track", trackFile);
pres.Save(Path.Combine("YOUR_OUTPUT_DIRECTORY", "VideoCaptionAdd_out.pptx"), SaveFormat.Pptx);
}
```

#### Paramètres et objectifs de la méthode
- `Presentation`: Représente une présentation PowerPoint.
- `IVideo` et `IVideoFrame`: Représente respectivement le contenu vidéo et son cadre dans les diapositives.
- `captionTracks.Add()`: Ajoute des légendes à la piste spécifiée.

### Fonctionnalité 2 : Extraire et supprimer les sous-titres d'une image vidéo

#### Aperçu
Une fois les sous-titres ajoutés, il peut arriver que vous ayez besoin de les extraire ou de les supprimer. Cette fonctionnalité vous explique comment réaliser ces deux tâches efficacement.

#### Étapes de mise en œuvre
**Étape 1 : Charger la présentation**
Ouvrez la présentation contenant votre vidéo avec des sous-titres.

```csharp
string outAddPath = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "VideoCaptionAdd_out.pptx");
using (Presentation pres = new Presentation(outAddPath))
{
    IVideoFrame videoFrame = pres.Slides[0].Shapes[0] as VideoFrame;
```

**Étape 2 : Extraire les sous-titres**
Extraire les données binaires des légendes et les enregistrer dans un fichier.

```csharp
if (videoFrame != null)
{
    foreach (var captionTrack in videoFrame.CaptionTracks) 
    {
        File.WriteAllBytes(Path.Combine("YOUR_OUTPUT_DIRECTORY", "Caption_out.vtt"), captionTrack.BinaryData);
    }
```

**Étape 3 : supprimer les sous-titres**
Effacer toutes les légendes du VideoFrame.

```csharp
videoFrame.CaptionTracks.Clear();
pres.Save(Path.Combine("YOUR_OUTPUT_DIRECTORY", "VideoCaptionRemove_out.pptx"), SaveFormat.Pptx);
}
```

#### Paramètres et objectifs de la méthode
- `BinaryData`: Représente les données de légende au format binaire.
- `CaptionTracks.Clear()`: Supprime toutes les légendes de l'image vidéo.

## Applications pratiques
L'intégration de sous-titres vidéo peut considérablement améliorer vos présentations. Voici quelques exemples concrets :

1. **Contenu éducatif**:Améliorer la compréhension des élèves malentendants ou de ceux qui apprennent une deuxième langue.
2. **Formation en entreprise**:Assurer la clarté et la rétention des informations au sein d’équipes diverses.
3. **Conférences internationales**:Adaptez votre contenu aux locuteurs non natifs en fournissant des sous-titres localisés.
4. **Radiodiffusion publique**: Améliorer l’accessibilité pour un public plus large, y compris les malentendants.

## Considérations relatives aux performances
Lorsque vous travaillez avec des données vidéo dans .NET à l'aide d'Aspose.Slides :
- **Optimiser l'utilisation de la mémoire**: Gérez efficacement la mémoire en éliminant les ressources rapidement après utilisation.
- **Rationaliser les opérations d'E/S**:Réduisez les opérations de lecture/écriture de fichiers pour améliorer les performances.
- **Meilleures pratiques pour la gestion de la mémoire .NET**: Utiliser `using` instructions et assurez-vous que les objets sont déréférencés lorsqu'ils ne sont plus nécessaires.

## Conclusion
En maîtrisant ces fonctionnalités, vous pouvez améliorer considérablement la qualité de vos présentations. La possibilité d'ajouter ou de supprimer des sous-titres aux images vidéo rend le contenu plus accessible et assure une touche professionnelle à tous vos supports de présentation.

Explorez davantage en intégrant Aspose.Slides à d'autres systèmes et en expérimentant des fonctionnalités supplémentaires offertes par la bibliothèque.

## Section FAQ
**Q1 : Comment garantir la compatibilité des fichiers de sous-titres ?**
A1 : Utilisez le format VTT standard pour les sous-titres afin de garantir une large compatibilité entre les plateformes.

**Q2 : Puis-je ajouter plusieurs sous-titres à une seule image vidéo ?**
A2 : Oui, vous pouvez gérer plusieurs pistes en parcourant le `CaptionTracks` collection.

**Q3 : Quelles sont les erreurs courantes lors de l’ajout de sous-titres ?**
A3 : Assurez-vous que les chemins d'accès sont correctement définis et que les fichiers existent. Vérifiez les problèmes d'autorisations lors des opérations sur les fichiers.

**Q4 : Comment résoudre les problèmes de sous-titres manquants dans les présentations ?**
A4 : Vérifiez que la piste de sous-titres a été ajoutée correctement et enregistrée avec la présentation.

**Q5 : Existe-t-il des limites quant à la taille des vidéos ou à la longueur des sous-titres ?**
A5 : Bien qu'Aspose.Slides gère efficacement les fichiers volumineux, pensez à optimiser les médias pour les performances.

## Ressources
- **Documentation**: [Documentation Aspose.Slides](https://reference.aspose.com/slides/net/)
- **Télécharger la bibliothèque**: [Dernières sorties](https://releases.aspose.com/slides/net/)
- **Licence d'achat**: [Acheter maintenant](https://purchase.aspose.com/buy)
- **Essai gratuit**: [Démarrer l'essai gratuit](https://releases.aspose.com/slides/net/)
- **Permis temporaire**: [Obtenir un permis temporaire](https://purchase.aspose.com/temporary-license/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}