---
date: '2026-03-18'
description: Apprenez à créer un graphique à colonnes groupées en Java avec Aspose.Slides,
  comment ajouter un graphique, définir les couleurs et enregistrer la présentation
  au format PPTX. Guide étape par étape avec des exemples de code.
keywords:
- create clustered column chart
- aspose slides java tutorial
- clustered column chart java
title: Comment créer un graphique à colonnes groupées en Java avec Aspose.Slides
url: /fr/java/charts-graphs/aspose-slides-java-clustered-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment créer un graphique à colonnes groupées en Java avec Aspose.Slides

## Introduction
Créer des représentations de données visuellement attrayantes est essentiel pour des présentations d'entreprise percutantes, et apprendre **comment créer un graphique à colonnes groupées** de façon programmatique peut vous faire gagner des heures de travail manuel. Dans ce tutoriel, vous verrez **comment ajouter un graphique**, **définir automatiquement les couleurs**, et enfin **enregistrer la présentation au format PPTX** en utilisant **Aspose.Slides for Java**. Nous parcourrons tout ce dont vous avez besoin — de la configuration de la bibliothèque à l'ajout du graphique, la personnalisation des couleurs de remplissage des séries, et la persistance du fichier.

### Ce que vous allez réaliser
- Installer et configurer Aspose.Slides for Java  
- **Créer un graphique à colonnes groupées** dans une toute nouvelle présentation  
- Appliquer automatiquement les couleurs de remplissage des séries (**how to set colors**)  
- **Enregistrer la présentation au format PPTX** sur le disque (**how to save presentation**)  

Passons rapidement en revue les prérequis avant de commencer à créer le graphique.

## Réponses rapides
- **Quelle est la classe principale ?** `Presentation` de `com.aspose.slides`  
- **Comment ajouter un graphique ?** Utilisez `addChart(ChartType.ClusteredColumn, …)` sur la collection de formes d’une diapositive (**how to add chart**)  
- **Puis-je définir les couleurs automatiquement ?** Oui, appelez `setAutomaticSeriesColor(true)` sur chaque série (**how to set colors**)  
- **Quel format est utilisé pour l’enregistrement ?** `SaveFormat.Pptx` (PowerPoint) (**save presentation as pptx**)  
- **Ai‑je besoin d’une licence ?** Un essai fonctionne pour les tests ; une licence complète est requise en production  

## Prérequis
Avant de commencer, assurez‑vous de disposer des outils et des connaissances nécessaires :

### Bibliothèques et dépendances requises
Vous aurez besoin de la bibliothèque Aspose.Slides for Java. Assurez‑vous d’utiliser la version 25.4 avec le support de JDK16.

### Exigences de configuration de l’environnement
Votre environnement de développement doit prendre en charge Java (de préférence JDK16) et être capable de construire des projets avec Maven ou Gradle.

### Prérequis de connaissances
Une familiarité avec la programmation Java de base, l’utilisation de bibliothèques via Maven/Gradle, et la compréhension des présentations PowerPoint sera bénéfique.

## Configuration d’Aspose.Slides pour Java
Pour intégrer Aspose.Slides à votre projet, suivez les instructions d’installation ci‑dessous :

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

