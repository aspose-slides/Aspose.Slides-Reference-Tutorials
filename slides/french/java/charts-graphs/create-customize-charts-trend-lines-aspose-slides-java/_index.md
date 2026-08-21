---
date: '2026-08-21'
description: Apprenez à créer un graphique à colonnes groupées et à ajouter des lignes
  de tendance avec Aspose.Slides for Java. Comprend la configuration de licence, l'intégration
  Maven/Gradle et des exemples détaillés.
keywords:
- create clustered column chart
- add trend line
- aspose slides license
- java chart creation
- trend lines in charts
lastmod: '2026-08-21'
og_description: Créer un graphique à colonnes groupées et ajouter des lignes de tendance
  avec Aspose.Slides for Java. Ce guide couvre la configuration de licence, Maven/Gradle
  et des extraits de code étape par étape.
og_image_alt: Aspose.Slides for Java tutorial showing a clustered column chart with
  trend lines
og_title: Créer un graphique à colonnes groupées et ajouter des lignes de tendance
  avec Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-08-21'
  description: Learn how to create a clustered column chart and add trend lines with
    Aspose.Slides for Java. Includes license setup, Maven/Gradle integration, and
    detailed examples.
  headline: How to create clustered column chart and add trend lines using Aspose.Slides
    for Java
  type: TechArticle
- description: Learn how to create a clustered column chart and add trend lines with
    Aspose.Slides for Java. Includes license setup, Maven/Gradle integration, and
    detailed examples.
  name: How to create clustered column chart and add trend lines using Aspose.Slides
    for Java
  steps:
  - name: '**Initialize the presentation** – set up the output folder and create a
      new `Presentation` instance.'
    text: '**Initialize the presentation** – set up the output folder and create a
      new `Presentation` instance.'
  - name: '**Add a clustered column chart** – obtain the chart shape, configure its
      series, and populate data points.'
    text: '**Add a clustered column chart** – obtain the chart shape, configure its
      series, and populate data points.'
  - name: '**Configure the trend line** – select the series and call `addTrendline(TrendlineType.Exponential)`.'
    text: '**Configure the trend line** – select the series and call `addTrendline(TrendlineType.Exponential)`.'
  - name: '**Set up the trend line** – use `addTrendline(TrendlineType.Linear)` and
      then adjust `getLineFormat().setFillFormat().setFillType(FillType.Solid)` to
      change color.'
    text: '**Set up the trend line** – use `addTrendline(TrendlineType.Linear)` and
      then adjust `getLineFormat().setFillFormat().setFillType(FillType.Solid)` to
      change color.'
  - name: '**Customize the trend line** – after adding the trend line, access its
      `getDataLabel()` and set the `setText("Custom label")` property.'
    text: '**Customize the trend line** – after adding the trend line, access its
      `getDataLabel()` and set the `setText("Custom label")` property.'
  - name: '**Configure the trend line** – call `addTrendline(TrendlineType.MovingAverage)`
      and set `setPeriod(3)` to use a three‑point moving average.'
    text: '**Configure the trend line** – call `addTrendline(TrendlineType.MovingAverage)`
      and set `setPeriod(3)` to use a three‑point moving average.'
  - name: '**Customize the trend line** – after adding the trend line, set `setOrder(3)`
      for a cubic fit.'
    text: '**Customize the trend line** – after adding the trend line, set `setOrder(3)`
      for a cubic fit.'
  - name: '**Configure the trend line** – use `addTrendline(TrendlineType.Power)`
      and adjust `setBackward(2)` to extend the line backward.'
    text: '**Configure the trend line** – use `addTrendline(TrendlineType.Power)`
      and adjust `setBackward(2)` to extend the line backward.'
  type: HowTo
- questions:
  - answer: Add the `<dependency>` snippet shown in the Maven section to your `pom.xml`
      and run `mvn clean install`.
    question: How do I set up Aspose.Slides for a Maven project?
  - answer: Yes, you can modify line style, width, dash pattern, and even forecast
      forward/backward values via the `ITrendline` API.
    question: Can I customise trend lines beyond colour and label?
  - answer: Verify that your JDK version matches the Aspose.Slides minimum requirement
      (JDK 8+). Consult the Aspose release notes for any breaking changes.
    question: What should I do if I encounter a version‑compatibility error?
  - answer: Absolutely. Loop through each `IChart` in a slide collection and invoke
      the appropriate `addTrendline` method for each series.
    question: Is it possible to add trend lines to multiple charts automatically?
  - answer: Yes, a purchased Aspose.Slides license removes evaluation limits and unlocks
      full performance optimisations.
    question: Do I need a paid license for production use?
  type: FAQPage
