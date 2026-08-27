---
date: '2026-08-27'
description: Apprenez à effacer les points de données des graphiques PowerPoint à
  l'aide d'Aspose.Slides for Java. Ce tutoriel étape par étape montre comment effacer
  les valeurs du graphique de manière programmatique, les meilleures pratiques et
  la gestion efficace des séries.
keywords:
- how to clear chart
- programmatically clear chart
- remove chart data points
- Aspose.Slides Java chart manipulation
- PowerPoint chart automation
lastmod: '2026-08-27'
og_description: Apprenez à effacer les points de données des graphiques PowerPoint
  à l'aide d'Aspose.Slides for Java. Suivez les instructions étape par étape pour
  réinitialiser les graphiques de manière programmatique et efficace.
og_image_alt: Code example showing how to clear chart data points in a PowerPoint
  presentation using Aspose.Slides for Java
og_title: Comment effacer les points de données des graphiques PowerPoint avec Aspose.Slides
  for Java
schemas:
- author: Aspose
  dateModified: '2026-08-27'
  description: Learn how to clear chart data points in PowerPoint using Aspose.Slides
    for Java. This step‑by‑step tutorial shows how to programmatically clear chart
    values, best practices, and efficient series handling.
  headline: 'How to clear data points in PowerPoint charts using Aspose.Slides for
    Java: a comprehensive guide'
  type: TechArticle
- description: Learn how to clear chart data points in PowerPoint using Aspose.Slides
    for Java. This step‑by‑step tutorial shows how to programmatically clear chart
    values, best practices, and efficient series handling.
  name: 'How to clear data points in PowerPoint charts using Aspose.Slides for Java:
    a comprehensive guide'
  steps:
  - name: '**Load the presentation** – create a `Presentation` instance pointing to
      your source file.'
    text: '**Load the presentation** – create a `Presentation` instance pointing to
      your source file.'
  - name: '**Access the slide and chart** – retrieve the slide (usually index 0) and
      cast the first shape to `IChart`.'
    text: '**Access the slide and chart** – retrieve the slide (usually index 0) and
      cast the first shape to `IChart`.'
  - name: '**Iterate through the target series** – select the series you want to clear
      (e.g., `chart.getChartData().getSeries().get_Item(0)`) and loop over its data
      points, setting both X and Y cell values to `null`.'
    text: '**Iterate through the target series** – select the series you want to clear
      (e.g., `chart.getChartData().getSeries().get_Item(0)`) and loop over its data
      points, setting both X and Y cell values to `null`.'
  - name: '**Save the modified presentation** – write the changes to a new file or
      overwrite the original.'
    text: '**Save the modified presentation** – write the changes to a new file or
      overwrite the original.'
  - name: '**Data refresh pipelines** – replace stale numbers with fresh analytics
      without rebuilding the chart layout.'
    text: '**Data refresh pipelines** – replace stale numbers with fresh analytics
      without rebuilding the chart layout.'
  - name: '**Template distribution** – provide PowerPoint templates that contain empty
      charts ready for user input.'
    text: '**Template distribution** – provide PowerPoint templates that contain empty
      charts ready for user input.'
  - name: '**Dynamic dashboards** – generate nightly presentations that pull data
      from APIs, clearing old values first.'
    text: '**Dynamic dashboards** – generate nightly presentations that pull data
      from APIs, clearing old values first.'
  - name: '**Automated reporting jobs** – integrate the clearing logic into CI/CD
      pipelines for automated report generation.'
    text: '**Automated reporting jobs** – integrate the clearing logic into CI/CD
      pipelines for automated report generation.'
  type: HowTo
- questions:
  - answer: A free trial license is sufficient for development and testing. A commercial
      license is required for production deployments.
    question: Do I need a license for development builds?
  - answer: Yes, the library fully supports modern PPTX features, including advanced
      chart types and SmartArt.
    question: Does Aspose.Slides for Java support PowerPoint 2016/2019 features?
  - answer: Absolutely – just reference the series that belongs to the secondary axis
      and set its data points to `null` as described above.
    question: Can I clear data points in a chart that uses a secondary axis?
  - answer: Yes. Call `dataPoint.getYValue().setValue(null)` and leave the X cell
      untouched.
    question: Is it possible to clear only Y values while keeping X labels?
  - answer: Wrap the clearing code in a loop that iterates over a directory of PPTX
      files, applying the same logic to each file.
    question: How can I automate this for multiple presentations?
  type: FAQPage
tags:
- clear chart
- Aspose.Slides
- Java chart manipulation
- PowerPoint automation
- chart data points
title: 'Comment effacer les points de données dans les graphiques PowerPoint à l''aide
  d''Aspose.Slides for Java : guide complet'
url: /fr/java/charts-graphs/clear-data-points-ppt-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment effacer les points de données dans les graphiques PowerPoint à l'aide d'Aspose.Slides pour Java

