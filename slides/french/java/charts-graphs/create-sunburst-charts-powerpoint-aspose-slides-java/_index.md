---
"date": "2025-04-17"
"description": "Apprenez à créer et personnaliser des graphiques en forme de soleil dans PowerPoint avec Aspose.Slides pour Java. Ce guide étape par étape couvre la configuration, la personnalisation et les applications pratiques."
"title": "Créez et personnalisez des graphiques Sunburst dans PowerPoint avec Aspose.Slides pour Java"
"url": "/fr/java/charts-graphs/create-sunburst-charts-powerpoint-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Créez et personnalisez des graphiques Sunburst dans PowerPoint avec Aspose.Slides pour Java

## Introduction

Créer des présentations convaincantes implique souvent l'intégration de graphiques percutants qui transmettent efficacement les données. Le graphique en forme de soleil est un exemple de ce type de graphique, qui offre une façon unique de représenter des données hiérarchiques grâce à sa disposition radiale. Cependant, ajouter et personnaliser ces graphiques peut s'avérer complexe sans les outils appropriés. Ce guide vous guidera dans la création et la modification de graphiques en forme de soleil dans des présentations PowerPoint avec Aspose.Slides pour Java.

**Ce que vous apprendrez :**
- Configurer votre environnement pour Aspose.Slides
- Créer une nouvelle présentation avec un graphique en forme de soleil
- Personnalisation des points de données dans le graphique
- Applications concrètes de ces compétences

Voyons comment vous pouvez simplifier ce processus en utilisant Aspose.Slides pour Java.

## Prérequis

Avant de commencer, assurez-vous que votre environnement de développement est prêt. Vous aurez besoin de :
- **Kit de développement Java (JDK)** version 16 ou supérieure
- Un **Environnement de développement intégré (IDE)** comme IntelliJ IDEA ou Eclipse
- Connaissances de base de **Java** et des présentations PowerPoint

## Configuration d'Aspose.Slides pour Java

### Dépendance Maven

Pour inclure Aspose.Slides dans votre projet, ajoutez la dépendance suivante à votre `pom.xml` déposer:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Dépendance Gradle

Si vous utilisez Gradle, incluez les éléments suivants dans votre `build.gradle`:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Téléchargement direct

