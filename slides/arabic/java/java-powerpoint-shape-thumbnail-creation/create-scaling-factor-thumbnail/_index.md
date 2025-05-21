---
"description": "تعلّم كيفية إنشاء صور مصغّرة لعوامل القياس في جافا باستخدام Aspose.Slides لجافا. دليل سهل الاستخدام مع تعليمات خطوة بخطوة."
"linktitle": "إنشاء صورة مصغرة لعامل القياس"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "إنشاء صورة مصغرة لعامل القياس"
"url": "/ar/java/java-powerpoint-shape-thumbnail-creation/create-scaling-factor-thumbnail/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء صورة مصغرة لعامل القياس

## مقدمة
في هذا البرنامج التعليمي، سنرشدك خلال عملية إنشاء صورة مصغّرة لعامل القياس باستخدام Aspose.Slides لجافا. اتبع هذه التعليمات خطوة بخطوة لتحقيق النتيجة المرجوة.
## المتطلبات الأساسية
قبل أن تبدأ، تأكد من أن لديك المتطلبات الأساسية التالية:
- تم تثبيت Java Development Kit (JDK) على نظامك.
- تم تنزيل Aspose.Slides لمكتبة Java وإعدادها في مشروع Java الخاص بك.
- فهم أساسي للغة البرمجة جافا.

## استيراد الحزم
أولاً، قم باستيراد الحزم اللازمة المطلوبة للعمل مع Aspose.Slides في كود Java الخاص بك. 
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ShapeThumbnailBounds;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```

الآن، دعونا نقسم المثال المقدم إلى خطوات متعددة:
## الخطوة 1: تعيين دليل المستندات
قم بتحديد المسار إلى دليل المستند الذي يوجد به ملف عرض PowerPoint.
```java
String dataDir = "Your Document Directory";
```
يستبدل `"Your Document Directory"` مع المسار إلى دليل المستند الفعلي الخاص بك.
## الخطوة 2: إنشاء كائن العرض التقديمي
قم بإنشاء مثيل لفئة العرض التقديمي لتمثيل ملف العرض التقديمي PowerPoint.
```java
Presentation p = new Presentation(dataDir + "HelloWorld.pptx");
```
تأكد من الاستبدال `"HelloWorld.pptx"` مع اسم ملف العرض التقديمي PowerPoint الخاص بك.
## الخطوة 3: إنشاء صورة بالحجم الكامل
إنشاء صورة كاملة الحجم للشريحة المطلوبة من العرض التقديمي.
```java
BufferedImage bitmap = p.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail(ShapeThumbnailBounds.Shape, 1, 1);
```
يقوم هذا الكود باسترجاع الصورة المصغرة للشكل الأول في الشريحة الأولى من العرض التقديمي.
## الخطوة 4: حفظ الصورة
احفظ الصورة الناتجة على القرص بتنسيق PNG.
```java
ImageIO.write(bitmap, ".png", new File(dataDir + "Scaling Factor Thumbnail_out.png"));
```
تأكد من الاستبدال `"Scaling Factor Thumbnail_out.png"` مع اسم ملف الإخراج المطلوب.

## خاتمة
في الختام، لقد نجحت في إنشاء صورة مصغّرة لعامل القياس باستخدام Aspose.Slides لجافا. باتباع الخطوات الموضحة، يمكنك دمج هذه الوظيفة بسهولة في تطبيقات جافا.
## الأسئلة الشائعة
### هل يمكنني استخدام Aspose.Slides لـ Java مع أي Java IDE؟
نعم، يمكن استخدام Aspose.Slides for Java مع أي بيئة تطوير متكاملة لـ Java (IDE) مثل Eclipse أو IntelliJ IDEA أو NetBeans.
### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Slides لنظام Java؟
نعم، يمكنك الاستفادة من النسخة التجريبية المجانية من Aspose.Slides for Java من خلال زيارة [موقع إلكتروني](https://releases.aspose.com/).
### أين يمكنني العثور على الدعم لـ Aspose.Slides لـ Java؟
يمكنك العثور على الدعم لـ Aspose.Slides لـ Java على [منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11).
### كيف يمكنني شراء Aspose.Slides لـ Java؟
يمكنك شراء Aspose.Slides لـ Java من [صفحة الشراء](https://purchase.aspose.com/buy).
### هل أحتاج إلى ترخيص مؤقت لاستخدام Aspose.Slides لـ Java؟
نعم يمكنك الحصول على ترخيص مؤقت من [صفحة الترخيص المؤقت](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}