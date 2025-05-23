---
"date": "2025-04-15"
"description": "Apprenez à créer des graphiques à colonnes empilées en pourcentage visuellement attrayants avec Aspose.Slides pour .NET. Suivez ce guide étape par étape pour une visualisation claire des données."
"title": "Comment créer des graphiques à colonnes empilées en pourcentage dans .NET avec Aspose.Slides"
"url": "/fr/net/charts-graphs/create-stacked-column-charts-asposeslides-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment créer un graphique à colonnes empilées basé sur des pourcentages avec Aspose.Slides pour .NET

## Introduction

Dans le domaine de la visualisation de données, présenter l'information de manière claire et efficace est essentiel pour une prise de décision efficace. Pour afficher intuitivement des ensembles de données complexes, les graphiques à colonnes empilées en pourcentage sont idéaux. Ce guide vous guidera dans la création de ces graphiques avec Aspose.Slides pour .NET, une bibliothèque robuste conçue pour la manipulation de fichiers de présentation.

En suivant ce tutoriel, vous apprendrez :
- Configuration des données du graphique et configuration des formats de nombres.
- Ajout de séries et personnalisation de leur apparence.
- Formatage des étiquettes pour améliorer la lisibilité.

Prêt à vous lancer ? Commençons par les prérequis !

## Prérequis

Avant de créer vos graphiques à colonnes empilées en pourcentage, assurez-vous que votre environnement est correctement configuré. Vous aurez besoin des éléments suivants :

### Bibliothèques, versions et dépendances requises
- **Aspose.Slides pour .NET**: Assurez-vous que cette bibliothèque est installée.

### Configuration requise pour l'environnement
- Un environnement de développement avec le SDK .NET installé.
- Visual Studio ou tout autre IDE compatible pour exécuter du code C#.

### Prérequis en matière de connaissances
- Compréhension de base de la programmation C#.
- Connaissance de la configuration de projets .NET et de la gestion de packages.

## Configuration d'Aspose.Slides pour .NET

Pour commencer à créer des graphiques avec Aspose.Slides, installez d'abord la bibliothèque en utilisant l'une de ces méthodes :

**.NET CLI**
```bash
dotnet add package Aspose.Slides
```

**Gestionnaire de paquets**
```powershell
Install-Package Aspose.Slides
```

**Interface utilisateur du gestionnaire de packages NuGet**
- Recherchez « Aspose.Slides » et installez la dernière version.

### Étapes d'acquisition de licence

Commencez par un essai gratuit en téléchargeant une licence temporaire à partir de [Site Web d'Aspose](https://purchase.aspose.com/temporary-license/)Pour une utilisation continue, envisagez d'acheter une licence complète. 

Une fois configuré, lancez Aspose.Slides dans votre projet :
```csharp
using Aspose.Slides;
```

## Guide de mise en œuvre

L'environnement étant prêt, décomposons la création d'un graphique à colonnes empilées basé sur un pourcentage en étapes.

### Création et configuration du graphique

#### Aperçu
Créer une instance de `Presentation` classe, essentielle pour travailler avec des diapositives. Ensuite, ajoutez et configurez un graphique à colonnes empilées sur votre diapositive.

#### Ajout d'un graphique à colonnes empilées
```csharp
// Créer une instance de la classe Presentation
document = new Presentation();

// Obtenir une référence à la première diapositive
slide = document.Slides[0];

// Ajouter un graphique en colonnes empilées en pourcentages à la position (20, 20) avec une taille (500x400)
chart = slide.Shapes.AddChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

#### Configuration du format numérique
Assurez-vous que vos données sont affichées sous forme de pourcentages :
```csharp
// Configurer le format numérique pour l'axe vertical
columnChart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
columnChart.Axes.VerticalAxis.NumberFormat = "0.00%"; // Définir le format numérique sur pourcentage
```

#### Ajout de séries de données et de points
Effacer les données de série existantes et en ajouter de nouvelles :
```csharp
// Effacer toutes les données de série existantes
columnChart.ChartData.Series.Clear();

int defaultWorksheetIndex = 0;

// Accéder au classeur de données du graphique
dataWorkbook = columnChart.ChartData.ChartDataWorkbook;

// Ajouter une nouvelle série de données « Rouges »
series = columnChart.ChartData.Series.Add(dataWorkbook.GetCell(defaultWorksheetIndex, 0, 1, "Reds"), columnChart.Type);
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 1, 1, 0.30));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 2, 1, 0.50));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 3, 1, 0.80));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 4, 1, 0.65));

