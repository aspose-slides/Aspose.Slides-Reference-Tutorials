---
title: تحويل شريحة فردية في شرائح جافا
linktitle: تحويل شريحة فردية في شرائح جافا
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية تحويل شرائح PowerPoint الفردية إلى HTML خطوة بخطوة باستخدام أمثلة التعليمات البرمجية باستخدام Aspose.Slides for Java.
weight: 12
url: /ar/java/presentation-conversion/convert-individual-slide-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## مقدمة لتحويل الشرائح الفردية في شرائح جافا

في هذا البرنامج التعليمي، سنتعرف على عملية تحويل الشرائح الفردية من عرض PowerPoint التقديمي إلى HTML باستخدام Aspose.Slides for Java. سيزودك هذا الدليل المفصّل خطوة بخطوة بكود المصدر وشروحات لمساعدتك في تحقيق هذه المهمة.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من أن لديك ما يلي:

- تم تثبيت Aspose.Slides لمكتبة Java.
- ملف عرض تقديمي لـ PowerPoint ‏(`Individual-Slide.pptx`) الذي تريد تحويله.
- إعداد بيئة تطوير جافا.

## الخطوة 1: إعداد المشروع

1. قم بإنشاء مشروع Java في بيئة التطوير المفضلة لديك.
2. أضف مكتبة Aspose.Slides for Java إلى مشروعك.

## الخطوة 2: استيراد الفئات الضرورية

في فئة Java الخاصة بك، قم باستيراد الفئات المطلوبة وقم بإعداد التكوين الأولي.

```java
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.INotesCommentsLayoutingOptions;
import com.aspose.slides.NotesPositions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.IHtmlFormattingController;
import com.aspose.slides.IHtmlGenerator;
import com.aspose.slides.ISlide;
import com.aspose.slides.IShape;
```

## الخطوة 3: تحديد طريقة التحويل الرئيسية

 إنشاء طريقة لإجراء تحويل الشرائح الفردية. تأكد من استبدال`"Your Document Directory"` بالمسار الفعلي إلى دليل المستندات الخاص بك.

```java
public static void convertIndividualSlides() {
    String dataDir = "Your Document Directory";
    Presentation presentation = new Presentation(dataDir + "Individual-Slide.pptx");
    try {
        HtmlOptions htmlOptions = new HtmlOptions();
        htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(new CustomFormattingController()));
        INotesCommentsLayoutingOptions notesOptions = htmlOptions.getNotesCommentsLayouting();
        notesOptions.setNotesPosition(NotesPositions.BottomFull);
        
        // حفظ الملف
        for (int i = 0; i < presentation.getSlides().size(); i++) {
            presentation.save(dataDir + "Individual-Slide" + (i + 1) + "_out.html", new int[]{i + 1}, SaveFormat.Html, htmlOptions);
        }
    } finally {
        if (presentation != null) presentation.dispose();
    }
}
```

## الخطوة 4: تنفيذ CustomFormattingController

 إنشاء`CustomFormattingController` فئة للتعامل مع التنسيق المخصص أثناء التحويل.

```java
public static class CustomFormattingController implements IHtmlFormattingController {
    public void writeDocumentStart(IHtmlGenerator generator, IPresentation presentation) {
    }
    
    public void writeDocumentEnd(IHtmlGenerator generator, IPresentation presentation) {
    }
    
    public void writeSlideStart(IHtmlGenerator generator, ISlide slide) {
        generator.addHtml(String.format(SlideHeader, generator.getSlideIndex() + 1));
    }
    
    public void writeSlideEnd(IHtmlGenerator generator, ISlide slide) {
        generator.addHtml(SlideFooter);
    }
    
    public void writeShapeStart(IHtmlGenerator generator, IShape shape) {
    }
    
    public void writeShapeEnd(IHtmlGenerator generator, IShape shape) {
    }
    
    private static String SlideHeader = "<div class=\"slide\" name=\"slide\" id=\"slide{0}\">";
    private static String SlideFooter = "</div>";
}
```

## الخطوة 5: تنفيذ التحويل

 وأخيرا اتصل ب`convertIndividualSlides` طريقة تنفيذ عملية التحويل.

```java
public static void main(String[] args) {
    convertIndividualSlides();
}
```

## كود المصدر الكامل لتحويل الشرائح الفردية في شرائح جافا

```java
	String dataDir = "Your Document Directory";
	Presentation presentation = new Presentation(dataDir + "Individual-Slide.pptx");
	try
	{
		HtmlOptions htmlOptions = new HtmlOptions();
		htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(new CustomFormattingController()));
		INotesCommentsLayoutingOptions notesOptions = htmlOptions.getNotesCommentsLayouting();
		notesOptions.setNotesPosition(NotesPositions.BottomFull);
		// حفظ الملف
		for (int i = 0; i < presentation.getSlides().size(); i++)
			presentation.save(dataDir + "Individual Slide" + i + 1 + "_out.html", new int[]{i + 1}, SaveFormat.Html, htmlOptions);
	}
	finally
	{
		if (presentation != null) presentation.dispose();
	}
}
public static class CustomFormattingController implements IHtmlFormattingController
{
	public void writeDocumentStart(IHtmlGenerator generator, IPresentation presentation)
	{
	}
	public void writeDocumentEnd(IHtmlGenerator generator, IPresentation presentation)
	{
	}
	public void writeSlideStart(IHtmlGenerator generator, ISlide slide)
	{
		generator.addHtml(String.format(SlideHeader, generator.getSlideIndex() + 1));
	}
	public void writeSlideEnd(IHtmlGenerator generator, ISlide slide)
	{
		generator.addHtml(SlideFooter);
	}
	public void writeShapeStart(IHtmlGenerator generator, IShape shape)
	{
	}
	public void writeShapeEnd(IHtmlGenerator generator, IShape shape)
	{
	}
	private static String SlideHeader = "<div class=\"slide\" name=\"slide\" id=\"slide{0}\">";
	private static String SlideFooter = "</div>";
```

## خاتمة

لقد نجحت في تحويل شرائح فردية من عرض تقديمي لـ PowerPoint إلى HTML باستخدام Aspose.Slides لـ Java. زودك هذا البرنامج التعليمي بالكود والخطوات اللازمة لتحقيق هذه المهمة. لا تتردد في تخصيص الإخراج والتنسيق حسب الحاجة لمتطلباتك المحددة.

## الأسئلة الشائعة

### كيف يمكنني تخصيص مخرجات HTML بشكل أكبر؟

 يمكنك تخصيص مخرجات HTML عن طريق تعديل ملف`CustomFormattingController` فصل. أضبط ال`writeSlideStart` و`writeSlideEnd` طرق لتغيير بنية HTML للشرائح وتصميمها.

### هل يمكنني تحويل عروض PowerPoint التقديمية المتعددة دفعة واحدة؟

 نعم، يمكنك تعديل التعليمات البرمجية للتكرار عبر ملفات العروض التقديمية المتعددة وتحويلها بشكل فردي عن طريق استدعاء ملف`convertIndividualSlides` طريقة لكل عرض تقديمي.

### كيف أتعامل مع التنسيق الإضافي للأشكال والنص داخل الشرائح؟

 يمكنك تمديد`CustomFormattingController` فئة للتعامل مع التنسيق الخاص بالشكل من خلال تنفيذ`writeShapeStart` و`writeShapeEnd` الأساليب وتطبيق منطق التنسيق المخصص داخلها.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
