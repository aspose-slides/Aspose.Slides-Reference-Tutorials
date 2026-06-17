---
date: '2026-06-03'
description: Apprenez comment ajouter des graphiques avec la aspose slides maven dependency,
  configurer les étiquettes de données et générer des graphiques dynamiques dans les
  présentations Java.
keywords:
- aspose slides maven dependency
- how to add charts
- add data labels chart
- dynamic chart generation
- create presentation chart
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to add charts with the aspose slides maven dependency, configure
    data labels, and generate dynamic charts in Java presentations.
  headline: 'aspose slides maven dependency: Add and Configure Charts in Presentations
    Using Aspose.Slides for Java'
  type: TechArticle
- description: Learn how to add charts with the aspose slides maven dependency, configure
    data labels, and generate dynamic charts in Java presentations.
  name: 'aspose slides maven dependency: Add and Configure Charts in Presentations
    Using Aspose.Slides for Java'
  steps:
  - name: Add the aspose slides maven dependency
    text: '**Maven:** xml <dependency> <groupId>com.aspose</groupId> <artifactId>aspose-slides</artifactId>
      <version>25.4</version> <classifier>jdk16</classifier> </dependency> **Gradle:**
      gradle implementation group: ''com.aspose'', name: ''aspose-slides'', version:
      ''25.4'', classifier: ''jdk16'' These snippets pull'
  - name: Load the presentation and insert a Bubble Chart
    text: '**Implementation:** java import com.aspose.slides.Presentation; /* The
      `Presentation` class represents a PowerPoint file and provides access to its
      slides and content. */ String dataDir = "YOUR_DOCUMENT_DIRECTORY"; Presentation
      pres = new Presentation(dataDir + "/chart2.pptx"); try { // Modification'
  - name: Configure the chart’s data series and labels
    text: '**Implementation:** java import com.aspose.slides.IChart; import com.aspose.slides.ISlide;
      import com.aspose.slides.Presentation; import com.aspose.slides.ChartType; /*
      `IChart` is the interface for chart objects, allowing manipulation of series,
      axes, and formatting. */ Presentation pres = new Pres'
  - name: Save the modified presentation
    text: '**Implementation:** java import com.aspose.slides.IChartDataWorkbook; import
      com.aspose.slides.IChartSeriesCollection; /* `IChartDataWorkbook` represents
      the internal workbook that stores chart data and cell references. */ IChartSeriesCollection
      series = chart.getChartData().getSeries(); series.get_'
  type: HowTo
- questions:
  - answer: Yes, the `ChartType` enumeration includes line, bar, pie, radar, stock,
      and more than 70 additional types.
    question: Can I add other chart types besides Bubble?
  - answer: Absolutely; it is fully compatible with OpenJDK 8‑21 and runs on all major
      operating systems.
    question: Does the aspose slides maven dependency work with OpenJDK?
  - answer: Load the Excel workbook with `WorkbookFactory.create(new FileInputStream("data.xlsx"))`,
      then bind the chart’s `ChartDataWorkbook` to the workbook before setting cell
      references.
    question: How do I embed a chart from an existing Excel file?
  - answer: Practically no—Aspose.Slides can handle dozens of charts per slide, limited
      only by available memory.
    question: Is there a limit to the number of charts per slide?
  - answer: PPTX, PPT, ODP, PDF, XPS, HTML, and even image formats such as PNG and
      JPEG are supported.
    question: What format can I export the final presentation to?
  type: FAQPage
title: 'aspose slides maven dependency : Ajouter et configurer des graphiques dans
  les présentations avec Aspose.Slides for Java'
url: /fr/java/charts-graphs/add-charts-aspose-slides-java-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# aspose slides maven dependency : Ajouter et configurer des graphiques dans les présentations avec Aspose.Slides pour Java

## Introduction
Le **aspose slides maven dependency** permet aux développeurs Java de créer, modifier et enrichir des fichiers PowerPoint de manière programmatique, sans jamais ouvrir PowerPoint lui‑même. Dans de nombreux scénarios professionnels et académiques, l’insertion manuelle de graphiques est chronophage et sujette aux erreurs. Ce tutoriel vous montre, étape par étape, comment ajouter un graphique à bulles, lier les étiquettes de données à des cellules de feuille de calcul, et enregistrer le résultat — le tout en tirant parti du aspose slides maven dependency de façon propre et reproductible.

**Ce que vous apprendrez**
- Comment ajouter des graphiques avec le aspose slides maven dependency
- Configurer un projet Java avec Maven ou Gradle
- Charger une présentation existante et insérer un graphique à bulles
- Configurer les étiquettes de données à l’aide de références de cellules (add data labels chart)
- Enregistrer le fichier mis à jour pour une distribution ultérieure
- Cas d’utilisation concrets tels que la génération dynamique de graphiques et les flux de travail de création de graphiques de présentation

## Réponses rapides
- **Quel artefact Maven ajoute les capacités de graphiques ?** `com.aspose:aspose-slides:25.4` (ou la dernière version)  
- **Puis‑je lier les étiquettes de données à des cellules de type Excel ?** Oui – utilisez `ChartDataLabel` avec `setDataLabelFormat` et des références de cellules.  
- **Une licence est‑elle requise pour la production ?** Une licence complète supprime le filigrane d’évaluation et débloque toutes les fonctionnalités.  
- **Cela fonctionne‑t‑il avec Java 11+ ?** Absolument ; la bibliothèque est compatible avec Java 8 jusqu’à Java 21.  
- **Combien de types de graphiques sont pris en charge ?** Plus de 70 types de graphiques distincts, y compris les graphiques à bulles, radar et boursiers.

## Qu’est‑ce que le aspose slides maven dependency ?
Le **aspose slides maven dependency** est un paquet compatible Maven qui fournit une API complète pour créer et modifier des fichiers PowerPoint (PPTX, PPT, ODP) en Java. En ajoutant cette dépendance à votre `pom.xml` ou `build.gradle`, vous accédez à plus de 70 types de graphiques, plus de 150 mises en page de diapositives, et la possibilité de manipuler formes, animations et métadonnées sans qu’Office soit installé.

## Pourquoi utiliser le aspose slides maven dependency pour l’automatisation des graphiques ?
Aspose.Slides traite des présentations de plusieurs milliers de diapositives en moins d’une seconde sur du matériel serveur standard, prend en charge **plus de 70 types de graphiques**, et peut rendre des présentations jusqu’à **10 000 diapositives** sans charger le fichier complet en mémoire. Ces capacités quantifiées le rendent idéal pour la génération dynamique de graphiques à l’échelle d’entreprise, où performance et évolutivité sont non négociables.

## Prérequis
- **Java Development Kit (JDK)** 8 ou plus récent (Java 11+ recommandé).  
- **Maven** 3.6+ **ou** **Gradle** 6+.  
- Bibliothèque **Aspose.Slides for Java** (le aspose slides maven dependency, version 25.4 ou ultérieure).  
- Familiarité de base avec les collections Java et les I/O de fichiers.  
- Un fichier de licence d’évaluation ou complet (`license.json`) si vous prévoyez d’exécuter le code au‑delà de la période d’essai.

## Comment ajouter un graphique à une diapositive avec Aspose.Slides ?
Chargez la présentation cible, créez une nouvelle forme de graphique sur la diapositive souhaitée, et spécifiez le type de graphique (Bulles dans cet exemple). L’opération complète peut être réalisée en **trois lignes de code concises** une fois la bibliothèque référencée, ce qui la rend parfaite pour le prototypage rapide et les pipelines de production.

### Étape 1 : Ajouter le aspose slides maven dependency
**Maven :**  
```text
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
```  
**Gradle :**  
```text
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
```  
Ces extraits récupèrent l’API complète d’Aspose.Slides—y compris la prise en charge des graphiques—directement depuis Maven Central.

### Étape 2 : Charger la présentation et insérer un graphique à bulles
**Implémentation :**  
```text
```java
import com.aspose.slides.Presentation;

/* The `Presentation` class represents a PowerPoint file and provides access to its slides and content. */
String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/chart2.pptx");
try {
    // Modifications will be done here
} finally {
    if (pres != null) pres.dispose();
}
```
```  

### Étape 3 : Configurer les séries de données du graphique et les étiquettes
**Implémentation :**  
```text
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;

/* `IChart` is the interface for chart objects, allowing manipulation of series, axes, and formatting. */
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(
        ChartType.Bubble, 50, 50, 600, 400, true
    );
} finally {
    if (pres != null) pres.dispose();
}
```
```  

### Étape 4 : Enregistrer la présentation modifiée
**Implémentation :**  
```text
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeriesCollection;

/* `IChartDataWorkbook` represents the internal workbook that stores chart data and cell references. */
IChartSeriesCollection series = chart.getChartData().getSeries();
series.get_Item(0).getLabels()
    .getDefaultDataLabelFormat()
    .setShowLabelValueFromCell(true);

String lbl0 = "Label 0 cell value";
String lbl1 = "Label 1 cell value";
String lbl2 = "Label 2 cell value";
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
series.get_Item(0).getLabels()
    .get_Item(0).setValueFromCell(wb.getCell(0, "A10", lbl0));
series.get_Item(0).getLabels()
    .get_Item(1).setValueFromCell(wb.getCell(0, "A11", lbl1));
series.get_Item(0).getLabels()
    .get_Item(2).setValueFromCell(wb.getCell(0, "A12", lbl2));
```
```  

## Comment configurer les étiquettes de données à l’aide de références de cellules ?
Les étiquettes de données peuvent être liées à des valeurs de cellules externes, reproduisant la fonction Excel « Link to Cell ». Cette approche élimine les valeurs codées en dur et permet une **génération dynamique de graphiques** où le contenu des étiquettes se met à jour automatiquement dès que les données sous‑jacentes changent. En liant chaque étiquette à une cellule de classeur spécifique, vous garantissez que toute modification des données sources se reflète instantanément dans la présentation, réduisant ainsi les efforts de maintenance et le risque d’informations obsolètes.

### Réponse directe
Appelez `chart.getSeries().get_Item(0).getDataPoints().get_Item(i).getLabel().setDataLabelFormat(...)` et transmettez un `DataLabelFormat` qui référence une adresse de cellule telle que `"Sheet1!A2"`. Aspose.Slides résout la référence à l’exécution, insérant la valeur actuelle de la cellule dans l’étiquette du graphique.

### Étape par étape
1. Identifiez la série que vous souhaitez étiqueter.  
2. Récupérez l’objet `IDataLabel` pour chaque point de données.  
3. Utilisez `setDataLabelFormat` avec un `DataLabelFormat` configuré pour `CellReference`.  
4. Personnalisez éventuellement la police, la couleur et les options d’affichage.

## Comment enregistrer la présentation modifiée ?
L’enregistrement se fait en un seul appel de méthode qui écrit l’objet `Presentation` en mémoire vers un chemin de fichier ou un flux de sortie. Vous pouvez également choisir le format de sortie (PPTX, PDF, ODP) en passant l’énumération `SaveFormat` appropriée. Cette opération diffuse le résultat directement sur le disque, libérant toutes les ressources natives automatiquement lorsque l’instance `Presentation` est fermée ou sort de portée, ce qui aide à maintenir une faible consommation de mémoire même pour de gros decks.

### Réponse directe
Appelez `presentation.save("output.pptx", SaveFormat.Pptx)` ; la bibliothèque diffuse le résultat directement sur le disque, libérant toutes les ressources natives automatiquement lorsque l’instance `Presentation` est fermée ou sort de portée.

## Applications pratiques
1. **Rapports d’entreprise** : Générer automatiquement des graphiques de ventes trimestrielles à partir d’un dump de base de données.  
2. **Cours académiques** : Intégrer des données de recherche en direct dans les diapositives de cours pour chaque session.  
3. **Présentations commerciales** : Construire des tableaux de bord de performance spécifiques au client à la volée.  
4. **Gestion de projet** : Visualiser des chronologies de type Gantt avec des étiquettes de données dynamiques.  
5. **Analyse marketing** : Intégrer les KPI de campagne dans des présentations qui se mettent à jour dès l’arrivée de nouvelles métriques.

## Considérations de performance
- **Gestion de la mémoire** : Utilisez try‑with‑resources ou appelez explicitement `presentation.dispose()` pour libérer rapidement la mémoire native.  
- **Jeux de données volumineux** : Lors du traitement de plus de 10 000 points de données, remplissez les données du graphique via `ChartDataWorkbook` afin d’éviter de charger l’ensemble du jeu de données dans des objets Java.  
- **Sécurité des threads** : Chaque thread doit travailler avec sa propre instance `Presentation` ; l’API n’est pas thread‑safe pour des objets partagés.  

## Problèmes courants et solutions
- **Problème** : « License file not found. »  
  **Solution** : Placez `license.json` dans le classpath et appelez `License license = new License(); license.setLicense("license.json");` avant toute utilisation de l’API.  
- **Problème** : Le graphique apparaît vide après l’enregistrement.  
  **Solution** : Assurez‑vous que le classeur de données du graphique est enregistré avec la présentation (`presentation.getCharts().setDataWorkbook(chartWorkbook);`).  
- **Problème** : Les étiquettes de données affichent des erreurs « #REF! ».  
  **Solution** : Vérifiez que la chaîne de référence de cellule correspond exactement au nom de la feuille et à l’adresse, et que le classeur référencé est bien attaché au graphique.  

## Questions fréquentes

**Q : Puis‑je ajouter d’autres types de graphiques que le Bulles ?**  
R : Oui, l’énumération `ChartType` comprend ligne, barre, secteur, radar, boursier, et plus de 70 types supplémentaires.

**Q : Le aspose slides maven dependency fonctionne‑t‑il avec OpenJDK ?**  
R : Absolument ; il est entièrement compatible avec OpenJDK 8‑21 et fonctionne sur tous les principaux systèmes d’exploitation.

**Q : Comment intégrer un graphique à partir d’un fichier Excel existant ?**  
R : Chargez le classeur Excel avec `WorkbookFactory.create(new FileInputStream("data.xlsx"))`, puis liez le `ChartDataWorkbook` du graphique au classeur avant de définir les références de cellules.

**Q : Y a‑t‑il une limite au nombre de graphiques par diapositive ?**  
R : Pratiquement aucune — Aspose.Slides peut gérer des dizaines de graphiques par diapositive, limité uniquement par la mémoire disponible.

**Q : Vers quels formats puis‑je exporter la présentation finale ?**  
R : PPTX, PPT, ODP, PDF, XPS, HTML, ainsi que des formats image tels que PNG et JPEG sont pris en charge.

## Ressources
- [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) – téléchargez les derniers binaires de la bibliothèque.  
- [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/) – référence API complète et guides.  
- [Download Aspose.Slides for Java](https://releases.aspose.com/slides/java/) – page de téléchargement directe des paquets Maven/Gradle.  
- [Purchase a License](https://purchase.aspose.com/buy) – obtenez une licence commerciale complète.  
- [Free Trial](https://releases.aspose.com/slides/java/) – commencez avec un essai pour évaluer les fonctionnalités.  
- [Temporary License](https://purchase.aspose.com/temporary-license/) – demandez une clé temporaire pour une évaluation prolongée.  
- [Aspose Support Forum](https://forum.aspose.com/c/slides/11) – obtenez de l’aide de la communauté et des ingénieurs Aspose.

## Conclusion
Vous disposez maintenant d’un guide complet, de bout en bout, pour utiliser le **aspose slides maven dependency** afin d’ajouter, configurer et persister des graphiques dans des présentations Java. En suivant les étapes ci‑dessus, vous pouvez automatiser la création de graphiques, lier les étiquettes de données à des valeurs de cellules en direct, et générer des présentations de qualité professionnelle à grande échelle. Expérimentez avec d’autres types de graphiques, explorez les API d’animation, et intégrez ce flux de travail à vos pipelines de reporting pour un impact maximal.

---  
**Dernière mise à jour :** 2026-06-03  
**Testé avec :** Aspose.Slides for Java 25.4  
**Auteur :** Aspose

```java
import com.aspose.slides.SaveFormat;

String outputDir = "YOUR_OUTPUT_DIRECTORY";
pres.save(outputDir + "/resultchart.pptx", SaveFormat.Pptx);
```

## Tutoriels associés

- [How to Create and Configure Presentations with Aspose.Slides Java&#58; A Step-by-Step Guide](/slides/java/getting-started/create-configure-presentation-aspose-slides-java/)
- [Create PPTX Java with Aspose.Slides Maven – Automation Guide](/slides/java/batch-processing/aspose-slides-java-automate-presentation-management/)
- [How to Create Chart in Java with Aspose.Slides: A Comprehensive Guide](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}