Vous pouvez également télécharger le dernier JAR à partir de [Versions d'Aspose.Slides pour Java](https://releases.aspose.com/slides/java/).

### Acquisition de licence

Pour utiliser Aspose.Slides sans limitations d'évaluation :
- **Essai gratuit :** Commencez avec une licence temporaire pour explorer toutes les fonctionnalités.
- **Licence temporaire :** Demandez un permis temporaire sur le [Site Web d'Aspose](https://purchase.aspose.com/temporary-license).
- **Achat:** Pour les projets en cours, pensez à acheter un abonnement.

### Initialisation de base

Voici comment vous pouvez initialiser Aspose.Slides dans votre application Java :
```java
import com.aspose.slides.Presentation;

public class PresentationExample {
    public static void main(String[] args) {
        // Initialiser Aspose.Slides avec une licence si disponible
        Presentation pres = new Presentation();
        try {
            // Votre code ici...
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

## Guide de mise en œuvre

### Créer une présentation et ajouter un graphique Sunburst

#### Aperçu

Cette fonctionnalité montre comment créer une présentation PowerPoint à partir de zéro et ajouter un graphique en forme de soleil.

#### Mesures:
##### Étape 1 : Initialiser la présentation
```java
Presentation pres = new Presentation();
try {
    String dataDir = "YOUR_DOCUMENT_DIRECTORY"; // Remplacez par votre chemin
```

##### Étape 2 : Ajouter un graphique Sunburst
Ajoutez un graphique en forme de soleil à la première diapositive à la position (100, 100) avec la taille (450x400).
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Sunburst, 100, 100, 450, 400);
```

##### Étape 3 : Enregistrer la présentation
Enregistrez votre présentation pour vous assurer que toutes les modifications sont enregistrées.
```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### Modifier les points de données dans le graphique

#### Aperçu
Apprenez à modifier les points de données, y compris les étiquettes et les couleurs, dans un graphique en forme de soleil.

#### Mesures:
##### Étape 1 : Accéder à la collecte de points de données
Accédez à la première collection de points de données de la série à partir du graphique.
```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

##### Étape 2 : Afficher la valeur d'un point de données spécifique
Modifiez l’étiquette pour afficher les valeurs à un niveau spécifique.
```java
dataPoints.get_Item(3).getDataPointLevels().get_Item(0).getLabel()
    .getDataLabelFormat().setShowValue(true);
```

##### Étape 3 : Modifier les formats d’étiquettes
Ajustez les paramètres d’étiquette tels que la visibilité du nom de catégorie et la couleur du texte.
```java
IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
branch1Label.getDataLabelFormat().setShowCategoryName(false);
branch1Label.getDataLabelFormat().setShowSeriesName(true);

branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().setFillType(FillType.Solid);
branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().getSolidFillColor()
    .setColor(java.awt.Color.YELLOW);
```

##### Étape 4 : Définir la couleur de remplissage des points de données
Personnalisez la couleur de remplissage de points de données spécifiques.
```java
IFormat steam4Format = dataPoints.get_Item(9).getFormat();
steam4Format.getFill().setFillType(FillType.Solid);
steam4Format.getFill().getSolidFillColor()
    .setColor(new com.aspose.slides.Color(0, 176, 240, 255));
```

##### Étape 5 : Enregistrer la présentation modifiée
Enregistrez toujours vos modifications pour les finaliser.
```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Applications pratiques

1. **Analyse commerciale :** Utilisez des graphiques en forme de soleil pour visualiser des hiérarchies de données complexes, telles que les données de vente par région et par catégorie.
2. **Gestion de projet :** Affichez les tâches du projet décomposées en sous-tâches à l'aide d'un graphique radial pour une visualisation facile.
3. **Éducation:** Représenter les modules de cours et leurs conférences respectives dans des présentations pédagogiques.

## Considérations relatives aux performances

- **Optimiser l’utilisation des ressources :** Assurez-vous que votre application gère efficacement la mémoire, en particulier lors de la manipulation de grands ensembles de données ou de plusieurs graphiques.
- **Gestion de la mémoire Java :** Utilisez les meilleures pratiques comme l’élimination rapide des objets pour éviter les fuites de mémoire.

## Conclusion

Créer et personnaliser des graphiques en forme de soleil avec Aspose.Slides pour Java est un moyen efficace d'améliorer vos présentations. En suivant ce guide, vous avez appris les bases de la configuration de votre environnement, de l'implémentation des fonctionnalités graphiques et de la modification efficace des points de données.

**Prochaines étapes :**
- Découvrez d’autres types de graphiques disponibles dans Aspose.Slides.
- Expérimentez différentes options de personnalisation pour vos graphiques.

**Appel à l'action :** Essayez d’implémenter ces solutions dans votre prochain projet de présentation pour voir comment elles peuvent améliorer vos efforts de visualisation de données !

## Section FAQ

1. **Qu'est-ce qu'un graphique en rayons de soleil ?**
   - Un graphique en forme de soleil affiche les données hiérarchiques de manière radiale, idéal pour présenter les relations imbriquées.
2. **Comment installer Aspose.Slides pour Java à l'aide de Maven ?**
   - Ajoutez la dépendance à votre `pom.xml` fichier comme indiqué dans la section de configuration ci-dessus.
3. **Puis-je modifier d’autres types de graphiques avec Aspose.Slides ?**
   - Oui, Aspose.Slides prend en charge différents types de graphiques tels que les graphiques à colonnes, à lignes et à secteurs.
4. **Que dois-je faire si ma présentation ne s'enregistre pas correctement ?**
   - Assurez-vous que le chemin de votre fichier est correct et que vous disposez des autorisations d'écriture pour le répertoire.
5. **Comment puis-je obtenir plus d’aide avec Aspose.Slides ?**
   - Visitez le [Forum Aspose](https://forum.aspose.com/c/slides/11) ou consultez la documentation sur [Référence Aspose.Slides](https://reference.aspose.com/slides/java/).

## Ressources
- **Documentation:** [Référence Aspose.Slides](https://reference.aspose.com/slides/java)
- **Forum:** [Forum Aspose](https://forum.aspose.com/c/slides)
- **Téléchargements :** [Téléchargements Aspose.Slides](https://releases.aspose.com/slides/java)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}