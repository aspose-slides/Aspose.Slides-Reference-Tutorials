---
"date": "2025-04-15"
"description": "Découvrez comment enrichir vos présentations avec des graphiques en nuage de points grâce à Aspose.Slides pour .NET. Suivez ce guide complet pour créer et personnaliser efficacement des graphiques."
"title": "Ajouter des graphiques en nuage de points aux présentations à l'aide d'Aspose.Slides .NET &#58; un guide étape par étape"
"url": "/fr/net/charts-graphs/aspose-slides-net-scatter-charts-presentation-guide/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Ajouter des graphiques en nuage de points aux présentations avec Aspose.Slides .NET : guide étape par étape

## Introduction
Vous souhaitez améliorer vos présentations en intégrant facilement des graphiques en nuage de points ? Grâce à la puissance d'Aspose.Slides pour .NET, créer et personnaliser des graphiques devient un jeu d'enfant. Ce tutoriel vous guidera dans l'ajout de graphiques en nuage de points à vos diapositives avec Aspose.Slides pour .NET. En maîtrisant ces techniques, vous présenterez vos données plus efficacement et créerez des présentations visuellement attrayantes.

**Ce que vous apprendrez :**
- Configurer Aspose.Slides pour .NET dans votre projet
- Créer une nouvelle présentation et accéder à sa première diapositive
- Ajout de graphiques en nuage de points avec des lignes lisses aux diapositives
- Effacer les séries existantes et en ajouter de nouvelles aux graphiques
- Modification des points de données et des styles de marqueurs pour une visualisation améliorée
- Enregistrer la présentation dans un répertoire spécifié

Commençons par passer en revue les prérequis.

## Prérequis
Avant d'implémenter Aspose.Slides pour .NET, assurez-vous de disposer des éléments suivants :
- **Bibliothèque Aspose.Slides pour .NET**:Version 23.7 ou ultérieure.
- **Environnement de développement**: Visual Studio 2019 ou plus récent avec .NET Framework 4.6.1+ ou .NET Core/5+.
- **Connaissances de base en C#**: Familiarité avec la programmation orientée objet en C#.

## Configuration d'Aspose.Slides pour .NET
Pour commencer à utiliser Aspose.Slides, vous devez installer la bibliothèque dans votre projet. Voici comment :

**Utilisation de .NET CLI :**
```bash
dotnet add package Aspose.Slides
```

**Utilisation de la console du gestionnaire de packages :**
```powershell
Install-Package Aspose.Slides
```

**Interface utilisateur du gestionnaire de packages NuGet :**
- Recherchez « Aspose.Slides » et installez la dernière version.

### Acquisition de licence
Vous pouvez commencer par un essai gratuit ou demander une licence temporaire pour explorer toutes les fonctionnalités. Pour acheter, suivez ces étapes :
1. Visite [Acheter Aspose.Slides](https://purchase.aspose.com/buy) pour acheter une licence complète.
2. Pour une licence temporaire, visitez [Page de licence temporaire](https://purchase.aspose.com/temporary-license/).

Une fois que vous avez obtenu votre fichier de licence, ajoutez-le à votre projet en utilisant :
```csharp
Aspose.Slides.License license = new Aspose.Slides.License();
license.SetLicense("Aspose.Slides.lic");
```

## Guide de mise en œuvre
Nous allons décomposer l’implémentation en sections logiques basées sur les fonctionnalités.

### Créer une présentation et ajouter une diapositive
Cette section montre comment créer une présentation et accéder à sa première diapositive.

#### Aperçu
Commencez par créer une instance du `Presentation` classe, qui représente votre fichier PowerPoint. L'accès aux diapositives est simple grâce à ce modèle objet.

#### Étapes de mise en œuvre
**Étape 1 : Initialiser la présentation**
```csharp
using Aspose.Slides;

// Créer une nouvelle présentation
t Presentation pres = new Presentation();
```
Ce code initialise un nouveau document de présentation.

**Étape 2 : Accéder à la première diapositive**
```csharp
// Accéder à la première diapositive de la présentation
ISlide slide = pres.Slides[0];
```
Ici, `pres.Slides[0]` accède à la toute première diapositive. 

### Ajouter un graphique à dispersion à la diapositive
Ajoutons maintenant un graphique en nuage de points à votre présentation.

#### Aperçu
L'ajout de graphiques peut vous aider à représenter visuellement vos données dans vos présentations. Aspose.Slides simplifie l'intégration de différents types de graphiques, notamment les nuages de points.

#### Étapes de mise en œuvre
**Étape 1 : Créer et ajouter un graphique en nuage de points**
```csharp
using Aspose.Slides.Charts;

// Créer et ajouter un graphique en nuage de points par défaut avec des lignes lisses
IChart chart = slide.Shapes.AddChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
Cet extrait ajoute un graphique en nuage de points à la position et à la taille spécifiées.

### Effacer et ajouter des séries aux données du graphique
#### Aperçu
Vous devrez peut-être personnaliser votre graphique en supprimant des séries existantes et en en ajoutant de nouvelles. Cette section décrit cette fonctionnalité.

#### Étapes de mise en œuvre
**Étape 1 : Accéder au classeur de données graphiques**
```csharp
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;

// Effacer toutes les séries préexistantes
chart.ChartData.Series.Clear();
```
Ce code efface les données existantes pour repartir à zéro avec une nouvelle série.

**Étape 2 : Ajouter une nouvelle série**
```csharp
// Ajouter une nouvelle série nommée « Série 1 »
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);

// Ajouter une autre série nommée « Série 2 »
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.Type);
```
Ces étapes ajoutent deux nouvelles séries au graphique.

### Modifier les points de données de la première série et le style du marqueur
#### Aperçu
Personnalisez les points de données et les styles de marqueurs pour une meilleure visualisation de vos nuages de points.

#### Étapes de mise en œuvre
**Étape 1 : Accéder aux points de données et les ajouter**
```csharp
IChartSeries series = chart.ChartData.Series[0];

