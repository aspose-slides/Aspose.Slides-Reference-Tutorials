---
"date": "2025-04-17"
"description": "Apprenez à créer et formater des graphiques avec Aspose.Slides pour Java. Ce guide couvre la configuration, la création de graphiques, la mise en forme et l'enregistrement de présentations."
"title": "Créer et formater des graphiques en Java à l'aide d'Aspose.Slides &#58; un guide complet"
"url": "/fr/java/charts-graphs/create-format-charts-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Créer et formater des graphiques avec Aspose.Slides en Java

## Comment créer et formater des graphiques en Java avec Aspose.Slides

### Introduction
Créer des présentations visuellement attrayantes est essentiel pour une communication efficace. Que vous soyez professionnel ou enseignant, il peut être difficile de garantir que vos visuels de données soient à la fois informatifs et esthétiques. Ce tutoriel vous guide dans leur utilisation. **Aspose.Slides pour Java** pour créer et formater des graphiques dans des présentations PowerPoint de manière transparente.

Ce guide se concentre sur la configuration de l'environnement, la création d'un graphique, la configuration des propriétés telles que les titres, la mise en forme des axes, le quadrillage, les libellés, les paramètres de légende et l'enregistrement de la présentation. En suivant ce tutoriel, vous apprendrez à :
- Configurez votre environnement avec Aspose.Slides pour Java
- Vérifier et créer des répertoires par programmation en Java
- Créer et configurer un graphique à l'aide d'Aspose.Slides
- Mettre en forme les titres des graphiques, les axes, les lignes de la grille, les étiquettes, les légendes et les arrière-plans
- Enregistrer la présentation avec des graphiques formatés

Assurons-nous que tout est configuré avant de commencer le codage.

### Prérequis
Avant de commencer, assurez-vous d’avoir :
1. **Kit de développement Java (JDK)**: Assurez-vous que JDK 8 ou supérieur est installé sur votre système.
2. **Environnement de développement intégré (IDE)**:Utilisez n’importe quel IDE compatible Java comme IntelliJ IDEA, Eclipse ou NetBeans.
3. **Aspose.Slides pour Java**:Cette bibliothèque sera au cœur de notre tutoriel.

#### Bibliothèques et dépendances requises
Pour utiliser Aspose.Slides dans votre projet, ajoutez-le via Maven ou Gradle :

