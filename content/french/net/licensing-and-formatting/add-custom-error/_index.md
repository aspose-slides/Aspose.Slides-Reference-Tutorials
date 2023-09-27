---
title: Ajouter des barres d'erreur personnalisées au graphique
linktitle: Ajouter des barres d'erreur personnalisées au graphique
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Découvrez comment ajouter des barres d'erreur personnalisées aux graphiques à l'aide d'Aspose.Slides pour .NET. Créez, stylisez et personnalisez des barres d'erreur pour une visualisation précise des données.
type: docs
weight: 13
url: /fr/net/licensing-and-formatting/add-custom-error/
---

## Introduction aux barres d'erreur personnalisées

Les barres d'erreur sont des représentations graphiques utilisées pour indiquer la variabilité ou l'incertitude des points de données dans un graphique. Ils peuvent aider à décrire la plage dans laquelle la valeur réelle du point de données est susceptible de se situer. Les barres d'erreur personnalisées vous permettent de définir des valeurs d'erreur spécifiques pour chaque point de données, offrant ainsi plus de contrôle sur la façon dont l'incertitude est affichée dans votre graphique.

## Configuration de l'environnement de développement

 Avant de commencer, assurez-vous que la bibliothèque Aspose.Slides pour .NET est installée. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/slides/net). Suivez les instructions d'installation fournies dans la documentation.

## Création d'un exemple de graphique

Commençons par créer un exemple de graphique à l’aide d’Aspose.Slides pour .NET. Nous allons créer un graphique à barres de base à des fins de démonstration. Assurez-vous d'avoir référencé la bibliothèque dans votre projet.

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;

// Instancier un objet Présentation
using Presentation presentation = new Presentation();

// Ajouter une diapositive
ISlide slide = presentation.Slides.AddSlide(0, presentation.SlideSize.Size);

// Ajouter un graphique
IChart chart = slide.Shapes.AddChart(ChartType.ClusteredBar, 100, 100, 500, 300);

// Ajouter des exemples de données
IChartDataWorkbook workbook = chart.ChartData.ChartDataWorkbook;
IChartSeries series = chart.ChartData.Series.Add(workbook.GetCell(0, "A1"), chart.Type);
series.Values.Add(workbook.GetCell(0, "B1"));
series.Values.Add(workbook.GetCell(0, "B2"));

// Définir des étiquettes de catégorie
chart.ChartData.Categories.Add(workbook.GetCell(0, "A2"));
chart.ChartData.Categories.Add(workbook.GetCell(0, "A3"));

// Définir le titre du graphique
chart.ChartTitle.AddTextFrameForOverriding("Sample Chart");
chart.ChartTitle.TextFrameForOverriding.Text = "Sample Chart";

// Enregistrez la présentation
presentation.Save("SampleChart.pptx", SaveFormat.Pptx);
```

Ce code crée une présentation PowerPoint avec un exemple de graphique à barres.

## Ajout de barres d'erreur au graphique

Ajoutons maintenant des barres d'erreur au graphique. Des barres d'erreur sont ajoutées à des points de données spécifiques dans une série. Nous ajouterons des barres d’erreur au premier point de données de notre exemple de graphique.

```csharp
// Accédez à la première série
IChartSeries firstSeries = chart.ChartData.Series[0];

// Ajouter des barres d'erreur
IErrorBarsFormat errorBarsFormat = firstSeries.ErrorBarsFormat.Add();
errorBarsFormat.Type = ErrorBarType.FixedValue;

// Définir la valeur de la barre d'erreur
errorBarsFormat.Value = 5; // Vous pouvez ajuster la valeur en fonction de vos données

// Enregistrez la présentation mise à jour
presentation.Save("ChartWithErrorBars.pptx", SaveFormat.Pptx);
```

Ce code ajoute des barres d'erreur de valeur fixe au premier point de données du graphique.

## Personnalisation des valeurs de la barre d'erreur

Vous pouvez personnaliser les valeurs de la barre d'erreur pour chaque point de données individuellement. Modifions le code pour définir différentes valeurs d'erreur pour chaque point de données.

```csharp
// Définir des valeurs d'erreur personnalisées pour chaque point
double[] errorValues = { 3, 6 }; // Valeurs d'erreur pour les deux points de données

for (int i = 0; i < firstSeries.DataPoints.Count; i++)
{
    firstSeries.ErrorBarsFormat[i].Value = errorValues[i];
}

// Enregistrez la présentation mise à jour
presentation.Save("CustomErrorValuesChart.pptx", SaveFormat.Pptx);
```

Ce code définit des valeurs d'erreur personnalisées pour chaque point de données de la série.

## Barres d'erreur de style

Vous pouvez styliser les barres d'erreur pour améliorer leur visibilité et correspondre à l'esthétique de votre graphique. Personnalisons l'apparence des barres d'erreur.

```csharp
// Personnaliser l'apparence de la barre d'erreur
errorBarsFormat.LineFormat.Width = 2; // Définir la largeur de la ligne
errorBarsFormat.LineFormat.SolidFillColor.Color = Color.Red; // Définir la couleur de la ligne

