---
date: '2026-08-06'
description: Apprenez à changer la font color de la legend et à modifier le legend
  text du chart avec Aspose.Slides for Java. Suivez des instructions étape par étape
  pour personnaliser rapidement les legends du chart.
keywords:
- customize chart legends in Aspose.Slides Java
- Aspose.Slides for Java legend customization
- Java presentation chart styling
lastmod: '2026-08-06'
og_description: Apprenez à changer la font color de la legend et à modifier le legend
  text du chart avec Aspose.Slides for Java. Ce guide vous montre les étapes exactes
  et les meilleures pratiques.
og_image_alt: 'Developer guide: change legend font color in Aspose.Slides for Java'
og_title: Comment changer la font color de la legend dans Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Learn how to change legend font color and modify chart legend text
    using Aspose.Slides for Java. Follow step‑by‑step instructions to customize chart
    legends quickly.
  headline: How to change legend font color in Aspose.Slides for Java
  type: TechArticle
- description: Learn how to change legend font color and modify chart legend text
    using Aspose.Slides for Java. Follow step‑by‑step instructions to customize chart
    legends quickly.
  name: How to change legend font color in Aspose.Slides for Java
  steps:
  - name: Initialize Aspose.Slides in your Java application.
    text: Initialize Aspose.Slides in your Java application.
  - name: Load an existing presentation or create a new one.
    text: Load an existing presentation or create a new one.
  - name: '**Load the presentation:**'
    text: '**Load the presentation:**'
  - name: '**Add a clustered column chart:**'
    text: '**Add a clustered column chart:**'
  - name: '**Access legend entry text format:**'
    text: '**Access legend entry text format:**'
  - name: '**Set bold and italic styles with a specific height:**'
    text: '**Set bold and italic styles with a specific height:**'
  - name: '**Change fill type to solid color for better visibility:**'
    text: '**Change fill type to solid color for better visibility:**'
  - name: '**Save your changes:**'
    text: '**Save your changes:**'
  - name: '**Business presentations:** Align legend colors with corporate branding
      for a polished look.'
    text: '**Business presentations:** Align legend colors with corporate branding
      for a polished look.'
  - name: '**Educational materials:** Highlight key data series by using contrasting
      legend colors.'
    text: '**Educational materials:** Highlight key data series by using contrasting
      legend colors.'
  type: HowTo
- questions:
  - answer: No, the color change is preserved in all export formats supported by Aspose.Slides,
      including PDF and PPTX.
    question: Does changing the legend font color affect exported PDF files?
  - answer: Yes – set `FillType.Gradient` and configure the gradient stops via `getGradientStyle()`.
    question: Can I use a gradient instead of a solid color?
  - answer: A chart can have up to 256 legend entries, limited only by the number
      of data series you add.
    question: How many legend entries can a chart have?
  type: FAQPage
tags:
- change legend font color
- Aspose.Slides
- Java chart customization
- presentation styling
title: Comment changer la font color de la legend dans Aspose.Slides for Java
url: /fr/java/charts-graphs/customize-chart-legends-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment modifier la couleur de police de la légende dans Aspose.Slides for Java

## Introduction
Si vous devez **modifier la couleur de police de la légende** dans un graphique, Aspose.Slides for Java vous offre un contrôle total sur chaque entrée de légende. Ce tutoriel vous guide à travers la personnalisation des styles de texte de la légende, l'application de polices en gras ou en italique, et la définition de couleurs unies afin que vos graphiques aient exactement l'apparence souhaitée. À la fin de ce guide, vous serez capable de modifier le texte de la légende du graphique en toute confiance et d'intégrer les modifications dans n'importe quelle présentation existante.

**Ce que vous apprendrez**
- Comment **modifier la couleur de police de la légende** programmétiquement.
- Moyens de **modifier le texte de la légende du graphique** tels que gras, italique et taille.
- Conseils pour appliquer les modifications à plusieurs graphiques dans une même présentation.
- Comment intégrer ces étapes dans un flux de travail d'automatisation plus large.

## Réponses rapides
- **Puis-je changer la couleur d'une seule entrée de légende ?** Oui – accédez à l'entrée via son index et définissez le format de remplissage sur une couleur unie.  
- **Ai-je besoin d'une licence pour utiliser ces API ?** Une licence temporaire ou payante est requise pour la production ; un essai gratuit fonctionne pour l'évaluation.  
- **Quelle version de Java est prise en charge ?** Aspose.Slides for Java 25.4+ fonctionne avec JDK 16 et versions ultérieures.  
- **Les modifications affecteront-elles d'autres éléments du graphique ?** Non, le formatage de la légende est isolé du style des séries de données.  
- **Le traitement par lots est-il possible ?** Absolument – parcourez les diapositives et les graphiques pour appliquer les mêmes paramètres de légende à l'ensemble du diaporama.

## Qu'est-ce que le changement de couleur de police de la légende ?
`change legend font color` désigne l'opération programmatique consistant à définir la couleur du texte des entrées de légende d'un graphique à l'aide de l'API Aspose.Slides. Cette opération met à jour l'apparence visuelle de la légende sans modifier les données sous-jacentes.

