---
date: '2026-01-09'
description: Découvrez comment utiliser Aspose Slides Maven pour ajouter un graphique
  à une diapositive et personnaliser un diagramme circulaire dans des présentations
  Java. Configuration étape par étape, code et exemples concrets.
keywords:
- add pie chart with Aspose.Slides Java
- Aspose.Slides for Java tutorial
- Java presentation automation
title: 'aspose slides maven - Ajouter un diagramme circulaire à une présentation'
url: /fr/java/charts-graphs/add-pie-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment ajouter un diagramme circulaire à une présentation en utilisant Aspose.Slides Java

## Introduction
Créer des présentations visuellement attrayantes est essentiel pour transmettre efficacement l'information, surtout lorsque la visualisation des données joue un rôle clé. Si vous cherchez à automatiser ce processus avec **aspose slides maven**, vous êtes au bon endroit. Dans ce tutoriel, vous apprendrez comment **add chart to slide** — plus précisément un diagramme circulaire — en utilisant Aspose.Slides pour Java, et vous verrez comment le personnaliser pour des scénarios réels.

### Ce que vous allez apprendre
- Comment initialiser un objet présentation en Java.  
- Étapes pour **add a pie chart java** sur la première diapositive d’une présentation.  
- Accéder aux classeurs de données du diagramme et lister les feuilles de calcul qui s’y trouvent.  

Plongeons dans la façon dont vous pouvez exploiter Aspose.Slides Java pour enrichir vos présentations avec des diagrammes dynamiques !

## Réponses rapides
- **Quelle bibliothèque ajoute des diagrammes via Maven ?** aspose slides maven  
- **Quel type de diagramme est démontré ?** Diagramme circulaire (add chart to slide)  
- **Version minimale de Java requise ?** JDK 16 ou supérieur  
- **Ai‑je besoin d’une licence pour les tests ?** Un essai gratuit fonctionne ; la production nécessite une licence  
- **Où trouver la dépendance Maven ?** Dans la section d’installation ci‑dessous  

## Qu’est‑ce qu’Aspose Slides Maven ?
Aspose.Slides pour Java est une API puissante qui permet aux développeurs de créer, modifier et rendre des fichiers PowerPoint de façon programmatique. Le package Maven (`aspose‑slides`) simplifie la gestion des dépendances, vous permettant de vous concentrer sur la construction et la personnalisation des diapositives—comme l’ajout d’un diagramme circulaire—sans vous soucier de la manipulation bas‑niveau des fichiers.

## Pourquoi utiliser Aspose.Slides Maven pour ajouter un diagramme à une diapositive ?
- **Automatisation :** Générer des rapports et tableaux de bord automatiquement.  
- **Précision :** Contrôle total sur les types de diagrammes, les données et le style.  
- **Multi‑plateforme :** Fonctionne sur tout environnement compatible Java.  

## Prérequis
- **Aspose.Slides pour Java** version 25.4 ou ultérieure (Maven/Gradle).  
- JDK 16+ installé.  
- Un IDE (IntelliJ IDEA, Eclipse, etc.).  
- Connaissances de base en Java et familiarité avec Maven ou Gradle.

## Installation d’Aspose.Slides pour Java
Tout d’abord, incluez Aspose.Slides dans votre projet via Maven ou Gradle.

**Maven :**  
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

