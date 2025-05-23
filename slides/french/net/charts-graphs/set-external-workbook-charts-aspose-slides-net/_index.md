---
"date": "2025-04-15"
"description": "Apprenez à configurer des graphiques avec des classeurs Excel externes à l’aide d’Aspose.Slides pour .NET, améliorant ainsi vos présentations et la gestion de vos données."
"title": "Comment définir un classeur externe comme source de données de graphique dans Aspose.Slides .NET"
"url": "/fr/net/charts-graphs/set-external-workbook-charts-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment utiliser Aspose.Slides .NET pour définir un classeur externe comme source de données de graphique
## Introduction
Créer des graphiques attrayants dans les présentations est essentiel pour communiquer efficacement des informations basées sur les données. Gérer les données des graphiques séparément des fichiers de présentation peut s'avérer fastidieux. Avec Aspose.Slides pour .NET, vous pouvez lier un classeur externe comme source de données pour vos graphiques, simplifiant ainsi votre flux de travail et organisant vos données. Ce tutoriel vous guidera dans la mise en œuvre de la fonctionnalité « Définir les données du graphique à partir d'un classeur externe » avec Aspose.Slides pour .NET.

**Ce que vous apprendrez :**
- Comment utiliser Aspose.Slides pour .NET pour définir un classeur externe comme source de données pour les graphiques.
- Étapes pour ajouter et configurer un graphique dans votre présentation avec des données externes.
- Intégration des fonctionnalités d'Aspose.Slides dans vos projets .NET.

