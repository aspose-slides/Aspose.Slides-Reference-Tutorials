---
"description": "تعرف على كيفية إضافة إطارات صور ذات ارتفاع نسبي في عروض PowerPoint باستخدام Aspose.Slides لـ Java، مما يعزز المحتوى المرئي لديك."
"linktitle": "إضافة إطار صورة بارتفاع مقياس نسبي في PowerPoint"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "إضافة إطار صورة بارتفاع مقياس نسبي في PowerPoint"
"url": "/ar/java/java-powerpoint-shape-media-insertion/add-relative-scale-height-picture-frame-powerpoint/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إضافة إطار صورة بارتفاع مقياس نسبي في PowerPoint

## مقدمة
في هذا البرنامج التعليمي، ستتعلم كيفية إضافة إطار صورة بارتفاع مقياس نسبي في عروض PowerPoint باستخدام Aspose.Slides لـ Java.
## المتطلبات الأساسية
قبل أن تبدأ، تأكد من أن لديك ما يلي:
1. تم تثبيت Java Development Kit (JDK) على نظامك.
2. تم تنزيل Aspose.Slides لمكتبة Java وإضافتها إلى مشروع Java الخاص بك.

## استيراد الحزم
للبدء، قم باستيراد الحزم الضرورية في مشروع Java الخاص بك:
```java
import com.aspose.slides.*;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## الخطوة 1: إعداد مشروعك
أولاً، تأكد من إعداد دليل لمشروعك، وتأكد من تكوين بيئة Java الخاصة بك بشكل صحيح.
## الخطوة 2: إنشاء كائن العرض التقديمي
إنشاء كائن عرض تقديمي جديد باستخدام Aspose.Slides:
```java
Presentation presentation = new Presentation();
```
## الخطوة 3: تحميل الصورة المراد إضافتها
قم بتحميل الصورة التي تريد إضافتها إلى العرض التقديمي:
```java
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage image = presentation.getImages().addImage(img);
```
## الخطوة 4: إضافة إطار الصورة إلى الشريحة
إضافة إطار صورة إلى شريحة في العرض التقديمي:
```java
IPictureFrame pf = presentation.getSlides().get_Item(0).getShapes().addPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
## الخطوة 5: تعيين العرض والارتفاع النسبيين للمقياس
تعيين العرض والارتفاع النسبي لإطار الصورة:
```java
pf.setRelativeScaleHeight(0.8f);
pf.setRelativeScaleWidth(1.35f);
```
## الخطوة 6: حفظ العرض التقديمي
احفظ العرض التقديمي باستخدام إطار الصورة المضاف:
```java
presentation.save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```

## خاتمة
باتباع هذه الخطوات، يمكنك بسهولة إضافة إطار صورة بارتفاع مقياس نسبي في عروض PowerPoint التقديمية باستخدام Aspose.Slides لجافا. جرّب قيم مقياس مختلفة لتحقيق المظهر المطلوب لصورك.

## الأسئلة الشائعة
### هل يمكنني إضافة إطارات صور متعددة إلى شريحة واحدة باستخدام هذه الطريقة؟
نعم، يمكنك إضافة إطارات صور متعددة إلى شريحة واحدة عن طريق تكرار العملية لكل صورة.
### هل Aspose.Slides for Java متوافق مع كافة إصدارات PowerPoint؟
يعد Aspose.Slides for Java متوافقًا مع الإصدارات المختلفة من PowerPoint، مما يضمن المرونة في إنشاء العروض التقديمية.
### هل يمكنني تخصيص موضع وحجم إطار الصورة؟
بالتأكيد، يمكنك تعديل معلمات الموضع والحجم في `addPictureFrame` الطريقة التي تناسب متطلباتك.
### هل يدعم Aspose.Slides for Java تنسيقات الصور الأخرى إلى جانب JPEG؟
نعم، يدعم Aspose.Slides for Java تنسيقات الصور المختلفة، بما في ذلك PNG وGIF وBMP والمزيد.
### هل يوجد منتدى مجتمعي أو قناة دعم متاحة لمستخدمي Aspose.Slides؟
نعم، يمكنك زيارة منتدى Aspose.Slides لأي أسئلة أو مناقشات أو مساعدة بخصوص المكتبة.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}