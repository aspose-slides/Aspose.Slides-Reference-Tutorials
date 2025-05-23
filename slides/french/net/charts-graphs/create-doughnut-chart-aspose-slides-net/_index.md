---
"date": "2025-04-15"
"description": "Apprenez à créer des graphiques en anneau dynamiques avec Aspose.Slides pour .NET. Suivez ce guide pour des instructions étape par étape, incluant la configuration et les fonctionnalités avancées."
"title": "Guide étape par étape &#58; Créer un graphique en anneau avec Aspose.Slides .NET | Graphiques"
"url": "/fr/net/charts-graphs/create-doughnut-chart-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Guide étape par étape : Créer un graphique en anneau avec Aspose.Slides .NET

## Introduction

Imaginez que vous devez présenter des résultats d'analyse de données à votre équipe ou à vos clients et que vous recherchez un moyen attrayant de visualiser ces informations. Découvrez le graphique en anneau : un outil polyvalent capable de transformer des chiffres bruts en informations facilement assimilables. Avec Aspose.Slides pour .NET, créer un graphique en anneau personnalisé dans vos diapositives de présentation est simple et efficace. Ce guide vous guidera dans l'utilisation d'Aspose.Slides pour créer un graphique en anneau attrayant, avec des configurations de séries personnalisées.

**Ce que vous apprendrez :**
- Configurer votre environnement de développement avec Aspose.Slides pour .NET
- Création et personnalisation de graphiques en anneau dans les présentations
- Implémentation de fonctionnalités avancées telles que les noms de catégories et les lignes de repère
- Optimisation des performances pour les grands ensembles de données

Plongeons dans les prérequis dont vous avez besoin pour commencer.

## Prérequis

Avant d'implémenter cette fonctionnalité, assurez-vous que votre environnement de développement est correctement configuré. Ce tutoriel suppose des connaissances de base en programmation .NET et une familiarité avec Visual Studio ou un IDE similaire.

