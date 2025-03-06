---
title: التحويل إلى PDF باستخدام الشرائح المخفية في شرائح Java
linktitle: التحويل إلى PDF باستخدام الشرائح المخفية في شرائح Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية تحويل عروض PowerPoint التقديمية إلى PDF باستخدام الشرائح المخفية باستخدام Aspose.Slides for Java. اتبع دليلنا خطوة بخطوة مع الكود المصدري لإنشاء ملفات PDF بسلاسة.
weight: 27
url: /ar/java/presentation-conversion/convert-pdf-hidden-slides-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# التحويل إلى PDF باستخدام الشرائح المخفية في شرائح Java


## مقدمة لتحويل عرض PowerPoint التقديمي إلى PDF باستخدام الشرائح المخفية باستخدام Aspose.Slides لـ Java

في هذا الدليل التفصيلي، ستتعلم كيفية تحويل عرض PowerPoint التقديمي إلى PDF مع الاحتفاظ بالشرائح المخفية باستخدام Aspose.Slides for Java. الشرائح المخفية هي تلك التي لا يتم عرضها أثناء العرض التقديمي العادي ولكن يمكن تضمينها في مخرجات PDF. سنزودك بالكود المصدري والتعليمات التفصيلية لتحقيق هذه المهمة.

## المتطلبات الأساسية

قبل البدء، تأكد من توفر المتطلبات الأساسية التالية:

1.  Aspose.Slides for Java Library: تأكد من إعداد مكتبة Aspose.Slides for Java في مشروع Java الخاص بك. يمكنك تنزيله من[Aspose.Slides لتوثيق جافا](https://reference.aspose.com/slides/java/).

2. بيئة تطوير Java: يجب أن تكون لديك بيئة تطوير Java مثبتة على نظامك.

## الخطوة 1: استيراد Aspose.Slides إلى Java

أولاً، تحتاج إلى استيراد مكتبة Aspose.Slides إلى مشروع Java الخاص بك. تأكد من إضافة المكتبة إلى مسار إنشاء مشروعك.

```java
import com.aspose.slides.*;
```

## الخطوة 2: قم بتحميل عرض PowerPoint التقديمي

 ستبدأ بتحميل عرض PowerPoint التقديمي الذي تريد تحويله إلى PDF. يستبدل`"Your Document Directory"` و`"HiddingSlides.pptx"` مع مسار الملف المناسب.

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
```

## الخطوة 3: تكوين خيارات PDF

قم بتكوين خيارات PDF لتضمين الشرائح المخفية في مخرجات PDF. يمكنك القيام بذلك عن طريق تعيين`setShowHiddenSlides` ملكية`PdfOptions` الفئة الى`true`.

```java
// إنشاء مثيل لفئة PdfOptions
PdfOptions pdfOptions = new PdfOptions();
// حدد أن المستند الذي تم إنشاؤه يجب أن يتضمن شرائح مخفية
pdfOptions.setShowHiddenSlides(true);
```

## الخطوة 4: احفظ العرض التقديمي بصيغة PDF

 الآن، احفظ العرض التقديمي في ملف PDF بالخيارات المحددة. يستبدل`"PDFWithHiddenSlides_out.pdf"` مع اسم ملف الإخراج المطلوب.

```java
// احفظ العرض التقديمي بصيغة PDF مع الخيارات المحددة
presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## الخطوة 5: تنظيف الموارد

تأكد من تحرير الموارد التي يستخدمها العرض التقديمي عند الانتهاء منه.

```java
finally
{
    if (presentation != null) presentation.dispose();
}
```

## أكمل كود المصدر للتحويل إلى PDF باستخدام الشرائح المخفية في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
try
{
	// إنشاء مثيل لفئة PdfOptions
	PdfOptions pdfOptions = new PdfOptions();
	// حدد أن المستند الذي تم إنشاؤه يجب أن يتضمن شرائح مخفية
	pdfOptions.setShowHiddenSlides(true);
	// احفظ العرض التقديمي بصيغة PDF مع الخيارات المحددة
	presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## خاتمة

في هذا الدليل الشامل، تعلمت كيفية تحويل عرض PowerPoint التقديمي إلى PDF مع الحفاظ على الشرائح المخفية باستخدام Aspose.Slides لـ Java. لقد قدمنا لك برنامجًا تعليميًا خطوة بخطوة بالإضافة إلى كود المصدر الضروري لتحقيق هذه المهمة بسلاسة.

## الأسئلة الشائعة

### كيف يمكنني إخفاء الشرائح في عرض PowerPoint التقديمي؟

لإخفاء شريحة في عرض تقديمي لـ PowerPoint، اتبع الخطوات التالية:
1. حدد الشريحة التي تريد إخفاءها في طريقة العرض "فارز الشرائح".
2. انقر بزر الماوس الأيمن على الشريحة المحددة.
3. اختر "إخفاء الشريحة" من قائمة السياق.

### هل يمكنني إظهار الشرائح المخفية برمجيًا في Aspose.Slides لـ Java؟

 نعم، يمكنك إظهار الشرائح المخفية برمجيًا في Aspose.Slides لـ Java عن طريق تعيين`Hidden` ملكية`Slide` الفئة الى`false`. هنا مثال:

```java
Slide slide = presentation.getSlides().get_Item(slideIndex); // استبدل SlideIndex بفهرس الشريحة المخفية
slide.setHidden(false);
```

### كيف يمكنني تنزيل Aspose.Slides لنظام Java؟

 يمكنك تنزيل Aspose.Slides for Java من موقع Aspose. قم بزيارة[صفحة تنزيل Aspose.Slides لـ Java](https://releases.aspose.com/slides/java/) للحصول على أحدث إصدار.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
