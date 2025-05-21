---
"description": "تعرّف على كيفية إضافة أعمدة إلى مربعات النص في PowerPoint باستخدام Aspose.Slides لجافا. حسّن عروضك التقديمية باتباع هذا الدليل المفصل."
"linktitle": "إضافة عمود في مربعات النص باستخدام Aspose.Slides لـ Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "إضافة عمود في مربعات النص باستخدام Aspose.Slides لـ Java"
"url": "/ar/java/java-powerpoint-text-box-manipulation/add-column-in-text-boxes/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إضافة عمود في مربعات النص باستخدام Aspose.Slides لـ Java

## مقدمة
في هذا البرنامج التعليمي، سنستكشف كيفية تحسين مربعات النص بإضافة أعمدة باستخدام Aspose.Slides لجافا. Aspose.Slides هي مكتبة جافا فعّالة تُمكّن المطورين من إنشاء عروض PowerPoint التقديمية وتعديلها وتحويلها برمجيًا دون الحاجة إلى مايكروسوفت أوفيس. إضافة أعمدة إلى مربعات النص تُحسّن بشكل كبير من سهولة قراءة المحتوى وتنظيمه داخل الشرائح، مما يجعل عروضك التقديمية أكثر جاذبية واحترافية.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك المتطلبات الأساسية التالية:
- المعرفة الأساسية ببرمجة جافا.
- تم تثبيت JDK (Java Development Kit) على جهازك.
- مكتبة Aspose.Slides لجافا. يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/java/).

## استيراد الحزم
للبدء، عليك استيراد فئات Aspose.Slides اللازمة إلى ملف Java. إليك كيفية القيام بذلك:
```java
import com.aspose.slides.*;
```
## الخطوة 1: تهيئة العرض التقديمي والشريحة
أولاً، قم بإنشاء عرض تقديمي جديد في PowerPoint وقم بتنشيط الشريحة الأولى.
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
try {
    // احصل على الشريحة الأولى من العرض التقديمي
    ISlide slide = presentation.getSlides().get_Item(0);
```
## الخطوة 2: إضافة الشكل التلقائي (المستطيل)
بعد ذلك، قم بإضافة شكل تلقائي من نوع المستطيل إلى الشريحة.
```java
    // إضافة شكل تلقائي من نوع المستطيل
    IAutoShape aShape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 300, 300);
```
## الخطوة 3: إضافة إطار نصي إلى المستطيل
الآن، أضف إطار نص إلى الشكل التلقائي للمستطيل وقم بتعيين النص الأولي الخاص به.
```java
    // إضافة إطار نصي إلى المستطيل
    aShape.addTextFrame("All these columns are limited to be within a single text container -- " +
            "you can add or delete text and the new or remaining text automatically adjusts " +
            "itself to flow within the container. You cannot have text flow from one container " +
            "to other though -- we told you PowerPoint's column options for text are limited!");
```
## الخطوة 4: تعيين عدد الأعمدة
حدد عدد الأعمدة داخل TextFrame.
```java
    // الحصول على تنسيق النص من TextFrame
    ITextFrameFormat format = aShape.getTextFrame().getTextFrameFormat();
    // تحديد عدد الأعمدة في TextFrame
    format.setColumnCount(3);
```
## الخطوة 5: ضبط تباعد الأعمدة
تعيين المسافة بين الأعمدة في TextFrame.
```java
    // تحديد المسافة بين الأعمدة
    format.setColumnSpacing(10);
```
## الخطوة 6: حفظ العرض التقديمي
وأخيرًا، احفظ العرض التقديمي المعدّل في ملف PowerPoint.
```java
    // حفظ العرض التقديمي الذي تم إنشاؤه
    presentation.save(dataDir + "ColumnCount.pptx", SaveFormat.Pptx);
} finally {
    if (presentation != null) presentation.dispose();
}
```

## خاتمة
باتباع هذه الخطوات، يمكنك بسهولة إضافة أعمدة إلى مربعات النص في عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ Java. تتيح لك هذه الميزة تحسين بنية شرائحك وسهولة قراءتها، مما يجعلها أكثر جاذبية بصريًا واحترافية.
## الأسئلة الشائعة
### هل يمكنني إضافة أكثر من ثلاثة أعمدة إلى مربع النص؟
نعم، يمكنك تحديد أي عدد من الأعمدة برمجيًا باستخدام Aspose.Slides.
### هل Aspose.Slides متوافق مع Java 11؟
نعم، يدعم Aspose.Slides إصدار Java 11 والإصدارات الأحدث.
### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Slides؟
يمكنك الحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).
### هل يتطلب Aspose.Slides تثبيت Microsoft Office؟
لا، لا يتطلب Aspose.Slides تثبيت Microsoft Office على الجهاز.
### أين يمكنني العثور على مزيد من الوثائق حول Aspose.Slides لـ Java؟
الوثائق التفصيلية متاحة [هنا](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}