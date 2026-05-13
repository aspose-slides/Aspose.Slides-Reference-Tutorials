---
date: '2026-02-19'
description: Apprenez à créer un diagramme circulaire en Java avec Aspose.Slides,
  à personnaliser les couleurs du diagramme, à ajouter des séries, à travailler avec
  la feuille de données du graphique et à définir l’angle de rotation.
keywords:
- Aspose.Slides Java
- Java pie charts
- data visualization in Java
title: Comment personnaliser les couleurs des graphiques circulaires en Java avec
  Aspose.Slides – Guide complet
url: /fr/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Créer des graphiques circulaires avec Aspose.Slides pour Java : un tutoriel complet

## Introduction
Créer des présentations dynamiques et visuellement attrayantes est essentiel pour transmettre des informations percutantes. Avec Aspose.Slides pour Java, vous pouvez intégrer sans effort des graphiques complexes comme les graphiques circulaires dans vos diapositives, **personnaliser les couleurs du graphique circulaire**, et améliorer la visualisation des données aisément. Ce guide complet vous accompagnera pas à pas dans la création et la personnalisation d’un graphique circulaire à l’aide d’Aspose.Slides Java, en résolvant facilement les défis courants de présentation.

**Ce que vous apprendrez :**
- Initialiser une présentation et ajouter des diapositives.
- Créer et configurer un graphique circulaire sur votre diapositive.
- Définir les titres du graphique, les étiquettes de données, et **personnaliser les couleurs du graphique circulaire**.
- Optimiser les performances et gérer les ressources efficacement.
- Intégrer Aspose.Slides dans des projets Java en utilisant Maven ou Gradle.

Commençons par nous assurer que vous disposez de tous les outils et connaissances nécessaires pour suivre le tutoriel !

## Réponses rapides
- **Quelle est la classe principale pour démarrer une présentation ?** `Presentation` de `com.aspose.slides`.
- **Quelle méthode ajoute un graphique circulaire à une diapositive ?** `addChart(ChartType.Pie, …)`.
- **Comment activer des couleurs variées pour chaque tranche ?** Appelez `setColorVaried(true)` sur le groupe de séries.
- **Peut-on faire pivoter le graphique circulaire ?** Oui, utilisez `setRotationAngle(double)` sur l’objet du graphique.
- **Ai-je besoin d’une licence pour une utilisation en production ?** Une licence Aspose.Slides est requise pour les déploiements commerciaux.

## Qu’est‑ce que « personnaliser les couleurs du graphique circulaire » ?
Personnaliser les couleurs du graphique circulaire consiste à attribuer des couleurs de remplissage distinctes à chaque tranche du cercle, améliorant ainsi la lisibilité et l’impact visuel. Dans Aspose.Slides, vous obtenez cela en activant les couleurs variées puis en définissant des couleurs de remplissage solides pour chaque point de données.

## Pourquoi utiliser Aspose.Slides pour Java pour créer des graphiques circulaires ?
- **Contrôle complet** de l’apparence du graphique sans besoin de Microsoft Office.
- **Compatibilité multiplateforme** – fonctionne sous Windows, Linux et macOS.
- **API riche** pour la liaison de données, le style et l’exportation vers PPTX, PDF ou images.
- **Flexibilité de licence** – commencez avec un essai gratuit et passez à la version complète lorsque vous avez besoin de toutes les fonctionnalités.

## Prérequis

Avant de plonger dans ce tutoriel, assurez-vous que votre environnement est prêt :

### Bibliothèques requises, versions et dépendances
- **Aspose.Slides for Java** : version 25.4 ou ultérieure.
- **Java Development Kit (JDK)** : version 16 ou supérieure.

### Exigences de configuration de l’environnement
- Un environnement de développement avec Java installé et configuré.
- Un environnement de développement intégré (IDE) tel qu’IntelliJ IDEA, Eclipse ou NetBeans.

### Prérequis de connaissances
- Compréhension de base de la programmation Java.
- Familiarité avec Maven ou Gradle pour la gestion des dépendances.

## Configuration d’Aspose.Slides pour Java
Pour commencer à utiliser Aspose.Slides dans vos projets Java, vous devez ajouter la bibliothèque en tant que dépendance. Voici comment procéder avec différents outils de construction :

