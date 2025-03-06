---
title: Enregistrer en tant que type de vue prédéfini dans les diapositives Java
linktitle: Enregistrer en tant que type de vue prédéfini dans les diapositives Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment définir des types d'affichage prédéfinis dans Java Slides à l'aide d'Aspose.Slides pour Java. Guide étape par étape avec des exemples de code et des FAQ.
weight: 10
url: /fr/java/saving-options/save-as-predefined-view-type-in-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Enregistrer en tant que type de vue prédéfini dans les diapositives Java


## Introduction à l'enregistrement en tant que type de vue prédéfini dans les diapositives Java

Dans ce guide étape par étape, nous explorerons comment enregistrer une présentation avec un type de vue prédéfini à l'aide d'Aspose.Slides pour Java. Nous vous fournirons le code et les explications nécessaires pour accomplir cette tâche avec succès.

## Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Connaissance de base de la programmation Java.
- Aspose.Slides pour la bibliothèque Java installée.
- Environnement de développement intégré (IDE) de votre choix.

## Configuration de votre environnement

Pour commencer, suivez ces étapes pour configurer votre environnement de développement :

1. Créez un nouveau projet Java dans votre IDE.
2. Ajoutez la bibliothèque Aspose.Slides pour Java à votre projet en tant que dépendance.

Maintenant que votre environnement est configuré, passons au code.

## Étape 1 : Créer une présentation

Pour illustrer l’enregistrement d’une présentation avec un type d’affichage prédéfini, nous allons d’abord créer une nouvelle présentation. Voici le code pour créer une présentation :

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
// Ouverture du fichier de présentation
Presentation presentation = new Presentation();
```

 Dans ce code, nous créons un nouveau`Presentation` objet, qui représente notre présentation PowerPoint.

## Étape 2 : Définition du type d'affichage

Ensuite, nous définirons le type d’affichage de notre présentation. Les types de vue définissent la façon dont la présentation est affichée une fois ouverte. Dans cet exemple, nous le définirons sur « Vue maître des diapositives ». Voici le code :

```java
// Définition du type d'affichage
presentation.getViewProperties().setLastView(ViewType.SlideMasterView);
```

 Dans le code ci-dessus, nous utilisons le`setLastView` méthode du`ViewProperties` classe pour définir le type de vue sur`SlideMasterView`. Vous pouvez choisir d'autres types de vues selon vos besoins.

## Étape 3 : enregistrement de la présentation

Maintenant que nous avons créé notre présentation et défini le type d'affichage, il est temps de sauvegarder la présentation. Nous l'enregistrerons au format PPTX. Voici le code :

```java
// Enregistrement de la présentation
presentation.save(dataDir + "SetViewType_out.pptx", SaveFormat.Pptx);
```

 Dans ce code, nous utilisons le`save` méthode du`Presentation` classe pour enregistrer la présentation avec le nom de fichier et le format spécifiés.

## Code source complet pour enregistrer en tant que type de vue prédéfini dans les diapositives Java

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
// Ouverture du fichier de présentation
Presentation presentation = new Presentation();
try
{
	// Définition du type d'affichage
	presentation.getViewProperties().setLastView(ViewType.SlideMasterView);
	// Enregistrement de la présentation
	presentation.save(dataDir + "SetViewType_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusion

Dans ce didacticiel, nous avons appris à enregistrer une présentation avec un type de vue prédéfini en Java à l'aide d'Aspose.Slides pour Java. En suivant le code et les étapes fournis, vous pouvez facilement définir le type d'affichage de vos présentations et les enregistrer au format souhaité.

## FAQ

### Comment puis-je changer le type d'affichage en autre chose que « Vue maître des diapositives » ?

 Pour modifier le type d'affichage en autre chose que « Vue maître des diapositives », remplacez simplement`ViewType.SlideMasterView` avec le type de vue souhaité, tel que`ViewType.NormalView` ou`ViewType.SlideSorterView`, dans le code où nous définissons le type de vue.

### Puis-je définir les propriétés d’affichage pour des diapositives individuelles dans la présentation ?

Oui, vous pouvez définir les propriétés d'affichage pour des diapositives individuelles à l'aide d'Aspose.Slides for Java. Vous pouvez accéder et manipuler les propriétés de chaque diapositive séparément en parcourant les diapositives de la présentation.

### Dans quels autres formats puis-je enregistrer ma présentation ?

Aspose.Slides pour Java prend en charge divers formats de sortie, notamment PPTX, PDF, TIFF, HTML, etc. Vous pouvez spécifier le format souhaité lors de l'enregistrement de votre présentation en utilisant le`SaveFormat` valeur enum.

### Aspose.Slides for Java est-il adapté au traitement par lots de présentations ?

Oui, Aspose.Slides pour Java est bien adapté aux tâches de traitement par lots. Vous pouvez automatiser le traitement de plusieurs présentations, appliquer des modifications et les enregistrer en masse à l'aide du code Java.

### Où puis-je trouver plus d’informations et de documentation sur Aspose.Slides pour Java ?

 Pour une documentation complète et des références liées à Aspose.Slides pour Java, veuillez visiter le site Web de documentation :[Aspose.Slides pour Java Documentation](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
