---
date: '2026-09-02'
description: Apprenez comment ajouter un graphique à colonnes groupées à une diapositive
  PowerPoint en utilisant Aspose.Slides for Java, couvrant la création du graphique,
  le formatage et l'enregistrement au format PPTX.
keywords:
- add clustered column chart
- save powerpoint as pptx
- powerpoint chart formatting
- add chart to slide
- java create chart slide
lastmod: '2026-09-02'
og_description: Apprenez comment ajouter un graphique à colonnes groupées à une diapositive
  PowerPoint en utilisant Aspose.Slides for Java, couvrant la création du graphique,
  le formatage et l'enregistrement au format PPTX.
og_image_alt: Guide showing how to add a clustered column chart to a PowerPoint slide
  with Aspose.Slides for Java
og_title: Ajouter un graphique à colonnes groupées à PPT avec Aspose.Slides Java
schemas:
- author: Aspose
  dateModified: '2026-09-02'
  description: Learn how to add clustered column chart to a PowerPoint slide using
    Aspose.Slides for Java, covering chart creation, formatting, and saving as PPTX.
  headline: Add clustered column chart to PPT using Aspose.Slides Java
  type: TechArticle
- questions:
  - answer: Replace `ChartType.ClusteredColumn` with any other enum value such as
      `ChartType.Pie`, `ChartType.Line`, or `ChartType.Bar`.
    question: How do I add different types of charts using Aspose.Slides?
  - answer: Double‑check that you’re using JDK 16 or newer and that the Maven/Gradle
      dependency version matches the library you downloaded.
    question: What should I do if I encounter compilation errors?
  - answer: Yes. Access the chart’s `getChartData()` collection, create series and
      categories, and fill them with values retrieved at runtime.
    question: Can I populate the chart with data from a database?
  - answer: Split the work into multiple `Presentation` instances, reuse chart templates,
      and always dispose of objects promptly.
    question: How can I improve performance for very large presentations?
  type: FAQPage
tags:
- add clustered column chart
- Aspose.Slides
- Java PowerPoint automation
- chart formatting
- PPTX
title: Ajouter un graphique à colonnes groupées à PPT avec Aspose.Slides Java
url: /fr/java/charts-graphs/create-format-powerpoint-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter un graphique à colonnes groupées à PPT avec Aspose.Slides Java

## Introduction
Dans ce guide, vous allez **ajouter un graphique à colonnes groupées** à une présentation PowerPoint de manière programmatique avec Aspose.Slides pour Java. Que vous créiez des rapports d’entreprise, des présentations éducatives ou des présentations marketing, l’automatisation de la création de graphiques fait gagner du temps et garantit la cohérence. Nous parcourrons la configuration de la bibliothèque, la création d’une diapositive, l’ajout du graphique, l’application de styles de ligne et de coins arrondis, puis l’enregistrement du fichier au format PPTX. À la fin, vous serez à l’aise avec le flux complet pour **ajouter un graphique à une diapositive** et même **créer des solutions PowerPoint Java**.

### Réponses rapides
- **Quelle est la classe principale pour commencer ?** `Presentation`
- **Quel type de graphique est utilisé ?** `ChartType.ClusteredColumn`
- **Comment activer les coins arrondis ?** `chart.setRoundedCorners(true);`
- **Quel format est recommandé pour l’enregistrement ?** `SaveFormat.Pptx`
- **Ai-je besoin d’une licence pour le développement ?** Un essai gratuit suffit pour les tests ; une licence achetée est requise pour la production.

## Qu’est‑ce qu’un graphique à colonnes groupées ?
Un graphique à colonnes groupées regroupe plusieurs séries de données côte à côte pour chaque catégorie, ce qui le rend idéal pour comparer des valeurs entre différents groupes. Aspose.Slides vous permet de générer ce type de graphique entièrement en code sans ouvrir PowerPoint, et vous pouvez personnaliser les couleurs, les marqueurs et les options d’axe pour correspondre à votre marque.

