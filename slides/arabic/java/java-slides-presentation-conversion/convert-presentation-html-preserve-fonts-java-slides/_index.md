---
title: تحويل العرض التقديمي إلى HTML مع الحفاظ على الخطوط الأصلية في شرائح Java
linktitle: تحويل العرض التقديمي إلى HTML مع الحفاظ على الخطوط الأصلية في شرائح Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: قم بتحويل عروض PowerPoint التقديمية إلى HTML مع الحفاظ على الخطوط الأصلية باستخدام Aspose.Slides لـ Java.
weight: 14
url: /ar/java/presentation-conversion/convert-presentation-html-preserve-fonts-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## مقدمة لتحويل العرض التقديمي إلى HTML مع الحفاظ على الخطوط الأصلية في شرائح Java

في هذا البرنامج التعليمي، سوف نستكشف كيفية تحويل عرض PowerPoint التقديمي (PPTX) إلى HTML مع الحفاظ على الخطوط الأصلية باستخدام Aspose.Slides لـ Java. سيضمن هذا أن HTML الناتج يشبه إلى حد كبير مظهر العرض التقديمي الأصلي.

## الخطوة 1: إعداد المشروع
قبل أن نتعمق في الكود، دعنا نتأكد من أن لديك الإعداد اللازم:

1. تنزيل Aspose.Slides for Java: إذا لم تكن قد قمت بذلك بالفعل، فقم بتنزيل مكتبة Aspose.Slides for Java وتضمينها في مشروعك.

2. إنشاء مشروع Java: قم بإعداد مشروع Java في IDE المفضل لديك، وتأكد من أن لديك مجلد "lib" حيث يمكنك وضع ملف Aspose.Slides JAR.

3. استيراد الفئات المطلوبة: قم باستيراد الفئات الضرورية في بداية ملف Java الخاص بك:

```java
import com.aspose.slides.EmbedAllFontsHtmlController;
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## الخطوة 2: تحويل العرض التقديمي إلى HTML باستخدام الخطوط الأصلية

الآن، لنحول عرض PowerPoint التقديمي إلى HTML مع الحفاظ على الخطوط الأصلية:

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";

// قم بتحميل العرض التقديمي
Presentation pres = new Presentation("input.pptx");

try {
    // استبعاد خطوط العرض الافتراضية مثل Calibri وArial
    String[] fontNameExcludeList = {"Calibri", "Arial"};
    EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
    
    // قم بإنشاء خيارات HTML وقم بتعيين منسق HTML المخصص
    HtmlOptions htmlOptionsEmbed = new HtmlOptions();
    htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
    
    // احفظ العرض التقديمي بتنسيق HTML
    pres.save("output.html", SaveFormat.Html, htmlOptionsEmbed);
} finally {
    // تخلص من كائن العرض التقديمي
    if (pres != null) pres.dispose();
}
```

في مقتطف الشفرة هذا:

-  نقوم بتحميل عرض PowerPoint التقديمي باستخدام`Presentation`.

- نحدد قائمة الخطوط (`fontNameExcludeList`الذي نريد استبعاده من التضمين في HTML. يعد هذا مفيدًا لاستبعاد الخطوط الشائعة مثل Calibri وArial لتقليل حجم الملف.

-  نقوم بإنشاء مثيل لـ`EmbedAllFontsHtmlController` وتمرير قائمة استبعاد الخطوط إليها.

-  نخلق`HtmlOptions` وتعيين منسق HTML مخصص باستخدام`HtmlFormatter.createCustomFormatter(embedFontsController)`.

- وأخيرًا، نقوم بحفظ العرض التقديمي بتنسيق HTML مع الخيارات المحددة.

## أكمل كود المصدر لتحويل العرض التقديمي إلى HTML مع الحفاظ على الخطوط الأصلية في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation("input.pptx");
try
{
	// استبعاد خطوط العرض الافتراضية
	String[] fontNameExcludeList = {"Calibri", "Arial"};
	EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
	HtmlOptions htmlOptionsEmbed = new HtmlOptions();
	htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
	pres.save("input-PFDinDisplayPro-Regular-installed.html", SaveFormat.Html, htmlOptionsEmbed);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## خاتمة

في هذا البرنامج التعليمي، تعلمت كيفية تحويل عرض PowerPoint التقديمي إلى HTML مع الحفاظ على الخطوط الأصلية باستخدام Aspose.Slides لـ Java. يعد هذا مفيدًا عندما تريد الحفاظ على الدقة المرئية لعروضك التقديمية عند مشاركتها على الويب.

## الأسئلة الشائعة

### كيف يمكنني تنزيل Aspose.Slides لنظام Java؟

 يمكنك تنزيل Aspose.Slides for Java من موقع Aspose. يزور[هنا](https://downloads.aspose.com/slides/java/) للحصول على أحدث إصدار.

### هل يمكنني تخصيص قائمة الخطوط المستبعدة؟

 نعم، يمكنك تخصيص`fontNameExcludeList` مجموعة لتضمين أو استبعاد خطوط معينة وفقًا لمتطلباتك.

### هل تعمل هذه الطريقة مع تنسيقات PowerPoint الأقدم مثل PPT؟

تم تصميم مثال التعليمات البرمجية هذا لملفات PPTX. إذا كنت بحاجة إلى تحويل ملفات PPT قديمة، فقد تحتاج إلى إجراء تعديلات على التعليمات البرمجية.

### كيف يمكنني تخصيص مخرجات HTML بشكل أكبر؟

 يمكنك استكشاف`HtmlOptions` فئة لتخصيص الجوانب المختلفة لمخرجات HTML، مثل حجم الشريحة وجودة الصورة والمزيد.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
