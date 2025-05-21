---
"description": "تعلّم كيفية تحويل شرائح PowerPoint إلى PDF مع ملاحظات بلغة Java باستخدام Aspose.Slides لـ Java. دليل خطوة بخطوة لمطوري Java. حسّن مشاركة عرضك التقديمي."
"linktitle": "تحويل الشرائح إلى PDF مع الملاحظات في Java Slides"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "تحويل الشرائح إلى PDF مع الملاحظات في Java Slides"
"url": "/ar/java/presentation-conversion/convert-slides-pdf-notes-java-slides/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تحويل الشرائح إلى PDF مع الملاحظات في Java Slides


## مقدمة لتحويل الشرائح إلى PDF مع الملاحظات في Java

في عالم العروض التقديمية الرقمية، تُعد إمكانية تحويل الشرائح إلى ملفات PDF مع الملاحظات ميزةً قيّمة. يمكن لمطوري جافا تحقيق ذلك باستخدام مكتبة Aspose.Slides for Java، التي توفر مجموعةً فعّالة من الأدوات للعمل مع عروض PowerPoint التقديمية برمجيًا. في هذا الدليل المُفصّل، سنستكشف كيفية تحويل الشرائح إلى ملفات PDF مع الملاحظات باستخدام جافا وAspose.Slides for Java.

## المتطلبات الأساسية

قبل أن نتعمق في الكود، تأكد من أن لديك المتطلبات الأساسية التالية:

- تم تثبيت Java Development Kit (JDK) على نظامك.
- مكتبة Aspose.Slides لجافا. يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/java/).

الآن بعد أن أصبح لدينا مخططنا التفصيلي، دعونا ننتقل إلى عملية التنفيذ خطوة بخطوة.
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

## الخطوة 7: الحفظ بتنسيق PDF

```java
auxPresentation.save(dataDir + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## الكود المصدر الكامل لتحويل الشرائح إلى PDF مع الملاحظات في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء كائن عرض تقديمي يمثل ملف عرض تقديمي 
Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
try
{
	Presentation auxPresentation = new Presentation();
	try
	{
		ISlide slide = presentation.getSlides().get_Item(0);
		auxPresentation.getSlides().insertClone(0, slide);
		// ضبط نوع الشريحة وحجمها
		//auxPresentation.getSlideSize().setSize(العرض التقديمي.getSlideSize().getSize().getWidth()، العرض التقديمي.getSlideSize().getSize().getHeight()،SlideSizeScaleType.EnsureFit)؛
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

في هذا البرنامج التعليمي، تعلمنا كيفية تحويل الشرائح إلى ملفات PDF مع ملاحظات بلغة جافا باستخدام Aspose.Slides. غطينا إعداد المشروع، وتحميل العرض التقديمي، وإنشاء عرض تقديمي جديد، ونسخ الشرائح، وتعديل حجمها، وتكوين خيارات PDF، وأخيرًا، حفظ العرض التقديمي كملف PDF مع ملاحظات.

## الأسئلة الشائعة

### كيف أقوم بتثبيت Aspose.Slides لـ Java؟

لتثبيت Aspose.Slides لـ Java، اتبع الخطوات التالية:
1. تنزيل المكتبة من [هنا](https://releases.aspose.com/slides/java/).
2. أضف ملف JAR إلى مسار فئة مشروع Java الخاص بك.

### هل يمكنني تخصيص موضع الملاحظات في ملف PDF الناتج؟

نعم، يمكنك تخصيص موضع الملاحظات عن طريق تعديل `NotesPositions` في خيارات PDF. في هذا البرنامج التعليمي، قمنا بتعيينه على `BottomFull`ولكن يمكنك استكشاف خيارات أخرى أيضًا.

### هل هناك أي متطلبات ترخيص لاستخدام Aspose.Slides لـ Java؟

نعم، Aspose.Slides for Java هي مكتبة تجارية، وقد تحتاج إلى ترخيص لاستخدامها في بيئة الإنتاج. تفضل بزيارة موقع Aspose الإلكتروني للاطلاع على تفاصيل الترخيص.

### هل يمكنني تحويل شرائح متعددة في وقت واحد؟

بالتأكيد! يمكنك تكرار عرض شرائحك التقديمية ونسخها إلى العرض التقديمي الجديد، مما يتيح لك تحويل عدة شرائح إلى ملف PDF مع ملاحظات دفعةً واحدة.

### أين يمكنني العثور على مزيد من الوثائق الخاصة بـ Aspose.Slides لـ Java؟

يمكنك العثور على وثائق مفصلة لـ Aspose.Slides for Java على الموقع: [مرجع واجهة برمجة تطبيقات Aspose.Slides لـ Java](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}