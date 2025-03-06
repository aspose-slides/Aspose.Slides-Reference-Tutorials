---
title: Propriétés recommandées en lecture seule dans les diapositives Java
linktitle: Propriétés recommandées en lecture seule dans les diapositives Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment activer les propriétés recommandées en lecture seule dans les présentations Java PowerPoint à l'aide d'Aspose.Slides pour Java. Suivez notre guide étape par étape avec des exemples de code source pour une sécurité améliorée des présentations.
weight: 17
url: /fr/java/presentation-properties/read-only-recommended-properties-in-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Introduction à l'activation des propriétés recommandées en lecture seule dans les diapositives Java

Dans ce didacticiel, nous allons explorer comment activer les propriétés recommandées en lecture seule pour les présentations PowerPoint à l'aide d'Aspose.Slides pour Java. Les propriétés recommandées en lecture seule peuvent être utiles lorsque vous souhaitez encourager les utilisateurs à afficher une présentation sans apporter de modifications. Ces propriétés suggèrent que la présentation doit être ouverte en mode lecture seule. Nous vous fournirons un guide étape par étape ainsi que le code source Java pour y parvenir.

## Conditions préalables

 Avant de commencer, assurez-vous que la bibliothèque Aspose.Slides pour Java est configurée dans votre projet. Vous pouvez le télécharger depuis le[Site Web Aspose.Slides pour Java](https://products.aspose.com/slides/java/).

## Étape 1 : Créer une nouvelle présentation PowerPoint

Nous allons commencer par créer une nouvelle présentation PowerPoint à l'aide d'Aspose.Slides pour Java. Si vous avez déjà une présentation, vous pouvez ignorer cette étape.

```java
String outPptxPath = "Your Output Directory" + "ReadOnlyRecommended.pptx";
Presentation pres = new Presentation();
```

Dans le code ci-dessus, nous avons défini le chemin du fichier PowerPoint de sortie et créé un nouvel objet de présentation.

## Étape 2 : Activer la propriété recommandée en lecture seule

Maintenant, activons la propriété Lecture seule recommandée pour la présentation.

```java
try
{
    pres.getProtectionManager().setReadOnlyRecommended(true);
    pres.save(outPptxPath, SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

 Dans cet extrait de code, nous utilisons le`getProtectionManager().setReadOnlyRecommended(true)` méthode pour définir la propriété Lecture seule recommandée sur`true`. Cela garantit que lorsque quelqu'un ouvre la présentation, il sera invité à l'ouvrir en mode lecture seule.

## Étape 3 : Enregistrez la présentation

Enfin, nous enregistrons la présentation avec la propriété Lecture seule recommandée activée.

## Code source complet pour les propriétés recommandées en lecture seule dans les diapositives Java

```java
String outPptxPath = "Your Output Directory" + "ReadOnlyRecommended.pptx";
Presentation pres = new Presentation();
try
{
	pres.getProtectionManager().setReadOnlyRecommended(true);
	pres.save(outPptxPath, SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusion

Dans ce didacticiel, vous avez appris comment activer la propriété Lecture seule recommandée pour une présentation PowerPoint à l'aide d'Aspose.Slides pour Java. Cette fonctionnalité peut être utile lorsque vous souhaitez restreindre les modifications et encourager les spectateurs à utiliser la présentation en mode lecture seule. Vous pouvez renforcer encore la sécurité en définissant un mot de passe pour la présentation.

## FAQ

### Comment puis-je désactiver la propriété Lecture seule recommandée ?

Pour désactiver la propriété Lecture seule recommandée, utilisez simplement le code suivant :

```java
pres.getProtectionManager().setReadOnlyRecommended(false);
```

### Puis-je définir un mot de passe pour une présentation recommandée en lecture seule ?

Oui, vous pouvez définir un mot de passe pour une présentation recommandée en lecture seule à l'aide d'Aspose.Slides pour Java. Vous pouvez utiliser le`setPassword` méthode pour définir un mot de passe pour la présentation. Si un mot de passe est défini, les utilisateurs devront le saisir pour ouvrir la présentation, même en mode lecture seule.

```java
pres.getProtectionManager().setPassword("YourPassword");
```

 N'oubliez pas de remplacer`"YourPassword"` avec le mot de passe souhaité.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
