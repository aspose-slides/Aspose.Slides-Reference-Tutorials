---
title: Mettre à jour les propriétés de la présentation en utilisant une autre présentation comme modèle dans les diapositives Java
linktitle: Mettre à jour les propriétés de la présentation en utilisant une autre présentation comme modèle dans les diapositives Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Améliorez les présentations PowerPoint avec des métadonnées mises à jour à l'aide d'Aspose.Slides pour Java. Apprenez à mettre à jour des propriétés telles que l'auteur, le titre et les mots-clés à l'aide de modèles dans Java Slides.
weight: 14
url: /fr/java/media-controls/update-presentation-properties-using-another-presentation-as-a-template-in-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Introduction à la mise à jour des propriétés de présentation en utilisant une autre présentation comme modèle dans les diapositives Java

Dans ce didacticiel, nous vous guiderons tout au long du processus de mise à jour des propriétés de présentation (métadonnées) pour les présentations PowerPoint à l'aide d'Aspose.Slides pour Java. Vous pouvez utiliser une autre présentation comme modèle pour mettre à jour des propriétés telles que l'auteur, le titre, les mots-clés, etc. Nous vous fournirons des instructions étape par étape et des exemples de code source.

## Conditions préalables

 Avant de commencer, assurez-vous que la bibliothèque Aspose.Slides pour Java est intégrée à votre projet Java. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/slides/java/).

## Étape 1 : Configurez votre projet

Assurez-vous d'avoir créé un projet Java et ajouté la bibliothèque Aspose.Slides for Java aux dépendances de votre projet.

## Étape 2 : Importer les packages requis

Vous devrez importer les packages Aspose.Slides nécessaires pour travailler avec les propriétés de présentation. Incluez les instructions d'importation suivantes au début de votre classe Java :

```java
import com.aspose.slides.DocumentProperties;
import com.aspose.slides.IDocumentProperties;
import com.aspose.slides.IPresentationInfo;
import com.aspose.slides.PresentationFactory;
```

## Étape 3 : mettre à jour les propriétés de la présentation

Maintenant, mettons à jour les propriétés de la présentation en utilisant une autre présentation comme modèle. Dans cet exemple, nous mettrons à jour les propriétés de plusieurs présentations, mais vous pouvez adapter ce code à votre cas d'utilisation spécifique.

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";

// Chargez le modèle de présentation à partir duquel vous souhaitez copier les propriétés
DocumentProperties template;
IPresentationInfo info = PresentationFactory.getInstance().getPresentationInfo(dataDir + "template.pptx");
template = (DocumentProperties) info.readDocumentProperties();

// Définissez les propriétés que vous souhaitez mettre à jour
template.setAuthor("Template Author");
template.setTitle("Template Title");
template.setCategory("Template Category");
template.setKeywords("Keyword1, Keyword2, Keyword3");
template.setCompany("Our Company");
template.setComments("Created from template");
template.setContentType("Template Content");
template.setSubject("Template Subject");

// Mettre à jour plusieurs présentations en utilisant le même modèle
updateByTemplate(dataDir + "doc1.pptx", template);
updateByTemplate(dataDir + "doc2.odp", template);
updateByTemplate(dataDir + "doc3.ppt", template);
```

##  Étape 4 : Définir le`updateByTemplate` Method

Définissons une méthode pour mettre à jour les propriétés des présentations individuelles à l'aide du modèle. Cette méthode prendra le chemin de la présentation à mettre à jour et les propriétés du modèle comme paramètres.

```java
private static void updateByTemplate(String path, IDocumentProperties template)
{
    // Charger la présentation à mettre à jour
    IPresentationInfo toUpdate = PresentationFactory.getInstance().getPresentationInfo(path);
    
    // Mettre à jour les propriétés du document à l'aide du modèle
    toUpdate.updateDocumentProperties(template);
    
    // Enregistrez la présentation mise à jour
    toUpdate.writeBindedPresentation(path);
}
```

## Code source complet pour mettre à jour les propriétés de la présentation en utilisant une autre présentation comme modèle dans les diapositives Java

```java
	// Le chemin d'accès au répertoire des documents.
	String dataDir = "Your Document Directory";
	DocumentProperties template;
	IPresentationInfo info = PresentationFactory.getInstance().getPresentationInfo(dataDir + "template.pptx");
	template = (DocumentProperties) info.readDocumentProperties();
	template.setAuthor("Template Author");
	template.setTitle("Template Title");
	template.setCategory("Template Category");
	template.setKeywords("Keyword1, Keyword2, Keyword3");
	template.setCompany("Our Company");
	template.setComments("Created from template");
	template.setContentType("Template Content");
	template.setSubject("Template Subject");
	updateByTemplate(dataDir + "doc1.pptx", template);
	updateByTemplate(dataDir + "doc2.odp", template);
	updateByTemplate(dataDir + "doc3.ppt", template);
}
private static void updateByTemplate(String path, IDocumentProperties template)
{
	IPresentationInfo toUpdate = PresentationFactory.getInstance().getPresentationInfo(path);
	toUpdate.updateDocumentProperties(template);
	toUpdate.writeBindedPresentation(path);
```

## Conclusion

Dans ce didacticiel complet, nous avons exploré comment mettre à jour les propriétés de présentation dans les présentations PowerPoint à l'aide d'Aspose.Slides pour Java. Nous nous sommes spécifiquement concentrés sur l'utilisation d'une autre présentation comme modèle pour mettre à jour efficacement les métadonnées telles que les noms d'auteurs, les titres, les mots-clés, etc.

## FAQ

### Comment puis-je mettre à jour les propriétés pour plus de présentations ?

 Vous pouvez mettre à jour les propriétés de plusieurs présentations en appelant le`updateByTemplate` méthode pour chaque présentation avec le chemin souhaité.

### Puis-je personnaliser ce code pour différentes propriétés ?

Oui, vous pouvez personnaliser le code pour mettre à jour des propriétés spécifiques en fonction de vos besoins. Modifiez simplement le`template` objet avec les valeurs de propriété souhaitées.

### Existe-t-il des limites quant au type de présentations pouvant être mises à jour ?

Non, vous pouvez mettre à jour les propriétés des présentations dans différents formats, notamment PPTX, ODP et PPT.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
