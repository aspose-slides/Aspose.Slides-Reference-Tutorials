---
"date": "2025-04-17"
"description": "Apprenez à créer des graphiques en nuage de points dynamiques avec Aspose.Slides pour Java. Améliorez vos présentations grâce à des fonctionnalités graphiques personnalisables."
"title": "Créez et personnalisez des graphiques en nuage de points en Java avec Aspose.Slides"
"url": "/fr/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Créez et personnalisez des graphiques en nuage de points en Java avec Aspose.Slides

Améliorez vos présentations en ajoutant des graphiques en nuage de points dynamiques en Java avec Aspose.Slides. Ce tutoriel complet vous guidera dans la configuration des répertoires, l'initialisation des présentations, la création de graphiques en nuage de points, la gestion des données graphiques, la personnalisation des types de séries et des marqueurs, et l'enregistrement de votre travail, le tout en toute simplicité.

**Ce que vous apprendrez :**
- Configuration d'un répertoire pour stocker les fichiers de présentation
- Initialisation et manipulation de présentations à l'aide d'Aspose.Slides
- Créer des graphiques en nuage de points sur des diapositives
- Gestion et ajout de données aux séries de graphiques
- Personnalisation des types de séries de graphiques et des marqueurs
- Enregistrer votre présentation avec des modifications

Commençons par nous assurer que vous disposez des prérequis nécessaires.

## Prérequis

Pour suivre ce tutoriel, assurez-vous d'avoir :
- **Aspose.Slides pour Java**:La version 25.4 ou ultérieure est requise.
- **Kit de développement Java (JDK)**: JDK 8 ou supérieur est nécessaire.
- Connaissances de base de la programmation Java et familiarité avec les outils de construction Maven ou Gradle.

## Configuration d'Aspose.Slides pour Java

Avant de commencer à coder, intégrez Aspose.Slides dans votre projet en utilisant l’une des méthodes suivantes :

### Maven
Incluez cette dépendance dans votre `pom.xml` déposer:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Ajoutez cette ligne à votre `build.gradle` déposer:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Vous pouvez également télécharger la dernière version d'Aspose.Slides pour Java à partir de [Sorties d'Aspose](https://releases.aspose.com/slides/java/).

#### Acquisition de licence
- **Essai gratuit**: Commencez par un essai gratuit de 30 jours pour découvrir les fonctionnalités.
- **Permis temporaire**:Obtenez une licence temporaire pour des tests prolongés.
- **Achat**: Achetez une licence pour un accès complet et une assistance.

Maintenant, initialisez Aspose.Slides dans votre application Java en ajoutant les importations nécessaires comme indiqué ci-dessous.

## Guide de mise en œuvre

### Configuration du répertoire
Tout d'abord, assurez-vous que notre répertoire existe pour stocker les fichiers de présentation. Cette étape permet d'éviter les erreurs lors de l'enregistrement des fichiers.

#### Créer le répertoire s'il n'existe pas
```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Créer le répertoire
    new File(dataDir).mkdirs();
}
```
Cet extrait vérifie la présence d'un répertoire spécifique et le crée s'il n'existe pas. Il utilise `File.exists()` pour vérifier la présence et `File.mkdirs()` pour créer des répertoires.

### Initialisation de la présentation

Ensuite, initialisez votre objet de présentation où vous ajouterez le graphique en nuage de points.

#### Initialisez votre présentation
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```
Ici, `new Presentation()` Crée une présentation vierge. Nous accédons directement à la première diapositive pour l'utiliser.

### Création de graphiques
La prochaine étape consiste à créer un graphique en nuage de points sur notre diapositive initialisée.

#### Ajouter un graphique à dispersion à la diapositive
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
Cet extrait de code ajoute un graphique en nuage de points avec des lignes lisses à la première diapositive. Les paramètres définissent la position et la taille du graphique.

### Gestion des données graphiques
Gérons maintenant nos données graphiques en effaçant toutes les séries existantes et en en ajoutant de nouvelles.

#### Gérer les séries de graphiques
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeries;

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Ajout d'une nouvelle série au graphique
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
```
Cette section efface les données existantes et ajoute deux nouvelles séries à notre graphique en nuage de points.

### Ajout de points de données pour les séries de dispersion
Pour visualiser nos données, nous ajoutons des points à chaque série dans le graphique en nuage de points.

#### Ajouter des points de données
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```
Nous utilisons `addDataPointForScatterSeries()` pour ajouter des points de données à notre première série. Les paramètres définissent les valeurs X et Y.

### Modification du type de série et du marqueur
Personnalisez l'apparence de votre graphique en modifiant le type et le style des marqueurs dans chaque série.

#### Personnaliser la série
```java
import com.aspose.slides.MarkerStyleType;

series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);

// Modification de la deuxième série
series = chart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```
Ces modifications ajustent le type de série pour utiliser des lignes droites et des marqueurs. Nous avons également défini la taille et le symbole du marqueur pour une meilleure distinction visuelle.

### Sauvegarde de la présentation
Enfin, enregistrez votre présentation avec toutes les modifications apportées.

#### Enregistrez votre présentation
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```
Utiliser `SaveFormat.Pptx` pour spécifier le format PowerPoint d'enregistrement de votre fichier. Cette étape est cruciale pour conserver toutes les modifications.

## Applications pratiques
Voici quelques cas d’utilisation réels :
1. **Analyse financière**:Utilisez des graphiques en nuage de points pour afficher les tendances boursières au fil du temps.
2. **Recherche scientifique**:Représente des points de données expérimentaux pour l'analyse.
3. **Gestion de projet**:Visualisez l’allocation des ressources et les indicateurs de progression.

L'intégration d'Aspose.Slides dans votre système vous permet d'automatiser la génération de rapports, améliorant ainsi la productivité et la précision.

## Considérations relatives aux performances
Pour des performances optimales :
- Gérez l'utilisation de la mémoire en supprimant les présentations après l'enregistrement.
- Utilisez des structures de données efficaces pour les grands ensembles de données.
- Minimisez les opérations gourmandes en ressources au sein des boucles.

Les meilleures pratiques garantissent une exécution fluide même avec des manipulations graphiques complexes.

## Conclusion
Dans ce tutoriel, vous avez appris à configurer des répertoires, à initialiser des présentations Aspose.Slides, à créer et personnaliser des graphiques en nuage de points, à gérer des données de séries, à modifier des marqueurs et à enregistrer votre travail. Pour explorer davantage les fonctionnalités d'Aspose.Slides, envisagez d'explorer des fonctionnalités plus avancées comme l'animation et les transitions de diapositives.

**Prochaines étapes**:Expérimentez différents types de graphiques ou intégrez ces techniques dans un projet Java plus vaste.

## FAQ

### Comment changer la couleur des marqueurs ?
Pour changer la couleur du marqueur, utilisez `series.getMarker().getFillFormat().setFillColor(ColorObject)`, où `ColorObject` est la couleur que vous désirez.

### Puis-je ajouter plus de deux séries à un graphique en nuage de points ?
Oui, vous pouvez ajouter autant de séries que nécessaire en répétant le processus d’ajout de nouvelles séries et de nouveaux points de données.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}