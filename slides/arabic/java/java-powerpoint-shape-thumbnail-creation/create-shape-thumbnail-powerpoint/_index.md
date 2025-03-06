---
title: إنشاء صورة مصغرة للشكل في برنامج PowerPoint
linktitle: إنشاء صورة مصغرة للشكل في برنامج PowerPoint
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية إنشاء صور مصغرة للأشكال في عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ Java. دليل خطوة بخطوة المقدمة.
type: docs
weight: 14
url: /ar/java/java-powerpoint-shape-thumbnail-creation/create-shape-thumbnail-powerpoint/
---
## مقدمة
في هذا البرنامج التعليمي، سنتعمق في إنشاء صور مصغرة للأشكال في عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ Java. Aspose.Slides هي مكتبة قوية تمكن المطورين من العمل مع ملفات PowerPoint برمجيًا، مما يسمح بأتمتة المهام المختلفة، بما في ذلك إنشاء صور مصغرة للأشكال.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
- المعرفة الأساسية ببرمجة جافا.
- تم تثبيت Java Development Kit (JDK) على نظامك.
-  تم تنزيل Aspose.Slides لمكتبة Java وإعدادها في مشروعك. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/java/).

## حزم الاستيراد
أولاً، تحتاج إلى استيراد الحزم الضرورية في كود Java الخاص بك للاستفادة من وظائف Aspose.Slides. قم بتضمين عبارات الاستيراد التالية في بداية ملف Java الخاص بك:
```java
import com.aspose.slides.Presentation;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## الخطوة 1: تحديد دليل المستندات
```java
String dataDir = "Your Document Directory";
```
 يستبدل`"Your Document Directory"` مع المسار إلى الدليل الذي يحتوي على ملف PowerPoint الخاص بك.
## الخطوة 2: إنشاء كائن العرض التقديمي
```java
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
```
 إنشاء مثيل جديد لـ`Presentation` فئة، وتمرير المسار إلى ملف PowerPoint الخاص بك كمعلمة.
## الخطوة 3: إنشاء صورة مصغرة للشكل
```java
BufferedImage bitmap = presentation.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail();
```
استرجاع الصورة المصغرة للشكل المطلوب من الشريحة الأولى للعرض التقديمي.
## الخطوة 4: حفظ الصورة المصغرة
```java
ImageIO.write(bitmap, ".png", new File(dataDir + "Shape_thumbnail_out.png"));
```
احفظ الصورة المصغرة التي تم إنشاؤها على القرص بتنسيق PNG باسم الملف المحدد.

## خاتمة
في الختام، يوضح هذا البرنامج التعليمي كيفية إنشاء صور مصغرة للأشكال في عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ Java. باتباع الدليل الموضح خطوة بخطوة واستخدام مقتطفات التعليمات البرمجية المتوفرة، يمكنك إنشاء صور مصغرة للأشكال برمجيًا بكفاءة.

## الأسئلة الشائعة
### هل يمكنني إنشاء صور مصغرة للأشكال على أي شريحة في العرض التقديمي؟
نعم، يمكنك تعديل التعليمات البرمجية لاستهداف الأشكال في أي شريحة عن طريق ضبط فهرس الشريحة وفقًا لذلك.
### هل يدعم Aspose.Slides تنسيقات الصور الأخرى لحفظ الصور المصغرة؟
نعم، إلى جانب PNG، يدعم Aspose.Slides حفظ الصور المصغرة بتنسيقات صور مختلفة مثل JPEG وGIF وBMP.
### هل Aspose.Slides مناسب للاستخدام التجاري؟
 نعم، يقدم Aspose.Slides تراخيص تجارية للشركات والمؤسسات. يمكنك شراء ترخيص من[هنا](https://purchase.aspose.com/buy).
### هل يمكنني تجربة Aspose.Slides قبل الشراء؟
 قطعاً! يمكنك تنزيل نسخة تجريبية مجانية من Aspose.Slides من[هنا](https://releases.aspose.com/) لتقييم مميزاته وقدراته.
### أين يمكنني العثور على الدعم لـ Aspose.Slides؟
 إذا كانت لديك أية أسئلة أو كنت بحاجة إلى مساعدة فيما يتعلق بـ Aspose.Slides، فيمكنك زيارة الموقع[منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) للدعم.