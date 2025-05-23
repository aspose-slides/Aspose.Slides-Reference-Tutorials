---
"description": "Apprenez à relier des formes dans PowerPoint avec Aspose.Slides pour Java. Automatisez vos présentations sans effort."
"linktitle": "Connecter des formes à l'aide de sites de connexion dans PowerPoint"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Connecter des formes à l'aide de sites de connexion dans PowerPoint"
"url": "/fr/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connection-sites-powerpoint/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Connecter des formes à l'aide de sites de connexion dans PowerPoint

## Introduction
Dans ce tutoriel, nous découvrirons comment connecter des formes à l'aide de sites de connexion dans PowerPoint avec Aspose.Slides pour Java. Cette puissante bibliothèque permet de manipuler des présentations PowerPoint par programmation, rendant ainsi des tâches comme la connexion de formes fluides et efficaces.
## Prérequis
Avant de commencer, assurez-vous d’avoir les éléments suivants :
1. Kit de développement Java (JDK) : Assurez-vous que Java est installé sur votre système. Vous pouvez le télécharger et l'installer depuis le [site web](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
2. Aspose.Slides pour Java : Téléchargez et installez Aspose.Slides pour Java à partir du [page de téléchargement](https://releases.aspose.com/slides/java/).
3. Environnement de développement intégré (IDE) : choisissez un IDE pour le développement Java, tel qu'IntelliJ IDEA, Eclipse ou NetBeans.

## Importer des packages
Pour commencer, importez les packages nécessaires dans votre projet Java :
```java
import com.aspose.slides.*;

```
## Étape 1 : Accéder à la collection de formes
Accéder à la collection de formes pour la diapositive sélectionnée :
```java
// Le chemin vers le répertoire des documents.                    
String dataDir = "Your Document Directory";
// Instancier la classe de présentation qui représente le fichier PPTX
Presentation presentation = new Presentation();
IShapeCollection shapes = presentation.getSlides().get_Item(0).getShapes();
```
## Étape 2 : Ajout d'une forme de connecteur
Ajoutez une forme de connecteur à la collection de formes de diapositives :
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector3, 0, 0, 10, 10);
```
## Étape 3 : Ajout de formes automatiques
Ajoutez des formes automatiques comme une ellipse et un rectangle :
```java
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 200, 100, 100);
```
## Étape 4 : Joindre des formes à des connecteurs
Joignez les formes au connecteur :
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## Étape 5 : Définition de l'index du site de connexion
Définissez l’index du site de connexion souhaité pour les formes :
```java
long wantedIndex = 6;
if (ellipse.getConnectionSiteCount() > (wantedIndex & 0xFFFFFFFFL))
{
    connector.setStartShapeConnectionSiteIndex(wantedIndex);
}
```

## Conclusion
Dans ce tutoriel, nous avons appris à connecter des formes à l'aide de sites de connexion dans PowerPoint avec Aspose.Slides pour Java. Grâce à ces connaissances, vous pouvez désormais automatiser et personnaliser facilement vos présentations PowerPoint.
## FAQ
### Aspose.Slides pour Java peut-il être utilisé pour d’autres tâches de manipulation PowerPoint ?
Oui, Aspose.Slides pour Java fournit une large gamme de fonctionnalités pour créer, éditer et convertir des présentations PowerPoint.
### Aspose.Slides pour Java est-il gratuit à utiliser ?
Aspose.Slides pour Java est une bibliothèque commerciale, mais vous pouvez explorer ses fonctionnalités grâce à un essai gratuit. Visitez [ici](https://releases.aspose.com/) pour commencer.
### Puis-je obtenir de l'aide si je rencontre des problèmes lors de l'utilisation d'Aspose.Slides pour Java ?
Oui, vous pouvez obtenir de l'aide sur les forums de la communauté Aspose. [ici](https://forum.aspose.com/c/slides/11).
### Des licences temporaires sont-elles disponibles pour Aspose.Slides pour Java ?
Oui, des licences temporaires sont disponibles à des fins de test et d'évaluation. Vous pouvez en obtenir une. [ici](https://purchase.aspose.com/temporary-license/).
### Où puis-je acheter une licence pour Aspose.Slides pour Java ?
Vous pouvez acheter une licence sur le site Web d'Aspose [ici](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}