Commençons par mettre en place les prérequis nécessaires.
## Prérequis
Avant de commencer, assurez-vous d’avoir la configuration suivante :
### Bibliothèques requises
- **Aspose.Slides pour .NET**Cette bibliothèque prend en charge la création et la manipulation de présentations PowerPoint dans les applications .NET. Assurez la compatibilité avec votre environnement de développement.
### Configuration requise pour l'environnement
- Environnement de développement AC# tel que Visual Studio.
- Un classeur externe (par exemple, `externalWorkbook.xlsx`) contenant les données du graphique.
### Prérequis en matière de connaissances
- Compréhension de base de la programmation C# et des concepts du framework .NET.
- Connaissance du travail sur des présentations PowerPoint par programmation.
## Configuration d'Aspose.Slides pour .NET
Pour intégrer Aspose.Slides dans votre projet, utilisez l’une des méthodes d’installation suivantes :
**.NET CLI**
```bash
dotnet add package Aspose.Slides
```
**Gestionnaire de paquets**
```powershell
Install-Package Aspose.Slides
```
**Interface utilisateur du gestionnaire de packages NuGet**
- Ouvrez le gestionnaire de packages NuGet dans votre IDE.
- Recherchez « Aspose.Slides » et installez la dernière version.
### Acquisition de licence
Pour utiliser pleinement Aspose.Slides, vous devrez peut-être acquérir une licence. Voici comment :
- **Essai gratuit**Commencez avec une licence temporaire pour explorer toutes les fonctionnalités sans limitations.
- **Permis temporaire**:Postulez sur le site d'Aspose à des fins d'évaluation.
- **Achat**:Pour une utilisation à long terme, achetez un abonnement.
**Initialisation de base :**
```csharp
// Initialisez la licence Aspose.Slides si vous en avez une
Aspose.Slides.License license = new Aspose.Slides.License();
license.SetLicense("path_to_your_license.lic");
```
## Guide de mise en œuvre
### Définition d'un classeur externe pour un graphique
Cette fonctionnalité vous permet de lier vos données de graphique à un classeur Excel externe, garantissant que toutes les mises à jour du classeur se reflètent automatiquement dans votre présentation.
#### Étape 1 : Initialiser la présentation et ajouter un graphique
Créez une nouvelle instance de présentation et ajoutez un graphique à secteurs à la première diapositive.
```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;

public class Feature_SetExternalWorkbook {
    public static void Run() {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        using (Presentation pres = new Presentation()) {
            // Ajoutez un graphique à secteurs à la première diapositive à la position 50,50 avec une taille de 400x600
            IChart chart = pres.Slides[0].Shapes.AddChart(ChartType.Pie, 50, 50, 400, 600, false);
```
#### Étape 2 : Accéder aux données du graphique et définir un classeur externe
Accédez à la collection de données du graphique pour spécifier votre classeur externe comme source de données.
```csharp
            // Accéder aux données du graphique pour les manipuler.
            IChartData chartData = chart.ChartData;
            
            // Définissez le classeur externe qui contient les données du graphique.
            chartData.SetExternalWorkbook(dataDir + "externalWorkbook.xlsx");
```
#### Étape 3 : Ajouter des séries et des points de données à partir d'un classeur externe
Ajoutez une nouvelle série à votre graphique, en la reliant à des cellules spécifiques du classeur externe pour les catégories et les valeurs.
```csharp
            // Ajouter une nouvelle série en utilisant les données de la cellule B1 dans le classeur externe
            chartData.Series.Add(chartData.ChartDataWorkbook.GetCell(0, "B1"), ChartType.Pie);

            // Ajoutez des points de données pour la série à partir des cellules B2, B3 et B4
            chartData.Series[0].DataPoints.AddDataPointForPieSeries(
                chartData.ChartDataWorkbook.GetCell(0, "B2"));
            chartData.Series[0].DataPoints.AddDataPointForPieSeries(
                chartData.ChartDataWorkbook.GetCell(0, "B3"));
            chartData.Series[0].DataPoints.AddDataPointForPieSeries(
                chartData.ChartDataWorkbook.GetCell(0, "B4"));

            // Définir des catégories pour la série en utilisant les données des cellules A2, A3 et A4
            chartData.Categories.Add(chartData.ChartDataWorkbook.GetCell(0, "A2"));
            chartData.Categories.Add(chartData.ChartDataWorkbook.GetCell(0, "A3"));
            chartData.Categories.Add(chartData.ChartDataWorkbook.GetCell(0, "A4"));

            // Enregistrez la présentation avec le nom de fichier spécifié
            pres.Save(dataDir + "Presentation_with_externalWorkbook.pptx");
        }
    }
}
```
### Conseils de dépannage
- Assurez-vous que le chemin du classeur externe est correct et accessible.
- Vérifiez que les références de cellule dans votre code correspondent à celles de votre fichier Excel.
## Applications pratiques
Voici quelques scénarios dans lesquels la définition d’un classeur externe pour un graphique peut être incroyablement utile :
1. **Rapports financiers**: Mettez à jour automatiquement les graphiques à mesure que les données financières changent dans les feuilles de calcul.
2. **Tableaux de bord de gestion de projet**Liez les mesures de progression stockées dans des classeurs distincts aux diapositives de présentation.
3. **Analyse marketing**:Maintenez les présentations à jour avec les dernières données de performance de la campagne.
## Considérations relatives aux performances
Lorsque vous travaillez avec Aspose.Slides, tenez compte de ces conseils pour des performances optimales :
- Minimisez les appels de classeur externes en préchargeant les données nécessaires si possible.
- Utilisez des pratiques efficaces de gestion de la mémoire dans .NET pour gérer des présentations volumineuses.
- Mettez régulièrement à jour votre bibliothèque Aspose.Slides pour bénéficier d'optimisations et de corrections de bugs.
## Conclusion
En suivant ce tutoriel, vous avez appris à définir un classeur externe comme source de données de graphique avec Aspose.Slides pour .NET. Cette fonctionnalité améliore la gestion des données et garantit que vos présentations restent à jour, quelles que soient les modifications des données sous-jacentes.
**Prochaines étapes :**
- Découvrez des fonctionnalités supplémentaires d'Aspose.Slides pour améliorer davantage vos présentations.
- Expérimentez avec différents types de graphiques et configurations de données.
Nous vous encourageons à essayer d'appliquer ces techniques dans vos projets. Pour approfondir vos connaissances, plongez dans le [Documentation Aspose.Slides](https://reference.aspose.com/slides/net/) ou explorez leurs forums pour obtenir du soutien communautaire.
## Section FAQ
1. **Comment lier un classeur externe qui se trouve sur un lecteur réseau ?**
   - Assurez-vous que les autorisations et les chemins appropriés sont définis pour l'accès à partir de votre environnement d'application.
2. **Puis-je mettre à jour les données du graphique en temps réel ?**
   - Bien qu'Aspose.Slides ne prenne pas directement en charge les mises à jour en temps réel, des actualisations fréquentes peuvent simuler cet effet.
3. **Existe-t-il une limite au nombre de classeurs externes que je peux lier ?**
   - Il n'existe aucune limite inhérente, mais les performances peuvent varier en fonction des capacités de votre système et de la complexité du classeur.
4. **Comment résoudre le problème si mon graphique n’affiche pas correctement les données ?**
   - Vérifiez l’exactitude des références de cellule dans votre code par rapport à votre fichier Excel.
5. **Quels formats sont pris en charge pour les classeurs externes ?**
   - Aspose.Slides prend principalement en charge `.xlsx` fichiers, mais assurez la compatibilité en fonction des paramètres spécifiques de votre classeur.
## Ressources
- [Documentation Aspose.Slides](https://reference.aspose.com/slides/net/)
- [Télécharger Aspose.Slides](https://releases.aspose.com/slides/net/)
- [Acheter la licence Aspose.Slides](https://purchase.aspose.com/buy)
- [Essai gratuit pour évaluation](https://releases.aspose.com/slides/net/)
- [Demande de licence temporaire](https://purchase.aspose.com/temporary-license/)
- [Forum d'assistance Aspose](https://forum.aspose.com/c/slides/14)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}