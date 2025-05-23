---
"date": "2025-04-16"
"description": "Apprenez à transformer des formes standard en croquis avec Aspose.Slides pour .NET. Ce guide couvre les techniques de configuration, de mise en œuvre et d'enregistrement."
"title": "Créez des formes esquissées dans .NET avec Aspose.Slides &#58; un guide étape par étape"
"url": "/fr/net/shapes-text-frames/create-sketches-asposeslides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Créer des formes esquissées dans .NET avec Aspose.Slides : un guide étape par étape

## Introduction

Améliorez vos présentations en transformant des formes simples en croquis attrayants grâce à Aspose.Slides pour .NET. Ce guide vous aidera à créer facilement des croquis, parfaits pour vos présentations professionnelles ou vos supports pédagogiques.

**Ce que vous apprendrez :**
- Configuration d'Aspose.Slides pour .NET
- Ajouter et modifier des formes dans vos diapositives
- Application d'effets d'esquisse aux formes
- Sauvegarde des présentations et des images

Prêt à commencer ? Assurez-vous d'avoir tout le nécessaire pour suivre !

## Prérequis

Avant de commencer, assurez-vous d’avoir les outils et les connaissances nécessaires :

### Bibliothèques et dépendances requises

Vous aurez besoin de :
- .NET SDK (version 5.0 ou ultérieure recommandée)
- Visual Studio ou tout autre IDE compatible
- Bibliothèque Aspose.Slides pour .NET

### Configuration requise pour l'environnement

Assurez-vous que votre environnement de développement est prêt en installant les bibliothèques requises à l’aide de l’une de ces méthodes :

**Utilisation de .NET CLI :**
```bash
dotnet add package Aspose.Slides
```

**Utilisation du gestionnaire de paquets :**
```powershell
Install-Package Aspose.Slides
```

**Interface utilisateur du gestionnaire de packages NuGet :**
Recherchez « Aspose.Slides » et installez la dernière version.

### Prérequis en matière de connaissances
- Compréhension de base de la programmation C#.
- Connaissance de l'environnement de développement .NET (Visual Studio).

## Configuration d'Aspose.Slides pour .NET

