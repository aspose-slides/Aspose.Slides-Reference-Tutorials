---
title: Exporter des formes au format SVG à partir d'une présentation
linktitle: Exporter des formes au format SVG à partir d'une présentation
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Découvrez comment exporter des formes d'une présentation PowerPoint au format SVG à l'aide d'Aspose.Slides pour .NET. Guide étape par étape avec code source inclus. Extrayez efficacement des formes pour diverses applications.
weight: 16
url: /fr/net/presentation-manipulation/export-shapes-to-svg-format-from-presentation/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


Dans le monde numérique d'aujourd'hui, les présentations jouent un rôle crucial dans la transmission efficace des informations. Cependant, nous devons parfois exporter des formes spécifiques de nos présentations vers différents formats à des fins diverses. L'un de ces formats est le SVG (Scalable Vector Graphics), connu pour son évolutivité et son adaptabilité. Dans ce didacticiel, nous vous guiderons tout au long du processus d'exportation de formes au format SVG à partir d'une présentation à l'aide d'Aspose.Slides pour .NET.

## 1. Introduction

Les présentations contiennent souvent des éléments visuels importants tels que des graphiques, des diagrammes et des illustrations. L'exportation de ces éléments au format SVG peut être utile pour les applications Web, l'impression ou l'édition ultérieure dans un logiciel de graphiques vectoriels. Aspose.Slides for .NET est une bibliothèque puissante qui vous permet d'automatiser des tâches comme celle-ci.

## 2. Conditions préalables

Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :

- Un environnement de développement avec Aspose.Slides pour .NET installé.
- Une présentation PowerPoint (PPTX) contenant la forme que vous souhaitez exporter.
- Connaissance de base de la programmation C#.

## 3. Configuration de votre environnement

Pour commencer, créez un nouveau projet C# dans votre IDE préféré. Assurez-vous d'avoir référencé la bibliothèque Aspose.Slides for .NET dans votre projet.

## 4. Chargement de la présentation

Dans votre code C#, vous devez spécifier le répertoire de votre présentation et le répertoire de sortie du fichier SVG. Voici un exemple :

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
string outSvgFileName = outPath + "SingleShape.svg";

using (Presentation pres = new Presentation(dataDir + "YourPresentation.pptx"))
{
    // Votre code pour exporter la forme ira ici.
}
```

## 5. Exporter une forme vers SVG

 Au sein du`using` bloc, vous pouvez accéder aux formes de votre présentation et les exporter au format SVG. Ici, nous exportons la première forme de la première diapositive :

```csharp
using (Stream stream = new FileStream(outSvgFileName, FileMode.Create, FileAccess.Write))
{
    pres.Slides[0].Shapes[0].WriteAsSvg(stream);
}
```

Vous pouvez personnaliser ce code pour exporter différentes formes ou appliquer des transformations supplémentaires si nécessaire.

## 6. Conclusion

Dans ce didacticiel, nous avons parcouru le processus d'exportation de formes au format SVG à partir d'une présentation PowerPoint à l'aide d'Aspose.Slides pour .NET. Cette puissante bibliothèque simplifie la tâche, vous permettant d'automatiser le processus d'exportation et d'améliorer votre flux de travail.

## 7. FAQ

### Q1 : Qu'est-ce que le format SVG ?

Scalable Vector Graphics (SVG) est un format d'image vectorielle basé sur XML qui est largement utilisé pour son évolutivité et sa compatibilité avec les navigateurs Web.

### Q2 : Puis-je exporter plusieurs formes à la fois ?

Oui, vous pouvez parcourir les formes de votre présentation et les exporter une par une.

### Q3 : Aspose.Slides pour .NET est-il une bibliothèque payante ?

Oui, Aspose.Slides for .NET est une bibliothèque commerciale avec un essai gratuit disponible.

### Q4 : Existe-t-il des limites à l’exportation de formes avec Aspose.Slides ?

La possibilité d'exporter des formes peut varier en fonction de la complexité de la forme et des fonctionnalités prises en charge par la bibliothèque.

### Q5 : Où puis-je obtenir de l'aide pour Aspose.Slides pour .NET ?

 Vous pouvez visiter le[Forum Aspose.Slides](https://forum.aspose.com/) pour du soutien et des discussions communautaires.

Maintenant que vous avez appris à exporter des formes au format SVG, vous pouvez améliorer vos présentations et les rendre plus polyvalentes à différentes fins. Bon codage !

 Pour plus de détails et de fonctionnalités avancées, reportez-vous au[Aspose.Slides pour la référence de l'API .NET](https://reference.aspose.com/slides/net/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
