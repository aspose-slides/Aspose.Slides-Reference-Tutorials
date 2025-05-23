---
"date": "2025-04-15"
"description": "Apprenez à ajouter par programmation des graphiques à secteurs à vos présentations avec Aspose.Slides pour .NET, améliorant ainsi la visualisation des données sans effort."
"title": "Créer un graphique à secteurs dans PowerPoint à l'aide d'Aspose.Slides pour .NET"
"url": "/fr/net/charts-graphs/create-pie-chart-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment créer et ajouter un graphique à secteurs à une présentation avec Aspose.Slides pour .NET
## Introduction
Créer des présentations convaincantes ne se limite souvent pas à du texte ; des éléments visuels comme des graphiques peuvent considérablement améliorer l'impact de votre narration de données. Si vous souhaitez intégrer des diagrammes circulaires dynamiques à vos présentations PowerPoint par programmation, **Aspose.Slides pour .NET** est un outil puissant qui simplifie et simplifie cette tâche. Ce tutoriel vous guidera dans l'ajout d'un graphique à secteurs à une diapositive de présentation et sa configuration avec des sources de données externes.

### Ce que vous apprendrez
- Comment créer une nouvelle présentation avec Aspose.Slides pour .NET
- Ajouter un graphique à secteurs à votre première diapositive
- Définition d'une URL de classeur externe comme source de données pour votre graphique
- Enregistrer votre présentation au format PPTX
Voyons comment vous pouvez y parvenir facilement, en commençant par les prérequis.
## Prérequis
Avant de commencer, assurez-vous d’avoir les éléments suivants à disposition :
- **Aspose.Slides pour .NET** Bibliothèque installée. Vous aurez besoin d'une version compatible avec .NET Framework ou .NET Core/.NET 5+.
- Connaissances de base de la programmation C# et familiarité avec Visual Studio IDE.
- Un environnement de développement configuré sur votre machine (Windows, macOS ou Linux).
## Configuration d'Aspose.Slides pour .NET
### Instructions d'installation
Aspose.Slides pour .NET peut être ajouté à votre projet à l'aide de différentes méthodes :
**.NET CLI**
```shell
dotnet add package Aspose.Slides
```
**Console du gestionnaire de paquets**
```powershell
Install-Package Aspose.Slides
```
**Interface utilisateur du gestionnaire de packages NuGet**
1. Ouvrez le gestionnaire de packages NuGet dans Visual Studio.
2. Recherchez « Aspose.Slides ».
3. Installez la dernière version.
### Acquisition de licence
Pour utiliser Aspose.Slides, vous pouvez commencer par une licence d'essai gratuite afin d'explorer ses fonctionnalités sans limites. Pour les environnements de production, envisagez l'achat d'une licence commerciale ou d'une licence temporaire pour des tests prolongés. Visitez [Page d'achat d'Aspose](https://purchase.aspose.com/buy) pour plus de détails.
### Initialisation de base
Pour utiliser Aspose.Slides dans votre projet, vous devez l'initialiser avec votre licence si disponible :
```csharp
// Initialiser la bibliothèque
License license = new License();
license.SetLicense("path/to/your/license.lic");
```
## Guide de mise en œuvre
Maintenant que vous êtes configuré, parcourons chaque fonctionnalité étape par étape.
### Créer et ajouter un graphique à une présentation
#### Aperçu
Nous commencerons par créer une présentation et ajouter un graphique à secteurs à la première diapositive.
#### Mesures:
1. **Initialiser la présentation**
   Commencez par créer une instance du `Presentation` classe, qui représente votre fichier PowerPoint.
   ```csharp
   using Aspose.Slides;
   
   string dataDir = "YOUR_DOCUMENT_DIRECTORY";
   
   using (Presentation pres = new Presentation())
   {
       // C'est ici que nous ajouterons notre graphique.
   }
   ```
2. **Ajouter un graphique à secteurs**
   Utilisez le `Shapes.AddChart` méthode pour insérer un graphique à secteurs à des coordonnées spécifiques sur votre diapositive.
   ```csharp
   IChart chart = pres.Slides[0].Shapes.AddChart(
       ChartType.Pie, 50, 50, 400, 600, true);
   ```
