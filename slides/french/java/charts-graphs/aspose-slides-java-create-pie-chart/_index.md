---
date: '2026-02-17'
description: Apprenez à ajouter des graphiques circulaires aux présentations PowerPoint
  à l’aide d’Aspose.Slides for Java. Suivez ce guide étape par étape pour créer et
  personnaliser des graphiques circulaires professionnels.
keywords:
- Create Pie Charts in PowerPoint Java
- Customize Pie Chart Aspose.Slides Java
- Aspose.Slides for Java Pie Chart
title: Comment ajouter un diagramme circulaire PowerPoint avec Aspose.Slides pour
  Java
url: /fr/java/charts-graphs/aspose-slides-java-create-pie-chart/
weight: 1
---

 placeholders unchanged.

Let's craft final answer.{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Créer et personnaliser des graphiques circulaires dans PowerPoint avec Aspose.Slides pour Java

## Introduction

Rencontrez-vous des difficultés à visualiser efficacement les données dans vos présentations PowerPoint ? **Ajouter une diapositive de graphique circulaire PowerPoint** peut instantanément transformer des chiffres bruts en une histoire visuelle claire. Avec Aspose.Slides pour Java, vous pouvez **ajouter des fichiers de graphique circulaire PowerPoint** de manière programmatique, vous offrant un contrôle total sur la conception et les données sans jamais ouvrir PowerPoint manuellement. Dans ce tutoriel, nous parcourrons l’ensemble du processus — de la configuration de la bibliothèque à la personnalisation des points de données individuels — afin que vous puissiez livrer des diapositives soignées, axées sur les données, en quelques minutes.

### Quick Answers
- **Quelle bibliothèque me faut‑il ?** Aspose.Slides for Java (dernière version).  
- **Puis‑je créer un graphique sans PowerPoint installé ?** Oui, l’API fonctionne entièrement hors ligne.  
- **Quelle version de Java est requise ?** JDK 16 ou ultérieure est recommandée.  
- **Comment changer la couleur d’une tranche ?** Utilisez les méthodes `setFillType` et `setSolidFillColor` sur le point de données.  
- **Une licence est‑elle obligatoire ?** Un essai fonctionne pour le développement ; une licence permanente supprime les limites d’évaluation.

### What You’ll Learn
- Comment **ajouter un graphique circulaire PowerPoint** de manière programmatique avec Java.  
- Moyens de personnaliser l’explosion des tranches, les couleurs et d’autres propriétés visuelles.  
- Bonnes pratiques de gestion des ressources et de performance lors du traitement de présentations volumineuses.

## Why add pie chart PowerPoint using Aspose.Slides for Java?
Intégrer un graphique circulaire directement depuis le code vous permet de générer des rapports à jour, d’automatiser des tableaux de bord mensuels ou de créer des présentations personnalisées à la volée. Cela élimine les erreurs de copier‑coller manuelles, assure la cohérence entre les présentations et s’intègre parfaitement aux back‑ends Java existants.

## Prerequisites

Avant de commencer, assurez‑vous d’avoir :

- **Bibliothèque Aspose.Slides pour Java** – le tutoriel fait référence à la version 25.4 (la dernière version au moment de la rédaction).  
- Un **Java Development Kit (JDK)** compatible – JDK 16+ est recommandé.  
- Familiarité de base avec **Maven** ou **Gradle** pour la gestion des dépendances.  

## Setting Up Aspose.Slides for Java