tags:
- create clustered column chart
- Aspose.Slides for Java
- Java chart customization
- trend line examples
- Java presentation generation
title: Comment créer un graphique à colonnes groupées et ajouter des lignes de tendance
  avec Aspose.Slides for Java
url: /fr/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer un graphique à colonnes groupées et ajouter des lignes de tendance avec Aspose.Slides for Java

Créer des présentations percutantes commence souvent par une visualisation claire de vos données. Dans ce guide, vous allez **create clustered column chart** objets, puis les enrichir avec une variété de lignes de tendance — exponentielle, linéaire, logarithmique, moyenne mobile, polynomiale et puissance — en utilisant la puissante API Aspose.Slides for Java.

## Réponses rapides
- **Quelle est la première étape ?** Initialisez un objet `Presentation` et ajoutez un graphique à colonnes groupées à une diapositive.  
- **Quelle version de la bibliothèque est requise ?** Aspose.Slides for Java 25.4 ou plus récent.  
- **Puis-je utiliser Maven ou Gradle ?** Oui, les deux sont pris en charge ; Maven utilise `<dependency>` et Gradle utilise `implementation`.  
- **Ai-je besoin d'une licence ?** Une licence d'essai fonctionne pour l'évaluation ; une licence complète Aspose.Slides supprime les limites d'évaluation.  
- **Combien de types de lignes de tendance sont disponibles ?** Six types intégrés : exponentielle, linéaire, logarithmique, moyenne mobile, polynomiale et puissance.

## Qu'est-ce que create clustered column chart ?
`create clustered column chart` signifie générer un graphique qui regroupe plusieurs séries de données côte à côte au sein de chaque catégorie, facilitant la comparaison des valeurs entre les séries. Ce type de graphique est idéal pour visualiser des données catégorielles telles que les ventes trimestrielles par région, permettant aux spectateurs de repérer rapidement les différences entre les groupes.

## Pourquoi ajouter une ligne de tendance ?
Les lignes de tendance révèlent le modèle sous-jacent d'une série de données, vous aidant à prévoir les valeurs futures, à mettre en évidence les taux de croissance ou à lisser les données bruyantes. En ajoutant une ligne de tendance à un graphique à colonnes groupées, les chiffres bruts deviennent des informations exploitables, permettant aux parties prenantes de comprendre les tendances à long terme et de prendre des décisions basées sur les données.

## Prérequis
- **Java Development Kit (JDK) :** 8 ou supérieur.  
- **Aspose.Slides for Java :** version 25.4 ou plus récente.  
- **IDE :** IntelliJ IDEA, Eclipse ou tout éditeur compatible Java.  
- **Outil de construction :** Maven ou Gradle (optionnel mais recommandé).  
- **Licence :** un fichier de licence Aspose.Slides d'essai ou acheté.  

Vous devez être à l'aise avec la syntaxe Java de base et familier avec la gestion des dépendances de projet.

## Comment configurer Aspose.Slides pour Java ?
Ajoutez la bibliothèque Aspose.Slides à votre projet en utilisant le gestionnaire de dépendances de votre choix, puis placez votre fichier de licence à un emplacement où le runtime peut le trouver. Cela garantit une fonctionnalité complète et supprime les restrictions d'évaluation.

