---
"date": "2025-04-15"
"description": "Découvrez comment automatiser la création de graphiques à secteurs dans les présentations .NET avec Aspose.Slides, améliorant ainsi la visualisation des données sans effort."
"title": "Comment créer et personnaliser des graphiques à secteurs dans des présentations .NET avec Aspose.Slides"
"url": "/fr/net/charts-graphs/create-style-pie-charts-net-asposeslides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment créer et personnaliser des graphiques à secteurs dans des présentations .NET avec Aspose.Slides

## Introduction
Créer des présentations engageantes et informatives est essentiel pour une communication efficace, qu'il s'agisse de présenter des données au travail ou de présenter les dernières conclusions de votre projet. Les diagrammes circulaires sont un excellent moyen de visualiser les données, car ils peuvent représenter succinctement les parties d'un tout. Cependant, la création manuelle de ces diagrammes dans un logiciel de présentation comme PowerPoint peut être chronophage et manquer de flexibilité pour des mises à jour dynamiques.

C'est là qu'Aspose.Slides pour .NET entre en jeu. Cette bibliothèque complète vous permet de créer, modifier et styliser des présentations par programmation, ce qui en fait un outil précieux pour les développeurs qui souhaitent automatiser leur flux de travail et garantir la cohérence de leurs présentations.

Dans ce tutoriel, nous découvrirons comment utiliser Aspose.Slides pour .NET pour créer et personnaliser des graphiques à secteurs dans vos présentations. Vous apprendrez à :
- **Créer une présentation et accéder aux diapositives**
- **Ajouter et configurer des graphiques à secteurs**
- **Personnaliser les données et les séries des graphiques**
- **Secteurs de style de graphique à secteurs**
- **Ajouter des étiquettes personnalisées**
- **Configurer les propriétés d'affichage et enregistrer la présentation**

Prêt à créer facilement de superbes diagrammes circulaires ? C'est parti !

## Prérequis
Avant de commencer, assurez-vous d’avoir la configuration suivante en place :

### Bibliothèques requises
- Aspose.Slides pour .NET (version 21.11 ou ultérieure recommandée)

### Configuration de l'environnement
- Un environnement de développement exécutant .NET Framework ou .NET Core/5+/6+
- Un éditeur de code tel que Visual Studio

### Prérequis en matière de connaissances
- Compréhension de base de la programmation C#
- Familiarité avec les concepts orientés objet

## Configuration d'Aspose.Slides pour .NET
Pour commencer, vous devez installer la bibliothèque Aspose.Slides. Vous pouvez le faire de l'une des manières suivantes :

**.NET CLI**
```bash
dotnet add package Aspose.Slides
```

**Console du gestionnaire de paquets**
```powershell
Install-Package Aspose.Slides
```

**Interface utilisateur du gestionnaire de packages NuGet**
- Ouvrez votre projet dans Visual Studio.
- Accédez à « Outils » > « Gestionnaire de packages NuGet » > « Gérer les packages NuGet pour la solution ».
- Recherchez « Aspose.Slides » et installez la dernière version.

### Étapes d'acquisition de licence
Pour utiliser Aspose.Slides, vous pouvez commencer par un essai gratuit en téléchargeant une licence temporaire. Visitez [Site Web d'Aspose](https://purchase.aspose.com/temporary-license/) Pour l'obtenir. Pour une utilisation continue, pensez à acheter une licence complète.

### Initialisation et configuration de base
Une fois installé, initialisez la classe Presentation, qui représente votre fichier PPTX :

```csharp
using Aspose.Slides;

Presentation presentation = new Presentation();
```

## Guide de mise en œuvre
Nous décomposerons le processus de création d'un diagramme circulaire en sections faciles à gérer. Chaque section est conçue pour se concentrer sur une fonctionnalité spécifique, vous permettant ainsi d'approfondir progressivement vos connaissances.

### Créer une présentation et accéder aux diapositives
**Aperçu:** Commencez par créer une nouvelle présentation et accédez à sa première diapositive. Cela prépare le terrain pour l'ajout de graphiques et d'autres éléments.

```csharp
using Aspose.Slides;

public static void CreatePresentationAndAccessSlide()
{
    // Instancier une classe de présentation qui représente un fichier PPTX
    Presentation presentation = new Presentation();
    
    // Accéder à la première diapositive
    ISlide slides = presentation.Slides[0];
}
```

### Ajouter et configurer un graphique à secteurs
**Aperçu:** Apprenez à ajouter un graphique à secteurs à votre diapositive et à définir son titre pour le contexte.

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;

public static void AddAndConfigurePieChart()
{
    // Instancier une classe de présentation qui représente un fichier PPTX
    Presentation presentation = new Presentation();
    
    // Accéder à la première diapositive
    ISlide slides = presentation.Slides[0];
    
    // Ajouter un graphique avec des données par défaut à la diapositive
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // Titre du tableau de réglage
    chart.ChartTitle.AddTextFrameForOverriding("Sample Title");
    chart.ChartTitle.TextFrameForOverriding.TextFrameFormat.CenterText = NullableBool.True;
    chart.ChartTitle.Height = 20;
    chart.HasTitle = true;
}
```

### Personnaliser les données et les séries des graphiques
**Aperçu:** Personnalisez les catégories et séries de données en fonction de vos besoins spécifiques.

```csharp
using Aspose.Slides.Charts;

public static void CustomizeChartDataAndSeries()
{
    // Instancier une classe de présentation qui représente un fichier PPTX
    Presentation presentation = new Presentation();
    
    // Accéder à la première diapositive
    ISlide slides = presentation.Slides[0];
    
    // Ajouter un graphique avec des données par défaut à la diapositive
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // Définir la première série sur Afficher les valeurs
    chart.ChartData.Series[0].Labels.DefaultDataLabelFormat.ShowValue = true;
    
    // Définition de l'index de la feuille de données du graphique
    int defaultWorksheetIndex = 0;
    
    // Obtenir la feuille de calcul des données du graphique
    IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
    
    // Supprimer les séries et catégories générées par défaut
    chart.ChartData.Series.Clear();
    chart.ChartData.Categories.Clear();
    
    // Ajout de nouvelles catégories
    chart.ChartData.Categories.Add(fact.GetCell(0, 1, 0, "First Qtr"));
    chart.ChartData.Categories.Add(fact.GetCell(0, 2, 0, "2nd Qtr"));
    chart.ChartData.Categories.Add(fact.GetCell(0, 3, 0, "3rd Qtr"));
    
    // Ajout de nouvelles séries
    IChartSeries series = chart.ChartData.Series.Add(fact.GetCell(0, 0, 1, "Series 1"), chart.Type);
    
    // Les données de la série sont maintenant en cours de remplissage
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 1, 1, 20));
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, 50));
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, 30));
}
```

### Personnaliser les styles de secteurs des graphiques à secteurs
**Aperçu:** Stylisez les secteurs individuels de votre graphique à secteurs pour améliorer l'attrait visuel et mettre en valeur les points de données clés.

```csharp
using Aspose.Slides.Charts;
using System.Drawing;

