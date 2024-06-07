---
title: إضافة إزاحة تمتد لملء الصورة في PowerPoint
linktitle: إضافة إزاحة تمتد لملء الصورة في PowerPoint
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية إضافة إزاحة ممتدة لملء الصور في عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ Java. وشملت البرنامج التعليمي خطوة بخطوة.
type: docs
weight: 16
url: /ar/java/java-powerpoint-shape-media-insertion/add-stretch-offset-image-fill-powerpoint/
---
## مقدمة
ستتعلم في هذا البرنامج التعليمي كيفية استخدام Aspose.Slides لـ Java لإضافة إزاحة ممتدة لملء الصورة في عروض PowerPoint التقديمية. تسمح لك هذه الميزة بمعالجة الصور داخل شرائحك، مما يمنحك تحكمًا أكبر في مظهرها.
## المتطلبات الأساسية
قبل البدء، تأكد من أن لديك ما يلي:
1. تم تثبيت Java Development Kit (JDK) على نظامك.
2. تم تنزيل Aspose.Slides لمكتبة Java وإعدادها في مشروع Java الخاص بك.
## حزم الاستيراد
للبدء، قم باستيراد الحزم الضرورية في مشروع Java الخاص بك:
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## الخطوة 1: قم بإعداد دليل المستندات الخاص بك
حدد الدليل الذي يوجد به مستند PowerPoint الخاص بك:
```java
String dataDir = "Your Document Directory";
```
## الخطوة 2: إنشاء كائن العرض التقديمي
إنشاء مثيل لفئة العرض التقديمي لتمثيل ملف PowerPoint:
```java
Presentation pres = new Presentation();
```
## الخطوة 3: إضافة صورة إلى الشريحة
استرجع الشريحة الأولى وأضف صورة إليها:
```java
ISlide sld = pres.getSlides().get_Item(0);
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx = pres.getImages().addImage(img);
```
## الخطوة 4: إضافة إطار الصورة
قم بإنشاء إطار صورة بأبعاد مكافئة للصورة:
```java
sld.getShapes().addPictureFrame(ShapeType.Rectangle, 50, 150, imgx.getWidth(), imgx.getHeight(), imgx);
```
## الخطوة 5: احفظ العرض التقديمي
احفظ ملف PowerPoint المعدل:
```java
pres.save(dataDir + "AddStretchOffsetForImageFill_out.pptx", SaveFormat.Pptx);
```

## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية إضافة إزاحة امتداد لملء الصورة في PowerPoint باستخدام Aspose.Slides لـ Java. تفتح هذه الميزة عالمًا من الإمكانيات لتحسين عروضك التقديمية باستخدام صور مخصصة.
## الأسئلة الشائعة
### هل يمكنني استخدام هذه الطريقة لإضافة صور إلى شرائح محددة في العرض التقديمي؟
نعم، يمكنك تحديد فهرس الشريحة عند استرجاع كائن الشريحة لاستهداف شريحة معينة.
### هل يدعم Aspose.Slides for Java تنسيقات الصور الأخرى إلى جانب JPEG؟
نعم، يدعم Aspose.Slides for Java تنسيقات الصور المختلفة، بما في ذلك PNG وGIF وBMP وغيرها.
### هل هناك حد لحجم الصور التي يمكنني إضافتها بهذه الطريقة؟
يمكن لـ Aspose.Slides for Java التعامل مع الصور ذات الأحجام المختلفة، ولكن يوصى بتحسين الصور للحصول على أداء أفضل في العروض التقديمية.
### هل يمكنني تطبيق تأثيرات أو تحويلات إضافية على الصور بعد إضافتها إلى الشرائح؟
نعم، يمكنك تطبيق مجموعة واسعة من التأثيرات والتحويلات على الصور باستخدام Aspose.Slides لواجهة برمجة التطبيقات الشاملة لـ Java.
### أين يمكنني العثور على المزيد من الموارد والدعم لـ Aspose.Slides لـ Java؟
 يمكنك زيارة[Aspose.Slides لتوثيق جافا](https://reference.aspose.com/slides/java/) للحصول على أدلة مفصلة واستكشاف[منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) لدعم المجتمع.