---
"description": "Apprenez à appliquer des effets de rotation 3D sur des formes dans PowerPoint à l'aide d'Aspose.Slides pour Java avec ce didacticiel complet, étape par étape."
"linktitle": "Appliquer l'effet de rotation 3D aux formes dans PowerPoint"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Appliquer l'effet de rotation 3D aux formes dans PowerPoint"
"url": "/fr/java/java-powerpoint-animation-shape-manipulation/apply-3d-rotation-effect-shapes-powerpoint/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Appliquer l'effet de rotation 3D aux formes dans PowerPoint

## Introduction
Prêt à donner une nouvelle dimension à vos présentations PowerPoint ? Ajouter des effets de rotation 3D peut rendre vos diapositives plus dynamiques et attrayantes. Que vous soyez un développeur expérimenté ou débutant, ce tutoriel vous montrera étape par étape comment appliquer des effets de rotation 3D à des formes dans PowerPoint avec Aspose.Slides pour Java. C'est parti !
## Prérequis
Avant de commencer, assurez-vous d’avoir les éléments suivants en place :
1. Kit de développement Java (JDK) : Assurez-vous que le JDK est installé sur votre système. Vous pouvez le télécharger depuis le [Site Web d'Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).
2. Aspose.Slides pour Java : Téléchargez la dernière version d'Aspose.Slides pour Java depuis le [lien de téléchargement](https://releases.aspose.com/slides/java/).
3. Environnement de développement intégré (IDE) : utilisez un IDE comme IntelliJ IDEA ou Eclipse pour le codage.
4. Un permis valide : Si vous n'avez pas de permis, vous pouvez en obtenir un [permis temporaire](https://purchase.aspose.com/temporary-license/) pour tester les fonctionnalités.
## Importer des packages
Commençons par importer les packages nécessaires dans votre projet Java. Ces importations vous aideront à gérer les présentations et les formes avec Aspose.Slides.
```java
import com.aspose.slides.*;

```
## Étape 1 : Configurez votre projet
Avant de vous plonger dans le code, configurez l'environnement de votre projet. Assurez-vous d'avoir ajouté Aspose.Slides pour Java aux dépendances de votre projet.
Ajoutez Aspose.Slides à votre projet :
1. Téléchargez les fichiers JAR Aspose.Slides depuis le [page de téléchargement](https://releases.aspose.com/slides/java/).
2. Ajoutez ces fichiers JAR au chemin de construction de votre projet.
## Étape 2 : Créer une nouvelle présentation PowerPoint
Dans cette étape, nous allons créer une nouvelle présentation PowerPoint.
```java
// Le chemin vers le répertoire des documents.
String dataDir = "Your Document Directory";
// Créer une instance de la classe Presentation
Presentation pres = new Presentation();
```
Cet extrait de code initialise un nouvel objet de présentation dans lequel nous ajouterons nos formes.
## Étape 3 : ajouter une forme rectangulaire
Ensuite, ajoutons une forme rectangulaire à la première diapositive.
```java
IShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 30, 30, 200, 200);
```
Ce code ajoute une forme rectangulaire à la position et à la taille spécifiées sur la première diapositive.
## Étape 4 : Appliquer la rotation 3D au rectangle
Appliquons maintenant un effet de rotation 3D à la forme rectangulaire.
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(40, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
Ici, nous définissons la profondeur, les angles de rotation de la caméra, le type de caméra et le type d'éclairage pour donner à notre rectangle un aspect 3D.
## Étape 5 : Ajouter une forme de ligne
Ajoutons une autre forme, cette fois une ligne, à la diapositive.
```java
autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Line, 30, 300, 200, 200);
```
Ce code place une forme de ligne sur la diapositive.
## Étape 6 : Appliquer une rotation 3D à la ligne
Enfin, nous appliquerons un effet de rotation 3D à la forme de la ligne.
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(0, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
Semblable au rectangle, nous définissons les propriétés 3D de la forme de la ligne.
## Étape 7 : Enregistrer la présentation
Après avoir ajouté et configuré vos formes, enregistrez la présentation.
```java
pres.save(dataDir + "Rotation_out.pptx", SaveFormat.Pptx);
```
Ce code enregistre votre présentation avec le nom de fichier spécifié dans le format souhaité.
## Conclusion
Félicitations ! Vous avez appliqué avec succès des effets de rotation 3D aux formes d'une présentation PowerPoint avec Aspose.Slides pour Java. En suivant ces étapes, vous pouvez créer des présentations visuellement attrayantes et dynamiques. Pour plus de personnalisation et de fonctionnalités avancées, consultez le [Documentation Aspose.Slides](https://reference.aspose.com/slides/java/).
## FAQ
### Qu'est-ce qu'Aspose.Slides pour Java ?
Aspose.Slides pour Java est une API puissante permettant de créer, modifier et manipuler des présentations PowerPoint par programmation.
### Puis-je essayer Aspose.Slides pour Java gratuitement ?
Oui, vous pouvez obtenir un [essai gratuit](https://releases.aspose.com/) ou un [permis temporaire](https://purchase.aspose.com/temporary-license/) pour tester les fonctionnalités.
### À quels types de formes puis-je ajouter des effets 3D dans Aspose.Slides ?
Vous pouvez ajouter des effets 3D à diverses formes telles que des rectangles, des lignes, des ellipses et des formes personnalisées.
### Comment obtenir de l'assistance pour Aspose.Slides pour Java ?
Vous pouvez visiter le [forum d'assistance](https://forum.aspose.com/c/slides/11) pour obtenir de l'aide et discuter de tout problème.
### Puis-je utiliser Aspose.Slides pour Java dans des projets commerciaux ?
Oui, mais vous devez acheter une licence. Vous pouvez en acheter une sur le site [page d'achat](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}