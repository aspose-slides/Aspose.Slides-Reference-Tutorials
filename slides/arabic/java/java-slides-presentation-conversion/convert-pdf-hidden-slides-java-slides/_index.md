---
"description": "تعرّف على كيفية تحويل عروض PowerPoint التقديمية إلى PDF مع شرائح مخفية باستخدام Aspose.Slides لجافا. اتبع دليلنا خطوة بخطوة مع الكود المصدري لإنشاء ملفات PDF بسلاسة."
"linktitle": "تحويل إلى PDF باستخدام الشرائح المخفية في Java Slides"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "تحويل إلى PDF باستخدام الشرائح المخفية في Java Slides"
"url": "/ar/java/presentation-conversion/convert-pdf-hidden-slides-java-slides/"
"weight": 27
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تحويل إلى PDF باستخدام الشرائح المخفية في Java Slides


## مقدمة لتحويل عرض PowerPoint إلى PDF مع شرائح مخفية باستخدام Aspose.Slides لـ Java

في هذا الدليل المفصل، ستتعلم كيفية تحويل عرض تقديمي من PowerPoint إلى PDF مع الحفاظ على الشرائح المخفية باستخدام Aspose.Slides لجافا. الشرائح المخفية هي تلك التي لا تُعرض في العرض التقديمي العادي، ولكن يمكن تضمينها في ملف PDF. سنزودك بالشفرة المصدرية والتعليمات المفصلة لتحقيق هذه المهمة.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من توفر المتطلبات الأساسية التالية:

1. مكتبة Aspose.Slides لجافا: تأكد من تثبيت مكتبة Aspose.Slides لجافا في مشروع جافا. يمكنك تنزيلها من [توثيق Aspose.Slides لـ Java](https://reference.aspose.com/slides/java/).

2. بيئة تطوير Java: يجب أن يكون لديك بيئة تطوير Java مثبتة على نظامك.

## الخطوة 1: استيراد Aspose.Slides لـ Java

أولاً، عليك استيراد مكتبة Aspose.Slides إلى مشروع جافا. تأكد من إضافة المكتبة إلى مسار بناء مشروعك.

```java
import com.aspose.slides.*;
```

## الخطوة 2: تحميل عرض PowerPoint

ستبدأ بتحميل عرض PowerPoint الذي تريد تحويله إلى PDF. استبدل `"Your Document Directory"` و `"HiddingSlides.pptx"` مع مسار الملف المناسب.

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
```

## الخطوة 3: تكوين خيارات PDF

قم بضبط خيارات PDF لتضمين الشرائح المخفية في مخرجات PDF. يمكنك القيام بذلك عن طريق ضبط `setShowHiddenSlides` ممتلكات `PdfOptions` الصف إلى `true`.

```java
// إنشاء مثيل لفئة PdfOptions
PdfOptions pdfOptions = new PdfOptions();
// حدد أن المستند المُنشأ يجب أن يتضمن شرائح مخفية
pdfOptions.setShowHiddenSlides(true);
```

## الخطوة 4: حفظ العرض التقديمي بصيغة PDF

الآن، احفظ العرض التقديمي في ملف PDF بالخيارات المحددة. استبدل `"PDFWithHiddenSlides_out.pdf"` مع اسم ملف الإخراج المطلوب.

```java
// حفظ العرض التقديمي بصيغة PDF باستخدام الخيارات المحددة
presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## الخطوة 5: تنظيف الموارد

تأكد من إصدار الموارد التي يستخدمها العرض التقديمي عند الانتهاء منه.

```java
finally
{
    if (presentation != null) presentation.dispose();
}
```

## كود المصدر الكامل لتحويل ملفات PDF إلى شرائح مخفية في Java Slides

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
try
{
	// إنشاء مثيل لفئة PdfOptions
	PdfOptions pdfOptions = new PdfOptions();
	// حدد أن المستند المُنشأ يجب أن يتضمن شرائح مخفية
	pdfOptions.setShowHiddenSlides(true);
	// حفظ العرض التقديمي بصيغة PDF باستخدام الخيارات المحددة
	presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## خاتمة

في هذا الدليل الشامل، ستتعلم كيفية تحويل عرض تقديمي من PowerPoint إلى PDF مع الحفاظ على الشرائح المخفية باستخدام Aspose.Slides لجافا. لقد قدمنا لك شرحًا تفصيليًا خطوة بخطوة مع الكود المصدري اللازم لإنجاز هذه المهمة بسلاسة.

## الأسئلة الشائعة

### كيف يمكنني إخفاء الشرائح في عرض تقديمي في PowerPoint؟

لإخفاء شريحة في عرض تقديمي في PowerPoint، اتبع الخطوات التالية:
1. قم بتحديد الشريحة التي تريد إخفاءها في عرض "فرز الشرائح".
2. انقر بزر الماوس الأيمن على الشريحة المحددة.
3. اختر "إخفاء الشريحة" من قائمة السياق.

### هل يمكنني إظهار الشرائح المخفية برمجيًا في Aspose.Slides لـ Java؟

نعم، يمكنك إظهار الشرائح المخفية برمجيًا في Aspose.Slides لـ Java عن طريق ضبط `Hidden` ممتلكات `Slide` الصف إلى `false`. وإليك مثال:

```java
Slide slide = presentation.getSlides().get_Item(slideIndex); // استبدال slideIndex بفهرس الشريحة المخفية
slide.setHidden(false);
```

### كيف يمكنني تنزيل Aspose.Slides لـ Java؟

يمكنك تنزيل Aspose.Slides لجافا من موقع Aspose الإلكتروني. تفضل بزيارة [صفحة تنزيل Aspose.Slides لـ Java](https://releases.aspose.com/slides/java/) للحصول على الإصدار الأحدث.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}