## Pourquoi personnaliser les légendes des graphiques ?
Aspose.Slides prend en charge **plus de 50 formats d'entrée et de sortie** et peut gérer des présentations contenant **plus de 500 diapositives** tout en maintenant l'utilisation de la mémoire en dessous de 200 Mo. Personnaliser les légendes améliore la lisibilité, renforce les couleurs de la marque et garantit que les points de données clés se démarquent—en particulier dans les présentations professionnelles ou éducatives où la clarté visuelle guide la prise de décision.

## Prérequis
- **Bibliothèque Aspose.Slides for Java** (Version 25.4 ou ultérieure).  
- Java Development Kit (JDK) 16 ou supérieur.  
- Un IDE tel qu'IntelliJ IDEA, Eclipse ou NetBeans.  
- Maven ou Gradle pour la gestion des dépendances.  
- Connaissances de base en programmation Java.

## Configuration d'Aspose.Slides for Java
Pour commencer à personnaliser les légendes de vos graphiques, ajoutez la bibliothèque à votre projet en utilisant l'une des méthodes ci-dessous.

### Maven
Ajoutez la dépendance suivante à votre fichier `pom.xml` :
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Incluez cette ligne dans votre fichier `build.gradle` :
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Téléchargement direct
Vous pouvez également obtenir le dernier JAR depuis [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Étapes d'obtention de licence
- **Essai gratuit :** Commencez avec un essai gratuit pour explorer les fonctionnalités d'Aspose.Slides.  
- **Licence temporaire :** Demandez une licence temporaire pour une évaluation prolongée.  
- **Achat :** Pour un accès complet, envisagez d'acheter une licence sur [Aspose Purchase](https://purchase.aspose.com/buy).

#### Initialisation et configuration de base
Après avoir ajouté la bibliothèque à votre projet :
1. Initialisez Aspose.Slides dans votre application Java.  
2. Chargez une présentation existante ou créez-en une nouvelle.

## Comment modifier la couleur de police de la légende ?
Pour modifier la couleur de police de la légende, chargez la présentation, récupérez l'objet graphique, obtenez sa légende, puis modifiez le format du texte de chaque entrée de légende en définissant le type de remplissage sur solide et en spécifiant la couleur souhaitée. Cette opération unique met à jour la couleur du texte de la légende instantanément sans avoir besoin de redessiner toute la diapositive. Exemple : `legendEntry.getTextFormat().getFillFormat().setFillType(FillType.Solid); legendEntry.getTextFormat().getFillFormat().setSolidFillColor(Color.RED);` Cette approche fonctionne pour tout type de graphique et ne nécessite pas de re‑rendu complet de la diapositive.

### Accès et modification des propriétés du texte de la légende

#### Ancre de définition
L'interface `IChart` représente un objet graphique sur une diapositive, et sa méthode `getLegend()` renvoie un objet `ILegend` qui contient une collection d'éléments `ILegendEntry`.

#### Ajout d'un graphique à votre présentation
1. **Charger la présentation :**  
   ```java
   Presentation pres = new Presentation(dataDir + "/test.pptx");
   ```  

2. **Ajouter un graphique à colonnes groupées :**  
   ```java
   IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
       ChartType.ClusteredColumn, 50, 50, 600, 400);
   ```  

#### Personnalisation des propriétés de police
3. **Accéder au format du texte de l'entrée de légende :**  
   Ici, `legendEntry` est un objet `ILegendEntry` représentant une seule entrée dans la légende du graphique.  
   ```java
   IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
   ```  

4. **Définir les styles gras et italique avec une hauteur spécifique :**  
   ```java
   tf.getPortionFormat().setFontBold(NullableBool.True);
   tf.getPortionFormat().setFontHeight(20);
   tf.getPortionFormat().setFontItalic(NullableBool.True);
   ```  

5. **Changer le type de remplissage en couleur unie pour une meilleure visibilité :**  
   ```java
   tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
   tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
   ```  

6. **Enregistrer vos modifications :**  
   ```java
   pres.save(outputDir + "/output.pptx", SaveFormat.Pptx);
   ```  

### Pièges courants et dépannage
- Vérifiez que l'index de l'entrée de légende correspond à l'ordre des séries dans votre graphique.  
- Assurez-vous d'utiliser une version de la bibliothèque qui prend en charge `setSolidFillColor` (disponible depuis la version 20.9).  

## Applications pratiques
La personnalisation du texte de la légende est utile dans de nombreux scénarios réels :

1. **Présentations professionnelles :** Alignez les couleurs de la légende avec l'identité visuelle de l'entreprise pour un rendu soigné.  
2. **Supports éducatifs :** Mettez en évidence les séries de données clés en utilisant des couleurs de légende contrastées.  
3. **Présentations marketing :** Soulignez les indicateurs de performance avec des légendes en gras et colorées pour capter l'attention des parties prenantes.  

Vous pouvez également automatiser les mises à jour des légendes en récupérant les valeurs de couleur depuis une base de données ou un fichier de configuration.

## Considérations de performance
Lors du traitement de gros diaporamas, gardez ces conseils à l'esprit :

- **Gestion efficace de la mémoire :** Appelez `presentation.dispose()` après l'enregistrement pour libérer les ressources natives.  
- **Charger uniquement les diapositives nécessaires :** Utilisez `Presentation.load(String path, LoadOptions options)` avec `LoadOptions.setLoadOnlySlideIds()` si vous avez besoin d'un sous‑ensemble.  
- **Traitement par lots :** Regroupez les mises à jour de légende par diapositive pour réduire le nombre d'appels API et améliorer le débit.

## Conclusion
Vous savez maintenant comment **modifier la couleur de police de la légende** et **modifier le texte de la légende du graphique** à l'aide d'Aspose.Slides for Java. Ces personnalisations améliorent la clarté visuelle et vous aident à transmettre les données plus efficacement. Expérimentez avec différentes polices, tailles et couleurs pour correspondre au guide de style de votre présentation, et explorez d'autres fonctionnalités de style de graphique pour créer des diaporamas vraiment professionnels.

**Prochaines étapes**
- Essayez d'appliquer le même style de légende aux graphiques en secteurs et en lignes.  
- Combinez la personnalisation de la légende avec le formatage des étiquettes de données pour un graphique entièrement brandé.  

Prêt à améliorer vos présentations ? Mettez en œuvre les étapes ci‑dessus et voyez la différence immédiatement !

## Section FAQ
1. **Comment changer la couleur du texte d'une entrée de légende ?**  
   Utilisez `getFillFormat().setFillType(FillType.Solid)` puis `setSolidFillColor(Color.YOUR_COLOR)` sur le format du texte de l'entrée de légende.  

2. **Puis-je appliquer ces modifications à toutes les légendes d'une présentation ?**  
   Oui – parcourez chaque diapositive, localisez chaque graphique et mettez à jour les entrées de légende dans une boucle.  

3. **Est‑il possible d'ajuster dynamiquement la taille de la police en fonction de la longueur du texte ?**  
   Vous pouvez calculer la taille requise avec `TextFrame.getTextFrameFormat().getFontHeight()` et la définir via `setFontHeight(double)`.  

4. **Que faire si je rencontre des problèmes d'indexation des entrées de légende ?**  
   Vérifiez que l'index que vous utilisez correspond à l'ordre des séries ; rappelez‑vous que les index commencent à zéro.  

5. **Où trouver plus d'exemples Aspose.Slides ?**  
   Explorez la [Aspose Documentation](https://reference.aspose.com/slides/java/) pour des guides complets et des références API.  

**Questions supplémentaires**
**Q : Le changement de couleur de la police de la légende affecte-t-il les fichiers PDF exportés ?**  
R : Non, le changement de couleur est conservé dans tous les formats d'exportation pris en charge par Aspose.Slides, y compris PDF et PPTX.  

**Q : Puis‑je utiliser un dégradé au lieu d'une couleur unie ?**  
R : Oui – définissez `FillType.Gradient` et configurez les arrêts du dégradé via `getGradientStyle()`.  

**Q : Combien d'entrées de légende un graphique peut‑il contenir ?**  
R : Un graphique peut contenir jusqu'à 256 entrées de légende, limité uniquement par le nombre de séries de données que vous ajoutez.  

## Ressources
- **Documentation :** Guide complet sur l'utilisation des fonctionnalités d'Aspose.Slides ([Link](https://reference.aspose.com/slides/java/)).  
- **Téléchargement :** Accédez à la dernière version d'Aspose.Slides for Java ([Link](https://releases.aspose.com/slides/java/)).  
- **Achat :** Achetez une licence pour débloquer toutes les capacités ([Link](https://purchase.aspose.com/buy)).  
- **Essai gratuit & licence temporaire :** Commencez avec des essais gratuits et demandez des licences temporaires ([Free Trial Link](https://releases.aspose.com/slides/java/), [Temporary License Link](https://purchase.aspose.com/temporary-license/)).  
- **Support :** Obtenez de l'aide de la communauté sur le forum de support d'Aspose ([Link](https://forum.aspose.com/c/slides/11)).  

---

**Dernière mise à jour :** 2026-08-06  
**Testé avec :** Aspose.Slides for Java 25.4  
**Auteur :** Aspose

## Tutoriels associés

- [Améliorer les graphiques PowerPoint : personnalisation des polices et des axes avec Aspose.Slides for Java](/slides/java/charts-graphs/enhance-powerpoint-charts-aspose-slides-java/)
- [Aspose.Slides for Java : guide des cadres de texte dynamiques et de la personnalisation des polices](/slides/java/shapes-text-frames/aspose-slides-java-dynamic-text-frames-fonts/)
- [Animer les graphiques PowerPoint avec Aspose.Slides for Java – guide étape par étape](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}