### Définir un classeur externe pour les données du graphique
#### Aperçu
Configurons maintenant le graphique à secteurs pour utiliser les données d’un classeur externe.
#### Mesures:
1. **Accéder aux données du graphique**
   Récupérez l'interface de données du graphique où vous spécifierez l'URL de votre source de données externe.
   ```csharp
   IChartData chartData = chart.ChartData;
   ```
2. **Définir l'URL du classeur externe**
   Définissez l'URL de votre source de données à l'aide de `SetExternalWorkbook`Cet exemple utilise une URL d'espace réservé, qui doit être remplacée par le chemin réel de votre source de données.
   ```csharp
   (chartData as ChartData).SetExternalWorkbook("http://chemin/n'existe/pas", false);
   ```
### Enregistrer la présentation dans un fichier
#### Aperçu
Enfin, enregistrez la présentation au format PPTX à l’emplacement souhaité.
#### Mesures:
1. **Enregistrer la présentation**
   Utilisez le `Save` méthode de la `Presentation` classe pour écrire le fichier sur le disque.
   ```csharp
   pres.Save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
   ```
## Applications pratiques
- **Rapports d'activité**:Générer automatiquement des graphiques pour les évaluations de performance trimestrielles.
- **Tableaux de bord de données**: Intégrez-vous aux sources de données pour mettre à jour les rapports visuels en temps réel.
- **Contenu éducatif**: Créez des présentations dynamiques qui extraient les dernières données d’études externes ou de documents de recherche.
En intégrant Aspose.Slides, vous pouvez automatiser et améliorer votre processus de création de présentations dans divers domaines.
## Considérations relatives aux performances
Lorsque vous travaillez avec de grands ensembles de données ou de nombreux graphiques :
- Optimisez l’utilisation des ressources en gérant efficacement la mémoire dans .NET.
- Jeter `Presentation` objets correctement pour libérer des ressources.
- Utilisez des opérations asynchrones lorsque cela est possible pour améliorer la réactivité de l’application.
## Conclusion
En suivant ce tutoriel, vous avez appris à créer par programmation des présentations avec des graphiques à secteurs grâce à Aspose.Slides pour .NET. Vous disposez désormais des outils nécessaires pour automatiser la création de graphiques et gérer efficacement les sources de données externes.
### Prochaines étapes
Explorez davantage en personnalisant les styles de graphiques, en ajoutant davantage de types de graphiques ou en intégrant d'autres composants Aspose comme Aspose.Cells pour des capacités de manipulation de données améliorées.
## Section FAQ
1. **Qu'est-ce qu'Aspose.Slides ?**  
   Une bibliothèque robuste pour manipuler des présentations PowerPoint par programmation dans .NET.
2. **Puis-je utiliser Aspose.Slides sans licence ?**  
   Oui, mais avec certaines limitations. Envisagez un essai gratuit ou l'achat d'une licence pour bénéficier de toutes les fonctionnalités.
3. **Comment mettre à jour les données d'un graphique de manière dynamique ?**  
   Utilisez des classeurs externes et définissez leurs URL dans le `SetExternalWorkbook` méthode.
4. **Aspose.Slides peut-il être utilisé sur plusieurs plates-formes ?**  
   Oui, il prend en charge .NET Framework et .NET Core/.NET 5+ sur Windows, macOS et Linux.
5. **Quels autres types de graphiques sont pris en charge ?**  
   En plus des graphiques à secteurs, vous pouvez créer des graphiques à barres, des graphiques linéaires et bien plus encore avec Aspose.Slides.
## Ressources
- [Documentation Aspose.Slides](https://reference.aspose.com/slides/net/)
- [Télécharger la dernière version](https://releases.aspose.com/slides/net/)
- [Licence d'achat](https://purchase.aspose.com/buy)
- [Essai gratuit](https://releases.aspose.com/slides/net/)
- [Permis temporaire](https://purchase.aspose.com/temporary-license/)
- [Forum d'assistance](https://forum.aspose.com/c/slides/11)
Commencez dès aujourd'hui à intégrer Aspose.Slides dans vos projets pour améliorer et automatiser vos présentations PowerPoint !

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}