**Maven**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Vous pouvez également télécharger le dernier JAR à partir de [Versions d'Aspose.Slides pour Java](https://releases.aspose.com/slides/java/).

#### Configuration requise pour l'environnement
- Installez une version récente du JDK.
- Configurez votre IDE et assurez-vous qu'il est configuré pour utiliser Maven ou Gradle (selon votre choix).
  
### Prérequis en matière de connaissances
Une compréhension de base de la programmation Java est requise. Une connaissance des principes orientés objet sera un atout.

## Configuration d'Aspose.Slides pour Java
Pour commencer à utiliser Aspose.Slides, incluez la bibliothèque dans votre projet :
1. **Ajouter une dépendance**: Incluez la dépendance Maven ou Gradle nécessaire comme indiqué ci-dessus.
2. **Acquisition de licence**:
   - Obtenir un [licence d'essai gratuite](https://purchase.aspose.com/temporary-license/) à des fins de test.
   - Pour une utilisation en production, pensez à acheter une licence complète auprès de [Site officiel d'Aspose](https://purchase.aspose.com/buy).

### Initialisation et configuration de base
Pour initialiser Aspose.Slides dans votre application Java :
```java
import com.aspose.slides.Presentation;
// Initialiser l'objet Présentation
Presentation pres = new Presentation();
```

## Guide de mise en œuvre
Cette section couvre chaque fonctionnalité étape par étape, en utilisant des sous-titres logiques pour plus de clarté.

### Configuration du répertoire
**Aperçu**: Assurez-vous que la structure de votre répertoire est en place avant d’enregistrer des graphiques dans une présentation.

#### Vérifier et créer des répertoires
```java
import java.io.File;
// Définir le répertoire cible
String dataDir = "YOUR_DOCUMENT_DIRECTORY";

// Vérifiez si le répertoire existe ; créez-le si ce n'est pas le cas
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    new File(dataDir).mkdirs(); // Créer des répertoires de manière récursive
}
```
**Explication**Cet extrait vérifie si un répertoire spécifié existe. Si ce n'est pas le cas, il crée les dossiers nécessaires.

### Création et configuration de graphiques
**Aperçu**:Nous allons créer un graphique dans PowerPoint à l’aide d’Aspose.Slides, personnaliser son apparence et l’enregistrer dans un fichier.

#### Créer une diapositive de présentation avec un graphique
```java
import com.aspose.slides.*;
// Créer une nouvelle présentation
Presentation pres = new Presentation();
try {
    // Accéder à la première diapositive
    ISlide slide = pres.getSlides().get_Item(0);

    // Ajouter un graphique à la diapositive
    IChart chart = slide.getShapes().addChart(
        ChartType.LineWithMarkers, 50, 50, 500, 400);
```
**Explication**:Nous initialisons une nouvelle présentation et ajoutons un graphique linéaire avec des marqueurs à des coordonnées spécifiques.

#### Définir le titre du graphique
```java
// Activer et formater le titre
chart.setTitle(true);
IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding()
    .getParagraphs().get_Item(0).getPortions().get_Item(0);

chartTitle.setText("Sample Chart");
chartTitle.getPortionFormat().setFontBold(NullableBool.True);
chartTitle.getPortionFormat().setFillType(FillType.Solid);
chartTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
chartTitle.getPortionFormat().setFontHeight(20);
```
**Explication**: Ce code définit et stylise le titre du graphique. La personnalisation des propriétés du texte améliore la lisibilité.

#### Format des axes
##### Formatage de l'axe vertical
```java
IChartAxis verticalAxis = chart.getAxes().getVerticalAxis();

// Formater les principales lignes de la grille
verticalAxis.getMajorGridLinesFormat().getLine()
    .setFillType(FillType.Solid)
    .getFillFormat().getSolidFillColor().setColor(Color.BLUE);
verticalAxis.getMajorGridLinesFormat().getLine().setWidth(5);

// Configurer les propriétés de l'axe
verticalAxis.setNumberFormat("0.0%");
verticalAxis.setMaxValue(15f);
verticalAxis.setMinValue(-2f);
```
**Explication**:Nous personnalisons les lignes de la grille de l'axe vertical et définissons la mise en forme numérique pour plus de clarté.

##### Formatage de l'axe horizontal
```java
IChartAxis horizontalAxis = chart.getAxes().getHorizontalAxis();

// Formater les principales lignes de la grille
horizontalAxis.getMajorGridLinesFormat().getLine()
    .setFillType(FillType.Solid)
    .getFillFormat().getSolidFillColor().setColor(Color.GREEN);
horizontalAxis.getMajorGridLinesFormat().getLine().setWidth(5);

// Définir les positions et les rotations des étiquettes
horizontalAxis.setTickLabelPosition(TickLabelPositionType.Low);
horizontalAxis.setTickLabelRotationAngle(45);
```
**Explication**:L'axe horizontal est formaté de la même manière, avec des ajustements supplémentaires pour le positionnement des étiquettes.

#### Personnaliser la légende
```java
IChartPortionFormat txtLeg = chart.getLegend().getTextFormat().getPortionFormat();
txtLeg.setFontBold(NullableBool.True);
txtLeg.getFillFormat().setFillType(FillType.Solid)
    .getSolidFillColor().setColor(Color.RED);

// Éviter le chevauchement avec la zone du graphique
chart.getLegend().setOverlay(true);
```
**Explication**:La définition des propriétés de légende garantit la clarté et évite l'encombrement visuel.

#### Configurer les arrière-plans
```java
chart.getBackWall().setThickness(1);
chart.getBackWall().getFormat().getFill()
    .setFillType(FillType.Solid)
    .getSolidFillColor().setColor(Color.ORANGE);

chart.getPlotArea().getFormat().getFill()
    .setFillType(FillType.Solid)
    .getSolidFillColor().setColor(new Color(PresetColor.LightCyan));
```
**Explication**:Les couleurs d'arrière-plan sont définies pour un attrait esthétique, améliorant l'aspect général de votre graphique.

### Enregistrer la présentation
```java
// Enregistrer la présentation sur le disque
pres.save("YOUR_OUTPUT_DIRECTORY/FormattedChart_out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose(); // Nettoyer les ressources
}
```
**Explication**:Cela garantit que toutes les modifications sont enregistrées et que les ressources sont correctement gérées.

## Applications pratiques
1. **Rapports d'activité**:Créez des rapports détaillés avec des graphiques formatés pour présenter les résultats trimestriels.
2. **Matériel pédagogique**:Développez des présentations attrayantes pour les étudiants en utilisant des visuels basés sur des données.
3. **Propositions de projets**:Améliorez les propositions en intégrant des graphiques visuellement attrayants qui mettent en évidence les indicateurs clés.
4. **Analyse marketing**:Utilisez des graphiques dans les supports marketing pour démontrer efficacement les tendances et les résultats des campagnes.
5. **Intégration du tableau de bord**:Intégrez des graphiques dans des tableaux de bord pour une visualisation des données en temps réel.

## Considérations relatives aux performances
- **Gestion de la mémoire**: Débarrassez-vous toujours des objets de présentation pour libérer rapidement les ressources.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}