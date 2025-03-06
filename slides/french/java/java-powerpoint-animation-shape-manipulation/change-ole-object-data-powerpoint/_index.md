---
title: Modifier les données d'objet OLE dans PowerPoint
linktitle: Modifier les données d'objet OLE dans PowerPoint
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment modifier les données d'un objet OLE dans PowerPoint à l'aide d'Aspose.Slides pour Java. Un guide étape par étape pour des mises à jour efficaces et faciles.
type: docs
weight: 14
url: /fr/java/java-powerpoint-animation-shape-manipulation/change-ole-object-data-powerpoint/
---
## Introduction
La modification des données d'objet OLE dans les présentations PowerPoint peut être une tâche cruciale lorsque vous devez mettre à jour le contenu incorporé sans modifier manuellement chaque diapositive. Ce guide complet vous guidera tout au long du processus d'utilisation d'Aspose.Slides pour Java, une puissante bibliothèque conçue pour gérer les présentations PowerPoint. Que vous soyez un développeur chevronné ou débutant, vous trouverez ce didacticiel utile et facile à suivre.
## Conditions préalables
Avant de plonger dans le code, assurons-nous que vous disposez de tout ce dont vous avez besoin pour commencer.
1.  Kit de développement Java (JDK) : assurez-vous que JDK est installé sur votre système. Vous pouvez le télécharger depuis[Le site d'Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides pour Java : téléchargez la dernière version à partir du[Page de téléchargement d'Aspose.Slides](https://releases.aspose.com/slides/java/).
3. Environnement de développement intégré (IDE) : vous pouvez utiliser n'importe quel IDE Java tel que IntelliJ IDEA, Eclipse ou NetBeans.
4.  Aspose.Cells pour Java : ceci est nécessaire pour modifier les données intégrées dans l'objet OLE. Téléchargez-le depuis[Page de téléchargement d'Aspose.Cells](https://releases.aspose.com/cells/java/).
5.  Fichier de présentation : préparez un fichier PowerPoint avec un objet OLE intégré. Pour ce tutoriel, nommons-le`ChangeOLEObjectData.pptx`.
## Importer des packages
Tout d’abord, importons les packages nécessaires dans votre projet Java.
```java
import com.aspose.cells.OoxmlSaveOptions;
import com.aspose.cells.Workbook;
import com.aspose.slides.*;

import java.io.ByteArrayInputStream;
import java.io.ByteArrayOutputStream;
```

Maintenant, décomposons le processus en étapes simples et gérables.
## Étape 1 : Charger la présentation PowerPoint
Pour commencer, vous devez charger la présentation PowerPoint contenant l'objet OLE.
```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx");
```
## Étape 2 : accéder à la diapositive contenant l'objet OLE
Ensuite, récupérez la diapositive dans laquelle l'objet OLE est intégré.
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Étape 3 : recherchez l'objet OLE dans la diapositive
Parcourez les formes de la diapositive pour localiser l’objet OLE.
```java
OleObjectFrame ole = null;
// Traverser toutes les formes pour le cadre Ole
for (IShape shape : slide.getShapes()) {
    if (shape instanceof OleObjectFrame) {
        ole = (OleObjectFrame) shape;
        break;
    }
}
```
## Étape 4 : extraire les données incorporées de l'objet OLE
Si l'objet OLE est trouvé, extrayez ses données incorporées.
```java
if (ole != null) {
    ByteArrayInputStream msln = new ByteArrayInputStream(ole.getEmbeddedData().getEmbeddedFileData());
```
## Étape 5 : modifier les données intégrées à l'aide d'Aspose.Cells
Maintenant, utilisez Aspose.Cells pour lire et modifier les données intégrées, qui dans ce cas sont probablement un classeur Excel.
```java
    Workbook wb = new Workbook(msln);
    // Modifier les données du classeur
    wb.getWorksheets().get(0).getCells().get(0, 4).putValue("E");
    wb.getWorksheets().get(0).getCells().get(1, 4).putValue(12);
    wb.getWorksheets().get(0).getCells().get(2, 4).putValue(14);
    wb.getWorksheets().get(0).getCells().get(3, 4).putValue(15);
```
## Étape 6 : Enregistrez les données modifiées dans l’objet OLE
Après avoir apporté les modifications nécessaires, enregistrez à nouveau le classeur modifié dans l'objet OLE.
```java
    ByteArrayOutputStream msout = new ByteArrayOutputStream();
    OoxmlSaveOptions so1 = new OoxmlSaveOptions(SaveFormat.XLSX);
    wb.save(msout, so1);
    IOleEmbeddedDataInfo newData = new OleEmbeddedDataInfo(msout.toByteArray(), ole.getEmbeddedData().getEmbeddedFileExtension());
    ole.setEmbeddedData(newData);
```
## Étape 7 : Enregistrez la présentation mise à jour
Enfin, enregistrez la présentation PowerPoint mise à jour.
```java
    pres.save(dataDir + "OleEdit_out.pptx", SaveFormat.Pptx);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## Conclusion
La mise à jour des données d'objets OLE dans des présentations PowerPoint à l'aide d'Aspose.Slides pour Java est un processus simple une fois que vous l'avez divisé en étapes simples. Ce guide vous a guidé dans le chargement d'une présentation, l'accès et la modification des données OLE intégrées, ainsi que l'enregistrement de la présentation mise à jour. Grâce à ces étapes, vous pouvez gérer et mettre à jour efficacement le contenu intégré dans vos diapositives PowerPoint par programmation.
## FAQ
### Qu’est-ce qu’un objet OLE dans PowerPoint ?
Un objet OLE (Object Linking and Embedding) permet d'intégrer du contenu provenant d'autres applications, comme des feuilles de calcul Excel, dans des diapositives PowerPoint.
### Puis-je utiliser Aspose.Slides avec d’autres langages de programmation ?
Oui, Aspose.Slides prend en charge plusieurs langages, notamment .NET, Python et C.++.
### Ai-je besoin d’Aspose.Cells pour modifier les objets OLE dans PowerPoint ?
Oui, si l'objet OLE est une feuille de calcul Excel, vous aurez besoin d'Aspose.Cells pour le modifier.
### Existe-t-il une version d’essai d’Aspose.Slides ?
 Oui, vous pouvez obtenir un[essai gratuit](https://releases.aspose.com/) pour tester les fonctionnalités d'Aspose.Slides.
### Où puis-je trouver la documentation pour Aspose.Slides ?
 Vous pouvez trouver une documentation détaillée sur le[Page de documentation Aspose.Slides](https://reference.aspose.com/slides/java/).