## Introduction

Dans de nombreux pipelines de reporting, vous devez **réinitialiser un graphique** sans recréer sa mise en page. Que vous rafraîchissiez un tableau de bord, distribuiez un modèle ou automatisiez des rapports nocturnes, savoir **comment effacer les points de données d'un graphique** fait gagner du temps et réduit les erreurs. Ce tutoriel vous montre comment utiliser **Aspose.Slides pour Java** pour effacer programmatiquement des points spécifiques ou une série entière, tout en conservant le style visuel.

**Ce que vous apprendrez**
- Comment Aspose.Slides vous permet de manipuler les graphiques PowerPoint depuis Java.  
- Instructions étape par étape pour effacer les points de données d'une série.  
- Conseils de bonnes pratiques pour les performances et la licence.

## Réponses rapides
- **Quelle bibliothèque est requise ?** Aspose.Slides pour Java (v25.4+).  
- **Quelle méthode efface réellement un point de données ?** Définir les valeurs des cellules X et Y sur `null`.  
- **Ai‑je besoin d’une licence pour la production ?** Oui – une licence commerciale supprime les limites d’essai.  
- **Java 16 est‑il pris en charge ?** Absolument ; la bibliothèque fonctionne avec JDK 16 et versions ultérieures.  
- **Puis‑je cibler une seule série ?** Oui – parcourez la série spécifique que vous souhaitez effacer.

## Qu’est‑ce qu’Aspose.Slides pour Java ?

Aspose.Slides pour Java est une API complète qui permet la création, la modification et la conversion de fichiers PowerPoint sans Microsoft Office. Elle prend en charge plus de 70 types de graphiques, plus de 150 formats de fichiers, et peut traiter des présentations jusqu’à 500 Mo sans charger le fichier entier en mémoire.

## Pourquoi effacer les points de données du graphique ?

Effacer les points de données du graphique vous permet de conserver la mise en page existante – couleurs, légendes, paramètres d’axes et marqueurs – tout en remplaçant les valeurs numériques sous‑jacentes. Cette approche est utile lorsque vous devez actualiser un graphique avec de nouvelles données, fournir un modèle avec des espaces réservés vides, ou générer des tableaux de bord dynamiques qui changent fréquemment sans reconstruire le design visuel.

- Rafraîchir un graphique avec un nouveau jeu de données tout en préservant les couleurs, légendes et paramètres d’axes.  
- Distribuer un modèle contenant des graphiques vides prêts à être remplis par l’utilisateur.  
- Construire des tableaux de bord dynamiques où les données changent fréquemment.

## Comment effacer les points de données du graphique dans PowerPoint à l'aide d'Aspose.Slides pour Java

Chargez votre présentation, localisez le graphique, et définissez les cellules X et Y de chaque point de données sur `null`. Cette opération supprime les valeurs numériques mais laisse la série, les marqueurs et le formatage intacts. Le processus complet se termine généralement en moins d’une seconde pour un PPTX standard de 10 diapositives.

### Réponse directe
Pour effacer les points de données, ouvrez le PPTX avec `new Presentation("input.pptx")`, récupérez l’objet `IChart` cible, parcourez la `IChartSeries` souhaitée, et appelez `dataPoint.getXValue().setValue(null)` et `dataPoint.getYValue().setValue(null)` pour chaque point. Enfin, enregistrez la présentation avec `pres.save("output.pptx", SaveFormat.Pptx)`. Cette approche efface programmatiquement les données tout en préservant le design visuel du graphique.

### Ancres de définition
- `Presentation` est l’objet de haut niveau d’Aspose.Slides qui représente un fichier PowerPoint en mémoire.  
- `IChart` est l’interface qui donne accès aux séries, axes et formatage d’une forme graphique.  
- `IChartSeries` représente une série unique au sein d’un graphique et contient une collection d’objets `IDataPoint`.  
- `IDataPoint` contient les valeurs X et Y individuelles d’un point du graphique.

### Mise en œuvre étape par étape

1. **Charger la présentation** – créez une instance `Presentation` pointant vers votre fichier source.  
   ```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

2. **Accéder à la diapositive et au graphique** – récupérez la diapositive (généralement l’index 0) et cast le premier shape en `IChart`.  
   ```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

