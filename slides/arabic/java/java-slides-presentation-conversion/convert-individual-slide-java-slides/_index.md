---
"description": "تعرف على كيفية تحويل شرائح PowerPoint الفردية إلى HTML خطوة بخطوة باستخدام أمثلة التعليمات البرمجية باستخدام Aspose.Slides لـ Java."
"linktitle": "تحويل شريحة فردية في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "تحويل شريحة فردية في شرائح Java"
"url": "/ar/java/presentation-conversion/convert-individual-slide-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تحويل شريحة فردية في شرائح Java


## مقدمة لتحويل الشريحة الفردية في شرائح Java

في هذا البرنامج التعليمي، سنشرح عملية تحويل شرائح فردية من عرض تقديمي في PowerPoint إلى HTML باستخدام Aspose.Slides لجافا. سيوفر لك هذا الدليل خطوة بخطوة الكود المصدري والشروحات اللازمة لإنجاز هذه المهمة.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من أن لديك ما يلي:

- تم تثبيت Aspose.Slides لمكتبة Java.
- ملف عرض تقديمي PowerPoint (`Individual-Slide.pptx`) التي تريد تحويلها.
- تم إعداد بيئة تطوير Java.

## الخطوة 1: إعداد المشروع

1. قم بإنشاء مشروع Java في بيئة التطوير المفضلة لديك.
2. أضف مكتبة Aspose.Slides for Java إلى مشروعك.

## الخطوة 2: استيراد الفئات الضرورية

في فئة Java الخاصة بك، قم باستيراد الفئات المطلوبة وإعداد التكوين الأولي.

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

أنشئ طريقةً لتحويل الشرائح الفردية. تأكد من استبدال `"Your Document Directory"` مع المسار الفعلي إلى دليل المستند الخاص بك.

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

إنشاء `CustomFormattingController` فئة للتعامل مع التنسيق المخصص أثناء التحويل.

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

وأخيرا، اتصل بـ `convertIndividualSlides` طريقة لتنفيذ عملية التحويل.

```java
public static void main(String[] args) {
    convertIndividualSlides();
}
```

## كود المصدر الكامل لتحويل شريحة فردية إلى شرائح Java

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

لقد نجحت في تحويل شرائح فردية من عرض تقديمي في PowerPoint إلى HTML باستخدام Aspose.Slides لجافا. زودك هذا البرنامج التعليمي بالرمز والخطوات اللازمة لتحقيق هذه المهمة. لا تتردد في تخصيص الإخراج والتنسيق حسب احتياجاتك الخاصة.

## الأسئلة الشائعة

### كيف يمكنني تخصيص إخراج HTML بشكل أكبر؟

يمكنك تخصيص إخراج HTML عن طريق تعديل `CustomFormattingController` الصف. اضبط `writeSlideStart` و `writeSlideEnd` طرق لتغيير هيكل وتنسيق الشريحة HTML.

### هل يمكنني تحويل عروض PowerPoint متعددة دفعة واحدة؟

نعم، يمكنك تعديل الكود للتنقل عبر ملفات العرض التقديمي المتعددة وتحويلها بشكل فردي عن طريق استدعاء `convertIndividualSlides` طريقة لكل عرض.

### كيف يمكنني التعامل مع التنسيق الإضافي للأشكال والنصوص داخل الشرائح؟

يمكنك تمديد `CustomFormattingController` فئة للتعامل مع التنسيق الخاص بالشكل من خلال تنفيذ `writeShapeStart` و `writeShapeEnd` الأساليب وتطبيق منطق التنسيق المخصص داخلها.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}