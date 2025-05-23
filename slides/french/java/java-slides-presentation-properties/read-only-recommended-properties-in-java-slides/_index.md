---
"description": "Découvrez comment activer les propriétés recommandées en lecture seule dans les présentations PowerPoint Java avec Aspose.Slides pour Java. Suivez notre guide étape par étape avec des exemples de code source pour une sécurité renforcée de vos présentations."
"linktitle": "Propriétés recommandées en lecture seule dans les diapositives Java"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Propriétés recommandées en lecture seule dans les diapositives Java"
"url": "/fr/java/presentation-properties/read-only-recommended-properties-in-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Propriétés recommandées en lecture seule dans les diapositives Java


## Introduction à l'activation des propriétés recommandées en lecture seule dans les diapositives Java

Dans ce tutoriel, nous allons découvrir comment activer les propriétés recommandées en lecture seule pour les présentations PowerPoint avec Aspose.Slides pour Java. Ces propriétés peuvent être utiles pour encourager les utilisateurs à consulter une présentation sans y apporter de modifications. Ces propriétés suggèrent que la présentation doit être ouverte en lecture seule. Nous vous fournirons un guide étape par étape ainsi que le code source Java pour y parvenir.

## Prérequis

Avant de commencer, assurez-vous que la bibliothèque Aspose.Slides pour Java est configurée dans votre projet. Vous pouvez la télécharger depuis le [Site Web Aspose.Slides pour Java](https://products.aspose.com/slides/java/).

## Étape 1 : Créer une nouvelle présentation PowerPoint

Nous commencerons par créer une présentation PowerPoint avec Aspose.Slides pour Java. Si vous avez déjà une présentation, vous pouvez ignorer cette étape.

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

Dans cet extrait de code, nous utilisons le `getProtectionManager().setReadOnlyRecommended(true)` méthode pour définir la propriété Lecture seule recommandée sur `true`Cela garantit que lorsque quelqu'un ouvre la présentation, il sera invité à l'ouvrir en mode lecture seule.

## Étape 3 : Enregistrer la présentation

Enfin, nous enregistrons la présentation avec la propriété Lecture seule recommandée activée.

## Code source complet des propriétés recommandées en lecture seule dans les diapositives Java

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

Dans ce tutoriel, vous avez appris à activer la propriété Lecture seule recommandée pour une présentation PowerPoint avec Aspose.Slides pour Java. Cette fonctionnalité peut être utile pour restreindre les modifications et encourager les utilisateurs à utiliser la présentation en lecture seule. Vous pouvez renforcer la sécurité en définissant un mot de passe pour la présentation.

## FAQ

### Comment désactiver la propriété Lecture seule recommandée ?

Pour désactiver la propriété Lecture seule recommandée, utilisez simplement le code suivant :

```java
pres.getProtectionManager().setReadOnlyRecommended(false);
```

### Puis-je définir un mot de passe pour une présentation recommandée en lecture seule ?

Oui, vous pouvez définir un mot de passe pour une présentation recommandée en lecture seule avec Aspose.Slides pour Java. Vous pouvez utiliser l'option `setPassword` Méthode permettant de définir un mot de passe pour la présentation. Si un mot de passe est défini, les utilisateurs devront le saisir pour ouvrir la présentation, même en lecture seule.

```java
pres.getProtectionManager().setPassword("YourPassword");
```

N'oubliez pas de remplacer `"YourPassword"` avec le mot de passe souhaité.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}