Vous pouvez également [télécharger la dernière version](https://releases.aspose.com/slides/java/) directement depuis le site d’Aspose.

### Acquisition de licence
Aspose.Slides pour Java propose un essai gratuit avec une licence temporaire pour les tests. Pour une utilisation en production sans restriction, achetez une licence via la [page d’achat](https://purchase.aspose.com/buy).

## Guide d’implémentation
Nous décomposons la solution en deux fonctionnalités : ajouter un diagramme circulaire et accéder à son classeur de données.

### Fonctionnalité 1 : Créer une présentation et ajouter un diagramme
#### Vue d’ensemble
Cette partie montre comment créer une nouvelle présentation et **add a pie chart** à la première diapositive.

#### Étape par étape

**Étape 1 : Initialiser un nouvel objet Presentation**  
```java
Presentation pres = new Presentation();
```
*Crée l’instance `Presentation` qui contiendra toutes les diapositives.*

**Étape 2 : Ajouter un diagramme circulaire**  
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Pie,
    50,
    50,
    400,
    500
);
```
*Place un diagramme circulaire aux coordonnées (50, 50) avec une largeur de 400 et une hauteur de 500. L’énumération `ChartType.Pie` indique à Aspose de rendre un diagramme circulaire.*

**Étape 3 : Libérer les ressources**  
```java
if (pres != null) pres.dispose();
```
*Libère les ressources natives ; appelez toujours `dispose()` lorsque vous avez terminé.*

### Fonctionnalité 2 : Accéder au classeur de données du diagramme et aux feuilles de calcul
#### Vue d’ensemble
Apprenez comment atteindre le classeur sous‑jacent qui stocke les données du diagramme et parcourir ses feuilles de calcul.

#### Étape par étape

**Étape 1 : (Réutiliser) Initialiser un nouvel objet Presentation**  
*Identique à la Fonctionnalité 1, Étape 1.*

**Étape 2 : (Réutiliser) Ajouter un diagramme circulaire**  
*Identique à la Fonctionnalité 1, Étape 2.*

**Étape 3 : Obtenir le classeur de données du diagramme**  
```java
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
```
*Récupère le `IChartDataWorkbook` lié au diagramme.*

**Étape 4 : Parcourir les feuilles de calcul**  
```java
for (int i = 0; i < workbook.getWorksheets().size(); i++) {
    System.out.println(workbook.getWorksheets().get_Item(i).getName());
}
```
*Affiche le nom de chaque feuille de calcul, vous permettant de vérifier la structure des données.*

**Étape 5 : Libérer les ressources**  
*Identique à la Fonctionnalité 1, Étape 3.*

## Applications pratiques
- **Rapports de données :** Générer automatiquement des présentations avec des indicateurs à jour pour l’intelligence d’affaires.  
- **Présentations académiques :** Visualiser les résultats de recherche sans création manuelle de diagrammes.  
- **Matériel marketing :** Présenter instantanément les performances d’un produit ou les résultats d’enquêtes.

## Considérations de performance
- Gardez le nombre de diapositives et de diagrammes raisonnable ; chacun consomme de la mémoire.  
- Appelez toujours `dispose()` pour libérer les ressources natives.  
- Optimisez la gestion des données du classeur — évitez de charger des jeux de données massifs dans un seul diagramme.

## Conclusion
Nous avons vu comment **aspose slides maven** vous permet de **add chart to slide** de façon programmatique et comment travailler avec le classeur de données du diagramme. Avec ces blocs de construction, vous pouvez automatiser tout flux de travail de reporting nécessitant une sortie PowerPoint soignée.

### Prochaines étapes
- Explorer les options de style du diagramme (couleurs, légendes, étiquettes de données).  
- Se connecter à des sources de données externes (CSV, bases de données) pour alimenter les diagrammes dynamiquement.  
- Combiner plusieurs types de diagrammes dans une même présentation pour un storytelling plus riche.

## Foire aux questions

**Q : Comment installer Aspose.Slides pour Java ?**  
R : Utilisez la dépendance Maven ou Gradle présentée ci‑dessus, ou téléchargez la bibliothèque depuis la page des releases.

**Q : Quelles sont les exigences système pour Aspose.Slides ?**  
R : JDK 16 ou supérieur ; la bibliothèque est indépendante de la plateforme.

**Q : Puis‑je ajouter d’autres types de diagrammes que les circulaires ?**  
R : Oui, Aspose.Slides prend en charge les diagrammes à barres, lignes, nuages de points et bien d’autres.

**Q : Comment gérer efficacement de grandes présentations ?**  
R : Libérez les objets rapidement, limitez le nombre d’images haute résolution et réutilisez les modèles de diagrammes lorsque possible.

**Q : Où trouver plus de détails sur les fonctionnalités d’Aspose.Slides ?**  
R : Consultez la [documentation Aspose](https://reference.aspose.com/slides/java/) pour une référence API complète.

**Q : Une licence est‑elle requise pour une utilisation commerciale ?**  
R : Une licence valide est nécessaire en production ; un essai gratuit est disponible pour l’évaluation.

**Q : Le package Maven inclut‑il toutes les capacités de diagrammes ?**  
R : Oui, l’artifact Maven `aspose‑slides` contient le moteur complet de création de diagrammes.

## Ressources
- Documentation : [Référence API Aspose.Slides Java](https://reference.aspose.com/slides/java/)
- Téléchargement : [Dernières releases](https://releases.aspose.com/slides/java/)
- Achat et essai : [Page d’achat](https://purchase.aspose.com/buy)
- Essai gratuit : [Téléchargements d’essai](https://releases.aspose.com/slides/java/)
- Licence temporaire : [Demander une licence temporaire](https://purchase.aspose.com/temporary-license/)
- Forum d’assistance : [Forum communautaire Aspose](https://forum.aspose.com/c/slides/11)

---  

**Dernière mise à jour :** 2026-01-09  
**Testé avec :** Aspose.Slides 25.4 pour Java (jdk16)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