// Enregistrez la présentation mise à jour
presentation.Save("StyledErrorBarsChart.pptx", SaveFormat.Pptx);
```

Ce code ajuste la largeur de ligne et la couleur des barres d'erreur.

## Mise à jour des données du graphique

Si vous devez mettre à jour les données du graphique, vous pouvez le faire facilement à l'aide d'Aspose.Slides pour .NET. Remplaçons les données par de nouvelles valeurs.

```csharp
// Mettre à jour les données du graphique
series.Values[0].Value = 15;
series.Values[1].Value = 20;

// Enregistrez la présentation mise à jour
presentation.Save("UpdatedChartData.pptx", SaveFormat.Pptx);
```

Ce code met à jour les valeurs des données du graphique.

## Barres d'erreur pour plusieurs séries

Vous pouvez ajouter des barres d'erreur à plusieurs séries dans un graphique. Ajoutons des barres d'erreur à la deuxième série de notre exemple de graphique.

```csharp
// Accédez à la deuxième série
IChartSeries secondSeries = chart.ChartData.Series[1];

// Ajouter des barres d'erreur à la deuxième série
IErrorBarsFormat secondSeriesErrorBars = secondSeries.ErrorBarsFormat.Add();
secondSeriesErrorBars.Type = ErrorBarType.Percent;

// Définir la valeur de la barre d'erreur pour la deuxième série
secondSeriesErrorBars.Value = 10; // Vous pouvez ajuster la valeur

// Enregistrez la présentation mise à jour
presentation.Save("MultiSeriesChartWithErrorBars.pptx", SaveFormat.Pptx);
```

Ce code ajoute des barres d'erreur à la deuxième série du graphique.

## Gestion des erreurs négatives et positives

Les barres d'erreur peuvent représenter des erreurs positives et négatives. Modifions le code pour ajouter les deux types de barres d'erreur.

```csharp
// Ajouter des barres d'erreur positives et négatives
errorBarsFormat.Type = ErrorBarType.Custom;
errorBarsFormat.PlusValue = 4; // Valeur d'erreur positive
errorBarsFormat.MinusValue = 2; // Valeur d'erreur négative

// Enregistrez la présentation mise à jour
presentation.Save("PositiveNegativeErrorBars.pptx", SaveFormat.Pptx);
```

Ce code ajoute des barres d'erreur positives et négatives personnalisées au graphique.

## Enregistrement et exportation du graphique

Une fois que vous avez ajouté des barres d'erreur et personnalisé votre graphique, vous pouvez l'enregistrer et l'exporter pour une utilisation ultérieure.

```csharp
// Enregistrez le graphique final
presentation.Save("FinalChart.pptx", SaveFormat.Pptx);
```

Ce code enregistre le graphique final avec des barres d'erreur.

## Conclusion

Dans ce didacticiel, nous avons expliqué comment ajouter des barres d'erreur personnalisées à un graphique à l'aide d'Aspose.Slides pour .NET. Nous avons couvert la création d'un exemple de graphique, l'ajout de barres d'erreur, la personnalisation des valeurs d'erreur, le style des barres d'erreur, la mise à jour des données du graphique, l'ajout de barres d'erreur à plusieurs séries et la gestion des erreurs positives et négatives. Avec Aspose.Slides pour .NET, vous avez la possibilité de créer des graphiques informatifs et visuellement attrayants avec des barres d'erreur personnalisées qui communiquent efficacement la variabilité de vos données.

## FAQ

### Comment puis-je ajuster l’épaisseur des barres d’erreur ?

 Vous pouvez ajuster l'épaisseur des barres d'erreur en modifiant le`LineFormat.Width` propriété du`ErrorBarsFormat`.

### Puis-je utiliser différentes valeurs d’erreur pour chaque point de données ?

Oui, vous pouvez définir des valeurs d'erreur personnalisées pour chaque point de données individuellement à l'aide d'une boucle et du`Value` propriété de`ErrorBarsFormat`.

### Est-il possible d'ajouter des barres d'erreur à plusieurs séries dans un seul graphique ?

Absolument, vous pouvez ajouter des barres d'erreur à plusieurs séries dans le même graphique. Accédez simplement à la série souhaitée et appliquez des barres d’erreur comme démontré dans l’article.

### Puis-je supprimer les barres d’erreur après les avoir ajoutées ?

 Oui, vous pouvez supprimer les barres d'erreur en appelant le`Clear` méthode sur le`ErrorBarsFormat` objet.

### Où puis-je trouver plus d’informations sur Aspose.Slides pour .NET ?

 Vous pouvez trouver une documentation détaillée et des exemples pour Aspose.Slides pour .NET sur le[Site de documentation Aspose](https://reference.aspose.com/slides/net/).