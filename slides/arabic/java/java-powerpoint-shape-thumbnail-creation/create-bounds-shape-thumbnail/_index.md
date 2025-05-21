---
"description": "تعلّم كيفية إنشاء صور مصغّرة للأشكال مع حدود باستخدام Aspose.Slides لجافا. يرشدك هذا البرنامج التعليمي خطوة بخطوة خلال العملية."
"linktitle": "إنشاء حدود لشكل الصورة المصغرة"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "إنشاء حدود لشكل الصورة المصغرة"
"url": "/ar/java/java-powerpoint-shape-thumbnail-creation/create-bounds-shape-thumbnail/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء حدود لشكل الصورة المصغرة

## مقدمة
Aspose.Slides لجافا هي مكتبة فعّالة تُمكّن مطوري جافا من إنشاء عروض PowerPoint التقديمية وتعديلها وتحويلها برمجيًا. في هذا البرنامج التعليمي، سنتعلم كيفية إنشاء صورة مصغّرة لشكل ذي حدود باستخدام Aspose.Slides لجافا.
## المتطلبات الأساسية
قبل أن تبدأ، تأكد من أن لديك ما يلي:
1. تم تثبيت Java Development Kit (JDK) على نظامك.
2. تم تنزيل مكتبة Aspose.Slides لجافا وإضافتها إلى مشروعك. يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/java/).

## استيراد الحزم
تأكد من استيراد الحزم الضرورية في كود Java الخاص بك:
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ShapeThumbnailBounds;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## الخطوة 1: إعداد مشروعك
قم بإنشاء مشروع Java جديد في IDE المفضل لديك وأضف مكتبة Aspose.Slides for Java إلى تبعيات مشروعك.
## الخطوة 2: إنشاء كائن عرض تقديمي
إنشاء مثيل `Presentation` الكائن عن طريق توفير المسار إلى ملف العرض التقديمي الخاص بك في PowerPoint.
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
```
## الخطوة 3: إنشاء صورة مصغرة لشكل الحدود
الآن، دعنا نقوم بإنشاء صورة مصغرة لشكل مع حدود من العرض التقديمي.
```java
try {
    BufferedImage bitmap = presentation.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail(ShapeThumbnailBounds.Appearance, 1, 1);
    ImageIO.write(bitmap, ".png", new File(dataDir + "Shape_thumbnail_Bound_Shape_out.png"));
} finally {
    if (presentation != null) presentation.dispose();
}
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية إنشاء صورة مصغّرة لشكل ذي حدود باستخدام Aspose.Slides لجافا. باتباع هذه الخطوات، يمكنك بسهولة إنشاء صور مصغّرة للأشكال في عروض PowerPoint التقديمية برمجيًا.
## الأسئلة الشائعة
### هل يمكنني إنشاء صور مصغرة لأشكال محددة ضمن شريحة؟
نعم، يمكنك الوصول إلى الأشكال الفردية داخل الشريحة وإنشاء صور مصغرة لها باستخدام Aspose.Slides لـ Java.
### هل برنامج Aspose.Slides for Java متوافق مع كافة إصدارات ملفات PowerPoint؟
يدعم Aspose.Slides for Java تنسيقات ملفات PowerPoint المختلفة، بما في ذلك PPT، وPPTX، وPPS، وPPSX، والمزيد.
### هل يمكنني تخصيص مظهر الصور المصغرة التي تم إنشاؤها؟
نعم، يمكنك تعديل خصائص الصور المصغرة، مثل الحجم والجودة، وفقًا لمتطلباتك.
### هل يدعم Aspose.Slides for Java ميزات أخرى إلى جانب إنشاء الصور المصغرة؟
نعم، يوفر Aspose.Slides for Java وظائف واسعة النطاق للعمل مع عروض PowerPoint، بما في ذلك معالجة الشرائح، واستخراج النص، وإنشاء المخططات.
### هل هناك نسخة تجريبية متاحة لـ Aspose.Slides لـ Java؟
نعم، يمكنك تنزيل نسخة تجريبية مجانية من [هنا](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}