Pour commencer, incluez la bibliothèque Aspose.Slides dans votre projet.

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
Incluez ce qui suit dans votre fichier `build.gradle` :
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Alternativement, téléchargez la dernière version directement depuis [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Licensing
Pour utiliser Aspose.Slides sans limitations :

- Commencez avec un **essai gratuit** pour évaluer l’API.  
- Demandez une **licence temporaire** pour des tests prolongés sur la page [Temporary License](https://purchase.aspose.com/temporary-license/).  
- Achetez un abonnement complet via la [Purchase page](https://purchase.aspose.com/buy).

## How to add pie chart PowerPoint using Aspose.Slides for Java

Voici un guide étape par étape qui montre exactement comment créer et personnaliser un graphique circulaire.

### Step 1: Initialize the Presentation
Tout d’abord, créez un nouvel objet `Presentation`. Cela représente un fichier PowerPoint vide.
```java
Presentation pres = new Presentation();
```

### Step 2: Add the Pie Chart
Insérez un graphique circulaire sur la première diapositive. Les coordonnées (50, 50) et la taille (600 × 400) conviennent bien à une diapositive standard 16 : 9.
```java
pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
```

### Step 3: Save the Presentation
Enregistrez la présentation sur le disque. Remplacez `YOUR_OUTPUT_DIRECTORY` par le dossier où vous souhaitez enregistrer le fichier.
```java
pres.save("YOUR_OUTPUT_DIRECTORY/output.pptx", SaveFormat.Pptx);
```

### Step 4: Clean Up Resources
Libérez l’objet `Presentation` pour libérer les ressources natives.
```java
if (pres != null) pres.dispose();
```

## Customizing Data Point Explosion and Color

Personnalisation de l'explosion et de la couleur des points de données

Personnaliser les tranches individuelles rend votre graphique plus lisible, surtout lorsque vous souhaitez mettre en évidence une valeur spécifique.

### Step 1: Load an Existing Presentation (or reuse the one you just created)
Chargez une présentation existante (ou réutilisez celle que vous venez de créer).
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

### Step 2: Access the Chart and Target Data Point
Ici, nous récupérons le deuxième point de données (index 1) de la première série.
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
IChartDataPoint point = chart.getChartData().getSeries().get_Item(0).getDataPoints().get_Item(1);
```

### Step 3: Apply Explosion and Color
Séparez visuellement la tranche et changez sa couleur de remplissage en bleu.
```java
point.setExplosion(30); // Set explosion distance
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE); // Change fill color
```

### Step 4: Save and Dispose
Enregistrez et libérez.
```java
pres.save("YOUR_OUTPUT_DIRECTORY/customized.pptx", SaveFormat.Pptx);
if (pres != null) pres.dispose();
```

## Practical Applications
- **Rapports de ventes :** Mettez en avant les produits les plus vendus avec des tranches éclatées.  
- **Analyse budgétaire :** Attribuez des couleurs distinctes aux départements pour une comparaison visuelle rapide.  
- **Diapositives éducatives :** Décomposez des concepts complexes en segments de graphique faciles à digérer.

## Performance Considerations
- **Libérez les objets** rapidement pour éviter les fuites de mémoire, surtout lors de la génération de nombreuses diapositives dans une boucle.  
- **Surveillez l’utilisation du tas** pour les présentations volumineuses ; envisagez de diffuser la sortie avec les surcharges de `Save` qui acceptent `OutputStream`.  
- Restez sur **JDK 16+** pour profiter des dernières améliorations de la collecte des déchets.

## Conclusion
Vous disposez maintenant d’un flux de travail complet, prêt pour la production, pour **ajouter des fichiers de graphique circulaire PowerPoint** avec Aspose.Slides pour Java. Expérimentez différentes distances d’explosion, couleurs et ensembles de données pour correspondre à votre identité visuelle. Lorsque vous êtes prêt, explorez d’autres types de graphiques — barres, lignes ou nuages de points — pour créer un tableau de bord analytique complet dans PowerPoint.

## FAQ Section
1. **Quel est l’avantage principal d’utiliser Aspose.Slides pour Java ?**  
   - Il simplifie la création et la manipulation de fichiers PowerPoint de manière programmatique, offrant une large gamme de fonctionnalités.  
2. **Puis‑je personnaliser d’autres types de graphiques avec Aspose.Slides ?**  
   - Absolument ! Aspose.Slides prend en charge divers types de graphiques tels que les graphiques à barres, lignes et nuages de points.  
3. **Comment gérer plusieurs diapositives lors de la création de graphiques ?**  
   - Accédez à chaque diapositive par son index en utilisant la méthode `get_Item()` pour appliquer des modifications sur différentes diapositives.  
4. **Que faire si mon graphique circulaire ne s’affiche pas correctement après la personnalisation ?**  
   - Vérifiez les coordonnées et les dimensions utilisées dans `addChart()`, en vous assurant qu’elles s’insèrent correctement dans la mise en page de votre diapositive.  
5. **Où puis‑je trouver des fonctionnalités plus avancées pour Aspose.Slides ?**  
   - Explorez la [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/) pour découvrir des fonctionnalités et options supplémentaires.

## Resources
- **Documentation:** [Aspose.Slides Java Docs](https://reference.aspose.com/slides/java/)  
- **Download Library:** [Aspose Releases](https://releases.aspose.com/slides/java/)  
- **Purchase License:** [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **Free Trial:** [Try Aspose.Slides](https://releases.aspose.com/slides/java/)  
- **Temporary License:** [Request Temporary License](https://purchase.aspose.com/temporary-license/)  
- **Support Forum:** [Aspose Support](https://forum.aspose.com/c/slides/11)

---

**Dernière mise à jour :** 2026-02-17  
**Testé avec :** Aspose.Slides for Java 25.4 (classificateur JDK 16)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}