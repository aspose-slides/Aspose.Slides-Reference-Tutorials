---
"description": "تعرّف على كيفية إضافة إزاحة تمدد لتعبئة الصور في عروض PowerPoint التقديمية باستخدام Aspose.Slides لجافا. يتضمن البرنامج التعليمي خطوة بخطوة."
"linktitle": "إضافة إزاحة التمدد لملء الصورة في PowerPoint"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "إضافة إزاحة التمدد لملء الصورة في PowerPoint"
"url": "/ar/java/java-powerpoint-shape-media-insertion/add-stretch-offset-image-fill-powerpoint/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إضافة إزاحة التمدد لملء الصورة في PowerPoint

## مقدمة
في هذا البرنامج التعليمي، ستتعلم كيفية استخدام Aspose.Slides لجافا لإضافة إزاحة تمدد لتعبئة الصور في عروض PowerPoint التقديمية. تتيح لك هذه الميزة التحكم بالصور داخل شرائحك، مما يمنحك تحكمًا أكبر في مظهرها.
## المتطلبات الأساسية
قبل البدء، تأكد من أن لديك ما يلي:
1. تم تثبيت Java Development Kit (JDK) على نظامك.
2. تم تنزيل Aspose.Slides لمكتبة Java وإعدادها في مشروع Java الخاص بك.
## استيراد الحزم
للبدء، قم باستيراد الحزم الضرورية في مشروع Java الخاص بك:
```java
import com.aspose.slides.*;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## الخطوة 1: إعداد دليل المستندات الخاص بك
قم بتحديد الدليل الذي يوجد فيه مستند PowerPoint الخاص بك:
```java
String dataDir = "Your Document Directory";
```
## الخطوة 2: إنشاء كائن العرض التقديمي
قم بإنشاء فئة العرض التقديمي لتمثيل ملف PowerPoint:
```java
Presentation pres = new Presentation();
```
## الخطوة 3: إضافة صورة إلى الشريحة
استرجاع الشريحة الأولى وإضافة صورة إليها:
```java
ISlide sld = pres.getSlides().get_Item(0);
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx = pres.getImages().addImage(img);
```
## الخطوة 4: إضافة إطار الصورة
إنشاء إطار صورة بأبعاد تعادل الصورة:
```java
sld.getShapes().addPictureFrame(ShapeType.Rectangle, 50, 150, imgx.getWidth(), imgx.getHeight(), imgx);
```
## الخطوة 5: حفظ العرض التقديمي
حفظ ملف PowerPoint المعدل:
```java
pres.save(dataDir + "AddStretchOffsetForImageFill_out.pptx", SaveFormat.Pptx);
```

## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية إضافة إزاحة تمدد لتعبئة الصور في PowerPoint باستخدام Aspose.Slides لجافا. تتيح لك هذه الميزة إمكانيات واسعة لتحسين عروضك التقديمية باستخدام صور مخصصة.
## الأسئلة الشائعة
### هل يمكنني استخدام هذه الطريقة لإضافة صور إلى شرائح محددة في العرض التقديمي؟
نعم، يمكنك تحديد فهرس الشريحة عند استرداد كائن الشريحة لاستهداف شريحة معينة.
### هل يدعم Aspose.Slides for Java تنسيقات الصور الأخرى إلى جانب JPEG؟
نعم، يدعم Aspose.Slides for Java تنسيقات الصور المختلفة، بما في ذلك PNG وGIF وBMP وغيرها.
### هل هناك حد لحجم الصور التي يمكنني إضافتها باستخدام هذه الطريقة؟
يمكن لـ Aspose.Slides for Java التعامل مع صور ذات أحجام مختلفة، ولكن يوصى بتحسين الصور للحصول على أداء أفضل في العروض التقديمية.
### هل يمكنني تطبيق تأثيرات أو تحويلات إضافية على الصور بعد إضافتها إلى الشرائح؟
نعم، يمكنك تطبيق مجموعة واسعة من التأثيرات والتحويلات على الصور باستخدام Aspose.Slides لواجهة برمجة التطبيقات الشاملة الخاصة بـ Java.
### أين يمكنني العثور على المزيد من الموارد والدعم لـ Aspose.Slides لـ Java؟
يمكنك زيارة [توثيق Aspose.Slides لـ Java](https://reference.aspose.com/slides/java/) للحصول على أدلة مفصلة واستكشاف [منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) لدعم المجتمع.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}