### Bibliothèques et versions requises
- **Aspose.Slides pour .NET**: Assurez la compatibilité avec la dernière version en vérifiant leur [documentation officielle](https://reference.aspose.com/slides/net/).

### Configuration requise pour l'environnement
- Un environnement .NET fonctionnel.
- Accès à un éditeur de code, tel que Visual Studio.

### Prérequis en matière de connaissances
- Compréhension de base de C# et du framework .NET.
- Connaissance des concepts des logiciels de présentation (facultatif mais utile).

## Configuration d'Aspose.Slides pour .NET

Pour commencer à utiliser Aspose.Slides dans votre projet, vous devez l'installer via NuGet. Voici les méthodes disponibles :

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

### Étapes d'acquisition de licence

1. **Essai gratuit**:Commencez par un [essai gratuit](https://releases.aspose.com/slides/net/) pour explorer les fonctionnalités de base.
2. **Permis temporaire**: Obtenez une licence temporaire si vous avez besoin d'accéder à toutes les fonctionnalités à des fins d'évaluation en visitant [ici](https://purchase.aspose.com/temporary-license/).
3. **Achat**: Pour une utilisation commerciale, achetez une licence auprès du [Site Web d'Aspose](https://purchase.aspose.com/buy).

Une fois installé et licencié, initialisez Aspose.Slides dans votre projet :
```csharp
using Aspose.Slides;

// Initialiser Aspose.Slides pour .NET
var presentation = new Presentation();
```

## Guide de mise en œuvre

### Créer une nouvelle présentation et ajouter un graphique en anneau

#### Aperçu
Nous commencerons par créer une nouvelle présentation et ajouterons un graphique en anneau à la première diapositive. Cette section explique comment charger une présentation existante, accéder aux diapositives et insérer des graphiques.

**Étape 1 : Charger ou créer une présentation**
Tout d’abord, spécifiez votre répertoire de documents et chargez une présentation existante :
```csharp
string dataDir = \@"YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "testc.pptx");
```
Si vous n'avez pas de fichier existant, créez-en un nouveau avec `new Presentation()`.

**Étape 2 : Accéder à la première diapositive**
Accédez à la première diapositive où nous ajouterons notre graphique :
```csharp
ISlide slide = pres.Slides[0];
```

**Étape 3 : Ajouter un graphique en anneau**
Ajoutez un graphique en anneau aux coordonnées et dimensions spécifiées :
```csharp
IChart chart = slide.Shapes.AddChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### Configuration du classeur de données

#### Aperçu
Cette section explique comment configurer le classeur de données associé à votre graphique en anneau.

**Étape 4 : Accéder aux données existantes et les effacer**
Accédez au classeur de données du graphique. Supprimez ensuite les séries ou catégories existantes :
```csharp
IChartDataWorkbook workBook = chart.ChartData.ChartDataWorkbook;
chart.ChartData.Series.Clear();
chart.ChartData.Categories.Clear();
```

**Étape 5 : Désactiver la légende et ajouter une série**
Désactivez la légende pour garder le graphique propre, puis ajoutez jusqu'à 15 séries avec des configurations personnalisées :
```csharp
chart.HasLegend = false;

int seriesIndex = 0;
while (seriesIndex < 15)
{
    IChartSeries series = chart.ChartData.Series.Add(workBook.GetCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.Type);
    series.Explosion = 0;
    series.ParentSeriesGroup.DoughnutHoleSize = (byte)20;
    series.ParentSeriesGroup.FirstSliceAngle = 351;
    seriesIndex++;
}
```

### Ajout de catégories et de points de données

#### Aperçu
Maintenant, remplissons le graphique avec des catégories et des points de données pour chaque série.

**Étape 6 : Ajouter des catégories**
Parcourez pour ajouter 15 catégories :
```csharp
int categoryIndex = 0;
while (categoryIndex < 15)
{
    chart.ChartData.Categories.Add(workBook.GetCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
```

**Étape 7 : Renseigner les points de données**
Ajoutez des points de données pour chaque série dans la catégorie actuelle :
```csharp
int i = 0;
while (i < chart.ChartData.Series.Count)
{
    IChartSeries iCS = chart.ChartData.Series[i];
    IChartDataPoint dataPoint = iCS.DataPoints.AddDataPointForDoughnutSeries(workBook.GetCell(0, categoryIndex + 1, i + 1, 1));

    // Personnaliser l'apparence
    dataPoint.Format.Fill.FillType = FillType.Solid;
    dataPoint.Format.Line.FillFormat.FillType = FillType.Solid;
    dataPoint.Format.Line.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;
    dataPoint.Format.Line.Width = 1;
    dataPoint.Format.Line.Style = LineStyle.Single;
    dataPoint.Format.Line.DashStyle = LineDashStyle.Solid;

    // Configurer le format d'étiquette pour la dernière série
    if (i == chart.ChartData.Series.Count - 1)
    {
        IDataLabel lbl = dataPoint.Label;
        lbl.TextFormat.TextBlockFormat.AutofitType = TextAutofitType.Shape;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FontBold = NullableBool.True;
        lbl.DataLabelFormat.TextFormat.PortionFormat.LatinFont = new FontData("DINPro-Bold");
        lbl.DataLabelFormat.TextFormat.PortionFormat.FontHeight = 12;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.LightGray;
        lbl.DataLabelFormat.Format.Line.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;

        // Configurer l'affichage des étiquettes
        lbl.DataLabelFormat.ShowValue = false;
        lbl.DataLabelFormat.ShowCategoryName = true;
        lbl.DataLabelFormat.ShowSeriesName = false;
        lbl.DataLabelFormat.ShowLeaderLines = true;

        chart.ValidateChartLayout();
        lbl.AsILayoutable.X += 0.5f;
        lbl.AsILayoutable.Y += 0.5f;
    }
    i++;
}
categoryIndex++;
```

### Enregistrer la présentation

**Étape 8 : Enregistrer le fichier**
Enfin, enregistrez votre présentation dans un répertoire spécifié :
```csharp
pres.Save(dataDir + "chart.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}