public static void CustomizePieChartSectorStyles()
{
    // Instancier une classe de présentation qui représente un fichier PPTX
    Presentation presentation = new Presentation();
    
    // Accéder à la première diapositive
    ISlide slides = presentation.Slides[0];
    
    // Ajouter un graphique avec des données par défaut à la diapositive
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // Obtenir une série à partir d'un graphique
    IChartSeries series = chart.ChartData.Series[0];
    
    // Personnalisation des styles de secteur pour chaque point de données de la série
    IChartDataPoint point = series.DataPoints[0];
    point.Format.Fill.FillType = FillType.Solid;
    point.Format.Fill.SolidFillColor.Color = Color.Cyan;
    
    // Définition de la bordure du secteur
    point.Format.Line.FillFormat.FillType = FillType.Solid;
    point.Format.Line.FillFormat.SolidFillColor.Color = Color.Gray;
    point.Format.Line.Width = 3.0;
    point.Format.Line.Style = LineStyle.ThinThick;
    point.Format.Line.DashStyle = LineDashStyle.DashDot;

    IChartDataPoint point1 = series.DataPoints[1];
    point1.Format.Fill.FillType = FillType.Solid;
    point1.Format.Fill.SolidFillColor.Color = Color.Green;
    
    // Définition de la bordure du secteur
    point1.Format.Line.FillFormat.FillType = FillType.Solid;
    point1.Format.Line.FillFormat.SolidFillColor.Color = Color.Black;
    point1.Format.Line.Width = 2.0;
    point1.Format.Line.Style = LineStyle.Solid;

    IChartDataPoint point2 = series.DataPoints[2];
    point2.Format.Fill.FillType = FillType.Solid;
    point2.Format.Fill.SolidFillColor.Color = Color.Yellow;
    
    // Définition de la bordure du secteur
    point2.Format.Line.FillFormat.FillType = FillType.Solid;
    point2.Format.Line.FillFormat.SolidFillColor.Color = Color.Red;
    point2.Format.Line.Width = 2.0;
    point2.Format.Line.Style = LineStyle.Dot;
}
```

### Ajouter des étiquettes personnalisées au graphique à secteurs
**Aperçu:** Améliorez votre graphique à secteurs en ajoutant des étiquettes personnalisées pour une représentation plus claire des données.

```csharp
public static void AddCustomLabelsToPieChart(IChart chart)
{
    IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
    IChartSeries series = chart.ChartData.Series[0];

    foreach (IChartDataPoint point in series.DataPoints)
    {
        IDataLabel lbl = point.Label;
        lbl.TextFrameForOverriding.Text = $"{point.Value}";
        lbl.Position = LegendPositionType.Center; // Ajustez la position de l'étiquette selon vos besoins
    }
}
```

### Conclusion
Vous savez maintenant comment créer et personnaliser des graphiques à secteurs dans vos présentations .NET avec Aspose.Slides. Cette automatisation peut considérablement améliorer vos efforts de visualisation de données, vous faire gagner du temps et garantir la cohérence de vos présentations.

Pour explorer davantage les fonctionnalités d'Aspose.Slides pour .NET, envisagez de vous plonger dans des fonctionnalités supplémentaires telles que la création d'autres types de graphiques ou l'intégration d'éléments de conception plus complexes dans vos diapositives.

Bon codage !

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}