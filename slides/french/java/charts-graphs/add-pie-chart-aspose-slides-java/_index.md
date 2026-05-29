---
date: '2026-05-29'
description: Apprenez comment créer un pie chart Aspose en utilisant Aspose.Slides
  Maven, ajouter un pie chart java à une slide, et personnaliser les données du chart.
  Guide étape par étape avec la configuration Maven et des exemples concrets.
keywords:
- create pie chart aspose
- add pie chart java
- add chart slide
- aspose slides maven example
schemas:
- author: Aspose
  dateModified: '2026-05-29'
  description: Learn how to create pie chart aspose using Aspose.Slides Maven, add
    pie chart java to a slide, and customize chart data. Step‑by‑step guide with Maven
    setup and real‑world examples.
  headline: Create Pie Chart Aspose – Add a Chart to a Presentation with Maven
  type: TechArticle
- questions:
  - answer: Use the Maven or Gradle dependency shown above, or download the library
      from the releases page.
    question: How do I install Aspose.Slides for Java?
  - answer: JDK 16 or later; the library runs on any platform that supports Java.
    question: What are the system requirements for Aspose.Slides?
  - answer: Yes, Aspose.Slides supports bar, line, scatter, radar, and more than 20
      chart types.
    question: Can I add other chart types besides pie charts?
  - answer: Dispose of objects promptly, limit high‑resolution images, and reuse chart
      templates to keep memory usage low.
    question: How should I handle large presentations efficiently?
  - answer: Visit the [Aspose documentation](https://reference.aspose.com/slides/java/)
      for a complete API reference.
    question: Where can I find more details about Aspose.Slides features?
  type: FAQPage
title: Créer un pie chart Aspose – Ajouter un chart à une presentation avec Maven
url: /fr/java/charts-graphs/add-pie-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment ajouter un diagramme circulaire à une présentation avec Aspose.Slides Java

## Introduction
Dans ce guide, vous allez **create pie chart aspose** avec Aspose.Slides Maven et voir comment l’intégrer dans une diapositive PowerPoint. Créer des présentations visuellement attrayantes est crucial pour transmettre efficacement l’information, surtout lorsque la visualisation des données joue un rôle clé. Si vous cherchez à automatiser ce processus avec **aspose slides maven**, vous êtes au bon endroit. Nous parcourrons l’ajout d’un graphique à une diapositive — spécifiquement un diagramme circulaire — et sa personnalisation pour des scénarios réels.

### Ce que vous apprendrez
- Comment initialiser un objet présentation en Java.  
- Étapes pour **add a pie chart java** sur la première diapositive d’une présentation.  
- Accéder aux classeurs de données du graphique et lister les feuilles de calcul qui s’y trouvent.  

Plongeons dans la façon dont vous pouvez exploiter Aspose.Slides Java pour améliorer vos présentations avec des graphiques dynamiques !

## Réponses rapides
- **Quelle bibliothèque ajoute des graphiques via Maven ?** aspose slides maven  
- **Quel type de graphique est démontré ?** Pie chart (add chart to slide)  
- **Version minimale de Java requise ?** JDK 16 or later  
- **Ai-je besoin d’une licence pour les tests ?** A free trial works; production needs a license  
- **Où puis‑je trouver la dépendance Maven ?** In the setup section below  

## Qu’est‑ce que Aspose Slides Maven ?
Aspose.Slides for Java est une API puissante qui permet aux développeurs de créer, modifier et rendre des fichiers PowerPoint de manière programmatique. Le package Maven (`aspose-slides`) simplifie la gestion des dépendances, vous permettant de vous concentrer sur la création et la personnalisation des diapositives—comme l’ajout d’un diagramme circulaire—sans gérer la manipulation de fichiers de bas niveau.

## Pourquoi utiliser Aspose.Slides Maven pour ajouter un graphique à une diapositive ?
Utiliser Aspose.Slides Maven vous permet de générer des graphiques directement depuis le code Java sans édition manuelle de PowerPoint. Il offre un contrôle programmatique complet sur les types de graphiques, les sources de données et le style, garantissant une cohérence de la marque et une précision. L’artifact Maven gère également toutes les dépendances requises, simplifiant les builds et permettant une intégration fluide dans les pipelines CI/CD.

## Prérequis
- **Aspose.Slides for Java** version 25.4 ou ultérieure (Maven/Gradle).  
- JDK 16+ installé.  
- Un IDE (IntelliJ IDEA, Eclipse, etc.).  
- Connaissances de base en Java et familiarité avec Maven ou Gradle.

## Configuration d’Aspose.Slides pour Java
Tout d’abord, incluez Aspose.Slides dans votre projet via Maven ou Gradle.

**Maven:**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
</dependency>
```
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**  
```groovy
implementation 'com.aspose:aspose-slides:25.4'
```
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Alternativement, vous pouvez [télécharger la dernière version](https://releases.aspose.com/slides/java/) directement depuis le site d’Aspose.

### Acquisition de licence
Aspose.Slides for Java propose un essai gratuit avec une licence temporaire pour les tests. Pour une utilisation en production sans restriction, achetez une licence via la [page d’achat](https://purchase.aspose.com/buy).

## Guide d’implémentation
Ci‑dessous, nous décomposons la solution en deux fonctionnalités : ajouter un diagramme circulaire et accéder à son classeur de données.

### Fonctionnalité 1 : création d’une présentation et ajout d’un graphique
#### Vue d’ensemble
Cette partie montre comment créer une nouvelle présentation et **add a pie chart** à la première diapositive.

#### Comment créer pie chart aspose ?
Chargez la classe `Presentation`, ajoutez un graphique de type `ChartType.Pie`, puis enregistrez le fichier. L’opération complète ne nécessite que trois appels API et s’exécute en moins d’une seconde pour un jeu de diapositives typique de 10 diapositives, ce qui le rend idéal pour la génération automatisée de rapports.

#### Étape par étape

**Étape 1 : Initialiser un nouvel objet Presentation**  
La classe `Presentation` est l’objet de haut niveau d’Aspose.Slides qui représente un fichier PowerPoint en mémoire.  
```java
Presentation pres = new Presentation();
```
*Crée l’instance `Presentation` qui contiendra toutes les diapositives.*

**Étape 2 : Ajouter un diagramme circulaire**  
`ChartType.Pie` indique à Aspose de rendre un diagramme circulaire.  
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Pie,
    50,
    50,
    400,
    500
);
```
*Place un diagramme circulaire aux coordonnées (50, 50) avec une largeur de 400 et une hauteur de 500.*

**Étape 3 : Libérer les ressources**  
Appeler `dispose()` libère les ressources natives et empêche les fuites de mémoire.  
```java
if (pres != null) pres.dispose();
```
*Libère les ressources natives ; appelez toujours `dispose()` une fois terminé.*

### Fonctionnalité 2 : accéder au classeur de données du graphique et aux feuilles de calcul
#### Vue d’ensemble
Apprenez comment accéder au classeur sous‑jacent qui stocke les données du graphique et parcourir ses feuilles de calcul.

#### Comment accéder au classeur de données du graphique ?
Récupérez le `IChartDataWorkbook` depuis le graphique, puis parcourez sa collection `Worksheets`. Ce classeur imite un fichier Excel, vous permettant de lire, modifier ou ajouter des séries de données de façon programmatique, ce que le graphique reflétera instantanément lorsqu’il sera actualisé pendant l’exécution sans redémarrage.

#### Étape par étape

**Étape 1 : (Réutiliser) Initialiser un nouvel objet Presentation**  
*Identique à la Fonctionnalité 1, Étape 1.*

**Étape 2 : (Réutiliser) Ajouter un diagramme circulaire**  
*Identique à la Fonctionnalité 1, Étape 2.*

**Étape 3 : Obtenir le classeur de données du graphique**  
`IChartDataWorkbook` est l’interface qui fournit un accès en lecture/écriture au classeur interne du graphique, similaire à Excel.  
```java
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
```
*Récupère le `IChartDataWorkbook` lié au graphique.*

**Étape 4 : Parcourir les feuilles de calcul**  
Les objets `Worksheet` représentent les feuilles individuelles à l’intérieur du classeur.  
```java
for (int i = 0; i < workbook.getWorksheets().size(); i++) {
    System.out.println(workbook.getWorksheets().get_Item(i).getName());
}
```
*Affiche le nom de chaque feuille de calcul, vous permettant de vérifier la structure des données.*

**Étape 5 : Libérer les ressources**  
*Identique à la Fonctionnalité 1, Étape 3.*

## Applications pratiques
- **Reporting de données :** Générer automatiquement des présentations avec des indicateurs à jour pour l’intelligence d’affaires.  
- **Présentations académiques :** Visualiser les résultats de recherche sans création manuelle de graphiques.  
- **Matériel marketing :** Présenter instantanément la performance d’un produit ou les résultats d’enquêtes.

## Considérations de performance
- Aspose.Slides peut gérer **plus de 50 formats d’entrée et de sortie** et traiter des présentations de plusieurs centaines de pages sans charger le fichier complet en mémoire.  
- Gardez le nombre de diapositives et de graphiques raisonnable ; chaque graphique consomme de la mémoire native.  
- Appelez toujours `dispose()` pour libérer rapidement les ressources.  
- Optimisez la gestion des données du classeur — évitez de charger d’énormes ensembles de données dans un seul graphique.

## Conclusion
Nous avons vu comment **aspose slides maven** vous permet de **add chart to slide** de façon programmatique et comment travailler avec le classeur de données du graphique. Avec ces éléments de base, vous pouvez automatiser tout flux de travail de reporting nécessitant une sortie PowerPoint soignée.

### Prochaines étapes
- Explorez les options de style de graphique (couleurs, légendes, étiquettes de données).  
- Connectez-vous à des sources de données externes (CSV, bases de données) pour alimenter les graphiques dynamiquement.  
- Combinez plusieurs types de graphiques dans une même présentation pour un storytelling plus riche.

## Questions fréquemment posées

**Q : Comment installer Aspose.Slides pour Java ?**  
R : Utilisez la dépendance Maven ou Gradle indiquée ci‑dessus, ou téléchargez la bibliothèque depuis la page des releases.

**Q : Quelles sont les exigences système pour Aspose.Slides ?**  
R : JDK 16 ou ultérieur ; la bibliothèque fonctionne sur toute plateforme supportant Java.

**Q : Puis‑je ajouter d’autres types de graphiques en plus des diagrammes circulaires ?**  
R : Oui, Aspose.Slides prend en charge les graphiques à barres, lignes, nuages de points, radar, et plus de 20 types de graphiques.

**Q : Comment gérer efficacement de grandes présentations ?**  
R : Libérez les objets rapidement, limitez les images haute résolution et réutilisez les modèles de graphiques pour maintenir une faible utilisation de la mémoire.

**Q : Où puis‑je trouver plus de détails sur les fonctionnalités d’Aspose.Slides ?**  
R : Consultez la [documentation Aspose](https://reference.aspose.com/slides/java/) pour une référence API complète.

**Q : Une licence est‑elle requise pour une utilisation commerciale ?**  
R : Une licence valide est requise pour la production ; un essai gratuit est disponible pour l’évaluation.

**Q : Le package Maven inclut‑il toutes les capacités de graphiques ?**  
R : Oui, l’artifact Maven `aspose-slides` contient le moteur complet de graphiques.

## Ressources
- Documentation : [Référence API Aspose.Slides Java](https://reference.aspose.com/slides/java/)
- Téléchargement : [Dernières versions](https://releases.aspose.com/slides/java/)
- Achat et essai : [Page d’achat](https://purchase.aspose.com/buy)
- Essai gratuit : [Téléchargements d’essai](https://releases.aspose.com/slides/java/)
- Licence temporaire : [Demander une licence temporaire](https://purchase.aspose.com/temporary-license/)
- Forum de support : [Forum communautaire Aspose](https://forum.aspose.com/c/slides/11)

---  

**Dernière mise à jour :** 2026-05-29  
**Testé avec :** Aspose.Slides 25.4 for Java (jdk16)  
**Auteur :** Aspose

## Tutoriels associés

- [Comment personnaliser les couleurs d’un diagramme circulaire en Java avec Aspose.Slides – Guide complet](/slides/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/)
- [Créer un diagramme circulaire imbriqué en Java avec Aspose.Slides : guide complet](/slides/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/)
- [Animer les graphiques PowerPoint avec Aspose.Slides pour Java – Guide étape par étape](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}