---
title: تحويل الشرائح إلى PDF مع الملاحظات في شرائح جافا
linktitle: تحويل الشرائح إلى PDF مع الملاحظات في شرائح جافا
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية تحويل شرائح PowerPoint إلى PDF مع الملاحظات في Java باستخدام Aspose.Slides for Java. دليل خطوة بخطوة لمطوري جافا. تعزيز مشاركة العرض التقديمي الخاص بك.
weight: 19
url: /ar/java/presentation-conversion/convert-slides-pdf-notes-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## مقدمة لتحويل الشرائح إلى PDF مع الملاحظات في Java

في عالم العروض التقديمية الرقمية، تعد القدرة على تحويل الشرائح إلى PDF مع الملاحظات المصاحبة ميزة قيمة. يمكن لمطوري Java تحقيق ذلك باستخدام مكتبة Aspose.Slides for Java، والتي توفر مجموعة قوية من الأدوات للعمل مع عروض PowerPoint التقديمية برمجيًا. في هذا الدليل التفصيلي، سنستكشف كيفية تحويل الشرائح إلى PDF مع الملاحظات باستخدام Java وAspose.Slides for Java.

## المتطلبات الأساسية

قبل أن نتعمق في الكود، تأكد من توفر المتطلبات الأساسية التالية:

- تم تثبيت Java Development Kit (JDK) على نظامك.
-  Aspose.Slides لمكتبة جافا. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/java/).

الآن بعد أن حصلنا على الخطوط العريضة، دعونا نتعمق في التنفيذ خطوة بخطوة.
## الخطوة 1: إعداد المشروع

أولاً، قم بإنشاء مشروع Java وأضف مكتبة Aspose.Slides for Java إلى تبعيات مشروعك.

## الخطوة 2: تحميل العرض التقديمي

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
```

## الخطوة 3: إنشاء عرض تقديمي جديد

```java
Presentation auxPresentation = new Presentation();
```

## الخطوة 4: نسخ الشرائح

```java
ISlide slide = presentation.getSlides().get_Item(0);
auxPresentation.getSlides().insertClone(0, slide);
```

## الخطوة 5: ضبط حجم الشريحة

```java
auxPresentation.getSlideSize().setSize(612F, 792F, SlideSizeScaleType.EnsureFit);
```

## الخطوة 6: تكوين خيارات PDF

```java
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
options.setNotesPosition(NotesPositions.BottomFull);
```

## الخطوة 7: الحفظ بصيغة PDF

```java
auxPresentation.save(dataDir + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## كود المصدر الكامل لتحويل الشرائح إلى PDF مع الملاحظات في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء مثيل لكائن العرض التقديمي الذي يمثل ملف العرض التقديمي
Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
try
{
	Presentation auxPresentation = new Presentation();
	try
	{
		ISlide slide = presentation.getSlides().get_Item(0);
		auxPresentation.getSlides().insertClone(0, slide);
		// تحديد نوع الشريحة وحجمها
		//auxPresentation.getSlideSize().setSize(presentation.getSlideSize().getSize().getWidth(),presentation.getSlideSize().getSize().getHeight(),SlideSizeScaleType.EnsureFit);
		auxPresentation.getSlideSize().setSize(612F, 792F, SlideSizeScaleType.EnsureFit);
		PdfOptions pdfOptions = new PdfOptions();
		INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
		options.setNotesPosition(NotesPositions.BottomFull);
		auxPresentation.save(dataDir + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
	}
	finally
	{
		if (auxPresentation != null) auxPresentation.dispose();
	}
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية تحويل الشرائح إلى PDF مع الملاحظات في Java باستخدام Aspose.Slides for Java. لقد قمنا بتغطية إعداد المشروع، وتحميل العرض التقديمي، وإنشاء عرض تقديمي جديد، ونسخ الشرائح، وضبط حجم الشريحة، وتكوين خيارات PDF، وأخيرًا، حفظ العرض التقديمي كملف PDF مع الملاحظات.

## الأسئلة الشائعة

### كيف أقوم بتثبيت Aspose.Slides لـ Java؟

لتثبيت Aspose.Slides لـ Java، اتبع الخطوات التالية:
1.  تحميل المكتبة من[هنا](https://releases.aspose.com/slides/java/).
2. أضف ملف JAR إلى مسار فئة مشروع Java الخاص بك.

### هل يمكنني تخصيص موضع الملاحظات في ملف PDF الذي تم إنشاؤه؟

 نعم، يمكنك تخصيص موضع الملاحظات عن طريق تعديل`NotesPositions` التعداد في خيارات PDF. في هذا البرنامج التعليمي، قمنا بتعيينه على`BottomFull`، ولكن يمكنك استكشاف خيارات أخرى أيضًا.

### هل هناك أي متطلبات ترخيص لاستخدام Aspose.Slides لـ Java؟

نعم، Aspose.Slides for Java هي مكتبة تجارية، وقد تحتاج إلى الحصول على ترخيص لاستخدامها في الإنتاج. قم بزيارة موقع Aspose للحصول على تفاصيل الترخيص.

### هل يمكنني تحويل شرائح متعددة في وقت واحد؟

بالتأكيد! يمكنك التنقل بين الشرائح في العرض التقديمي الخاص بك واستنساخها في العرض التقديمي الجديد، مما يسمح لك بتحويل شرائح متعددة إلى PDF مع الملاحظات دفعة واحدة.

### أين يمكنني العثور على مزيد من الوثائق الخاصة بـ Aspose.Slides لـ Java؟

 يمكنك العثور على وثائق مفصلة عن Aspose.Slides for Java على الموقع:[Aspose.Slides لمرجع Java API](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
