---
"description": "Apprenez à obtenir le rectangle de portion dans PowerPoint avec Aspose.Slides pour Java grâce à ce tutoriel détaillé, étape par étape. Idéal pour les développeurs Java."
"linktitle": "Obtenir une portion rectangulaire dans PowerPoint avec Java"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Obtenir une portion rectangulaire dans PowerPoint avec Java"
"url": "/fr/java/java-powerpoint-advanced-paragraph-font-properties/get-portion-rectangle-powerpoint-java/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Obtenir une portion rectangulaire dans PowerPoint avec Java

## Introduction
Créer des présentations dynamiques en Java est un jeu d'enfant avec Aspose.Slides pour Java. Dans ce tutoriel, nous allons explorer les subtilités de la création d'un rectangle dans PowerPoint avec Aspose.Slides. Nous aborderons toutes les étapes, de la configuration de votre environnement à la décomposition du code étape par étape. Alors, c'est parti !
## Prérequis
Avant de passer au code, assurons-nous que vous disposez de tout ce dont vous avez besoin pour suivre le processus en douceur :
1. Kit de développement Java (JDK) : assurez-vous que JDK 8 ou supérieur est installé sur votre machine.
2. Aspose.Slides pour Java : téléchargez la dernière version depuis [ici](https://releases.aspose.com/slides/java/).
3. Environnement de développement intégré (IDE) : Eclipse, IntelliJ IDEA ou tout autre IDE Java de votre choix.
4. Connaissances de base de Java : la compréhension de la programmation Java est essentielle.
## Importer des packages
Commençons par importer les packages nécessaires. Cela comprendra Aspose.Slides et quelques autres pour gérer efficacement notre tâche.
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import java.awt.*;
import java.awt.geom.Rectangle2D;
```
## Étape 1 : Configuration de la présentation
La première étape consiste à créer une nouvelle présentation. Elle servira de toile de fond.
```java
Presentation pres = new Presentation();
```
## Étape 2 : Création d'un tableau
Ajoutons maintenant un tableau à la première diapositive de notre présentation. Ce tableau contiendra les cellules où nous ajouterons notre texte.
```java
ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```
## Étape 3 : Ajout de paragraphes aux cellules
Ensuite, nous allons créer des paragraphes et les ajouter à une cellule spécifique du tableau. Cela implique d'effacer tout texte existant, puis d'ajouter de nouveaux paragraphes.
```java
// Créer des paragraphes
IParagraph paragraph0 = new Paragraph();
paragraph0.getPortions().add(new Portion("Text "));
paragraph0.getPortions().add(new Portion("in0"));
paragraph0.getPortions().add(new Portion(" Cell"));
IParagraph paragraph1 = new Paragraph();
paragraph1.setText("On0");
IParagraph paragraph2 = new Paragraph();
paragraph2.getPortions().add(new Portion("Hi there "));
paragraph2.getPortions().add(new Portion("col0"));
// Ajouter du texte dans la cellule du tableau
ICell cell = tbl.get_Item(1, 1);
cell.getTextFrame().getParagraphs().clear();
cell.getTextFrame().getParagraphs().add(paragraph0);
cell.getTextFrame().getParagraphs().add(paragraph1);
cell.getTextFrame().getParagraphs().add(paragraph2);
```
## Étape 4 : Ajout d'un cadre de texte à une forme automatique
Pour rendre notre présentation plus dynamique, nous allons ajouter un cadre de texte à une forme automatique et définir son alignement.
```java
IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 400, 100, 60, 120);
autoShape.getTextFrame().setText("Text in shape");
autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```
## Étape 5 : Calcul des coordonnées
Nous devons obtenir les coordonnées du coin supérieur gauche de la cellule du tableau. Cela nous aidera à placer les formes avec précision.
```java
double x = tbl.getX() + cell.getOffsetX();
double y = tbl.getY() + cell.getOffsetY();
```
## Étape 6 : Ajout de cadres aux paragraphes et aux portions
En utilisant le `IParagraph.getRect()` et `IPortion.getRect()` Grâce à ces méthodes, nous pouvons ajouter des cadres à nos paragraphes et portions. Cela implique de parcourir les paragraphes et portions, de créer des formes autour d'eux et de personnaliser leur apparence.
```java
for (IParagraph para : cell.getTextFrame().getParagraphs()) {
    if ("".equals(para.getText())) continue;
    Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
    IAutoShape shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle,
        (float) rect.getX() + (float) x,
        (float) rect.getY() + (float) y,
        (float) rect.getWidth(),
        (float) rect.getHeight()
    );
    shape.getFillFormat().setFillType(FillType.NoFill);
    shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
    shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
    for (IPortion portion : para.getPortions()) {
        if (portion.getText().contains("0")) {
            rect = portion.getRect();
            shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
                ShapeType.Rectangle,
                (float) rect.getX() + (float) x,
                (float) rect.getY() + (float) y,
                (float) rect.getWidth(),
                (float) rect.getHeight()
            );
            shape.getFillFormat().setFillType(FillType.NoFill);
        }
    }
}
```
## Étape 7 : Ajout de cadres aux paragraphes de forme automatique
De même, nous ajouterons des cadres aux paragraphes de notre forme automatique, améliorant ainsi l’attrait visuel de la présentation.
```java
for (IParagraph para : autoShape.getTextFrame().getParagraphs()) {
    Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
    IAutoShape shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle,
        (float) rect.getX() + autoShape.getX(),
        (float) rect.getY() + autoShape.getY(),
        (float) rect.getWidth(),
        (float) rect.getHeight()
    );
    shape.getFillFormat().setFillType(FillType.NoFill);
    shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
    shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
}
```
## Étape 8 : Enregistrer la présentation
Enfin, nous enregistrerons notre présentation dans un chemin spécifié.
```java
String outPath = "path_to_output_directory";
pres.save(outPath + "GetRect_Out.pptx", SaveFormat.Pptx);
```
## Étape 9 : Nettoyage
Il est recommandé de supprimer l'objet de présentation pour libérer des ressources.
```java
if (pres != null) pres.dispose();
```
## Conclusion
Félicitations ! Vous avez appris à obtenir le rectangle de portion dans PowerPoint avec Aspose.Slides pour Java. Cette puissante bibliothèque ouvre un monde de possibilités pour créer des présentations dynamiques et visuellement attrayantes par programmation. Explorez Aspose.Slides et découvrez d'autres fonctionnalités pour améliorer vos présentations.
## FAQ
### Qu'est-ce qu'Aspose.Slides pour Java ?
Aspose.Slides pour Java est une bibliothèque puissante qui permet aux développeurs de créer, modifier et manipuler des présentations PowerPoint par programmation.
### Puis-je utiliser Aspose.Slides pour Java dans des projets commerciaux ?
Oui, Aspose.Slides pour Java peut être utilisé dans des projets commerciaux. Vous pouvez acheter une licence auprès de [ici](https://purchase.aspose.com/buy).
### Existe-t-il un essai gratuit disponible pour Aspose.Slides pour Java ?
Oui, vous pouvez télécharger une version d'essai gratuite à partir de [ici](https://releases.aspose.com/).
### Où puis-je trouver la documentation d'Aspose.Slides pour Java ?
La documentation est disponible [ici](https://reference.aspose.com/slides/java/).
### Comment puis-je obtenir de l'aide pour Aspose.Slides pour Java ?
Vous pouvez obtenir de l'aide sur le forum Aspose [ici](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}