---
"date": "2025-04-15"
"description": "Apprenez à créer des graphiques en anneau dynamiques et visuellement attrayants dans des présentations PowerPoint à l’aide de la puissante bibliothèque Aspose.Slides pour .NET."
"title": "Comment créer un graphique en anneau dans PowerPoint avec Aspose.Slides pour .NET"
"url": "/fr/net/charts-graphs/create-doughnut-chart-powerpoint-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment créer un graphique en anneau dans PowerPoint avec Aspose.Slides pour .NET
Créer des graphiques attrayants est essentiel pour une présentation efficace des données. Les graphiques en anneau sont parfaits pour illustrer les parties d'un tout, ce qui les rend parfaits pour la visualisation de données en pourcentage. Ce tutoriel vous guidera dans la création d'un graphique en anneau dynamique dans PowerPoint grâce à la puissante bibliothèque Aspose.Slides pour .NET.

## Introduction
Les présentations nécessitent souvent des représentations visuelles d'ensembles de données complexes, là où les graphiques à barres ou en courbes traditionnels peuvent s'avérer insuffisants. Le graphique en anneau s'avère être un outil polyvalent pour communiquer efficacement des données en pourcentage avec style et clarté. Dans ce tutoriel, nous découvrirons comment Aspose.Slides pour .NET simplifie la création de ces graphiques directement dans PowerPoint.

**Ce que vous apprendrez :**
- Configuration d'Aspose.Slides pour .NET
- Instructions étape par étape pour créer un graphique en anneau
- Ajouter des séries et des catégories à votre graphique
- Configuration des étiquettes de données pour une clarté accrue
- Sauvegarde de la présentation finale

Voyons comment vous pouvez exploiter Aspose.Slides pour .NET pour améliorer vos présentations avec des graphiques en anneau personnalisés.

## Prérequis
Avant de commencer, assurez-vous que les éléments suivants sont en place :
- **Bibliothèque Aspose.Slides pour .NET**:Disponible via NuGet ou téléchargement direct.
- **Environnement de développement**:Visual Studio est recommandé pour les projets .NET.
- Connaissances de base de C# et familiarité avec la structure de PowerPoint.

## Configuration d'Aspose.Slides pour .NET
Pour commencer à créer des graphiques, vous devez d'abord configurer la bibliothèque Aspose.Slides dans votre projet. Voici plusieurs façons de l'installer :

**Utilisation de .NET CLI :**

```bash
dotnet add package Aspose.Slides
```

**Utilisation de la console du gestionnaire de packages :**

```powershell
Install-Package Aspose.Slides
```

**Via l'interface utilisateur du gestionnaire de packages NuGet :**
Recherchez « Aspose.Slides » et installez la dernière version.

Une fois installé, vous pouvez commencer à configurer votre projet. Si vous débutez avec Aspose.Slides, envisagez d'obtenir une licence temporaire ou un essai gratuit pour explorer toutes ses fonctionnalités sans aucune limitation.

### Initialisez votre projet
Voici comment vous pouvez initialiser Aspose.Slides dans votre application :

```csharp
using Aspose.Slides;

class Program
{
    static void Main()
    {
        // Créer une instance de la classe Presentation
        Presentation presentation = new Presentation();
        
        // Votre code pour manipuler la présentation va ici
        
        // Enregistrer la présentation
        presentation.Save("output.pptx", SaveFormat.Pptx);
    }
}
```

## Guide de mise en œuvre
### Création d'un graphique en anneau
#### Aperçu
Nous allons d'abord créer un graphique en anneau vide dans une diapositive PowerPoint. Il servira de base pour ajouter des données et personnaliser son apparence.

**Étape 1 : Ajouter un graphique en anneau**

```csharp
using Aspose.Slides;

class CreateDoughnutChart
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        
        // Ajoutez un graphique en anneau à la première diapositive à la position (10, 10) avec une taille (500, 500)
        IChart chart = slide.getShapes().addChart(
            ChartType.Doughnut, 10, 10, 500, 500, false
        );

        // Effacer les séries et catégories existantes
        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getCategories().clear();

        // Désactiver la légende pour un look plus propre
        chart.setHasLegend(false);

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**Explication:**
- **ajouter un graphique**: Insère un nouveau graphique en anneau sur la diapositive.
- **getChartDataWorkbook**: Fournit un accès aux cellules de données du graphique pour la manipulation.

### Ajout de séries et de catégories
#### Aperçu
Ensuite, nous remplirons votre graphique avec des données significatives en ajoutant des séries et des catégories.

**Étape 2 : Ajouter une série de données**

```csharp
using Aspose.Slides;

class AddSeriesAndCategories
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        IChart chart = (IChart)slide.getShapes().get_Item(1);

        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

        // Ajouter une série
        for (int seriesIndex = 0; seriesIndex < 15; seriesIndex++)
        {
            IChartSeries series = chart.getChartData()
                .getSeries()
                .add(
                    workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
                    chart.getType()
                );

            // Personnalisation du trou du beignet et de l'angle de départ
            series.setExplosion(0);
            series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
            series.getParentSeriesGroup().setFirstSliceAngle(351);
        }

        // Ajouter des catégories
        for (int categoryIndex = 0; categoryIndex < 15; categoryIndex++)
        {
            chart.getChartData()
                .getCategories()
                .add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));

            for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
            {
                IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
                IChartDataPoint dataPoint = iCS
                    .getDataPoints()
                    .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

                // Formatage du remplissage et de la ligne du point de données
                dataPoint.getFormat().getFill().setFillType(FillType.Solid);
                dataPoint.getFormat().getLine()
                    .getFillFormat()
                    .setFillType(FillType.Solid);
                
                dataPoint.getFormat().getLine()
                    .getFillFormat()
                    .getSolidFillColor()
                    .setColor(Color.WHITE);
                
                dataPoint.getFormat().getLine().setWidth(1.0);
                dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
                dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
            }
        }

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**Explication:**
- **ajouter**: Insère de nouvelles séries et catégories dans le graphique.
- **définir la taille du trou du beignet**:Configure la taille du trou du beignet, améliorant ainsi son attrait visuel.

### Configuration des étiquettes de données
#### Aperçu
Les étiquettes de données contextualisent les données de votre graphique. Améliorez leur lisibilité en les personnalisant.

**Étape 3 : Personnaliser les étiquettes de données**

```csharp
using Aspose.Slides;

class ConfigureDataLabels
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        IChart chart = (IChart)slide.getShapes().get_Item(1);

        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

        for (int categoryIndex = 0; categoryIndex < 15; categoryIndex++)
        {
            for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
            {
                IChartSeries series = chart.getChartData().getSeries().get_Item(i);
                IChartDataPoint dataPoint = series
                    .getDataPoints()
                    .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

                // Personnalisation des étiquettes de données
                IDataLabel lbl = dataPoint.getLabel();
                lbl.getDataLabelFormat().setTextFormat()
                    .setCenterText(NullableBool.True)
                    .setShowPercentage(true);
                lbl.setVisible(true);
            }
        }

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**Explication:**
- **Étiquette de données**:Personnalise les étiquettes de données pour plus de clarté et de présentation.
- **définir le texte central**, **afficherPourcentage**: Améliorez la lisibilité des étiquettes en centrant le texte et en affichant les pourcentages.

## Conclusion
En suivant ce guide, vous avez appris à créer un graphique en anneau dynamique dans PowerPoint avec Aspose.Slides pour .NET. Cette puissante bibliothèque offre une personnalisation complète, vous permettant d'adapter précisément vos graphiques à vos besoins de présentation.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}