**Maven**  
Ajoutez ce fragment à votre fichier `pom.xml` :
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
Incluez ce qui suit dans votre fichier `build.gradle` :
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Téléchargement direct**  
Si vous préférez ne pas utiliser d’outil de construction, téléchargez la dernière version depuis [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Étapes d’obtention de licence
- **Essai gratuit** : commencez avec un essai gratuit pour explorer les fonctionnalités d’Aspose.Slides.  
- **Licence temporaire** : obtenez une licence temporaire pour une utilisation prolongée sans limitations.  
- **Achat** : envisagez d’acheter si vous avez besoin d’un accès à long terme.

**Initialisation et configuration de base**  
Pour commencer à utiliser Aspose.Slides, initialisez votre projet en créant un nouvel objet présentation :
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## Guide d’implémentation
Décomposons maintenant le processus d’ajout et de personnalisation d’un graphique circulaire en étapes gérables.

### Initialiser la présentation et la diapositive
Commencez par configurer une nouvelle présentation et accéder à la première diapositive. C’est votre toile pour créer des graphiques :
```java
import com.aspose.slides.*;

// Create a new presentation instance.
Presentation presentation = new Presentation();
// Access the first slide in the presentation.
ISlide slide = presentation.getSlides().get_Item(0);
```

### Ajouter un graphique circulaire à la diapositive
Insérez un graphique circulaire à la position spécifiée avec un jeu de données par défaut :
```java
import com.aspose.slides.*;

// Add a pie chart at position (100, 100) with size (400, 400).
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### Définir le titre du graphique
Personnalisez votre graphique en définissant et centrant le titre :
```java
import com.aspose.slides.*;

// Add a title to the pie chart.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### Configurer les étiquettes de données pour la série
Assurez‑vous que les étiquettes de données affichent les valeurs pour plus de clarté :
```java
import com.aspose.slides.*;

// Show data values on the first series.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### Préparer la feuille de données du graphique
Configurez la feuille de données du graphique en supprimant les séries et catégories existantes :
```java
import com.aspose.slides.*;

// Prepare the chart data workbook.
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Ajouter des catégories au graphique
Définissez les catégories pour votre graphique circulaire :
```java
import com.aspose.slides.*;

// Add new categories.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### Ajouter une série et remplir les points de données
Créez une série et remplissez‑la avec des points de données – c’est ici que nous **ajoutons une série de graphique** :
```java
import com.aspose.slides.*;

// Add a new series and set its name.
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### Personnaliser les couleurs et les bordures de la série
Améliorez l’aspect visuel en définissant les couleurs et en personnalisant les bordures – cela **personnalise directement les couleurs du graphique circulaire** :
```java
import com.aspose.slides.*;

// Set varied colors for the series sectors.
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Repeat for other data points with different colors and styles.
```

### Configurer les étiquettes de données personnalisées
Affinez les étiquettes pour chaque point de données :
```java
import com.aspose.slides.*;

// Configure custom labels.
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

IDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);

IDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);

// Enable leader lines for labels.
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

### Définir l’angle de rotation et enregistrer la présentation
Finalisez votre graphique circulaire en **définissant l’angle de rotation** et en enregistrant le fichier :
```java
import com.aspose.slides.*;

// Set rotation angle.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Save the presentation to a file.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## Problèmes courants et solutions
| Problème | Cause | Solution |
|----------|-------|----------|
| **Les tranches apparaissent toutes de la même couleur** | `setColorVaried(true)` non appelé | Assurez‑vous d’activer les couleurs variées sur le groupe de séries. |
| **Les étiquettes de données ne s’affichent pas** | drapeau `showValue` désactivé | Appelez `setShowValue(true)` sur le format d’étiquette approprié. |
| **La rotation n’a aucun effet** | Utilisation d’une version plus ancienne d’Aspose.Slides | Mettez à jour vers la version 25.4 ou ultérieure. |
| **Exception de licence à l’exécution** | Fichier de licence manquant ou invalide | Chargez votre licence avec `License license = new License(); license.setLicense("Aspose.Slides.lic");` avant de créer le `Presentation`. |

## Questions fréquentes

**Q : Comment obtenir une licence Aspose.Slides pour Java ?**  
R : Vous pouvez demander un essai gratuit sur le site Aspose, puis acheter une licence permanente. Chargez‑la à l’exécution comme indiqué dans le tableau des problèmes courants.

**Q : Puis‑je utiliser ce code avec des versions plus anciennes du JDK ?**  
R : L’API nécessite JDK 16 ou supérieur ; les versions antérieures ne sont pas prises en charge.

**Q : Est‑il possible d’exporter le graphique sous forme d’image au lieu de PPTX ?**  
R : Oui, appelez `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);` après le rendu.

**Q : Que faire si je dois ajouter plus d’une série à un graphique circulaire ?**  
R : Les graphiques circulaires affichent généralement une seule série ; pour plusieurs séries, envisagez un graphique en anneau à la place.

**Q : La bibliothèque fonctionne‑t‑elle sur des serveurs Linux ?**  
R : Absolument – Aspose.Slides pour Java est indépendant de la plateforme et s’exécute sur tout OS disposant d’un JDK compatible.

---

**Dernière mise à jour :** 2026-02-19  
**Testé avec :** Aspose.Slides for Java 25.4 (jdk16)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}