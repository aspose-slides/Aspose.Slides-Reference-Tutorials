---
title: إخفاء الأشكال في PowerPoint
linktitle: إخفاء الأشكال في PowerPoint
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية إخفاء الأشكال في PowerPoint باستخدام Aspose.Slides لـ Java من خلال دليلنا التفصيلي خطوة بخطوة. مثالي لمطوري Java من جميع المستويات.
weight: 27
url: /ar/java/java-powerpoint-shape-formatting-geometry/hide-shapes-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إخفاء الأشكال في PowerPoint

## مقدمة
مرحبًا بك في برنامجنا التعليمي الشامل حول إخفاء الأشكال في PowerPoint باستخدام Aspose.Slides لـ Java! إذا كنت بحاجة في أي وقت مضى إلى إخفاء أشكال معينة في عروض PowerPoint التقديمية برمجياً، فأنت في المكان الصحيح. سيرشدك هذا الدليل خلال كل خطوة بأسلوب محادثة بسيط. سواء كنت مطورًا متمرسًا أو بدأت للتو في استخدام Java، فنحن نوفر لك كل ما تحتاجه.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
-  Java Development Kit (JDK): تأكد من تثبيت JDK على جهازك. يمكنك تنزيله من[موقع أوراكل](https://www.oracle.com/java/technologies/javase-downloads.html).
-  Aspose.Slides لمكتبة Java: قم بتنزيل أحدث إصدار من[Aspose.Slides لإصدارات جافا](https://releases.aspose.com/slides/java/).
- بيئة التطوير المتكاملة (IDE): أي Java IDE مثل IntelliJ IDEA أو Eclipse أو NetBeans.
- الفهم الأساسي لجافا: على الرغم من أن هذا البرنامج التعليمي مناسب للمبتدئين، إلا أن الفهم الأساسي لجافا سيكون مفيدًا.
## حزم الاستيراد
للبدء، ستحتاج إلى استيراد الحزم اللازمة لـ Aspose.Slides. وإليك كيف يمكنك القيام بذلك:
```java
import com.aspose.slides.*;

```
في هذا القسم، سنقوم بتقسيم عملية إخفاء الأشكال في PowerPoint إلى خطوات سهلة المتابعة. تتضمن كل خطوة عنوانًا وشرحًا تفصيليًا.
## الخطوة 1: قم بإعداد مشروعك
أول الأشياء أولاً، تحتاج إلى إعداد مشروع Java الخاص بك وتضمين Aspose.Slides باعتباره تبعية. إليك الطريقة:
### إنشاء مشروع جافا جديد
 افتح IDE الخاص بك وقم بإنشاء مشروع Java جديد. سمها شيئًا ذا صلة، مثل`HideShapesInPowerPoint`.
### إضافة مكتبة Aspose.Slides
 قم بتنزيل ملف Aspose.Slides JAR من ملف[رابط التحميل](https://releases.aspose.com/slides/java/) وإضافته إلى مسار الفصل الخاص بمشروعك. قد تختلف هذه الخطوة قليلاً اعتمادًا على IDE الخاص بك.
## الخطوة 2: تهيئة العرض التقديمي
الآن، لنبدأ بالبرمجة. تحتاج إلى تهيئة كائن عرض تقديمي يمثل ملف PowerPoint الخاص بك.
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء فئة العرض التقديمي التي تمثل PPTX
Presentation pres = new Presentation();
```

## الخطوة 3: الوصول إلى الشريحة الأولى
بعد ذلك، ستحتاج إلى الوصول إلى الشريحة الأولى في العرض التقديمي الخاص بك.
```java
// احصل على الشريحة الأولى
ISlide sld = pres.getSlides().get_Item(0);
```
## الخطوة 4: إضافة الأشكال إلى الشريحة
في هذا المثال، سنضيف شكلين إلى الشريحة - مستطيل وشكل قمر.
```java
// إضافة شكل تلقائي لنوع المستطيل
IShape shp1 = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 40, 150, 50);
IShape shp2 = sld.getShapes().addAutoShape(ShapeType.Moon, 160, 40, 150, 50);
```
## الخطوة 5: تحديد النص البديل وإخفاء الأشكال
لتحديد الأشكال التي تريد إخفاءها، قم بتعيين نص بديل لها. ثم قم بالمرور عبر جميع الأشكال وقم بإخفاء الأشكال التي تطابق النص البديل.
```java
String alttext = "User Defined";
int iCount = sld.getShapes().size();
for (int i = 0; i < iCount; i++) {
    AutoShape ashp = (AutoShape) sld.getShapes().get_Item(i);
    if (ashp.getAlternativeText().equals(alttext)) {
        ashp.setHidden(true);
    }
}
```
## الخطوة 6: احفظ العرض التقديمي
وأخيرًا، احفظ العرض التقديمي المعدل في الموقع الذي تريده.
```java
// حفظ العرض التقديمي على القرص
pres.save(dataDir + "Hiding_Shapes_out.pptx", SaveFormat.Pptx);
```
## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية إخفاء الأشكال في عرض PowerPoint التقديمي باستخدام Aspose.Slides لـ Java. لقد غطى هذا الدليل التفصيلي كل شيء بدءًا من إعداد مشروعك وحتى حفظ العرض التقديمي النهائي. باستخدام هذه المهارات، يمكنك الآن أتمتة عروض PowerPoint التقديمية وتخصيصها بشكل أكثر كفاءة.
## الأسئلة الشائعة
### ما هو Aspose.Slides لجافا؟
Aspose.Slides for Java عبارة عن واجهة برمجة تطبيقات قوية لمعالجة ملفات PowerPoint برمجيًا. فهو يسمح للمطورين بإنشاء العروض التقديمية وتعديلها وإدارتها دون الحاجة إلى Microsoft PowerPoint.
### كيف يمكنني إخفاء شكل في PowerPoint باستخدام جافا؟
 يمكنك إخفاء الشكل من خلال ضبطه`setHidden` الملكية ل`true`. يتضمن ذلك تحديد الشكل من خلال نصه البديل والتكرار خلال الأشكال الموجودة على الشريحة.
### هل يمكنني استخدام Aspose.Slides لـ Java مع لغات البرمجة الأخرى؟
يتوفر Aspose.Slides للعديد من لغات البرمجة بما في ذلك .NET وPython وC++. ومع ذلك، يغطي هذا الدليل Java على وجه التحديد.
### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Slides؟
 نعم، يمكنك تنزيل نسخة تجريبية مجانية من[هنا](https://releases.aspose.com/).
### أين يمكنني الحصول على الدعم لـ Aspose.Slides؟
 يمكنك الحصول على الدعم من[منتدى دعم Aspose.Slides](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
