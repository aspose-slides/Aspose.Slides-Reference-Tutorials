---
title: إنشاء صورة مصغرة لعامل القياس
linktitle: إنشاء صورة مصغرة لعامل القياس
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية إنشاء صور مصغرة لعامل القياس في Java باستخدام Aspose.Slides لـ Java. دليل سهل المتابعة مع تعليمات خطوة بخطوة.
type: docs
weight: 12
url: /ar/java/java-powerpoint-shape-thumbnail-creation/create-scaling-factor-thumbnail/
---
## مقدمة
في هذا البرنامج التعليمي، سنرشدك خلال عملية إنشاء صورة مصغرة لعامل القياس باستخدام Aspose.Slides لـ Java. اتبع هذه التعليمات خطوة بخطوة لتحقيق النتيجة المرجوة.
## المتطلبات الأساسية
قبل البدء، تأكد من توفر المتطلبات الأساسية التالية:
- تم تثبيت Java Development Kit (JDK) على نظامك.
- تم تنزيل Aspose.Slides لمكتبة Java وإعدادها في مشروع Java الخاص بك.
- الفهم الأساسي للغة البرمجة جافا.

## حزم الاستيراد
أولاً، قم باستيراد الحزم اللازمة للعمل مع Aspose.Slides في كود Java الخاص بك. 
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ShapeThumbnailBounds;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```

الآن، دعونا نقسم المثال المقدم إلى خطوات متعددة:
## الخطوة 1: قم بتعيين دليل المستندات
حدد المسار إلى دليل المستند الخاص بك حيث يوجد ملف العرض التقديمي لـ PowerPoint.
```java
String dataDir = "Your Document Directory";
```
 يستبدل`"Your Document Directory"` مع المسار إلى دليل المستندات الفعلي الخاص بك.
## الخطوة 2: إنشاء كائن العرض التقديمي
قم بإنشاء مثيل لفئة العرض التقديمي لتمثيل ملف العرض التقديمي لـ PowerPoint.
```java
Presentation p = new Presentation(dataDir + "HelloWorld.pptx");
```
 تأكد من الاستبدال`"HelloWorld.pptx"` مع اسم ملف عرض PowerPoint التقديمي الخاص بك.
## الخطوة 3: إنشاء صورة كاملة الحجم
قم بإنشاء صورة كاملة الحجم للشريحة المطلوبة من العرض التقديمي.
```java
BufferedImage bitmap = p.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail(ShapeThumbnailBounds.Shape, 1, 1);
```
يسترد هذا الرمز الصورة المصغرة للشكل الأول في الشريحة الأولى من العرض التقديمي.
## الخطوة 4: احفظ الصورة
احفظ الصورة التي تم إنشاؤها على القرص بتنسيق PNG.
```java
ImageIO.write(bitmap, ".png", new File(dataDir + "Scaling Factor Thumbnail_out.png"));
```
 تأكد من الاستبدال`"Scaling Factor Thumbnail_out.png"` مع اسم ملف الإخراج المطلوب.

## خاتمة
في الختام، لقد نجحت في إنشاء صورة مصغرة لعامل القياس باستخدام Aspose.Slides لـ Java. باتباع الخطوات المتوفرة، يمكنك بسهولة دمج هذه الوظيفة في تطبيقات Java الخاصة بك.
## الأسئلة الشائعة
### هل يمكنني استخدام Aspose.Slides لـ Java مع أي Java IDE؟
نعم، يمكن استخدام Aspose.Slides for Java مع أي بيئة تطوير متكاملة لـ Java (IDE) مثل Eclipse أو IntelliJ IDEA أو NetBeans.
### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Slides لـ Java؟
 نعم، يمكنك الاستفادة من النسخة التجريبية المجانية من Aspose.Slides لـ Java من خلال زيارة الموقع[موقع إلكتروني](https://releases.aspose.com/).
### أين يمكنني العثور على الدعم لـ Aspose.Slides لـ Java؟
 يمكنك العثور على دعم لـ Aspose.Slides لـ Java على الموقع[منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11).
### كيف يمكنني شراء Aspose.Slides لجافا؟
 يمكنك شراء Aspose.Slides لـ Java من[صفحة الشراء](https://purchase.aspose.com/buy).
### هل أحتاج إلى ترخيص مؤقت لاستخدام Aspose.Slides لـ Java؟
 نعم يمكنك الحصول على ترخيص مؤقت من[صفحة الترخيص المؤقتة](https://purchase.aspose.com/temporary-license/).