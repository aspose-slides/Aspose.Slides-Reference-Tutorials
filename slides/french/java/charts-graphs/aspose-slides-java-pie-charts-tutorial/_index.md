---
"date": "2025-04-17"
"description": "Apprenez à créer et personnaliser des graphiques à secteurs avec Aspose.Slides pour Java. Ce tutoriel couvre toutes les étapes, de la configuration à la personnalisation avancée."
"title": "Créer des graphiques à secteurs en Java avec Aspose.Slides &#58; un guide complet"
"url": "/fr/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Créer des graphiques à secteurs avec Aspose.Slides pour Java : tutoriel complet

## Introduction
Créer des présentations dynamiques et visuellement attrayantes est essentiel pour diffuser des informations percutantes. Avec Aspose.Slides pour Java, vous pouvez intégrer facilement des graphiques complexes, comme des camemberts, à vos diapositives et ainsi améliorer la visualisation des données. Ce guide complet vous guidera pas à pas dans la création et la personnalisation d'un camembert avec Aspose.Slides Java, résolvant ainsi facilement les problèmes de présentation courants.

**Ce que vous apprendrez :**
- Initialisation d'une présentation et ajout de diapositives.
- Créer et configurer un graphique à secteurs sur votre diapositive.
- Définition des titres des graphiques, des étiquettes de données et des couleurs.
- Optimiser les performances et gérer efficacement les ressources.
- Intégration d'Aspose.Slides dans des projets Java à l'aide de Maven ou Gradle.

Commençons par nous assurer que vous disposez de tous les outils et connaissances nécessaires pour suivre !

## Prérequis
Avant de plonger dans ce tutoriel, assurez-vous que la configuration suivante est prête :

### Bibliothèques, versions et dépendances requises
- **Aspose.Slides pour Java**: Assurez-vous d'avoir la version 25.4 ou ultérieure.
- **Kit de développement Java (JDK)**: La version 16 ou supérieure est requise.

### Configuration requise pour l'environnement
- Un environnement de développement avec Java installé et configuré.
- Un environnement de développement intégré (IDE) comme IntelliJ IDEA, Eclipse ou NetBeans.

### Prérequis en matière de connaissances
- Compréhension de base de la programmation Java.
- Familiarité avec Maven ou Gradle pour la gestion des dépendances.

## Configuration d'Aspose.Slides pour Java
Pour commencer à utiliser Aspose.Slides dans vos projets Java, vous devez ajouter la bibliothèque en tant que dépendance. Voici comment procéder avec différents outils de compilation :

**Maven**
Ajoutez cet extrait à votre `pom.xml` déposer:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**
Incluez les éléments suivants dans votre `build.gradle` déposer:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Téléchargement direct**
Si vous préférez ne pas utiliser d'outil de construction, téléchargez la dernière version à partir de [Versions d'Aspose.Slides pour Java](https://releases.aspose.com/slides/java/).

### Étapes d'acquisition de licence
- **Essai gratuit**:Commencez par un essai gratuit pour explorer les fonctionnalités d'Aspose.Slides.
- **Permis temporaire**:Obtenez une licence temporaire pour une utilisation prolongée sans limitations.
- **Achat**:Envisagez d’acheter si vous avez besoin d’un accès à long terme.

**Initialisation et configuration de base**
Pour commencer à utiliser Aspose.Slides, initialisez votre projet en créant un nouvel objet de présentation :
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## Guide de mise en œuvre
Décomposons maintenant le processus d’ajout et de personnalisation d’un graphique à secteurs en étapes gérables.

### Initialiser la présentation et la diapositive
Commencez par créer une nouvelle présentation et accédez à la première diapositive. Voici votre base pour créer des graphiques :
```java
import com.aspose.slides.*;

// Créer une nouvelle instance de présentation.
Presentation presentation = new Presentation();
// Accédez à la première diapositive de la présentation.
islide slides = presentation.getSlides().get_Item(0);
```

### Ajouter un graphique à secteurs à la diapositive
Insérer un graphique à secteurs dans la position spécifiée avec un ensemble de données par défaut :
```java
import com.aspose.slides.*;

// Ajoutez un graphique à secteurs à la position (100, 100) avec une taille (400, 400).
ischart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### Définir le titre du graphique
Personnalisez votre graphique en définissant et en centrant le titre :
```java
import com.aspose.slides.*;

// Ajoutez un titre au graphique à secteurs.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### Configurer les étiquettes de données pour les séries
Assurez-vous que les étiquettes de données affichent les valeurs pour plus de clarté :
```java
import com.aspose.slides.*;

// Afficher les valeurs des données sur la première série.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### Préparer une feuille de calcul de données graphiques
Configurez la feuille de calcul de données de votre graphique en effaçant les séries et les catégories existantes :
```java
import com.aspose.slides.*;

// Préparez le classeur de données du graphique.
int defaultWorksheetIndex = 0;
isChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Ajouter des catégories au graphique
Définissez des catégories pour votre graphique à secteurs :
```java
import com.aspose.slides.*;

// Ajouter de nouvelles catégories.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### Ajouter des séries et renseigner des points de données
Créez une série et remplissez-la avec des points de données :
```java
import com.aspose.slides.*;

// Ajoutez une nouvelle série et définissez son nom.
ischartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### Personnaliser les couleurs et les bordures des séries
Améliorez l'attrait visuel en définissant des couleurs et en personnalisant les bordures :
```java
import com.aspose.slides.*;

// Définissez des couleurs variées pour les secteurs de la série.
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

isChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Répétez l’opération pour d’autres points de données avec des couleurs et des styles différents.
```

### Configurer des étiquettes de données personnalisées
Affinez les étiquettes pour chaque point de données :
```java
import com.aspose.slides.*;

// Configurer des étiquettes personnalisées.
isDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

isDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);

isDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);

// Activer les lignes de repère pour les étiquettes.
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

### Définir l'angle de rotation et enregistrer la présentation
Finalisez votre graphique à secteurs en définissant un angle de rotation et en enregistrant la présentation :
```java
import com.aspose.slides.*;

// Définir l'angle de rotation.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Enregistrez la présentation dans un fichier.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## Conclusion
Dans ce tutoriel, vous avez appris à créer et personnaliser des graphiques à secteurs avec Aspose.Slides pour Java. En suivant ces étapes, vous pouvez enrichir vos présentations avec des visualisations de données attrayantes. Pour toute question ou besoin d'aide, n'hésitez pas à nous contacter.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}