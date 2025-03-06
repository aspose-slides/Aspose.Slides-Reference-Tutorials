---
title: إنشاء صورة مصغرة لشكل الحدود
linktitle: إنشاء صورة مصغرة لشكل الحدود
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية إنشاء صور مصغرة للأشكال ذات حدود باستخدام Aspose.Slides لـ Java. يرشدك هذا البرنامج التعليمي خطوة بخطوة خلال هذه العملية.
type: docs
weight: 10
url: /ar/java/java-powerpoint-shape-thumbnail-creation/create-bounds-shape-thumbnail/
---
## مقدمة
Aspose.Slides for Java هي مكتبة قوية تسمح لمطوري Java بإنشاء عروض PowerPoint التقديمية ومعالجتها وتحويلها برمجياً. في هذا البرنامج التعليمي، سوف نتعلم كيفية إنشاء صورة مصغرة لشكل ذي حدود باستخدام Aspose.Slides for Java.
## المتطلبات الأساسية
قبل أن تبدأ، تأكد من أن لديك ما يلي:
1. تم تثبيت Java Development Kit (JDK) على نظامك.
2.  تم تنزيل Aspose.Slides لمكتبة Java وإضافتها إلى مشروعك. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/java/).

## حزم الاستيراد
تأكد من استيراد الحزم الضرورية في كود Java الخاص بك:
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ShapeThumbnailBounds;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## الخطوة 1: قم بإعداد مشروعك
قم بإنشاء مشروع Java جديد في IDE المفضل لديك وأضف مكتبة Aspose.Slides for Java إلى تبعيات مشروعك.
## الخطوة 2: إنشاء كائن عرض تقديمي
 إنشاء مثيل أ`Presentation` الكائن عن طريق توفير المسار إلى ملف العرض التقديمي لـ PowerPoint.
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
```
## الخطوة 3: إنشاء صورة مصغرة لشكل الحدود
الآن، لنقم بإنشاء صورة مصغرة لشكل بحدود من العرض التقديمي.
```java
try {
    BufferedImage bitmap = presentation.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail(ShapeThumbnailBounds.Appearance, 1, 1);
    ImageIO.write(bitmap, ".png", new File(dataDir + "Shape_thumbnail_Bound_Shape_out.png"));
} finally {
    if (presentation != null) presentation.dispose();
}
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية إنشاء صورة مصغرة لشكل ذي حدود باستخدام Aspose.Slides لـ Java. باتباع هذه الخطوات، يمكنك بسهولة إنشاء صور مصغرة للأشكال في عروض PowerPoint التقديمية الخاصة بك برمجياً.
## الأسئلة الشائعة
### هل يمكنني إنشاء صور مصغرة لأشكال معينة داخل الشريحة؟
نعم، يمكنك الوصول إلى الأشكال الفردية داخل الشريحة وإنشاء صور مصغرة لها باستخدام Aspose.Slides for Java.
### هل Aspose.Slides for Java متوافق مع كافة إصدارات ملفات PowerPoint؟
يدعم Aspose.Slides for Java تنسيقات ملفات PowerPoint المتنوعة، بما في ذلك PPT وPPTX وPPS وPPSX والمزيد.
### هل يمكنني تخصيص مظهر الصور المصغرة التي تم إنشاؤها؟
نعم، يمكنك ضبط خصائص الصور المصغرة، مثل الحجم والجودة، وفقًا لمتطلباتك.
### هل يدعم Aspose.Slides for Java ميزات أخرى إلى جانب إنشاء الصور المصغرة؟
نعم، يوفر Aspose.Slides for Java وظائف واسعة النطاق للعمل مع عروض PowerPoint التقديمية، بما في ذلك معالجة الشرائح واستخراج النص وإنشاء المخططات.
### هل هناك إصدار تجريبي متاح لـ Aspose.Slides لـ Java؟
 نعم، يمكنك تنزيل نسخة تجريبية مجانية من[هنا](https://releases.aspose.com/).