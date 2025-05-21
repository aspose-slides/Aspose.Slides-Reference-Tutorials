---
"description": "قم بتحويل عروض PowerPoint إلى HTML مع الحفاظ على الخطوط الأصلية باستخدام Aspose.Slides لـ Java."
"linktitle": "تحويل العرض التقديمي إلى HTML مع الحفاظ على الخطوط الأصلية في Java Slides"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "تحويل العرض التقديمي إلى HTML مع الحفاظ على الخطوط الأصلية في Java Slides"
"url": "/ar/java/presentation-conversion/convert-presentation-html-preserve-fonts-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تحويل العرض التقديمي إلى HTML مع الحفاظ على الخطوط الأصلية في Java Slides


## مقدمة لتحويل العرض التقديمي إلى HTML مع الحفاظ على الخطوط الأصلية في شرائح Java

في هذا البرنامج التعليمي، سنستكشف كيفية تحويل عرض تقديمي من PowerPoint (PPTX) إلى HTML مع الحفاظ على الخطوط الأصلية باستخدام Aspose.Slides لجافا. سيضمن هذا أن يكون شكل HTML الناتج مطابقًا تمامًا للعرض التقديمي الأصلي.

## الخطوة 1: إعداد المشروع
قبل أن نتعمق في الكود، دعنا نتأكد من أن لديك الإعداد اللازم:

1. تنزيل Aspose.Slides لـ Java: إذا لم تقم بذلك بالفعل، قم بتنزيل مكتبة Aspose.Slides لـ Java وتضمينها في مشروعك.

2. إنشاء مشروع Java: قم بإعداد مشروع Java في IDE المفضل لديك، وتأكد من وجود مجلد "lib" حيث يمكنك وضع ملف JAR الخاص بـ Aspose.Slides.

3. استيراد الفئات المطلوبة: استيراد الفئات الضرورية في بداية ملف Java الخاص بك:

```java
import com.aspose.slides.EmbedAllFontsHtmlController;
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## الخطوة 2: تحويل العرض التقديمي إلى HTML باستخدام الخطوط الأصلية

الآن، دعنا نقوم بتحويل عرض تقديمي من PowerPoint إلى HTML مع الحفاظ على الخطوط الأصلية:

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";

// تحميل العرض التقديمي
Presentation pres = new Presentation("input.pptx");

try {
    // استبعاد خطوط العرض الافتراضية مثل Calibri و Arial
    String[] fontNameExcludeList = {"Calibri", "Arial"};
    EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
    
    // إنشاء خيارات HTML وتعيين منسق HTML المخصص
    HtmlOptions htmlOptionsEmbed = new HtmlOptions();
    htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
    
    // حفظ العرض التقديمي بصيغة HTML
    pres.save("output.html", SaveFormat.Html, htmlOptionsEmbed);
} finally {
    // التخلص من كائن العرض
    if (pres != null) pres.dispose();
}
```

في مقتطف الكود هذا:

- نقوم بتحميل عرض PowerPoint المدخل باستخدام `Presentation`.

- نقوم بتحديد قائمة الخطوط (`fontNameExcludeList`) التي نريد استبعادها من التضمين في HTML. هذا مفيد لاستبعاد الخطوط الشائعة مثل Calibri وArial لتقليل حجم الملف.

- نحن ننشئ مثيلًا لـ `EmbedAllFontsHtmlController` ومرر قائمة استبعاد الخطوط إليها.

- نحن نخلق `HtmlOptions` وتعيين مُنسيق HTML مخصص باستخدام `HtmlFormatter.createCustomFormatter(embedFontsController)`.

- وأخيرًا، نحفظ العرض التقديمي بصيغة HTML مع الخيارات المحددة.

## كود المصدر الكامل لتحويل العرض التقديمي إلى HTML مع الحفاظ على الخطوط الأصلية في شرائح Java

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

في هذا البرنامج التعليمي، تعلمت كيفية تحويل عرض تقديمي من PowerPoint إلى HTML مع الحفاظ على الخطوط الأصلية باستخدام Aspose.Slides لجافا. يُعد هذا مفيدًا عند الرغبة في الحفاظ على جودة عرضك التقديمي عند مشاركته على الويب.

## الأسئلة الشائعة

### كيف يمكنني تنزيل Aspose.Slides لـ Java؟

يمكنك تنزيل Aspose.Slides لجافا من موقع Aspose الإلكتروني. تفضل بزيارة [هنا](https://downloads.aspose.com/slides/java/) للحصول على الإصدار الأحدث.

### هل يمكنني تخصيص قائمة الخطوط المستبعدة؟

نعم، يمكنك تخصيص `fontNameExcludeList` مصفوفة لتضمين أو استبعاد خطوط معينة حسب متطلباتك.

### هل تعمل هذه الطريقة مع تنسيقات PowerPoint القديمة مثل PPT؟

هذا المثال مُصمم لملفات PPTX. إذا كنت بحاجة إلى تحويل ملفات PPT قديمة، فقد تحتاج إلى إجراء تعديلات على الكود.

### كيف يمكنني تخصيص إخراج HTML بشكل أكبر؟

يمكنك استكشاف `HtmlOptions` فئة لتخصيص جوانب مختلفة من مخرجات HTML، مثل حجم الشريحة وجودة الصورة والمزيد.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}