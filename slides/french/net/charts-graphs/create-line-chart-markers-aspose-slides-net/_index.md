---
"date": "2025-04-15"
"description": "Apprenez à créer des graphiques en courbes avec des marqueurs avec Aspose.Slides pour .NET. Ce guide étape par étape couvre la configuration, la création et la personnalisation des graphiques."
"title": "Comment créer un graphique linéaire avec des marqueurs en C# avec Aspose.Slides pour .NET"
"url": "/fr/net/charts-graphs/create-line-chart-markers-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment créer un graphique linéaire avec des marqueurs en C# avec Aspose.Slides pour .NET

## Introduction
La création de graphiques linéaires visuellement attrayants et informatifs est essentielle pour une présentation efficace des données en C#. **Aspose.Slides pour .NET** Simplifie l'ajout de graphiques professionnels, y compris ceux avec marqueurs. Ce tutoriel vous guidera dans la création d'un graphique en courbes avec marqueurs par défaut à l'aide d'Aspose.Slides pour .NET.

Dans ce tutoriel, vous apprendrez :
- Configuration de votre environnement pour utiliser Aspose.Slides pour .NET.
- Création et personnalisation d'une présentation avec un graphique linéaire incluant des marqueurs.
- Configuration des propriétés du graphique telles que les catégories, les séries et les points de données.
- Enregistrement du fichier de présentation final.

Commençons par passer en revue les prérequis nécessaires avant de mettre en œuvre notre solution.

## Prérequis
Avant de commencer, assurez-vous d’avoir les éléments suivants :
- **Bibliothèques requises :** Aspose.Slides pour .NET installé dans votre environnement de développement via NuGet.
- **Configuration requise pour l'environnement :** Un environnement de développement C# fonctionnel comme Visual Studio et le framework .NET installé sur votre machine.
- **Prérequis en matière de connaissances :** Compréhension de base de la programmation C# et familiarité avec la création de présentations par programmation.

## Configuration d'Aspose.Slides pour .NET
### Informations d'installation
Pour commencer à utiliser Aspose.Slides pour .NET, ajoutez-le à votre projet via l'une des méthodes suivantes :

**Utilisation de .NET CLI :**
```bash
dotnet add package Aspose.Slides
```

**Via la console du gestionnaire de packages dans Visual Studio :**
```powershell
Install-Package Aspose.Slides
```

**Interface utilisateur du gestionnaire de packages NuGet :**
- Ouvrez votre solution dans Visual Studio.
- Accédez à « Gérer les packages NuGet pour la solution… »
- Recherchez « Aspose.Slides » et installez la dernière version.