// Définir la couleur de remplissage de la série sur Rouge
series.Format.Fill.FillType = FillType.Solid;
series.Format.Fill.SolidFillColor.Color = System.Drawing.Color.Red;

// Configurer les propriétés de format d'étiquette pour la série « Rouges »
series.Labels.DefaultDataLabelFormat.ShowValue = true;
series.Labels.DefaultDataLabelFormat.IsNumberFormatLinkedToSource = false;
series.Labels.DefaultDataLabelFormat.NumberFormat = "0.0%"; // Définir le format de pourcentage
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FontHeight = 10;
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;

// Ajouter une autre série « Blues »
series2 = columnChart.ChartData.Series.Add(dataWorkbook.GetCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.Type);
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 4, 2, 0.35));

// Définir la couleur de remplissage de la série sur Bleu
series2.Format.Fill.FillType = FillType.Solid;
series2.Format.Fill.SolidFillColor.Color = System.Drawing.Color.Blue;
series2.Labels.DefaultDataLabelFormat.ShowValue = true;
columnChart.Series[1].Labels.DefaultDataLabelFormat.IsNumberFormatLinkedToSource = false;
series2.Labels.DefaultDataLabelFormat.NumberFormat = "0.0%"; // Définir le format de pourcentage
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FontHeight = 10;
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;
```

#### Enregistrer la présentation
Enregistrez votre présentation dans un fichier :
```csharp
// Enregistrer la présentation au format PPTX
document.Save("YOUR_OUTPUT_DIRECTORY/SetDataLabelsPercentageSign_out.pptx");
```

### Conseils de dépannage
- Assurez-vous que tous les espaces de noms sont correctement importés.
- Vérifiez les fautes de frappe dans les noms de propriétés et les appels de méthodes.
- Vérifiez que vos chemins d’enregistrement des fichiers existent et disposent des autorisations appropriées.

## Applications pratiques

Voici quelques scénarios dans lesquels les graphiques à colonnes empilées basés sur des pourcentages peuvent être utiles :
1. **Analyse des ventes**:Visualisez les performances des produits dans différentes régions en proportion des ventes totales.
2. **Allocation budgétaire**:Montrez comment les départements allouent leur budget par rapport aux dépenses globales de l’entreprise.
3. **Étude de marché**:Comparez les préférences des consommateurs pour différentes catégories de produits au fil du temps.
4. **Données éducatives**:Afficher la répartition des notes des élèves dans différentes matières.
5. **Statistiques sur les soins de santé**:Représenter les données démographiques des patients dans plusieurs conditions de santé.

## Considérations relatives aux performances

Pour des performances optimales, pensez à :
- Limiter le nombre de points de données à ce qui est nécessaire.
- Préchargement des données pour minimiser le traitement d'exécution.
- Utilisation de pratiques efficaces de gestion de la mémoire avec Aspose.Slides pour .NET.

## Conclusion

Félicitations ! Vous avez appris à créer un graphique à colonnes empilées basé sur des pourcentages avec Aspose.Slides pour .NET. Cet outil améliore les présentations en rendant les données complexes plus compréhensibles et visuellement plus attrayantes.

Prochaines étapes ? Explorez les autres types de graphiques disponibles dans Aspose.Slides ou intégrez cette fonctionnalité à des applications plus vastes. Bon codage !

## Section FAQ

**Q1 : Puis-je utiliser Aspose.Slides gratuitement ?**
A1 : Oui, vous pouvez commencer par un essai gratuit pour tester les fonctionnalités d'Aspose.Slides.

**Q2 : Quels types de graphiques sont pris en charge par Aspose.Slides pour .NET ?**
A2 : Il prend en charge divers graphiques tels que des graphiques à secteurs, à barres, à colonnes, à lignes, etc.

**Q3 : Comment démarrer avec Aspose.Slides pour .NET ?**
A3 : Installez la bibliothèque à l'aide de NuGet ou de la CLI .NET comme décrit ci-dessus. Suivez notre documentation pour créer votre premier graphique.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}