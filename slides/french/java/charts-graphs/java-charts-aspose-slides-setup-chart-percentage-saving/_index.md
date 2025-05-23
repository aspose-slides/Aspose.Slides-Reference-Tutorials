---
"date": "2025-04-17"
"description": "Apprenez à créer, personnaliser et enregistrer des graphiques avec des étiquettes de pourcentage dans des présentations Java avec Aspose.Slides. Améliorez vos compétences en présentation dès aujourd'hui !"
"title": "Créer et personnaliser des graphiques dans des présentations Java avec Aspose.Slides"
"url": "/fr/java/charts-graphs/java-charts-aspose-slides-setup-chart-percentage-saving/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Créer et personnaliser des graphiques dans des présentations Java avec Aspose.Slides

## Introduction
Créer des présentations percutantes ne se limite pas à du texte ; il faut également des graphiques dynamiques qui transmettent efficacement l'information. Si vous souhaitez enrichir vos présentations Java avec des fonctionnalités graphiques sophistiquées grâce à Aspose.Slides, ce tutoriel est fait pour vous. Nous vous guiderons dans la création d'une présentation, l'ajout et la configuration de graphiques, le calcul des totaux, l'affichage des pourcentages et l'enregistrement de votre travail, le tout en quelques étapes simples.

**Ce que vous apprendrez :**
- Comment créer et personnaliser des présentations avec des graphiques à l'aide d'Aspose.Slides pour Java
- Calcul des totaux des catégories dans les graphiques
- Affichage des données sous forme d'étiquettes de pourcentage sur les graphiques
- Enregistrement de présentations avec des fonctionnalités graphiques améliorées

Plongeons dans les prérequis dont vous avez besoin avant de commencer.

## Prérequis
Pour suivre ce tutoriel, assurez-vous de disposer des éléments suivants :

- **Kit de développement Java (JDK)**:Version 8 ou supérieure.
- **IDE**: Tels qu'IntelliJ IDEA, Eclipse ou tout autre IDE pris en charge par Java.
- **Bibliothèque Aspose.Slides pour Java**: Ceci est crucial pour gérer les fonctionnalités de présentation.

### Bibliothèques et versions requises
Vous aurez besoin d'Aspose.Slides pour Java. Voici comment l'inclure dans votre projet :