### Acquisition de licence
Avant d'utiliser Aspose.Slides, obtenez une licence d'essai ou achetez :
1. **Essai gratuit :** Visite [Page d'essai gratuite d'Aspose](https://releases.aspose.com/slides/net/) pour démarrer rapidement.
2. **Licence temporaire :** Pour un accès étendu, visitez le [Page de licence temporaire](https://purchase.aspose.com/temporary-license/).
3. **Achat:** Pour utiliser Aspose.Slides en production, achetez une licence sur [Achat Aspose](https://purchase.aspose.com/buy).

### Initialisation de base
Après avoir configuré votre projet et obtenu les licences nécessaires, initialisez Aspose.Slides comme suit :
```csharp
using Aspose.Slides;
// Créer une instance de la classe Presentation
Presentation pres = new Presentation();
```
Maintenant que nous avons configuré notre environnement, passons à la création d'un graphique linéaire avec des marqueurs.

## Guide de mise en œuvre
### Création du graphique linéaire avec des marqueurs
Dans cette section, vous apprendrez chaque étape nécessaire pour créer et configurer un graphique linéaire avec des marqueurs par défaut dans votre présentation à l'aide d'Aspose.Slides pour .NET.

#### Étape 1 : Créer un objet de présentation
Commencez par créer une instance du `Presentation` classe:
```csharp
using (Presentation pres = new Presentation())
{
    ISlide slide = pres.Slides[0];
```
Ici, nous accédons à la première diapositive d’une présentation nouvellement créée.

#### Étape 2 : Ajouter un graphique linéaire avec des marqueurs
Ensuite, ajoutez un graphique linéaire avec des marqueurs à votre diapositive :
```csharp
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
```
Ce code ajoute un nouveau graphique de type `LineWithMarkers` aux coordonnées `(10, 10)` avec dimensions `400x400`.

#### Étape 3 : Effacer les séries et catégories existantes
Avant d’ajouter des données, effacez toutes les séries ou catégories existantes :
```csharp
chart.ChartData.Series.Clear();
chart.ChartData.Categories.Clear();
```
Cela garantit que notre graphique démarre sur une base vierge.

#### Étape 4 : Configurer le classeur de données graphiques
Accéder au `ChartDataWorkbook` pour gérer les données de votre graphique :
```csharp
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
```
Cet objet est essentiel pour gérer les cellules contenant des données de série et de catégorie.

#### Étape 5 : Ajouter des séries et des catégories
Ajoutez une nouvelle série au graphique et remplissez-la avec des points de données :
```csharp
chart.ChartData.Series.Add(fact.GetCell(0, 0, 1, "Series 1"), chart.Type);
IChartSeries series = chart.ChartData.Series[0];

// Définir les catégories et les points de données correspondants
chart.ChartData.Categories.Add(fact.GetCell(0, 1, 0, "C1"));
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 1, 1, 24));
chart.ChartData.Categories.Add(fact.GetCell(0, 2, 0, "C2"));
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 2, 1, 23));
chart.ChartData.Categories.Add(fact.GetCell(0, 3, 0, "C3"));
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 3, 1, -10));
chart.ChartData.Categories.Add(fact.GetCell(0, 4, 0, "C4"));

// Ajoutez un point de données nul pour illustrer la gestion des valeurs manquantes
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 4, 1, (double?)null));
```
Ici, nous remplissons le graphique avec des catégories et des données de séries correspondantes. Remarquez comment `null` la valeur est traitée comme une démonstration.

#### Étape 6 : Ajouter une autre série
Répétez le processus pour ajouter une autre série :
```csharp
chart.ChartData.Series.Add(fact.GetCell(0, 0, 2, "Series 2"), chart.Type);
IChartSeries series2 = chart.ChartData.Series[1];

series2.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 1, 2, 30));
series2.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 2, 2, 10));
series2.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 3, 2, 60));
series2.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 4, 2, 40));
```

#### Étape 7 : Activer et configurer la légende
Activer la légende du graphique pour améliorer la lisibilité :
```csharp
chart.HasLegend = true;
chart.Legend.Overlay = false;
```
Cela garantit que la légende est visible et non superposée sur le graphique.

#### Étape 8 : Enregistrer la présentation
Enfin, enregistrez votre présentation avec le graphique nouvellement ajouté :
```csharp
pres.Save("DefaultMarkersInChart.pptx");
}
```
### Conseils de dépannage
- **Erreurs de liaison de données :** Assurez-vous que les points de données correspondent correctement aux catégories.
- **Le graphique ne s'affiche pas :** Vérifiez que `chart.HasLegend` et d'autres propriétés sont définies de manière appropriée.

## Applications pratiques
1. **Rapports d'activité :** Utilisez des graphiques linéaires avec des marqueurs pour suivre les performances des ventes au fil du temps, en montrant les tendances des revenus mensuels.
2. **Analyse financière :** Visualisez les mouvements du cours des actions avec des marqueurs par défaut pour mettre en évidence les pics et les creux.
3. **Recherche scientifique :** Présenter les résultats expérimentaux lorsque les points de données nécessitent une démarcation claire pour l’analyse.

## Considérations relatives aux performances
- Optimisez en limitant le nombre de séries de données et de catégories lorsque vous traitez de grands ensembles de données.
- Utilisez des techniques de gestion de la mémoire telles que la suppression rapide des objets dans .NET pour réduire l’utilisation des ressources.

## Conclusion
Dans ce tutoriel, vous avez appris à créer un graphique en courbes avec des marqueurs avec Aspose.Slides pour .NET. En suivant ces étapes, vous pourrez enrichir vos présentations avec des graphiques détaillés et professionnels. N'hésitez pas à explorer d'autres fonctionnalités d'Aspose.Slides pour enrichir vos diaporamas.

### Prochaines étapes
- Expérimentez avec différents types de graphiques disponibles dans Aspose.Slides.
- Personnalisez l'apparence des graphiques pour un meilleur impact visuel.
- Explorez la documentation supplémentaire sur Aspose.Slides pour des fonctionnalités plus avancées.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}