---
title: تحويل العرض التقديمي بالكامل إلى HTML في شرائح Java
linktitle: تحويل العرض التقديمي بالكامل إلى HTML في شرائح Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية تحويل عروض PowerPoint التقديمية إلى HTML في Java باستخدام Aspose.Slides. دليل خطوة بخطوة مع أمثلة التعليمات البرمجية.
weight: 29
url: /ar/java/presentation-conversion/convert-whole-presentation-html-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## مقدمة لتحويل العرض التقديمي بالكامل إلى HTML في شرائح Java

في العصر الرقمي الحالي، يعد تحويل العروض التقديمية إلى HTML مطلبًا شائعًا، خاصة عندما تريد مشاركة عروضك التقديمية عبر الإنترنت أو تضمينها في موقع ويب. إذا كنت تعمل باستخدام Java Slides وتحتاج إلى تحويل عرض تقديمي كامل إلى HTML، فأنت في المكان الصحيح. في هذا الدليل المفصّل خطوة بخطوة، سنرشدك خلال العملية باستخدام Aspose.Slides for Java API.

## المتطلبات الأساسية

قبل أن نتعمق في عملية التحويل، تأكد من توفر المتطلبات الأساسية التالية:

1. بيئة تطوير Java: تأكد من تثبيت Java على نظامك.
2. Aspose.Slides for Java: قم بتنزيل وإعداد مكتبة Aspose.Slides for Java.
3. عرض تقديمي: ستحتاج إلى عرض تقديمي من PowerPoint تريد تحويله إلى HTML.

الآن بعد أن أصبح لدينا متطلباتنا الأساسية جاهزة، فلنبدأ عملية التحويل.

## الخطوة 1: استيراد المكتبات المطلوبة

في مشروع Java الخاص بك، ابدأ باستيراد المكتبات الضرورية. ستحتاج إلى Aspose.Slides للعمل مع العروض التقديمية.

```java
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.INotesCommentsLayoutingOptions;
import com.aspose.slides.NotesPositions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## الخطوة 2: قم بتحميل العرض التقديمي

بعد ذلك، يجب عليك تحميل عرض PowerPoint التقديمي الذي تريد تحويله إلى HTML. تأكد من تحديد المسار الصحيح لملف العرض التقديمي الخاص بك.

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء مثيل لكائن العرض التقديمي الذي يمثل ملف العرض التقديمي
Presentation presentation = new Presentation(dataDir + "Convert_HTML.pptx");
```

## الخطوة 3: قم بتعيين خيارات تحويل HTML

لتخصيص تحويل HTML، يمكنك تعيين خيارات متنوعة. على سبيل المثال، يمكنك تحديد منسق HTML وموضع الملاحظات والتعليقات في HTML.

```java
HtmlOptions htmlOpt = new HtmlOptions();
htmlOpt.setHtmlFormatter(HtmlFormatter.createDocumentFormatter("", false));
INotesCommentsLayoutingOptions notesOptions = htmlOpt.getNotesCommentsLayouting();
notesOptions.setNotesPosition(NotesPositions.BottomFull);
```

## الخطوة 4: التحويل إلى HTML

حان الوقت الآن لتحويل العرض التقديمي إلى HTML باستخدام الخيارات التي قمنا بتعيينها.

```java
// حفظ العرض التقديمي إلى HTML
presentation.save(dataDir + "ConvertWholePresentationToHTML_out.html", SaveFormat.Html, htmlOpt);
```

## الخطوة 5: التنظيف

وأخيرًا، لا تنس التخلص من كائن العرض التقديمي لتحرير الموارد.

```java
if (presentation != null) presentation.dispose();
```

## كود المصدر الكامل لتحويل العرض التقديمي بالكامل إلى HTML في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء مثيل لكائن العرض التقديمي الذي يمثل ملف العرض التقديمي
Presentation presentation = new Presentation(dataDir + "Convert_HTML.pptx");
try
{
	HtmlOptions htmlOpt = new HtmlOptions();
	htmlOpt.setHtmlFormatter(HtmlFormatter.createDocumentFormatter("", false));
	INotesCommentsLayoutingOptions notesOptions = htmlOpt.getNotesCommentsLayouting();
	notesOptions.setNotesPosition(NotesPositions.BottomFull);
	// حفظ العرض التقديمي إلى HTML
	presentation.save(dataDir + "ConvertWholePresentationToHTML_out.html", SaveFormat.Html, htmlOpt);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## خاتمة

تهانينا! لقد نجحت في تحويل عرض تقديمي كامل إلى HTML في Java Slides باستخدام Aspose.Slides for Java API. يمكن أن يكون هذا مفيدًا بشكل لا يصدق عندما تريد إتاحة الوصول إلى عروضك التقديمية عبر الإنترنت أو دمجها في تطبيقات الويب.

## الأسئلة الشائعة

### هل يمكنني تخصيص مخرجات HTML بشكل أكبر؟

نعم، يمكنك تخصيص مخرجات HTML عن طريق ضبط خيارات تحويل HTML في الكود. يمكنك تعديل التنسيق والتخطيط والمزيد بما يناسب احتياجاتك.

### هل Aspose.Slides for Java مكتبة مدفوعة؟

نعم، Aspose.Slides for Java هي مكتبة تجارية، ولكنها تقدم نسخة تجريبية مجانية. يمكنك استكشاف ميزاته ووظائفه قبل أن تقرر شراء ترخيص.

### هل هناك أي تنسيقات إخراج أخرى مدعومة؟

نعم، يدعم Aspose.Slides for Java تنسيقات الإخراج المختلفة، بما في ذلك PDF وPPTX والصور. يمكنك اختيار التنسيق الذي يناسب متطلباتك.

### هل يمكنني تحويل شرائح معينة بدلاً من العرض التقديمي بأكمله؟

نعم، يمكنك تحويل شرائح معينة عن طريق تحديدها في الكود قبل حفظ العرض التقديمي. يمنحك هذا التحكم في الشرائح التي سيتم تحويلها إلى HTML.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
