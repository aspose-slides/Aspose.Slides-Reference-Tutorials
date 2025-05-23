---
"description": "Découvrez comment définir le CLSID du répertoire racine dans Aspose.Slides pour les présentations Java. Personnalisez le comportement des hyperliens avec le CLSID."
"linktitle": "Diapositives sur le ClsId du répertoire racine en Java"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Diapositives sur le ClsId du répertoire racine en Java"
"url": "/fr/java/media-controls/root-directory-clsid-in-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Diapositives sur le ClsId du répertoire racine en Java


## Introduction à la définition du ClsId du répertoire racine dans Aspose.Slides pour Java

Dans Aspose.Slides pour Java, vous pouvez définir le ClsId du répertoire racine, qui est le CLSID (identifiant de classe) utilisé pour spécifier l'application à utiliser comme répertoire racine lorsqu'un lien hypertexte de votre présentation est activé. Ce guide vous explique comment procéder étape par étape.

## Prérequis

Avant de commencer, assurez-vous de disposer des prérequis suivants :

- Java Development Kit (JDK) installé sur votre système.
- Bibliothèque Aspose.Slides pour Java ajoutée à votre projet. Vous pouvez la télécharger ici. [Documentation Aspose.Slides pour Java](https://reference.aspose.com/slides/java/).
- Un éditeur de code ou un environnement de développement intégré (IDE) configuré pour le développement Java.

## Étape 1 : Créer une nouvelle présentation

Commençons par créer une présentation avec Aspose.Slides pour Java. Dans cet exemple, nous allons créer une présentation vide.

```java
// Nom du fichier de sortie
String resultPath = "your_output_path/pres.ppt"; // Remplacez « your_output_path » par le répertoire de sortie souhaité.
Presentation pres = new Presentation();
```

Dans le code ci-dessus, nous définissons le chemin du fichier de présentation de sortie et créons un nouveau `Presentation` objet.

## Étape 2 : définir le ClsId du répertoire racine

Pour définir le ClsId du répertoire racine, vous devez créer une instance de `PptOptions` et définissez le CLSID souhaité. Le CLSID représente l'application qui sera utilisée comme répertoire racine lors de l'activation d'un lien hypertexte.

```java
PptOptions pptOptions = new PptOptions();
// Définir CLSID sur « Microsoft Powerpoint.Show.8 »
pptOptions.setRootDirectoryClsid(UUID.fromString("64818D10-4F9B-11CF-86EA-00AA00B929E8"));
```

Dans le code ci-dessus, nous créons un `PptOptions` objet et définissez le CLSID sur « Microsoft Powerpoint.Show.8 ». Vous pouvez le remplacer par le CLSID de l'application que vous souhaitez utiliser comme répertoire racine.

## Étape 3 : Enregistrer la présentation

Maintenant, enregistrons la présentation avec le ClsId du répertoire racine défini.

```java
// Enregistrer la présentation
pres.save(resultPath, SaveFormat.Ppt, pptOptions);
```

Dans cette étape, nous enregistrons la présentation dans le dossier spécifié. `resultPath` avec le `PptOptions` nous avons créé plus tôt.

## Étape 4 : Nettoyage

N'oubliez pas de jeter le `Presentation` s'opposer à la libération des ressources allouées.

```java
if (pres != null) {
    pres.dispose();
}
```

## Code source complet pour le répertoire racine ClsId en Java (diapositives)

```java
// Nom du fichier de sortie
String resultPath = "Your Output Directory" + "pres.ppt";
Presentation pres = new Presentation();
try {
	PptOptions pptOptions = new PptOptions();
	// définir CLSID sur « Microsoft Powerpoint.Show.8 »
	pptOptions.setRootDirectoryClsid(UUID.fromString("64818D10-4F9B-11CF-86EA-00AA00B929E8"));
	// Enregistrer la présentation
	pres.save(resultPath, SaveFormat.Ppt, pptOptions);
} finally {
	if (pres != null) pres.dispose();
}
```

## Conclusion

Vous avez correctement défini le CLSID du répertoire racine dans Aspose.Slides pour Java. Cela vous permet de spécifier l'application qui sera utilisée comme répertoire racine lors de l'activation des hyperliens dans votre présentation. Vous pouvez personnaliser le CLSID selon vos besoins.

## FAQ

### Comment trouver le CLSID d’une application spécifique ?

Pour trouver le CLSID d'une application spécifique, vous pouvez consulter la documentation ou les ressources fournies par le développeur de l'application. Les CLSID sont des identifiants uniques attribués aux objets COM et sont généralement spécifiques à chaque application.

### Puis-je définir un CLSID personnalisé pour le répertoire racine ?

Oui, vous pouvez définir un CLSID personnalisé pour le répertoire racine en spécifiant la valeur CLSID souhaitée à l'aide du `setRootDirectoryClsid` méthode, comme illustré dans l'exemple de code. Cela vous permet d'utiliser une application spécifique comme répertoire racine lorsque des hyperliens sont activés dans votre présentation.

### Que se passe-t-il si je ne définis pas le ClsId du répertoire racine ?

Si vous ne définissez pas le ClsId du répertoire racine, le comportement par défaut dépendra de la visionneuse ou de l'application utilisée pour ouvrir la présentation. L'application par défaut peut être utilisée comme répertoire racine lors de l'activation des hyperliens.

### Puis-je modifier le ClsId du répertoire racine pour des hyperliens individuels ?

Non, le ClsId du répertoire racine est généralement défini au niveau de la présentation et s'applique à tous les hyperliens de celle-ci. Si vous devez spécifier des applications différentes pour des hyperliens individuels, vous devrez peut-être les gérer séparément dans votre code.

### Existe-t-il des limitations concernant les CLSID que je peux utiliser ?

Les CLSID utilisables sont généralement déterminés par les applications installées sur le système. Il est recommandé d'utiliser des CLSID correspondant à des applications valides capables de gérer les hyperliens. Attention : l'utilisation d'un CLSID non valide peut entraîner des comportements inattendus.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}