3. **Parcourir la série cible** – sélectionnez la série que vous souhaitez effacer (par ex., `chart.getChartData().getSeries().get_Item(0)`) et bouclez sur ses points de données, en définissant les deux cellules X et Y sur `null`.  
   ```java
import com.aspose.slides.*;

public class ChartManipulation {
    public static void main(String[] args) {
        Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/TestChart.pptx");
        try {
            // Your code here
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

4. **Enregistrer la présentation modifiée** – écrivez les modifications dans un nouveau fichier ou écrasez l’original.  
   ```java
   Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/TestChart.pptx");
   ```

## Configuration d'Aspose.Slides pour Java

### Installation Maven

```java
   ISlide sl = pres.getSlides().get_Item(0);
   IChart chart = (IChart) sl.getShapes().get_Item(0);
   ```

### Installation Gradle

```java
   for (IChartDataPoint dataPoint : chart.getChartData().getSeries().get_Item(0).getDataPoints()) {
       dataPoint.getXValue().getAsCell().setValue(null);
       dataPoint.getYValue().getAsCell().setValue(null);
   }
   ```

### Téléchargement direct

Alternativement, téléchargez la dernière version depuis [versions d'Aspose.Slides pour Java](https://releases.aspose.com/slides/java/).

### Obtention de licence

Pour utiliser Aspose.Slides au‑delà des limitations d’essai :
- Obtenez une licence d’**essai gratuit**.  
- Demandez une licence **temporaire** pour l’évaluation.  
- Achetez une licence **commerciale** pour la production.

#### Initialisation et configuration de base

```java
   pres.save("YOUR_DOCUMENT_DIRECTORY/UpdatedTestChart.pptx", SaveFormat.Pptx);
   ```

## Applications pratiques

Effacer les points de données du graphique est utile dans de nombreux scénarios réels :

1. **Pipelines de rafraîchissement de données** – remplacer les chiffres obsolètes par de nouvelles analyses sans reconstruire la mise en page du graphique.  
2. **Distribution de modèles** – fournir des modèles PowerPoint contenant des graphiques vides prêts à être remplis par l’utilisateur.  
3. **Tableaux de bord dynamiques** – générer des présentations nocturnes qui récupèrent des données depuis des API, en effaçant d’abord les anciennes valeurs.  
4. **Jobs de reporting automatisés** – intégrer la logique d’effacement dans les pipelines CI/CD pour la génération automatisée de rapports.

## Considérations de performance

- **Libérer les objets** : appelez `pres.dispose()` après l’enregistrement pour libérer les ressources natives.  
- **Traitement par lots** : réutilisez une même instance `License` sur de nombreux fichiers afin de réduire la surcharge.  
- **Ajustement JVM** : augmentez la taille du tas (`-Xmx2g` ou plus) lors du traitement de présentations supérieures à 200 Mo.  
- **Mode mémoire efficace** : Aspose.Slides peut diffuser de gros fichiers PPTX, permettant le traitement de jusqu’à 10 000 diapositives sans chargement complet en mémoire.

## Questions fréquentes

**Q : Ai‑je besoin d’une licence pour les builds de développement ?**  
R : Une licence d’essai gratuit suffit pour le développement et les tests. Une licence commerciale est requise pour les déploiements en production.

**Q : Aspose.Slides pour Java prend‑il en charge les fonctionnalités de PowerPoint 2016/2019 ?**  
R : Oui, la bibliothèque prend pleinement en charge les fonctionnalités PPTX modernes, y compris les types de graphiques avancés et SmartArt.

**Q : Puis‑je effacer les points de données d’un graphique utilisant un axe secondaire ?**  
R : Absolument – il suffit de référencer la série appartenant à l’axe secondaire et de définir ses points de données sur `null` comme décrit ci‑dessus.

**Q : Est‑il possible d’effacer uniquement les valeurs Y tout en conservant les libellés X ?**  
R : Oui. Appelez `dataPoint.getYValue().setValue(null)` et laissez la cellule X intacte.

**Q : Comment automatiser cela pour plusieurs présentations ?**  
R : Enveloppez le code d’effacement dans une boucle qui parcourt un répertoire de fichiers PPTX, en appliquant la même logique à chaque fichier.

## Ressources

- [Documentation Aspose.Slides](https://reference.aspose.com/slides/java/)
- [Télécharger Aspose.Slides pour Java](https://releases.aspose.com/slides/java/)
- [Acheter une licence](https://purchase.aspose.com/buy)
- [Version d’essai gratuite](https://releases.aspose.com/slides/java/)
- [Demande de licence temporaire](https://purchase.aspose.com/temporary-license/)
- [Forum communautaire Aspose](https://forum.aspose.com/c/slides/11)

Avec ces ressources, vous êtes prêt à commencer à effacer les points de données des graphiques dans vos applications Java. Bon codage !

---

**Dernière mise à jour :** 2026-08-27  
**Testé avec :** Aspose.Slides pour Java 25.4 (JDK 16)  
**Auteur :** Aspose

## Tutoriels associés

- [Comment modifier les données d’un graphique PowerPoint avec Aspose.Slides pour Java : guide complet](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [Comment ajouter un graphique à PowerPoint avec Aspose.Slides pour Java : guide étape par étape](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Effacer les points de données d’une série de graphique spécifique en Java Slides](/slides/java/java-slides-chart-data-manipulation/clear-specific-chart-series-data-points-java-slides/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}