**Téléchargement direct**  
Pour ceux qui préfèrent les téléchargements directs, visitez [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Étapes d’obtention de licence
- **Essai gratuit** : Commencez avec un essai gratuit pour explorer les fonctionnalités.  
- **Licence temporaire** : Obtenez une licence temporaire pour tester sans limitations.  
- **Achat** : Pour une utilisation continue, achetez une licence complète.

**Initialisation de base et configuration**  
Initialisez Aspose.Slides comme suit :
```java
import com.aspose.slides.Presentation;
// Initialize the Presentation class
Presentation presentation = new Presentation();
```

## Comment ajouter un graphique à colonnes groupées
Ajouter un graphique est la première étape fonctionnelle. Cette section explique **comment ajouter un graphique** en utilisant l’API.

### Fonctionnalité 1 : Créer un graphique à colonnes groupées
Créons un graphique à colonnes groupées avec Aspose.Slides for Java. Cette fonctionnalité vous permet d’ajouter facilement des graphiques visuellement attrayants à vos diapositives.

#### Vue d’ensemble
Dans cette section, nous allons initialiser une nouvelle présentation et insérer un graphique à colonnes groupées dans la première diapositive.

**Étape 1 : Initialiser la présentation**  
Créez un objet `Presentation` pour commencer à travailler avec des fichiers PowerPoint :
```java
import com.aspose.slides.Presentation;
// Initialize a new Presentation object
Presentation presentation = new Presentation();
```

**Étape 2 : Ajouter un graphique à colonnes groupées**  
Ajoutez le graphique aux coordonnées spécifiées (100, 50) et aux dimensions (600 × 400) :
```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
IChart chart = presentation.getSlides().get_Item(0).getShapes()
                            .addChart(ChartType.ClusteredColumn, 100, 50, 600, 400);
```

**Étape 3 : Nettoyer les ressources**  
Libérez toujours les ressources pour éviter les fuites de mémoire :
```java
finally {
    if (presentation != null) presentation.dispose();
}
```

## Comment définir les couleurs du graphique
Améliorez l’attrait visuel en appliquant automatiquement les couleurs de remplissage des séries (**how to set colors**).

### Fonctionnalité 2 : Définir automatiquement la couleur de remplissage des séries
#### Vue d’ensemble
Définissez automatiquement la couleur de chaque série du graphique pour un rendu cohérent.

**Étape 1 : Accéder au graphique et parcourir les séries**  
Après avoir créé votre graphique, accédez‑y et parcourez ses séries :
```java
import com.aspose.slides.IChart;
IChart chart = presentation.getSlides().get_Item(0).getShapes()
                            .addChart(com.aspose.slides.ChartType.ClusteredColumn, 100, 50, 600, 400);

for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
    chart.getChartData().getSeries().get_Item(i).setAutomaticSeriesColor(true);
}
```

**Étape 2 : Gestion des ressources**  
Libérez l’objet `Presentation` une fois terminé :
```java
finally {
    if (presentation != null) presentation.dispose();
}
```

## Comment enregistrer la présentation au format PPTX
Une fois le graphique satisfaisant, vous voudrez persister le fichier (**how to save presentation**).

### Fonctionnalité 3 : Enregistrer la présentation sur le disque
#### Vue d’ensemble
Enregistrez vos présentations modifiées dans le format et l’emplacement souhaités.

**Étape 1 : Définir le chemin de sortie**  
Spécifiez où vous souhaitez enregistrer le fichier :
```java
import com.aspose.slides.SaveFormat;
String outputPath = "YOUR_OUTPUT_DIRECTORY/AutoFillSeries_out.pptx";
```

**Étape 2 : Enregistrer la présentation**  
Utilisez la méthode `save` de l’objet `Presentation` :
```java
presentation.save(outputPath, SaveFormat.Pptx);
```

## Applications pratiques
- **Rapports financiers** : Visualisez les résultats trimestriels avec clarté.  
- **Analyse de données marketing** : Présentez les résultats de campagne à l’aide de visuels percutants.  
- **Gestion de projet** : Suivez les jalons et l’avancement visuellement lors des réunions d’équipe.

## Considérations de performance
Lorsque vous travaillez avec Aspose.Slides, prenez en compte ces meilleures pratiques :

- Gérez la mémoire efficacement en libérant rapidement les objets `Presentation`.  
- Optimisez la taille des fichiers lors de l’enregistrement des présentations pour économiser l’espace disque.  
- Utilisez des structures de données efficaces pour les séries de graphiques afin d’améliorer les performances.

## Conclusion
Félicitations ! Vous avez appris comment **créer un graphique à colonnes groupées**, **définir automatiquement les couleurs**, et **enregistrer la présentation au format PPTX** en utilisant Aspose.Slides for Java. Cette compétence améliore non seulement vos présentations mais simplifie également le processus de représentation visuelle des données.

**Prochaines étapes :**  
Explorez d’autres fonctionnalités telles que la personnalisation des éléments du graphique, l’ajout d’étiquettes de données, ou l’intégration avec des sources de données externes pour étendre les capacités de votre projet.

## Section FAQ
1. **Comment installer Aspose.Slides pour une version spécifique de JDK ?**  
   - Utilisez les dépendances Maven/Gradle en spécifiant le `classifier` comme indiqué dans la section d’installation.  
2. **Que faire si ma présentation ne s’enregistre pas correctement ?**  
   - Assurez‑vous d’avoir les permissions d’écriture sur le répertoire de sortie et que le chemin du fichier est correct.  
3. **Puis‑je créer d’autres types de graphiques avec Aspose.Slides for Java ?**  
   - Absolument ! Explorez les options `ChartType` comme les graphiques en secteurs, en barres ou en lignes.  
4. **Comment gérer de grands ensembles de données dans mon graphique ?**  
   - Optimisez les structures de données et envisagez de pré‑traiter vos données avant de les visualiser.  
5. **Où puis‑je trouver plus d’exemples d’utilisation d’Aspose.Slides for Java ?**  
   - Consultez la [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/) pour des guides complets et des exemples de code.

## Ressources
- **Documentation** : [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)  
- **Téléchargement** : [Get Aspose.Slides](https://releases.aspose.com/slides/java/)  
- **Achat** : [Buy a License](https://purchase.aspose.com/buy)  
- **Essai gratuit** : [Start a Free Trial](https://releases.aspose.com/slides/java/)  
- **Licence temporaire** : [Request Here](https://purchase.aspose.com/temporary-license/)  
- **Support** : [Aspose Forum](https://forum.aspose.com/c/slides/11)

---

**Dernière mise à jour :** 2026-03-18  
**Testé avec :** Aspose.Slides 25.4 (JDK16)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}