Pour commencer, configurez Aspose.Slides dans votre projet en suivant ces étapes :
1. **Installation:** Utilisez l’une des méthodes d’installation mentionnées ci-dessus pour ajouter Aspose.Slides à votre projet.
2. **Acquisition de licence :**
   - Commencez par un [essai gratuit](https://releases.aspose.com/slides/net/) ou obtenir une licence temporaire pour toutes les fonctionnalités.
   - Pour acheter, visitez le [page d'achat](https://purchase.aspose.com/buy).
3. **Initialisation de base :**
   ```csharp
   using Aspose.Slides;
   
   Presentation pres = new Presentation();
   // Votre code pour manipuler les diapositives va ici.
   ```

## Guide de mise en œuvre

Une fois tout configuré, implémentons la fonction de forme esquissée.

### Ajout et modification de formes

#### Aperçu

Dans cette section, nous allons ajouter une forme automatique de type rectangle sur une diapositive et configurer ses propriétés pour créer un effet esquissé.

**Ajout d'une forme rectangulaire**

Commencez par créer une nouvelle instance de présentation et ajoutez une forme rectangulaire :
```csharp
using Aspose.Slides;
using Aspose.Slides.Export;

string outPptxFile = Path.Combine("YOUR_OUTPUT_DIRECTORY", "SketchedShapes_out.pptx");
string outPngFile = Path.Combine("YOUR_OUTPUT_DIRECTORY", "SketchedShapes_out.png");

using (Presentation pres = new Presentation())
{
    // Ajouter une forme automatique de type Rectangle sur la première diapositive
    IAutoShape shape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 20, 20, 300, 150);
}
```

#### Définition du format de remplissage

Pour lui donner un aspect esquissé, supprimez tout remplissage de la forme :
```csharp
shape.FillFormat.FillType = FillType.NoFill;
```

### Application d'effets d'esquisse aux formes

#### Aperçu

Ensuite, transformez le rectangle en un croquis à main levée.

**Transformer une forme en esquisse**

Utilisez le `SketchFormat` propriété pour appliquer un effet de gribouillage :
```csharp
// Transformez la forme en un croquis de style à main levée (Scribble)
shape.LineFormat.SketchFormat.SketchType = LineSketchType.Scribble;
```

### Sauvegarde des présentations et des images

Enfin, enregistrez votre travail à la fois sous forme de fichier de présentation et d’image.

**Enregistrer au format PPTX**
```csharp
// Enregistrer la présentation dans un fichier PPTX
pres.Save(outPptxFile, SaveFormat.Pptx);
```

**Enregistrer au format PNG**
```csharp
// Enregistrez la diapositive sous forme de fichier image au format PNG
pres.Slides[0].GetThumbnail(4/3f, 4/3f).Save(outPngFile, System.Drawing.Imaging.ImageFormat.Png);
```

### Conseils de dépannage
- **Erreurs courantes :** Assurez-vous que tous les chemins sont correctement spécifiés et vérifiez s'il y a des problèmes d'installation de bibliothèque.
- **Problèmes de performances :** Optimisez les paramètres de résolution d'image si les performances sont lentes.

## Applications pratiques

Aspose.Slides .NET offre des solutions polyvalentes pour divers scénarios :
1. **Contenu éducatif :** Créez des diapositives pédagogiques attrayantes avec des diagrammes esquissés pour simplifier des concepts complexes.
2. **Présentations d'affaires :** Améliorez l’attrait visuel des présentations avec des éléments uniques dessinés à la main.
3. **Projets créatifs :** Utilisez des effets d’esquisse dans des récits créatifs ou des projets artistiques.

Les possibilités d'intégration incluent la combinaison des fonctionnalités d'Aspose.Slides avec d'autres applications .NET pour des fonctionnalités améliorées.

## Considérations relatives aux performances
- **Optimiser les ressources :** Minimisez l’utilisation des ressources en ajustant les résolutions d’image et la complexité des diapositives.
- **Gestion de la mémoire :** Assurez une gestion efficace de la mémoire en éliminant correctement les objets de présentation après utilisation.

**Meilleures pratiques :**
- Jeter le `Presentation` objet dans un `using` bloquer pour gérer efficacement les ressources.
- Mettez régulièrement à jour Aspose.Slides pour bénéficier des améliorations de performances.

## Conclusion

En suivant ce guide, vous avez appris à transformer des formes simples en croquis avec Aspose.Slides pour .NET. Cette fonctionnalité peut améliorer considérablement la qualité visuelle de vos présentations et projets créatifs.

Pour explorer davantage ce qu'Aspose.Slides a à offrir, envisagez de plonger plus profondément dans sa documentation complète et d'expérimenter d'autres fonctionnalités.

**Prochaines étapes :**
- Expérimentez avec différents types de croquis.
- Découvrez des transformations de formes supplémentaires disponibles dans Aspose.Slides.

Prêt à créer des formes esquissées uniques ? Essayez d'intégrer cette solution à votre prochain projet !

## Section FAQ

1. **Comment installer Aspose.Slides pour .NET ?**
   - Utilisez les commandes d’installation fournies via .NET CLI, Package Manager ou NuGet Package Manager UI.

2. **Puis-je appliquer des effets d’esquisse à d’autres formes ?**
   - Oui, la même méthode peut être appliquée à différents types de formes pris en charge par Aspose.Slides.

3. **Quels formats de fichiers Aspose.Slides prend-il en charge ?**
   - Il prend en charge plusieurs formats, notamment PPTX, PDF et des images comme PNG.

4. **Y a-t-il des frais de licence pour Aspose.Slides ?**
   - Un essai gratuit est disponible ; achetez une licence pour des fonctionnalités et une utilisation étendues.

5. **Puis-je intégrer Aspose.Slides avec d’autres applications ?**
   - Oui, il s’intègre bien avec divers systèmes et plates-formes basés sur .NET.

## Ressources
- [Documentation](https://reference.aspose.com/slides/net/)
- [Télécharger la bibliothèque](https://releases.aspose.com/slides/net/)
- [Licence d'achat](https://purchase.aspose.com/buy)
- [Essai gratuit](https://releases.aspose.com/slides/net/)
- [Permis temporaire](https://purchase.aspose.com/temporary-license/)
- [Forum d'assistance](https://forum.aspose.com/c/slides/11)

En exploitant ces ressources, vous pourrez améliorer vos compétences et explorer tout le potentiel d'Aspose.Slides pour .NET. Bon codage !

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}