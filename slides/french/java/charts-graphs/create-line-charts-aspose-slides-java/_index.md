---
"date": "2025-04-17"
"description": "Apprenez à créer des graphiques en courbes avec des marqueurs en Java avec Aspose.Slides. Ce tutoriel aborde la création de graphiques, l'ajout de séries et l'enregistrement efficace de présentations."
"title": "Créer des graphiques linéaires avec des marqueurs par défaut à l'aide d'Aspose.Slides pour Java"
"url": "/fr/java/charts-graphs/create-line-charts-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Créer des graphiques linéaires avec des marqueurs par défaut à l'aide d'Aspose.Slides pour Java
## Introduction
Créer des graphiques attrayants et informatifs est essentiel pour les présentations, les rapports et les tableaux de bord. Automatiser ce processus en développement logiciel permet de gagner du temps et de garantir la cohérence entre les documents. Ce tutoriel montre comment créer des graphiques en courbes avec des marqueurs à l'aide d'Aspose.Slides pour Java.
**Aspose.Slides pour Java** est une bibliothèque puissante qui permet aux développeurs de manipuler des présentations PowerPoint par programmation sans avoir besoin d'installer Microsoft Office. Elle simplifie des tâches telles que la création, la modification et l'exportation de diapositives, ce qui en fait un outil essentiel pour la génération automatisée de documents.
**Ce que vous apprendrez :**
- Comment initialiser Aspose.Slides pour Java
- Étapes pour créer un graphique linéaire avec des marqueurs
- Ajout de séries et de catégories aux graphiques
- Configuration des légendes des graphiques
- Sauvegarder la présentation
Prêt à vous lancer ? Commençons par tout configurer !
## Prérequis
Avant de commencer, assurez-vous que votre environnement de développement est prêt :
1. **Bibliothèques et dépendances :**
   - Bibliothèque Aspose.Slides pour Java (version 25.4 recommandée)
   - Kit de développement Java (JDK) version 16 ou supérieure
2. **Configuration de l'environnement :**
   - Votre IDE doit prendre en charge les outils de build Maven ou Gradle.
   - Assurez-vous d'avoir un fichier de licence valide si nécessaire.
3. **Prérequis en matière de connaissances :**
   - Compréhension de base de la programmation Java
   - Familiarité avec la création de projets utilisant Maven ou Gradle
Une fois ces éléments en place, configurons Aspose.Slides pour votre projet !
## Configuration d'Aspose.Slides pour Java
Pour utiliser Aspose.Slides pour Java, vous devez l'inclure comme dépendance dans votre projet. Selon que vous utilisez Maven ou Gradle, la configuration sera légèrement différente.
### Maven
Ajoutez la dépendance suivante à votre `pom.xml` déposer:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
### Gradle
Incluez ceci dans votre `build.gradle` déposer:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
### Téléchargement direct
Alternativement, vous pouvez télécharger la dernière version à partir de [Versions d'Aspose.Slides pour Java](https://releases.aspose.com/slides/java/).
**Étapes d'acquisition de la licence :**
- Pour un essai gratuit, visitez le [page d'essai gratuite](https://releases.aspose.com/slides/java/).
- Pour obtenir une licence temporaire, accédez au [page de licence temporaire](https://purchase.aspose.com/temporary-license/).
- Achetez une licence complète via leur [portail d'achat](https://purchase.aspose.com/buy).
**Initialisation de base :**
Voici comment vous pouvez initialiser Aspose.Slides dans votre application Java :
```java
import com.aspose.slides.Presentation;
// Initialiser un nouvel objet de présentation
Presentation pres = new Presentation();
```
Passons maintenant à la création de graphiques !
## Guide de mise en œuvre
### Fonctionnalité 1 : Création de graphiques avec marqueurs par défaut
Cette section explique comment créer un graphique linéaire avec des marqueurs. Cette fonctionnalité est essentielle pour visualiser efficacement les tendances des données.
#### Ajout d'un graphique linéaire
Pour ajouter un graphique linéaire avec des marqueurs :
```java
import com.aspose.slides.*;
// Accéder à la première diapositive
ISlide slide = pres.getSlides().get_Item(0);
// Ajoutez un graphique linéaire avec des marqueurs à la diapositive à la position (10, 10) avec une taille (400, 400)
IChart chart = slide.getShapes().addChart(
    ChartType.LineWithMarkers, 10, 10, 400, 400);
```
#### Séries et catégories de compensation
Pour repartir à zéro :
```java
// Effacer les séries et catégories existantes pour garantir une table rase
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Obtenez le classeur de données du graphique pour une manipulation ultérieure
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```
### Fonctionnalité 2 : Ajout de séries et de catégories
L'ajout de séries et de catégories est essentiel pour remplir vos graphiques avec des données significatives.
#### Créer une nouvelle série
Pour ajouter une nouvelle série nommée « Série 1 » :
```java
// Ajouter une nouvelle série au graphique
chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
// Accéder à la première série de population de données
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
```
#### Remplissage des catégories et des points de données
Pour ajouter des catégories et des points de données correspondants :
```java
// Ajoutez les noms de catégories et leurs points de données respectifs
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));

chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));

chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));

// Gestion élégante des points de données nuls
chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));
```
### Fonctionnalité 3 : Ajout d'une deuxième série et remplissage des points de données
L'ajout de séries supplémentaires apporte plus de profondeur à vos graphiques.
#### Création et remplissage d'une deuxième série
Pour ajouter « Série 2 » :
```java
// Ajouter une autre série nommée « Série 2 »
chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"), chart.getType());

// Accéder à la deuxième série pour la population des données
IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);

// Ajouter des points de données pour la « Série 2 »
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```
### Fonctionnalité 4 : Configuration de la légende du graphique
La configuration de la légende améliore la lisibilité du graphique.
#### Réglage des paramètres de légende
Pour configurer :
```java
// Activez la légende et configurez-la pour qu'elle ne se superpose pas aux points de données
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```
### Fonctionnalité 5 : Enregistrer la présentation
Une fois votre graphique prêt, enregistrez la présentation dans un fichier.
```java
try {
    // Enregistrer la présentation modifiée dans un répertoire spécifié
    pres.save("YOUR_DOCUMENT_DIRECTORY/DefaultMarkersInChart.pptx");
} finally {
    if (pres != null) pres.dispose();
}
```
## Applications pratiques
1. **Rapports d'activité :**
   - Utilisez des graphiques dans les rapports financiers pour illustrer les tendances au fil du temps.
2. **Analyse des données :**
   - Visualisez les modèles de données et les corrélations pendant les phases d'analyse.
3. **Matériel pédagogique :**
   - Créez des diapositives informatives pour des conférences ou des présentations universitaires.
4. **Gestion de projet :**
   - Améliorez les échéanciers des projets avec des éléments de tableau visuel.
5. **Présentations marketing :**
   - Présentez efficacement les tendances des ventes et les résultats des campagnes à l’aide de graphiques.
## Conclusion
Vous avez appris à créer des graphiques en courbes avec des marqueurs en Java avec Aspose.Slides, à ajouter des séries et des catégories, à configurer des légendes et à enregistrer des présentations. Ces compétences sont précieuses pour créer du contenu visuel dynamique dans diverses applications professionnelles.
Pour en savoir plus sur les fonctionnalités d'Aspose.Slides ou pour demander l'aide de la communauté, visitez leur [documentation officielle](https://docs.aspose.com/slides/java/) ou rejoignez des forums tels que Stack Overflow.
Bon codage !

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}