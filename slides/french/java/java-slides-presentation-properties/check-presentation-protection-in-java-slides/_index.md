---
title: Vérifier la protection des présentations dans les diapositives Java
linktitle: Vérifier la protection des présentations dans les diapositives Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment vérifier la protection des présentations dans les diapositives Java à l'aide d'Aspose.Slides for Java. Ce guide étape par étape fournit des exemples de code pour les contrôles de protection en écriture et en ouverture.
type: docs
weight: 15
url: /fr/java/presentation-properties/check-presentation-protection-in-java-slides/
---

## Introduction à la vérification de la protection des présentations dans les diapositives Java

Dans ce didacticiel, nous explorerons comment vérifier la protection des présentations à l'aide d'Aspose.Slides pour Java. Nous aborderons deux scénarios : vérifier la protection en écriture et vérifier la protection ouverte pour une présentation. Nous fournirons des exemples de code étape par étape pour chaque scénario.

## Conditions préalables

Avant de commencer, assurez-vous que la bibliothèque Aspose.Slides pour Java est configurée dans votre projet Java. Vous pouvez le télécharger depuis le site Aspose et l'ajouter aux dépendances de votre projet.

### Dépendance Maven

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>your_version_here</version>
</dependency>
```

 Remplacer`your_version_here` avec la version d'Aspose.Slides pour Java que vous utilisez.

## Étape 1 : Vérifiez la protection en écriture

 Pour vérifier si une présentation est protégée en écriture par un mot de passe, vous pouvez utiliser le`IPresentationInfo` interface. Voici le code pour faire cela :

```java
// Chemin d'accès à la présentation source
String pptxFile = "path_to_presentation.pptx";

// Vérifiez le mot de passe de protection en écriture via l'interface IPresentationInfo
IPresentationInfo presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptxFile);
boolean isWriteProtectedByPassword = presentationInfo.isWriteProtected() == NullableBool.True
        && presentationInfo.checkWriteProtection("password_here");

System.out.println("Is presentation write protected by password = " + isWriteProtectedByPassword);
```

 Remplacer`"path_to_presentation.pptx"` avec le chemin réel vers votre fichier de présentation et`"password_here"` avec le mot de passe de protection en écriture.

## Étape 2 : Vérifiez la protection ouverte

 Pour vérifier si une présentation est protégée par un mot de passe à l'ouverture, vous pouvez utiliser le`IPresentationInfo` interface. Voici le code pour faire cela :

```java
// Chemin d'accès à la présentation source
String pptFile = "path_to_presentation.ppt";

// Vérifier la protection contre l'ouverture de la présentation via l'interface IPresentationInfo
presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptFile);
if (presentationInfo.isPasswordProtected()) {
    System.out.println("The presentation is protected by password to open.");
}
```

 Remplacer`"path_to_presentation.ppt"` avec le chemin réel vers votre fichier de présentation.

## Code source complet pour la protection des présentations de chèques dans les diapositives Java

```java
//Chemin pour la présentation des sources
String pptxFile = "Your Document Directory";
String pptFile = "Your Document Directory";
// Vérifiez le mot de passe de protection en écriture via l'interface IPresentationInfo
IPresentationInfo presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptxFile);
boolean isWriteProtectedByPassword = presentationInfo.isWriteProtected() == NullableBool.True && presentationInfo.checkWriteProtection("pass2");
System.out.println("Is presentation write protected by password = " + isWriteProtectedByPassword);
// Vérifiez le mot de passe de protection en écriture via l'interface IProtectionManager
Presentation presentation = new Presentation();
try
{
	boolean isWriteProtected = presentation.getProtectionManager().checkWriteProtection("pass2");
	System.out.println("Is presentation write protected = " + isWriteProtected);
}
finally
{
	if (presentation != null) presentation.dispose();
}
// Vérifier la protection contre l'ouverture de la présentation via l'interface IPresentationInfo
presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptFile);
if (presentationInfo.isPasswordProtected())
{
	System.out.println("The presentation '" + pptxFile + "' is protected by password to open.");
}
```

## Conclusion

Dans ce didacticiel, nous avons appris à vérifier la protection des présentations dans les diapositives Java à l'aide d'Aspose.Slides for Java. Nous avons couvert deux scénarios : vérifier la protection en écriture et vérifier la protection ouverte. Vous pouvez désormais intégrer ces vérifications dans vos applications Java pour gérer efficacement les présentations protégées.

## FAQ

### Comment puis-je obtenir Aspose.Slides pour Java ?

Vous pouvez télécharger Aspose.Slides pour Java à partir du site Web Aspose ou l'ajouter en tant que dépendance Maven dans votre projet, comme indiqué dans la section des prérequis.

### Puis-je vérifier à la fois la protection en écriture et la protection en ouverture pour une présentation ?

Oui, vous pouvez vérifier à la fois la protection en écriture et la protection ouverte pour une présentation à l'aide des exemples de code fournis.

### Que dois-je faire si j'oublie le mot de passe de protection ?

Si vous oubliez le mot de passe de protection d'une présentation, il n'existe aucun moyen intégré de le récupérer. Assurez-vous de conserver une trace de vos mots de passe pour éviter de telles situations.

### Aspose.Slides pour Java est-il compatible avec les derniers formats de fichiers PowerPoint ?

Oui, Aspose.Slides pour Java prend en charge les derniers formats de fichiers PowerPoint, y compris les fichiers .pptx.