## Pourquoi utiliser Aspose.Slides pour Java pour ajouter un graphique à colonnes groupées ?
Vous pouvez automatiser l’ensemble du pipeline de création de graphiques sans interaction UI, indispensable pour la génération de rapports côté serveur. Aspose.Slides fonctionne sur tout système d’exploitation compatible Java, gère des présentations contenant jusqu’à 500 diapositives sans les charger entièrement, et propose plus de 50 styles de graphiques intégrés. Cela élimine les dépendances COM et vous permet d’intégrer des visuels de haute qualité directement depuis Java.

## Prérequis
- **Aspose.Slides for Java** (v25.4 ou plus récent) – prend en charge plus de 50 types de graphiques et plus de 30 formats d’image.  
- **JDK 16** (ou version ultérieure) – requis pour les dernières fonctionnalités du langage.  
- Un IDE tel qu’IntelliJ IDEA, Eclipse ou NetBeans.  

## Configuration d’Aspose.Slides pour Java
Vous pouvez ajouter la bibliothèque via Maven, Gradle ou un téléchargement direct.

### Utilisation de Maven
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Utilisation de Gradle
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Téléchargement direct
Téléchargez la dernière version depuis [versions d’Aspose.Slides pour Java](https://releases.aspose.com/slides/java/).

#### Étapes d’obtention de licence
- **Essai gratuit** – testez toutes les fonctionnalités sans limite de temps.  
- **Licence temporaire** – demandez‑en une sur le portail Aspose pour une évaluation complète des fonctionnalités.  
- **Achat** – obtenez une licence permanente pour une utilisation en production.

## Guide de mise en œuvre

### Création d’une présentation et ajout d’une diapositive
`Presentation` est l’objet principal d’Aspose.Slides qui représente un fichier PowerPoint en mémoire. Après l’avoir instancié, vous pouvez accéder, modifier ou ajouter des diapositives.

#### Vue d’ensemble
Tout d’abord, nous créons un nouvel objet `Presentation` et récupérons la diapositive par défaut fournie avec un fichier vierge.

#### Étape par étape
**1. initialiser l’objet Presentation**  
```java
Presentation presentation = new Presentation();
```  

**2. accéder à la première diapositive**  
```java
ISlide slide = presentation.getSlides().get_Item(0);
```  

**3. libérer les ressources**  
```java
if (presentation != null) presentation.dispose();
```  

### Ajout d’un graphique à une diapositive
`IChart` est l’interface qui représente tout graphique ajouté à une diapositive. En spécifiant `ChartType.ClusteredColumn`, vous indiquez à Aspose.Slides de rendre un graphique à colonnes groupées.

#### Vue d’ensemble
Nous intégrons maintenant un **graphique à colonnes groupées** dans la diapositive que nous venons de préparer.

#### Étape par étape
**1. initialiser l’objet Presentation**  
```java
Presentation presentation = new Presentation();
```  

**2. accéder à la première diapositive**  
```java
ISlide slide = presentation.getSlides().get_Item(0);
```  

**3. ajouter un graphique à colonnes groupées**  
```java
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```  

**4. libérer les ressources**  
```java
if (presentation != null) presentation.dispose();
```  

### Mise en forme du style de ligne du graphique et définition des coins arrondis
`Chart` fournit une méthode `getChartFormat()` qui renvoie un objet `ChartFormat`, que vous pouvez utiliser pour ajuster les remplissages de ligne, les styles de tiret et l’arrondissement des coins.

`Chart` est la classe concrète qui implémente `IChart` et représente un objet graphique sur une diapositive.

#### Vue d’ensemble
Améliorez l’aspect visuel en appliquant un remplissage de ligne plein, un style de ligne simple et des coins arrondis.

#### Étape par étape
**1. initialiser l’objet Presentation**  
```java
Presentation presentation = new Presentation();
```  

**2. accéder à la première diapositive**  
```java
ISlide slide = presentation.getSlides().get_Item(0);
```  

**3. ajouter un graphique à colonnes groupées**  
```java
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```  

**4. définir le format de ligne sur un type de remplissage solide**  
```java
chart.getLineFormat().getFillFormat().setFillType(FillType.Solid);
```  

**5. appliquer un style de ligne simple**  
```java
chart.getLineFormat().setStyle(LineStyle.Single);
```  

**6. activer les coins arrondis pour la zone du graphique**  
```java
chart.setRoundedCorners(true);
```  

**7. libérer les ressources**  
```java
if (presentation != null) presentation.dispose();
```  

### Enregistrement d’une présentation
`SaveFormat.Pptx` est le format recommandé pour les fichiers PowerPoint modernes, préservant tout le formatage du graphique et permettant une édition ultérieure.

#### Vue d’ensemble
Enfin, nous écrivons la présentation sur le disque au format PPTX, qui est la norme pour les opérations **enregistrer PowerPoint en PPTX**.

#### Étape par étape
**1. initialiser l’objet Presentation**  
```java
Presentation presentation = new Presentation();
```  

**2. définir le répertoire de sortie et le nom du fichier**  
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
String outputFile = dataDir + "out.pptx";
```  

**3. enregistrer la présentation au format PPTX**  
```java
presentation.save(outputFile, SaveFormat.Pptx);
```  

**4. libérer les ressources**  
```java
if (presentation != null) presentation.dispose();
```  

## Applications pratiques
- **Rapports d’entreprise** – automatiser les présentations financières trimestrielles avec des graphiques dynamiques.  
- **Contenu éducatif** – générer des diapositives de cours qui récupèrent les données d’une base de données.  
- **Présentations marketing** – visualiser les tendances produit avec des graphiques soignés et brandés.  

## Considérations de performance
- **Gestion des ressources** – appelez toujours `dispose()` ou utilisez try‑with‑resources pour libérer la mémoire native.  
- **Optimisation de la mémoire** – traitez les grands ensembles de données par lots plus petits ; Aspose.Slides peut gérer des présentations jusqu’à 500 Mo sans chargement complet.  
- **Bonnes pratiques** – privilégiez les structures de données immuables pour les séries de graphiques lorsque cela est possible ; cela réduit la pression sur le ramasse‑miettes et améliore le débit.  

## Problèmes courants et solutions

| Problème | Solution |
|----------|----------|
| **`NullPointerException` sur `getSlides()`** | Assurez‑vous que l’objet `Presentation` est correctement instancié avant d’accéder aux diapositives. |
| **Le graphique n’apparaît pas** | Vérifiez que les dimensions du graphique (x, y, largeur, hauteur) sont à l’intérieur des limites de la diapositive et que `ChartType.ClusteredColumn` est utilisé. |
| **Licence non appliquée** | Chargez votre fichier de licence avant de créer l’objet `Presentation` : `License license = new License(); license.setLicense("path/to/license.xml");` |

## Questions fréquentes

**Q : Comment ajouter différents types de graphiques avec Aspose.Slides ?**  
R : Remplacez `ChartType.ClusteredColumn` par n’importe quelle autre valeur d’énumération telle que `ChartType.Pie`, `ChartType.Line` ou `ChartType.Bar`.

**Q : Que faire si je rencontre des erreurs de compilation ?**  
R : Vérifiez que vous utilisez JDK 16 ou une version plus récente et que la version de la dépendance Maven/Gradle correspond à la bibliothèque que vous avez téléchargée.

**Q : Puis‑je remplir le graphique avec des données provenant d’une base de données ?**  
R : Oui. Accédez à la collection `getChartData()` du graphique, créez des séries et des catégories, et remplissez‑les avec les valeurs récupérées à l’exécution.

**Q : Comment améliorer les performances pour des présentations très volumineuses ?**  
R : Divisez le travail en plusieurs instances `Presentation`, réutilisez des modèles de graphiques et libérez toujours les objets rapidement.

## Conclusion
Vous disposez maintenant d’une recette complète, de bout en bout, pour **ajouter un graphique à colonnes groupées** à une diapositive PowerPoint avec Aspose.Slides pour Java. Expérimentez avec d’autres types de graphiques, liez des sources de données en direct et intégrez cette logique dans des pipelines de reporting plus larges afin d’automatiser votre flux de travail de présentation.

---

**Dernière mise à jour :** 2026-09-02  
**Testé avec :** Aspose.Slides 25.4 pour Java (JDK 16)  
**Auteur :** Aspose

## Tutoriels associés

- [Comment ajouter un graphique à PowerPoint avec Aspose.Slides pour Java : guide étape par étape](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Créer un graphique PowerPoint Java – Enregistrer des présentations avec des graphiques en utilisant Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)
- [Ajouter une animation à un graphique PowerPoint avec Aspose.Slides pour Java – guide étape par étape](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}