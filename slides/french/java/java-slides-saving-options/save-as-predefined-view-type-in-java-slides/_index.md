---
"description": "Apprenez à définir des types de vues prédéfinis dans Java Slides avec Aspose.Slides pour Java. Guide étape par étape avec exemples de code et FAQ."
"linktitle": "Enregistrer comme type de vue prédéfini dans les diapositives Java"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Enregistrer comme type de vue prédéfini dans les diapositives Java"
"url": "/fr/java/saving-options/save-as-predefined-view-type-in-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Enregistrer comme type de vue prédéfini dans les diapositives Java


## Introduction à l'enregistrement en tant que type de vue prédéfini dans les diapositives Java

Dans ce guide étape par étape, nous allons découvrir comment enregistrer une présentation avec un type d'affichage prédéfini à l'aide d'Aspose.Slides pour Java. Nous vous fournirons le code et les explications nécessaires pour réussir cette tâche.

## Prérequis

Avant de commencer, assurez-vous d’avoir les éléments suivants :

- Connaissances de base de la programmation Java.
- Bibliothèque Aspose.Slides pour Java installée.
- Environnement de développement intégré (IDE) de votre choix.

## Configuration de votre environnement

Pour commencer, suivez ces étapes pour configurer votre environnement de développement :

1. Créez un nouveau projet Java dans votre IDE.
2. Ajoutez la bibliothèque Aspose.Slides pour Java à votre projet en tant que dépendance.

Maintenant que votre environnement est configuré, passons au code.

## Étape 1 : Créer une présentation

Pour illustrer l'enregistrement d'une présentation avec un type d'affichage prédéfini, nous allons d'abord créer une nouvelle présentation. Voici le code pour créer une présentation :

```java
// Le chemin vers le répertoire des documents.
String dataDir = "Your Document Directory";
// Ouverture du fichier de présentation
Presentation presentation = new Presentation();
```

Dans ce code, nous créons un nouveau `Presentation` objet, qui représente notre présentation PowerPoint.

## Étape 2 : Définition du type de vue

Nous allons maintenant définir le type d'affichage de notre présentation. Les types d'affichage définissent l'affichage de la présentation à l'ouverture. Dans cet exemple, nous allons le définir sur « Affichage Masque des diapositives ». Voici le code :

```java
// Définition du type de vue
presentation.getViewProperties().setLastView(ViewType.SlideMasterView);
```

Dans le code ci-dessus, nous utilisons le `setLastView` méthode de la `ViewProperties` classe pour définir le type de vue `SlideMasterView`Vous pouvez choisir d’autres types de vue selon vos besoins.

## Étape 3 : Enregistrer la présentation

Maintenant que nous avons créé notre présentation et défini le type d'affichage, il est temps de l'enregistrer. Nous l'enregistrerons au format PPTX. Voici le code :

```java
// Sauvegarde de la présentation
presentation.save(dataDir + "SetViewType_out.pptx", SaveFormat.Pptx);
```

Dans ce code, nous utilisons le `save` méthode de la `Presentation` classe pour enregistrer la présentation avec le nom de fichier et le format spécifiés.

## Code source complet pour l'enregistrement en tant que type de vue prédéfini dans les diapositives Java

```java
// Le chemin vers le répertoire des documents.
String dataDir = "Your Document Directory";
// Ouverture du fichier de présentation
Presentation presentation = new Presentation();
try
{
	// Définition du type de vue
	presentation.getViewProperties().setLastView(ViewType.SlideMasterView);
	// Sauvegarde de la présentation
	presentation.save(dataDir + "SetViewType_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusion

Dans ce tutoriel, nous avons appris à enregistrer une présentation avec un type d'affichage prédéfini en Java grâce à Aspose.Slides pour Java. En suivant le code et les étapes fournis, vous pouvez facilement définir le type d'affichage de vos présentations et les enregistrer au format souhaité.

## FAQ

### Comment puis-je modifier le type d'affichage en un autre type que « Affichage Masque des diapositives » ?

Pour modifier le type d'affichage en un autre type que « Affichage Masque des diapositives », remplacez simplement `ViewType.SlideMasterView` avec le type de vue souhaité, tel que `ViewType.NoumalView` or `ViewType.SlideSorterView`, dans le code où nous définissons le type de vue.

### Puis-je définir les propriétés d’affichage pour des diapositives individuelles dans la présentation ?

Oui, vous pouvez définir les propriétés d'affichage de chaque diapositive avec Aspose.Slides pour Java. Vous pouvez accéder aux propriétés de chaque diapositive et les manipuler séparément en parcourant les diapositives de la présentation.

### Dans quels autres formats puis-je enregistrer ma présentation ?

Aspose.Slides pour Java prend en charge divers formats de sortie, notamment PPTX, PDF, TIFF, HTML, etc. Vous pouvez spécifier le format souhaité lors de l'enregistrement de votre présentation en utilisant le fichier approprié. `SaveFormat` valeur d'énumération.

### Aspose.Slides pour Java est-il adapté au traitement par lots de présentations ?

Oui, Aspose.Slides pour Java est parfaitement adapté aux tâches de traitement par lots. Vous pouvez automatiser le traitement de plusieurs présentations, appliquer des modifications et les enregistrer en masse grâce au code Java.

### Où puis-je trouver plus d'informations et de documentation sur Aspose.Slides pour Java ?

Pour une documentation complète et des références relatives à Aspose.Slides pour Java, veuillez visiter le site Web de documentation : [Documentation Aspose.Slides pour Java](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}