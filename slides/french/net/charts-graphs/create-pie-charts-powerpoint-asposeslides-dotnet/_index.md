---
"date": "2025-04-15"
"description": "Apprenez à automatiser la création de graphiques à secteurs dans PowerPoint avec Aspose.Slides pour .NET grâce à ce guide complet. Améliorez vos présentations sans effort."
"title": "Comment créer et personnaliser des graphiques à secteurs dans PowerPoint avec Aspose.Slides pour .NET (Guide étape par étape)"
"url": "/fr/net/charts-graphs/create-pie-charts-powerpoint-asposeslides-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment créer et personnaliser des graphiques à secteurs dans PowerPoint avec Aspose.Slides pour .NET

## Introduction
Créer des présentations attrayantes et riches en données est essentiel pour une communication efficace, notamment lorsqu'il s'agit d'ensembles de données complexes. Automatiser la création de graphiques, comme les camemberts, dans PowerPoint avec .NET permet de gagner du temps et de garantir la précision. Ce guide étape par étape explique comment créer et personnaliser des camemberts dans PowerPoint avec Aspose.Slides pour .NET, facilitant ainsi l'intégration de visualisations de données dynamiques dans vos présentations.

### Ce que vous apprendrez
- Configurer Aspose.Slides pour .NET dans votre projet
- Instanciation d'un nouvel objet de présentation
- Ajout et configuration de graphiques à secteurs dans les diapositives
- Personnalisation des titres, des étiquettes, des catégories et des séries de graphiques
- Bonnes pratiques pour enregistrer et exporter la présentation

Commençons par configurer votre environnement de développement.

## Prérequis
Avant de commencer, assurez-vous d’avoir les prérequis suivants :

### Bibliothèques requises
- **Aspose.Slides pour .NET**Une bibliothèque puissante pour travailler avec des présentations PowerPoint par programmation. Assurez-vous d'utiliser une version d'Aspose.Slides pour .NET compatible avec les exigences de votre projet.

### Configuration requise pour l'environnement
- Visual Studio : la dernière version est recommandée, mais n’importe quelle édition récente suffira.
- .NET Framework ou .NET Core/5+/6+ : selon votre environnement de développement et les besoins de votre application.

### Prérequis en matière de connaissances
- Compréhension de base du langage de programmation C#
- Familiarité avec les concepts de programmation orientée objet
- Une certaine expérience de travail avec les bibliothèques .NET peut être bénéfique, mais pas obligatoire

Une fois ces prérequis vérifiés, passons à la configuration d'Aspose.Slides pour votre projet.

## Configuration d'Aspose.Slides pour .NET
Pour intégrer Aspose.Slides dans votre application .NET, suivez ces étapes d'installation :

**.NET CLI**
```bash
dotnet add package Aspose.Slides
```

**Gestionnaire de paquets**
```powershell
Install-Package Aspose.Slides
```

**Interface utilisateur du gestionnaire de packages NuGet**
Recherchez « Aspose.Slides » et installez la dernière version.

