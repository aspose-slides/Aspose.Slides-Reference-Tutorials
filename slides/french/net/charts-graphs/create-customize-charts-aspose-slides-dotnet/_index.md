---
"date": "2025-04-15"
"description": "Apprenez à créer et personnaliser des graphiques avec Aspose.Slides pour .NET, notamment en affichant des pourcentages comme étiquettes de données. Suivez ce guide étape par étape."
"title": "Comment créer et personnaliser des graphiques avec Aspose.Slides .NET ? Afficher les pourcentages sous forme d'étiquettes"
"url": "/fr/net/charts-graphs/create-customize-charts-aspose-slides-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment créer et personnaliser des graphiques avec Aspose.Slides .NET : afficher les pourcentages sous forme d'étiquettes

## Introduction

Présenter efficacement les données est crucial dans de nombreux domaines, et les graphiques jouent un rôle essentiel en transformant des informations complexes en visuels clairs. Créer un graphique parfait implique des tâches de personnalisation, comme l'affichage de pourcentages sur les étiquettes, une tâche simplifiée grâce à Aspose.Slides pour .NET. Cette bibliothèque simplifie la création et la modification de graphiques dans les présentations PowerPoint.

Dans ce tutoriel, vous apprendrez à utiliser Aspose.Slides pour .NET pour créer un graphique à colonnes empilées de A à Z et le personnaliser en affichant des pourcentages comme étiquettes de données. En suivant ces étapes, vous enrichirez vos diapositives avec des représentations de données précises et visuellement attrayantes.

**Ce que vous apprendrez :**
- Initialisation d'Aspose.Slides pour .NET
- Création d'un graphique à colonnes empilées
- Calcul et affichage des pourcentages sur les étiquettes de données
- Meilleures pratiques d'optimisation des performances des graphiques

Avant de nous lancer dans la mise en œuvre, assurons-nous que tout est prêt pour commencer.

## Prérequis

Pour suivre efficacement ce tutoriel, assurez-vous d'avoir :
- **Kit de développement logiciel (SDK) .NET Core** installé sur votre machine.
- Compréhension de base du développement d'applications C# et .NET.
- Visual Studio ou un IDE similaire pour écrire et exécuter du code C#.

Vous aurez besoin d'Aspose.Slides pour .NET pour créer des graphiques, assurez-vous donc qu'il est configuré comme décrit ci-dessous.

## Configuration d'Aspose.Slides pour .NET

Aspose.Slides pour .NET est une bibliothèque puissante qui vous permet de travailler avec des présentations PowerPoint par programmation. Voici comment l'ajouter à votre projet :

### Installation

**.NET CLI :**
```bash
dotnet add package Aspose.Slides
```

**Console du gestionnaire de paquets :**
```powershell
Install-Package Aspose.Slides
```

**Interface utilisateur du gestionnaire de packages NuGet :** 
- Ouvrez le gestionnaire de paquets NuGet et recherchez « Aspose.Slides ». Installez la dernière version.

### Acquisition de licence

Pour profiter pleinement d'Aspose.Slides, commencez par un essai gratuit. Pour une utilisation prolongée, envisagez d'acquérir une licence temporaire ou d'en acheter une auprès de [Aspose](https://purchase.aspose.com/buy)Suivez leurs directives pour configurer votre licence dans l’environnement de votre projet.

### Initialisation de base

Une fois installé, initialisez le `Presentation` classe pour commencer à créer des diapositives :
```csharp
using Aspose.Slides;

// Initialiser l'instance de classe de présentation
tPresentation presentation = new Presentation();
```

Passons maintenant à l’implémentation de notre fonctionnalité de création et de personnalisation de graphiques à l’aide d’Aspose.Slides pour .NET.

## Guide de mise en œuvre

### Créer un graphique à colonnes empilées

Notre objectif est de créer un graphique à colonnes empilées et de le personnaliser en affichant des pourcentages comme étiquettes de données. Voici comment :

#### Initialiser la présentation

Commencez par créer une instance de `Presentation`:
```csharp
using Aspose.Slides;

// Initialiser l'instance de classe de présentation
tPresentation presentation = new Presentation();
ISlide slide = presentation.Slides[0];
```

#### Ajouter un graphique à la diapositive

Ajoutez un graphique à colonnes empilées à votre première diapositive aux coordonnées et dimensions spécifiées :
```csharp
IChart chart = slide.Shapes.AddChart(ChartType.StackedColumn, 20, 20, 400, 400);
```
Cette ligne crée un `StackedColumn` graphique à la position (20, 20) avec une largeur et une hauteur de 400.

#### Calculer les valeurs totales pour le calcul du pourcentage

Pour afficher les pourcentages, calculez la valeur totale de chaque catégorie sur toutes les séries :
```csharp
IChartSeries series;
double[] total_for_Cat = new double[chart.ChartData.Categories.Count];

for (int k = 0; k < chart.ChartData.Categories.Count; k++)
{
    IChartCategory cat = chart.ChartData.Categories[k];
    // Additionner les valeurs de toutes les séries pour chaque catégorie
    for (int i = 0; i < chart.ChartData.Series.Count; i++)
    {
        total_for_Cat[k] += Convert.ToDouble(chart.ChartData.Series[i].DataPoints[k].Value.Data);
    }
}
```