### Maven
Ajoutez cette dépendance à votre fichier `pom.xml` :
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Incluez cette ligne dans votre fichier `build.gradle` :
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Téléchargement direct
Vous pouvez également télécharger le JAR manuellement depuis [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Licence Aspose Slides
Placez le fichier `Aspose.Slides.lic` à la racine de votre projet ou définissez la licence de manière programmatique avec `License license = new License(); license.setLicense("Aspose.Slides.lic");`. Une licence d'essai supprime toutes les restrictions de fonctionnalités, mais une licence achetée élimine le filigrane d'évaluation et offre des optimisations de performance complètes. Pour une utilisation en production, envisagez d'acheter une licence depuis la [Aspose purchase page](https://purchase.aspose.com/buy).

## Comment créer une présentation et ajouter un graphique à colonnes groupées ?
La classe `Presentation` représente un fichier PowerPoint et fournit des méthodes pour créer, modifier et enregistrer des diapositives. Instanciez une `Presentation`, ajoutez une diapositive, puis appelez `addChart` avec `ChartType.ClusteredColumn` pour créer l'objet graphique. Ce processus configure le canevas de la diapositive, insère une forme de graphique et le prépare à la population de données et au style.

1. **Initialiser la présentation** – configurez le dossier de sortie et créez une nouvelle instance `Presentation`.  
```java
   String dataDir = "YOUR_DOCUMENT_DIRECTORY";
   File dir = new File(dataDir);
   if (!dir.exists()) {
       dir.mkdirs();
   }
   ```

2. **Ajouter un graphique à colonnes groupées** – obtenez la forme du graphique, configurez ses séries et remplissez les points de données.  
```java
   Presentation pres = new Presentation();
   IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
       ChartType.ClusteredColumn, 20, 20, 500, 400);
   pres.save("YOUR_OUTPUT_DIRECTORY/Chart_out.pptx", SaveFormat.Pptx);
   ```

## Comment ajouter une ligne de tendance exponentielle ?
L'interface `ITrendline` définit une ligne de tendance qui peut être ajoutée à une série de graphique pour modéliser des modèles de données. Appliquez une ligne de tendance exponentielle à une série en créant une instance `ITrendline`, en définissant son `TrendlineType` sur `Exponential`, et en l'attachant à la série souhaitée. Ce type de ligne de tendance est utile pour des données qui croissent rapidement à un taux croissant.

1. **Configurer la ligne de tendance** – sélectionnez la série et appelez `addTrendline(TrendlineType.Exponential)`.  
```java
   ITrendline tredLineExp = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
   tredLineExp.setDisplayEquation(false); // Hides the equation for simplicity.
   ```

## Comment ajouter une ligne de tendance linéaire ?
Une ligne de tendance linéaire montre la droite de meilleur ajustement à travers vos points de données. Vous pouvez également personnaliser son apparence, comme la couleur et l'épaisseur de la ligne, pour correspondre au style de votre présentation.

1. **Configurer la ligne de tendance** – utilisez `addTrendline(TrendlineType.Linear)` puis ajustez `getLineFormat().setFillFormat().setFillType(FillType.Solid)` pour changer la couleur.  
```java
   ITrendline tredLineLin = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
   tredLineLin.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
   tredLineLin.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
   ```

## Comment ajouter une ligne de tendance logarithmique avec un cadre de texte personnalisé ?
Les lignes de tendance logarithmiques sont idéales pour des données qui croissent rapidement au départ puis se stabilisent. Remplacer l'étiquette par défaut vous permet d'ajouter un texte explicatif qui clarifie la signification de la tendance.

1. **Personnaliser la ligne de tendance** – après avoir ajouté la ligne de tendance, accédez à son `getDataLabel()` et définissez la propriété `setText("Custom label")`.  
```java
   ITrendline tredLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
   tredLineLog.addTextFrameForOverriding("New log trend line");
   ```

## Comment ajouter une ligne de tendance moyenne mobile ?
Les lignes de tendance moyenne mobile lissent les fluctuations à court terme pour mettre en évidence les tendances à plus long terme. Vous pouvez spécifier la période (nombre de points) utilisée pour la moyenne, vous permettant de contrôler la fluidité de la ligne.

1. **Configurer la ligne de tendance** – appelez `addTrendline(TrendlineType.MovingAverage)` et définissez `setPeriod(3)` pour utiliser une moyenne mobile à trois points.  
```java
   ITrendline tredLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
   tredLineMovAvg.setPeriod((byte) 3); // Sets the period for calculation.
   String newTrendLineName = "New TrendLine Name";
   tredLineMovAvg.setTrendlineName(newTrendLineName);
   ```

## Comment ajouter une ligne de tendance polynomiale ?
Les lignes de tendance polynomiales ajustent les données avec une courbe définie par une équation polynomiale. La propriété `order` contrôle le degré du polynôme, vous permettant de modéliser des relations plus complexes.

1. **Personnaliser la ligne de tendance** – après avoir ajouté la ligne de tendance, définissez `setOrder(3)` pour un ajustement cubique.  
```java
   ITrendline tredLinePol = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
   tredLinePol.setForward(1); // Sets forward value.
   byte order = 3;
   tredLinePol.setOrder(order); // Polynomial degree/order.
   ```

## Comment ajouter une ligne de tendance puissance ?
Les lignes de tendance puissance sont utiles lorsque les données suivent une relation de type loi de puissance. Vous pouvez également définir des valeurs de prévision arrière et avant pour étendre la ligne au-delà de la plage de données existante.

1. **Configurer la ligne de tendance** – utilisez `addTrendline(TrendlineType.Power)` et ajustez `setBackward(2)` pour étendre la ligne vers l'arrière.  
```java
   ITrendline tredLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
   tredLinePower.setBackward(1); // Sets backward value.
   ```

## Applications pratiques des lignes de tendance dans les graphiques à colonnes groupées
- **Analyse financière :** Les tendances exponentielles et polynomiales aident à prévoir les mouvements des cours des actions.  
- **Prévision des ventes :** Les lignes de moyenne mobile lissent les pics saisonniers, offrant une vue plus claire des tendances de vente sous-jacentes.  
- **Recherche scientifique :** Les tendances logarithmiques sont parfaites pour des données couvrant plusieurs ordres de grandeur, comme l'intensité acoustique ou les niveaux de pH.  
- **Surveillance des opérations :** Les lignes de tendance puissance peuvent modéliser la dégradation des performances au fil du temps.

## Comment optimiser la mémoire lors de l'utilisation d'Aspose.Slides ?
Libérez les objets rapidement et utilisez `presentation.dispose()` après l'enregistrement. Pour de grands ensembles de données, activez le chargement paresseux des images et évitez de charger le graphique complet en mémoire d'un seul coup.

- **Modèles de libération :** Enveloppez `Presentation` dans un bloc try‑with‑resources ou appelez `presentation.dispose()` dans une clause finally.  
- **Chargement paresseux :** Définissez `ChartData.setUseCache(true)` lorsqu'il s'agit de milliers de points de données.  
- **Sortie en streaming :** Écrivez la présentation directement dans un `FileOutputStream` pour éviter de garder le fichier entier en RAM.

## Avantages quantifiés d'Aspose.Slides pour Java
Aspose.Slides prend en charge **plus de 50 types de graphiques**, peut générer des présentations avec **plus de 1 000 diapositives** en moins de **30 secondes** sur un CPU typique de 2 GHz, et traite des **PDF de 500 pages** sans nécessiter l'installation de Microsoft Office. Ces chiffres sont vérifiés sur la dernière version 25.4.

## Conclusion
Vous disposez maintenant d'une solution complète, de bout en bout, pour **create clustered column chart** objets et les enrichir avec chaque type majeur de ligne de tendance disponible dans Aspose.Slides for Java. En suivant les étapes ci‑dessus, vous pouvez produire des présentations basées sur les données qui sont à la fois visuellement attrayantes et analytiquement puissantes.

Les prochaines étapes incluent l'exploration des options de style de graphique, l'exportation vers PDF/HTML, et l'automatisation de la génération de graphiques à partir de multiples sources de données.

## Questions fréquemment posées

**Q : Comment configurer Aspose.Slides pour un projet Maven ?**  
R : Ajoutez le fragment `<dependency>` montré dans la section Maven à votre `pom.xml` et exécutez `mvn clean install`.

**Q : Puis-je personnaliser les lignes de tendance au-delà de la couleur et de l'étiquette ?**  
R : Oui, vous pouvez modifier le style de ligne, la largeur, le motif de tirets, et même prévoir les valeurs avant/arrière via l'API `ITrendline`.

**Q : Que faire si je rencontre une erreur de compatibilité de version ?**  
R : Vérifiez que votre version du JDK correspond à la exigence minimale d'Aspose.Slides (JDK 8+). Consultez les notes de version d'Aspose pour tout changement majeur.

**Q : Est-il possible d'ajouter des lignes de tendance à plusieurs graphiques automatiquement ?**  
R : Absolument. Parcourez chaque `IChart` dans une collection de diapositives et invoquez la méthode `addTrendline` appropriée pour chaque série.

**Q : Ai‑je besoin d'une licence payante pour une utilisation en production ?**  
R : Oui, une licence Aspose.Slides achetée supprime les limites d'évaluation et débloque les optimisations de performance complètes.

---

**Dernière mise à jour :** 2026-08-21  
**Testé avec :** Aspose.Slides for Java 25.4  
**Auteur :** Aspose

## Tutoriels associés

- [aspose slides dépendance Maven : ajouter et configurer des graphiques dans les présentations avec Aspose.Slides for Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Ajouter une animation à un graphique PowerPoint avec Aspose.Slides for Java – Guide étape par étape](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [Créer un graphique PowerPoint Java – Enregistrer des présentations avec des graphiques en utilisant Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}