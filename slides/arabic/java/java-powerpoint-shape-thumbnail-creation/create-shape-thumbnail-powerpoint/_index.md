---
"description": "تعرّف على كيفية إنشاء صور مصغرة للأشكال في عروض PowerPoint التقديمية باستخدام Aspose.Slides لجافا. دليل خطوة بخطوة مُقدّم."
"linktitle": "إنشاء صورة مصغرة للشكل في PowerPoint"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "إنشاء صورة مصغرة للشكل في PowerPoint"
"url": "/ar/java/java-powerpoint-shape-thumbnail-creation/create-shape-thumbnail-powerpoint/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء صورة مصغرة للشكل في PowerPoint

## مقدمة
في هذا البرنامج التعليمي، سنتعمق في إنشاء صور مصغرة للأشكال في عروض PowerPoint التقديمية باستخدام Aspose.Slides لجافا. Aspose.Slides مكتبة فعّالة تُمكّن المطورين من العمل مع ملفات PowerPoint برمجيًا، مما يسمح بأتمتة مهام متنوعة، بما في ذلك إنشاء صور مصغرة للأشكال.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك المتطلبات الأساسية التالية:
- المعرفة الأساسية ببرمجة جافا.
- تم تثبيت Java Development Kit (JDK) على نظامك.
- تم تنزيل مكتبة Aspose.Slides لجافا وضبطها في مشروعك. يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/java/).

## استيراد الحزم
أولاً، عليك استيراد الحزم اللازمة في شيفرة جافا لديك للاستفادة من وظائف Aspose.Slides. أدرج عبارات الاستيراد التالية في بداية ملف جافا:
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
يستبدل `"Your Document Directory"` مع المسار إلى الدليل الذي يحتوي على ملف PowerPoint الخاص بك.
## الخطوة 2: إنشاء كائن العرض التقديمي
```java
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
```
إنشاء مثيل جديد من `Presentation` الفئة، تمرير المسار إلى ملف PowerPoint الخاص بك كمعلمة.
## الخطوة 3: إنشاء صورة مصغرة للشكل
```java
BufferedImage bitmap = presentation.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail();
```
استرداد الصورة المصغرة للشكل المطلوب من الشريحة الأولى للعرض التقديمي.
## الخطوة 4: حفظ الصورة المصغرة
```java
ImageIO.write(bitmap, ".png", new File(dataDir + "Shape_thumbnail_out.png"));
```
احفظ الصورة المصغرة الناتجة على القرص بتنسيق PNG مع اسم الملف المحدد.

## خاتمة
في الختام، يوضح هذا البرنامج التعليمي كيفية إنشاء صور مصغرة للأشكال في عروض PowerPoint التقديمية باستخدام Aspose.Slides لجافا. باتباع الدليل خطوة بخطوة واستخدام مقتطفات التعليمات البرمجية المرفقة، يمكنك إنشاء صور مصغرة للأشكال برمجيًا بكفاءة.

## الأسئلة الشائعة
### هل يمكنني إنشاء صور مصغرة للأشكال على أي شريحة في العرض التقديمي؟
نعم، يمكنك تعديل الكود لاستهداف الأشكال على أي شريحة عن طريق ضبط فهرس الشريحة وفقًا لذلك.
### هل يدعم Aspose.Slides تنسيقات الصور الأخرى لحفظ الصور المصغرة؟
نعم، بالإضافة إلى PNG، يدعم Aspose.Slides حفظ الصور المصغرة بتنسيقات صور مختلفة مثل JPEG وGIF وBMP.
### هل Aspose.Slides مناسب للاستخدام التجاري؟
نعم، يوفر Aspose.Slides تراخيص تجارية للشركات والمؤسسات. يمكنك شراء الترخيص من [هنا](https://purchase.aspose.com/buy).
### هل يمكنني تجربة Aspose.Slides قبل الشراء؟
بالتأكيد! يمكنك تنزيل نسخة تجريبية مجانية من Aspose.Slides من [هنا](https://releases.aspose.com/) لتقييم مميزاته وقدراته.
### أين يمكنني العثور على الدعم لـ Aspose.Slides؟
إذا كان لديك أي أسئلة أو تحتاج إلى مساعدة بشأن Aspose.Slides، يمكنك زيارة [منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) للحصول على الدعم.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}