**Expert :**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle :**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Alternativement, vous pouvez télécharger directement la dernière version à partir de [Versions d'Aspose.Slides pour Java](https://releases.aspose.com/slides/java/).

### Configuration de l'environnement
Assurez-vous que votre environnement de développement est configuré pour utiliser JDK 8 ou une version ultérieure et que votre IDE est configuré pour gérer les dépendances à l'aide de Maven ou Gradle.

**Acquisition de licence :**
- **Essai gratuit**:Accédez aux fonctionnalités de base à des fins de test.
- **Permis temporaire**: Testez les fonctionnalités avancées sans limitations d'évaluation.
- **Achat**:Pour une utilisation commerciale à long terme, envisagez d'acheter une licence.

## Configuration d'Aspose.Slides pour Java
Commencez par configurer la bibliothèque Aspose.Slides dans votre projet Java. Voici comment l'initialiser et la configurer :

1. Ajoutez la dépendance via Maven ou Gradle comme indiqué ci-dessus.
2. Importez les packages Aspose.Slides nécessaires :
   ```java
   import com.aspose.slides.*;
   ```

3. Initialiser un nouveau `Presentation` exemple:
   ```java
   Presentation presentation = new Presentation();
   ```

Cette configuration vous permettra de commencer à créer des présentations par programmation.

## Guide de mise en œuvre

### Créez et personnalisez des graphiques dans votre présentation

#### Aperçu
La création d'un graphique implique l'initialisation de votre présentation, l'accès aux diapositives et l'ajout d'un graphique avec des attributs spécifiques tels que le type, la position et la taille.

**Mesures:**
1. **Créer une instance de présentation**: Commencez par créer une instance du `Presentation` classe.
2. **Diapositive d'accès**: Récupérez la première diapositive en utilisant `get_Item(0)`.
3. **Ajouter un graphique**: Utiliser `addChart()` pour ajouter un graphique à colonnes empilées à des coordonnées spécifiées avec des dimensions définies.

```java
// Fonctionnalité : Créer une présentation avec un graphique
import com.aspose.slides.*;

try {
    Presentation presentation = new Presentation();
    ISlide slide = presentation.getSlides().get_Item(0);
    
    IChart chart = slide.getShapes().addChart(
        ChartType.StackedColumn,
        20, 20, 400, 400
    );
} finally {
    if (presentation != null) presentation.dispose();
}
```

### Calculer les totaux pour les catégories

#### Aperçu
Le calcul des totaux des catégories implique de parcourir chaque série du graphique pour additionner les valeurs par catégorie.

**Mesures:**
1. **Initialiser le tableau**: Créez un tableau pour contenir les valeurs totales.
2. **Itérer à travers les catégories et les séries**:Utilisez des boucles imbriquées pour accumuler les totaux de chaque catégorie de toutes les séries.

```java
// Fonctionnalité : Calculer les totaux des catégories dans un graphique
import com.aspose.slides.*;

public void calculateCategoryTotals(IChart chart, double[] total_for_Cat) {
    for (int k = 0; k < chart.getChartData().getCategories().size(); k++) {
        IChartCategory cat = chart.getChartData().getCategories().get_Item(k);
        total_for_Cat[k] = 0;

        for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
            double value = (double) (
                chart.getChartData().getSeries().get_Item(i).
                    getDataPoints().get_Item(k).
                    getValue().getData());
            total_for_Cat[k] += value;
        }
    }
}
```

### Afficher les données sous forme d'étiquettes de pourcentage sur un graphique

#### Aperçu
Cette fonctionnalité se concentre sur la configuration des étiquettes de données pour afficher les valeurs sous forme de pourcentages, offrant ainsi plus de clarté dans la visualisation.

**Mesures:**
1. **Configurer les étiquettes de série**: Configurez les propriétés de l'étiquette telles que la taille de la police et la visibilité des clés de légende.
2. **Calculer les pourcentages**:Calculez le pourcentage pour chaque point de données en fonction de la valeur totale de la catégorie.
3. **Définir le texte de l'étiquette**: Formatez les étiquettes pour afficher les pourcentages avec deux décimales.

```java
// Fonctionnalité : Afficher les données sous forme d'étiquettes de pourcentage sur un graphique
import com.aspose.slides.*;

public void displayPercentageLabels(IChart chart, double[] total_for_Cat) {
    for (int x = 0; x < chart.getChartData().getSeries().size(); x++) {
        IChartSeries series = chart.getChartData().getSeries().get_Item(x);
        
        series.getLabels().getDefaultDataLabelFormat().setShowLegendKey(false);

        for (int j = 0; j < series.getDataPoints().size(); j++) {
            IDataLabel lbl = series.getDataPoints().get_Item(j).getLabel();
            double dataPontPercent = (double) (
                series.getDataPoints().get_Item(j).
                    getValue().getData()) / total_for_Cat[j] * 100;

            IPortion port = new Portion();
            port.setText(String.format("{0:F2} %%", dataPontPercent));
            port.getPortionFormat().setFontHeight(8f);
            
            lbl.getTextFrameForOverriding().setText("");
            IParagraph para = lbl.getTextFrameForOverriding().getParagraphs().get_Item(0);
            para.getPortions().add(port);

            lbl.getDataLabelFormat().setShowSeriesName(false);
            lbl.getDataLabelFormat().setShowPercentage(false);
            lbl.getDataLabelFormat().setShowLegendKey(false);
            lbl.getDataLabelFormat().setShowCategoryName(false);
            lbl.getDataLabelFormat().setShowBubbleSize(false);
        }
    }
}
```

### Enregistrer la présentation avec le graphique

#### Aperçu
Enfin, enregistrez votre présentation dans un chemin spécifié au format PPTX.

**Mesures:**
1. **Méthode de sauvegarde**:Utilisez le `save()` méthode sur le `Presentation` exemple.
2. **Éliminer les ressources**: Assurez-vous que les ressources sont libérées après la sauvegarde.

```java
// Fonctionnalité : Enregistrer la présentation avec un graphique
import com.aspose.slides.*;

public void savePresentation(Presentation presentation, String outputPath) {
    try {
        presentation.save(outputPath + "DisplayPercentageAsLabels_out.pptx", SaveFormat.Pptx);
    } finally {
        if (presentation != null) presentation.dispose();
    }
}
```

## Applications pratiques

1. **Rapports financiers**:Utilisez des graphiques pour afficher les pourcentages de croissance des revenus dans tous les services.
2. **Analyse des données de vente**:Visualisez les données de vente par région avec des étiquettes de pourcentage pour des informations plus claires.
3. **Présentations éducatives**:Améliorez les présentations académiques avec des statistiques visuelles.
4. **Campagnes marketing**:Affichez les indicateurs de performance de la campagne sous forme de visuels attrayants.
5. **Réunions de stratégie d'entreprise**:Utilisez des graphiques pour transmettre des données complexes dans les discussions de planification stratégique.

## Considérations relatives aux performances
- **Gestion de la mémoire**: Jeter `Presentation` objets rapidement pour libérer des ressources.
- **Optimiser le chargement des graphiques**: Ne chargez que les éléments essentiels du graphique en mémoire si possible.
- **Traitement par lots**:Lors du traitement de plusieurs présentations, pensez à les traiter par lots pour gérer efficacement la consommation des ressources.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}