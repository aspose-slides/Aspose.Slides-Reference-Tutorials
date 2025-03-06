---
title: أضف عمودًا في مربعات النص باستخدام Aspose.Slides لـ Java
linktitle: أضف عمودًا في مربعات النص باستخدام Aspose.Slides لـ Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية إضافة أعمدة إلى مربعات النص في PowerPoint باستخدام Aspose.Slides لـ Java. قم بتحسين عروضك التقديمية باستخدام هذا الدليل المفصّل خطوة بخطوة.
weight: 10
url: /ar/java/java-powerpoint-text-box-manipulation/add-column-in-text-boxes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## مقدمة
في هذا البرنامج التعليمي، سوف نستكشف كيفية تحسين مربعات النص عن طريق إضافة أعمدة باستخدام Aspose.Slides for Java. Aspose.Slides هي مكتبة Java قوية تسمح للمطورين بإنشاء عروض PowerPoint التقديمية ومعالجتها وتحويلها برمجياً دون الحاجة إلى Microsoft Office. يمكن أن تؤدي إضافة أعمدة إلى مربعات النص إلى تحسين إمكانية قراءة المحتوى وتنظيمه داخل الشرائح بشكل كبير، مما يجعل عروضك التقديمية أكثر جاذبية واحترافية.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
- المعرفة الأساسية ببرمجة جافا.
- JDK (Java Development Kit) مثبت على جهازك.
-  Aspose.Slides لمكتبة جافا. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/java/).

## حزم الاستيراد
للبدء، تحتاج إلى استيراد فئات Aspose.Slides الضرورية إلى ملف Java الخاص بك. وإليك كيف يمكنك القيام بذلك:
```java
import com.aspose.slides.*;
```
## الخطوة 1: تهيئة العرض التقديمي والشريحة
أولاً، قم بإنشاء عرض تقديمي جديد لبرنامج PowerPoint وقم بتهيئة الشريحة الأولى.
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
try {
    // احصل على الشريحة الأولى من العرض التقديمي
    ISlide slide = presentation.getSlides().get_Item(0);
```
## الخطوة 2: إضافة شكل تلقائي (مستطيل)
بعد ذلك، قم بإضافة شكل تلقائي من النوع المستطيل إلى الشريحة.
```java
    // إضافة شكل تلقائي لنوع المستطيل
    IAutoShape aShape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 300, 300);
```
## الخطوة 3: إضافة TextFrame إلى المستطيل
الآن، قم بإضافة TextFrame إلى الشكل التلقائي المستطيل وقم بتعيين النص الأولي الخاص به.
```java
    // أضف TextFrame إلى المستطيل
    aShape.addTextFrame("All these columns are limited to be within a single text container -- " +
            "you can add or delete text and the new or remaining text automatically adjusts " +
            "itself to flow within the container. You cannot have text flow from one container " +
            "to other though -- we told you PowerPoint's column options for text are limited!");
```
## الخطوة 4: تعيين عدد الأعمدة
حدد عدد الأعمدة داخل TextFrame.
```java
    // الحصول على تنسيق نص TextFrame
    ITextFrameFormat format = aShape.getTextFrame().getTextFrameFormat();
    // تحديد عدد الأعمدة في TextFrame
    format.setColumnCount(3);
```
## الخطوة 5: ضبط تباعد الأعمدة
ضبط التباعد بين الأعمدة في TextFrame.
```java
    // تحديد التباعد بين الأعمدة
    format.setColumnSpacing(10);
```
## الخطوة 6: احفظ العرض التقديمي
وأخيرًا، احفظ العرض التقديمي المعدل في ملف PowerPoint.
```java
    // حفظ العرض التقديمي الذي تم إنشاؤه
    presentation.save(dataDir + "ColumnCount.pptx", SaveFormat.Pptx);
} finally {
    if (presentation != null) presentation.dispose();
}
```

## خاتمة
باتباع هذه الخطوات، يمكنك بسهولة إضافة أعمدة إلى مربعات النص في عروض PowerPoint التقديمية باستخدام Aspose.Slides for Java. تتيح لك هذه الميزة تحسين بنية الشرائح وسهولة قراءتها، مما يجعلها أكثر جاذبية واحترافية من الناحية البصرية.
## الأسئلة الشائعة
### هل يمكنني إضافة أكثر من ثلاثة أعمدة إلى مربع النص؟
نعم، يمكنك تحديد أي عدد من الأعمدة برمجياً باستخدام Aspose.Slides.
### هل Aspose.Slides متوافق مع Java 11؟
نعم، يدعم Aspose.Slides الإصدار 11 من Java والإصدارات الأحدث.
### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Slides؟
 يمكنك الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).
### هل يتطلب Aspose.Slides تثبيت Microsoft Office؟
لا، لا يتطلب Aspose.Slides تثبيت Microsoft Office على الجهاز.
### أين يمكنني العثور على مزيد من الوثائق حول Aspose.Slides لـ Java؟
 الوثائق التفصيلية متاحة[هنا](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
