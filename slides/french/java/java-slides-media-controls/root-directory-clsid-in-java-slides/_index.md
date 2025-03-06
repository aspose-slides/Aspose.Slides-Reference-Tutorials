---
title: Répertoire racine ClsId dans les diapositives Java
linktitle: Répertoire racine ClsId dans les diapositives Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment définir le répertoire racine ClsId dans les présentations Aspose.Slides pour Java. Personnalisez le comportement des liens hypertexte avec CLSID.
type: docs
weight: 10
url: /fr/java/media-controls/root-directory-clsid-in-java-slides/
---

## Introduction à la définition du répertoire racine ClsId dans Aspose.Slides pour Java

Dans Aspose.Slides pour Java, vous pouvez définir le Root Directory ClsId, qui est le CLSID (Class Identifier) utilisé pour spécifier l'application à utiliser comme répertoire racine lorsqu'un lien hypertexte dans votre présentation est activé. Dans ce guide, nous vous expliquerons comment procéder, étape par étape.

## Conditions préalables

Avant de commencer, assurez-vous de disposer des prérequis suivants :

- Kit de développement Java (JDK) installé sur votre système.
-  Bibliothèque Aspose.Slides pour Java ajoutée à votre projet. Vous pouvez le télécharger depuis[Aspose.Slides pour Java Documentation](https://reference.aspose.com/slides/java/).
- Un éditeur de code ou un environnement de développement intégré (IDE) configuré pour le développement Java.

## Étape 1 : Créer une nouvelle présentation

Tout d’abord, créons une nouvelle présentation à l’aide d’Aspose.Slides pour Java. Dans cet exemple, nous allons créer une présentation vide.

```java
// Nom du fichier de sortie
String resultPath = "your_output_path/pres.ppt"; // Remplacez "your_output_path" par le répertoire de sortie souhaité.
Presentation pres = new Presentation();
```

Dans le code ci-dessus, nous définissons le chemin du fichier de présentation de sortie et créons un nouveau`Presentation` objet.

## Étape 2 : définir le ClsId du répertoire racine

 Pour définir le Root Directory ClsId, vous devez créer une instance de`PptOptions` et définissez le CLSID souhaité. Le CLSID représente l'application qui sera utilisée comme répertoire racine lorsqu'un lien hypertexte est activé.

```java
PptOptions pptOptions = new PptOptions();
// Définissez CLSID sur « Microsoft Powerpoint.Show.8 »
pptOptions.setRootDirectoryClsid(UUID.fromString("64818D10-4F9B-11CF-86EA-00AA00B929E8"));
```

 Dans le code ci-dessus, nous créons un`PptOptions` objet et définissez le CLSID sur « Microsoft Powerpoint.Show.8 ». Vous pouvez le remplacer par le CLSID de l'application que vous souhaitez utiliser comme répertoire racine.

## Étape 3 : Enregistrez la présentation

Maintenant, enregistrons la présentation avec l'ensemble Root Directory ClsId.

```java
// Enregistrer la présentation
pres.save(resultPath, SaveFormat.Ppt, pptOptions);
```

 Dans cette étape, nous enregistrons la présentation dans le format spécifié`resultPath` avec le`PptOptions` nous avons créé plus tôt.

## Étape 4 : Nettoyage

 N'oubliez pas de jeter le`Presentation` s'opposer à la libération des ressources allouées.

```java
if (pres != null) {
    pres.dispose();
}
```

## Code source complet pour le répertoire racine ClsId dans les diapositives Java

```java
// Nom du fichier de sortie
String resultPath = "Your Output Directory" + "pres.ppt";
Presentation pres = new Presentation();
try {
	PptOptions pptOptions = new PptOptions();
	//définir CLSID sur « Microsoft Powerpoint.Show.8 »
	pptOptions.setRootDirectoryClsid(UUID.fromString("64818D10-4F9B-11CF-86EA-00AA00B929E8"));
	// Enregistrer la présentation
	pres.save(resultPath, SaveFormat.Ppt, pptOptions);
} finally {
	if (pres != null) pres.dispose();
}
```

## Conclusion

Vous avez correctement défini le répertoire racine ClsId dans Aspose.Slides pour Java. Cela vous permet de spécifier l'application qui sera utilisée comme répertoire racine lorsque les hyperliens seront activés dans votre présentation. Vous pouvez personnaliser le CLSID en fonction de vos besoins spécifiques.

## FAQ

### Comment trouver le CLSID pour une application spécifique ?

Pour trouver le CLSID d'une application spécifique, vous pouvez vous référer à la documentation ou aux ressources fournies par le développeur de l'application. Les CLSID sont des identifiants uniques attribués aux objets COM et sont généralement spécifiques à chaque application.

### Puis-je définir un CLSID personnalisé pour le répertoire racine ?

 Oui, vous pouvez définir un CLSID personnalisé pour le répertoire racine en spécifiant la valeur CLSID souhaitée à l'aide de l'option`setRootDirectoryClsid` méthode, comme indiqué dans l’exemple de code. Cela vous permet d'utiliser une application spécifique comme répertoire racine lorsque les hyperliens sont activés dans votre présentation.

### Que se passe-t-il si je ne définis pas le ClsId du répertoire racine ?

Si vous ne définissez pas le Root Directory ClsId, le comportement par défaut dépendra de la visionneuse ou de l’application utilisée pour ouvrir la présentation. Il peut utiliser sa propre application par défaut comme répertoire racine lorsque les hyperliens sont activés.

### Puis-je modifier le ClsId du répertoire racine pour des liens hypertextes individuels ?

Non, le Root Directory ClsId est généralement défini au niveau de la présentation et s'applique à tous les hyperliens au sein de la présentation. Si vous devez spécifier différentes applications pour des hyperliens individuels, vous devrez peut-être gérer ces hyperliens séparément dans votre code.

### Existe-t-il des limitations concernant les CLSID que je peux utiliser ?

Les CLSID que vous pouvez utiliser sont généralement déterminés par les applications installées sur le système. Vous devez utiliser des CLSID qui correspondent à des applications valides capables de gérer les hyperliens. Sachez que l’utilisation d’un CLSID non valide peut entraîner un comportement inattendu.