// Ajoutez les points de données (1, 3) et (2, 10)
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, 1), fact.GetCell(defaultWorksheetIndex, 2, 2, 3));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, 2), fact.GetCell(defaultWorksheetIndex, 3, 2, 10));
```
**Étape 2 : Modifier le style du marqueur**
```csharp
// Modifier le type de série et modifier le style du marqueur
series.Type = ChartType.ScatterWithStraightLinesAndMarkers;
series.Marker.Size = 10;
series.Marker.Symbol = MarkerStyleType.Star;
```
### Modifier les points de données de la deuxième série et le style du marqueur
#### Aperçu
De même, personnalisez la deuxième série pour l’adapter à vos besoins de présentation.

#### Étapes de mise en œuvre
**Étape 1 : Accéder à plusieurs points de données et les ajouter**
```csharp
// Accéder à la deuxième série de graphiques
series = chart.ChartData.Series[1];

// Ajouter plusieurs points de données
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 2, 3, 5), fact.GetCell(defaultWorksheetIndex, 2, 4, 2));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 3, 3, 3), fact.GetCell(defaultWorksheetIndex, 3, 4, 1));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 4, 3, 2), fact.GetCell(defaultWorksheetIndex, 4, 4, 2));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 5, 3, 5), fact.GetCell(defaultWorksheetIndex, 5, 4, 1));
```
**Étape 2 : Modifier le style du marqueur**
```csharp
// Modifier la taille du marqueur et le symbole pour la deuxième série
series.Marker.Size = 10;
series.Marker.Symbol = MarkerStyleType.Circle;
```
### Enregistrer la présentation
Enfin, enregistrez votre présentation dans un répertoire spécifié.

#### Étapes de mise en œuvre
**Étape 1 : Définir le répertoire**
Assurez-vous que le répertoire de sortie existe. Sinon, créez-le :
```csharp
using Aspose.Slides.Export;
using System.IO;

string YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";
bool isExists = Directory.Exists(YOUR_DOCUMENT_DIRECTORY);
if (!isExists) 
    Directory.CreateDirectory(YOUR_DOCUMENT_DIRECTORY);

// Enregistrer la présentation
pres.Save(YOUR_DOCUMENT_DIRECTORY + "\AsposeChart_out.pptx", SaveFormat.Pptx);
```
Ce code enregistre votre fichier de présentation à un emplacement spécifié.

## Conclusion
Vous avez maintenant ajouté des graphiques en nuage de points à vos présentations avec Aspose.Slides pour .NET. Explorez les fonctionnalités et personnalisations supplémentaires disponibles dans la bibliothèque pour améliorer vos compétences en visualisation de données.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}