### Acquisition de licence
Aspose.Slides est un produit commercial, mais vous pouvez commencer par un essai gratuit ou demander une licence temporaire pour tester ses fonctionnalités sans limitations. Pour une utilisation continue, envisagez de souscrire un abonnement :
- **Essai gratuit**: Commencez par télécharger depuis [Page des sorties d'Aspose](https://releases.aspose.com/slides/net/).
- **Permis temporaire**: Demandez-en un via [ce lien](https://purchase.aspose.com/temporary-license/) pour une évaluation approfondie.
- **Achat**:Pour un accès complet, visitez le [page d'achat](https://purchase.aspose.com/buy).

Après avoir acquis une licence, initialisez-la dans votre application pour supprimer les limitations d'essai.

```csharp
// Exemple d'initialisation d'Aspose.Slides Licence
Aspose.Slides.License license = new Aspose.Slides.License();
license.SetLicense("path_to_license_file.lic");
```

## Guide de mise en œuvre
Maintenant que nous avons configuré notre environnement, commençons à mettre en œuvre le processus de création de graphique à secteurs.

### Créer une nouvelle présentation
Commencez par créer une nouvelle instance du `Presentation` classe, qui représente votre fichier PowerPoint :

```csharp
using (Presentation presentation = new Presentation())
{
    // Le reste de votre code ira ici.
}
```

Cette étape initialise une présentation vide dans laquelle vous pouvez ajouter des diapositives et des formes.

### Accéder aux diapositives
Accédez à la première diapositive pour ajouter un diagramme circulaire. Il s'agit généralement de la diapositive par défaut créée à chaque nouvelle présentation :

```csharp
ISlide slide = presentation.Slides[0];
```

Maintenant, passons à l’ajout de notre graphique à secteurs.

### Ajout d'un graphique à secteurs
Utiliser `AddChart` méthode sur votre objet slide pour insérer un graphique à secteurs aux coordonnées spécifiées (x, y) et aux dimensions (largeur, hauteur) :

```csharp
IChart chart = slide.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
```

### Configuration du titre du graphique
Définissez un titre pour votre graphique afin de fournir un contexte. `TextFrameForOverriding` vous permet de personnaliser son contenu et sa mise en forme :

```csharp
chart.ChartTitle.AddTextFrameForOverriding("Sample Title");
chart.ChartTitle.TextFrameForOverriding.TextFrameFormat.CenterText = NullableBool.True;
chart.ChartTitle.Height = 20;
chart.HasTitle = true;
```

Ces paramètres centrent le texte du titre et définissent une hauteur appropriée pour la lisibilité.

### Configuration des étiquettes de données
Configurez les étiquettes de données pour afficher les valeurs dans votre graphique à secteurs, ce qui permet aux spectateurs de comprendre plus facilement la contribution de chaque segment :

```csharp
chart.ChartData.Series[0].Labels.DefaultDataLabelFormat.ShowValue = true;
```

Cette ligne modifie la première série pour afficher les valeurs de ses points de données directement sur les tranches du graphique.

### Ajout de catégories et de séries
Effacez toutes les séries ou catégories existantes, puis définissez-en de nouvelles avec vos points de données :

```csharp
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;

// Effacer les données préexistantes
chart.ChartData.Series.Clear();
chart.ChartData.Categories.Clear();

// Ajouter de nouvelles catégories
chart.ChartData.Categories.Add(fact.GetCell(0, 1, 0, "First Qtr"));
chart.ChartData.Categories.Add(fact.GetCell(0, 2, 0, "2nd Qtr"));
chart.ChartData.Categories.Add(fact.GetCell(0, 3, 0, "3rd Qtr"));

// Ajouter une nouvelle série avec des points de données
IChartSeries series = chart.ChartData.Series.Add(fact.GetCell(0, 0, 1, "Series 1"), chart.Type);
series.DataPoints.AddDataPointForPieSeries(fact.GetCell(0, 1, 1, 20));
series.DataPoints.AddDataPointForPieSeries(fact.GetCell(0, 2, 1, 50));
series.DataPoints.AddDataPointForPieSeries(fact.GetCell(0, 3, 1, 30));

// Diversifier les couleurs pour chaque tranche
series.ParentSeriesGroup.IsColorVaried = true;
```

Cette configuration vous permet de personnaliser les catégories (par exemple, les trimestres) et les points de données de série (par exemple, les pourcentages).

### Enregistrer la présentation
Enfin, enregistrez votre présentation dans un répertoire spécifié :

```csharp
string outputDir = "YOUR_OUTPUT_DIRECTORY";
presentation.Save(outputDir + "/Pie.pptx", Aspose.Slides.Export.SaveFormat.Pptx);
```

Cette étape garantit que votre travail est préservé et accessible pour une utilisation ou un partage ultérieur.

## Applications pratiques
Voici quelques applications concrètes de la création de graphiques à secteurs dans PowerPoint à l'aide d'Aspose.Slides :
1. **Rapports financiers**:Visualisez les bénéfices trimestriels avec des catégories distinctes représentant différentes unités commerciales.
2. **Analyse de marché**: Présentez la répartition des parts de marché entre les concurrents dans une catégorie de produits.
3. **Résultats de l'enquête**:Afficher les pourcentages de réponses aux enquêtes de satisfaction client.

Ces applications démontrent la polyvalence et la puissance de la génération dynamique de graphiques pour divers scénarios professionnels.

## Considérations relatives aux performances
Lorsque vous travaillez avec de grands ensembles de données ou des présentations complexes, tenez compte de ces conseils d’optimisation :
- Limitez les points de données aux informations essentielles pour éviter l’encombrement.
- Réutilisez les objets graphiques lorsque cela est possible au lieu d'en créer de nouveaux.
- Surveillez l'utilisation de la mémoire lorsque vous traitez des fichiers de présentation volumineux.

Une gestion efficace des ressources et une conception réfléchie peuvent considérablement améliorer les performances et l’expérience utilisateur.

## Conclusion
Vous maîtrisez désormais les bases de la création et de la configuration de graphiques à secteurs dans PowerPoint avec Aspose.Slides pour .NET. Ce guide vous explique comment configurer votre projet, ajouter et personnaliser des graphiques, et enregistrer efficacement votre travail.

### Prochaines étapes
- Expérimentez avec différents types de graphiques disponibles dans Aspose.Slides.
- Explorez l’intégration de cette fonctionnalité dans des applications ou des services Web.
- Partagez vos créations pour démontrer la puissance de la visualisation automatisée des données.

## Section FAQ
1. **Puis-je utiliser Aspose.Slides gratuitement ?**
   - Oui, vous pouvez commencer par un essai gratuit. Pour une utilisation prolongée, pensez à acheter une licence.
2. **Comment personnaliser les couleurs des graphiques dans les graphiques à secteurs ?**
   - Utiliser `IsColorVaried` sur le `ParentSeriesGroup` pour permettre des couleurs de tranches variées.
3. **Que faire si ma présentation est lente lors de la gestion de nombreux graphiques ?**
   - Optimisez en réduisant la complexité des données et en réutilisant les objets graphiques lorsque cela est possible.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}