#### Personnaliser les étiquettes de données pour afficher les valeurs en pourcentage

Ensuite, parcourez chaque série et personnalisez les étiquettes de données :
```csharp
for (int x = 0; x < chart.ChartData.Series.Count; x++)
{
    series = chart.ChartData.Series[x];
    series.Labels.DefaultDataLabelFormat.ShowLegendKey = false;

    for (int j = 0; j < series.DataPoints.Count; j++)
    {
        IDataLabel lbl = series.DataPoints[j].Label;
        
        // Calculer le pourcentage
        double dataPontPercent = (Convert.ToDouble(series.DataPoints[j].Value.Data) / total_for_Cat[j]) * 100;
        IPortion port = new Portion();
        port.Text = String.Format("{0:F2} %", dataPontPercent);
        port.PortionFormat.FontHeight = 8f;

        lbl.TextFrameForOverriding.Text = ""; // Texte clair pour éviter les chevauchements
        IParagraph para = lbl.TextFrameForOverriding.Paragraphs[0];
        para.Portions.Add(port);

        // Configurer le format d'étiquette pour masquer les étiquettes de données par défaut
        lbl.DataLabelFormat.ShowSeriesName = false;
        lbl.DataLabelFormat.ShowPercentage = false; 
        lbl.DataLabelFormat.ShowLegendKey = false;
        lbl.DataLabelFormat.ShowCategoryName = false;
        lbl.DataLabelFormat.ShowBubbleSize = false;
    }
}
```

Cette section calcule le pourcentage pour chaque point de données et le définit comme une étiquette personnalisée, garantissant ainsi l'absence de chevauchement avec les étiquettes par défaut.

#### Enregistrer la présentation

Enfin, enregistrez votre présentation pour visualiser le résultat :
```csharp
string outputDir = "YOUR_OUTPUT_DIRECTORY";
presentation.Save(outputDir + "/DisplayPercentageAsLabels_out.pptx", SaveFormat.Pptx);
```

## Applications pratiques

L'affichage des pourcentages dans des graphiques peut être particulièrement utile dans des scénarios tels que :
1. **Rapports financiers :** Afficher les distributions de portefeuille ou les rendements des investissements sous forme de pourcentages.
2. **Analyse des ventes :** Représentez les données de part de marché en pourcentage pour mettre en évidence les performances entre les régions.
3. **Résultats de l'enquête :** Affichez les réponses à l’enquête sous forme de pourcentages pour une meilleure comparaison visuelle.
4. **Gestion de projet :** Utilisez des graphiques à secteurs avec des pourcentages pour illustrer l’allocation des ressources.
5. **Éducation:** Expliquez les concepts statistiques à l’aide de visuels clairs basés sur des pourcentages.

L’intégration de ces graphiques personnalisés dans des systèmes tels que CRM ou ERP peut améliorer les tableaux de bord et les rapports, facilitant ainsi les processus de prise de décision.

## Considérations relatives aux performances

Lorsque vous travaillez avec Aspose.Slides pour .NET, en particulier avec de grands ensembles de données :
- **Gestion de la mémoire :** Supprimez les objets de présentation correctement pour libérer de la mémoire. `using` déclarations, le cas échéant.
- **Traitement efficace des données :** Effectuez des calculs en dehors des boucles lorsque cela est possible pour réduire la surcharge de calcul.
- **Équilibrage de charge :** Pour les applications Web, assurez-vous que les ressources du serveur sont correctement provisionnées pour les demandes de génération de graphiques simultanées.

## Conclusion

Ce tutoriel a abordé la création et la personnalisation de graphiques avec Aspose.Slides pour .NET en affichant des pourcentages sous forme d'étiquettes. La maîtrise de ces techniques vous permettra d'améliorer vos présentations avec des représentations de données détaillées et visuellement attrayantes.

Ensuite, explorez les autres types de graphiques et options de personnalisation disponibles dans Aspose.Slides. Testez différents ensembles de données pour les transformer en visuels percutants et clairs.

## Section FAQ

**Q1 : Comment gérer de grands ensembles de données lors de la création de graphiques avec Aspose.Slides pour .NET ?**
A1 : Pour les grands ensembles de données, optimisez les calculs et utilisez des techniques efficaces de gestion de la mémoire. Décomposez les tâches de traitement pour éviter la surcharge mémoire.

**Q2 : Puis-je utiliser Aspose.Slides pour .NET dans une application Web ?**
A2 : Oui, il peut être intégré aux applications ASP.NET. Assurez-vous d'allouer correctement les ressources du serveur pour des performances optimales.

**Q3 : Est-il possible d'exporter des graphiques créés avec Aspose.Slides vers d'autres formats ?**
A3 : Absolument ! Vous pouvez exporter des présentations contenant vos graphiques personnalisés vers différents formats, tels que PDF et fichiers image, grâce aux fonctionnalités de la bibliothèque.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}