---
"description": "حسّن عرض شرائح جافا الخاص بك باستخدام Aspose.Slides. أنشئ عروضًا تقديمية جذابة بإعدادات مخصصة. استكشف الأدلة الإرشادية والأسئلة الشائعة خطوة بخطوة."
"linktitle": "إعداد عرض الشرائح التقديمي في Java Slides"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "إعداد عرض الشرائح التقديمي في Java Slides"
"url": "/ar/java/presentation-properties/presentation-slide-show-setup-in-java-slides/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إعداد عرض الشرائح التقديمي في Java Slides


## مقدمة لإعداد عرض الشرائح التقديمي في Java Slides

في هذا البرنامج التعليمي، سنستكشف كيفية إعداد عرض شرائح تقديمي باستخدام Aspose.Slides لجافا. سنشرح خطوة بخطوة عملية إنشاء عرض تقديمي في PowerPoint وضبط إعدادات عرض الشرائح المختلفة.

## المتطلبات الأساسية

قبل البدء، تأكد من إضافة مكتبة Aspose.Slides لجافا إلى مشروعك. يمكنك تنزيلها من [موقع Aspose](https://releases.aspose.com/slides/java/).

## الخطوة 1: إنشاء عرض تقديمي في PowerPoint

أولاً، علينا إنشاء عرض تقديمي جديد في PowerPoint. إليك كيفية القيام بذلك باستخدام Java:

```java
String outPptxPath = "Your Output Directory" + "PresentationSlideShowSetup.pptx";
Presentation pres = new Presentation();
```

في الكود أعلاه، نحدد مسار ملف الإخراج لعرضنا التقديمي وننشئ ملفًا جديدًا `Presentation` هدف.

## الخطوة 2: تكوين إعدادات عرض الشرائح

بعد ذلك، سنقوم بتكوين إعدادات عرض الشرائح المختلفة لعرضنا التقديمي. 

### استخدم معلمة التوقيت

يمكننا ضبط معلمة "استخدام التوقيت" للتحكم فيما إذا كانت الشرائح تتقدم تلقائيًا أو يدويًا أثناء عرض الشرائح.

```java
SlideShowSettings slideShow = pres.getSlideShowSettings();
slideShow.setUseTimings(false); // تم ضبطه على خطأ للتقدم اليدوي
```

في هذا المثال، قمنا بتعيينه على `false` للسماح بالتقدم اليدوي للشرائح.

### تعيين لون القلم

يمكنك أيضًا تخصيص لون القلم المستخدم أثناء عرض الشرائح. في هذا المثال، سنضبط لون القلم على الأخضر.

```java
IColorFormat penColor = (ColorFormat)slideShow.getPenColor();
penColor.setColor(Color.GREEN);
```

### إضافة الشرائح

لنُضِف بعض الشرائح إلى عرضنا التقديمي. سنستنسخ شريحة موجودة لتبسيط الأمور.

```java
pres.getSlides().addClone(pres.getSlides().get_Item(0));
pres.getSlides().addClone(pres.getSlides().get_Item(0));
pres.getSlides().addClone(pres.getSlides().get_Item(0));
pres.getSlides().addClone(pres.getSlides().get_Item(0));
```

في هذا الكود، نستنسخ الشريحة الأولى أربع مرات. يمكنك تعديل هذا الجزء لإضافة محتوى خاص بك.

## الخطوة 3: تحديد نطاق الشريحة لعرض الشرائح

يمكنك تحديد الشرائح المراد تضمينها في عرض الشرائح. في هذا المثال، سنحدد نطاق الشرائح من الشريحة الثانية إلى الشريحة الخامسة.

```java
SlidesRange slidesRange = new SlidesRange();
slidesRange.setStart(2);
slidesRange.setEnd(5);
slideShow.setSlides(slidesRange);
```

من خلال تعيين أرقام الشريحة في البداية والنهاية، يمكنك التحكم في الشرائح التي ستكون جزءًا من عرض الشرائح.

## الخطوة 4: حفظ العرض التقديمي

وأخيرًا، سنقوم بحفظ العرض التقديمي الذي تم تكوينه في ملف.

```java
pres.save(outPptxPath, SaveFormat.Pptx);
```

تأكد من توفير مسار ملف الإخراج المطلوب.

## كود المصدر الكامل لإعداد عرض الشرائح التقديمي في Java Slides

```java
String outPptxPath = "Your Output Directory" + "PresentationSlideShowSetup.pptx";
Presentation pres = new Presentation();
try {
	// يحصل على إعدادات عرض الشرائح
	SlideShowSettings slideShow = pres.getSlideShowSettings();
	// تعيين معلمة "استخدام التوقيت"
	slideShow.setUseTimings(false);
	// مجموعات ألوان القلم
	IColorFormat penColor = (ColorFormat)slideShow.getPenColor();
	penColor.setColor(Color.GREEN);
	// يضيف الشرائح لـ
	pres.getSlides().addClone(pres.getSlides().get_Item(0));
	pres.getSlides().addClone(pres.getSlides().get_Item(0));
	pres.getSlides().addClone(pres.getSlides().get_Item(0));
	pres.getSlides().addClone(pres.getSlides().get_Item(0));
	// تعيين معلمة عرض الشريحة
	SlidesRange slidesRange = new SlidesRange();
	slidesRange.setStart(2);
	slidesRange.setEnd(5);
	slideShow.setSlides(slidesRange);
	// حفظ العرض التقديمي
	pres.save(outPptxPath, SaveFormat.Pptx);
} finally {
	if (pres != null) pres.dispose();
}
```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية إعداد عرض شرائح تقديمي بلغة جافا باستخدام Aspose.Slides. يمكنك تخصيص إعدادات متنوعة لعرض الشرائح، بما في ذلك التوقيت ولون القلم ونطاق الشريحة، لإنشاء عروض تقديمية تفاعلية وجذابة.

## الأسئلة الشائعة

### كيف يمكنني تغيير توقيت انتقالات الشرائح؟

لتغيير توقيت انتقالات الشرائح، يمكنك تعديل معلمة "استخدام التوقيت" في إعدادات عرض الشرائح. اضبطها على `true` للتقدم التلقائي مع التوقيتات المحددة مسبقًا أو `false` للتقدم اليدوي أثناء عرض الشرائح.

### كيف يمكنني تخصيص لون القلم المستخدم أثناء عرض الشرائح؟

يمكنك تخصيص لون القلم بالوصول إلى إعدادات لون القلم في إعدادات عرض الشرائح. استخدم `setColor` طريقة لتعيين اللون المطلوب. على سبيل المثال، لتعيين لون القلم إلى الأخضر، استخدم `penColor.setColor(Color.GREEN)`.

### كيف أضيف شرائح محددة إلى عرض الشرائح؟

لتضمين شرائح محددة في عرض الشرائح، قم بإنشاء `SlidesRange` الكائن وتعيين أرقام الشريحة في البداية والنهاية باستخدام `setStart` و `setEnd` الأساليب. ثم، قم بتعيين هذا النطاق لإعدادات عرض الشرائح باستخدام `slideShow.setSlides(slidesRange)`.

### هل يمكنني إضافة المزيد من الشرائح إلى العرض التقديمي؟

نعم، يمكنك إضافة شرائح إضافية إلى عرضك التقديمي. استخدم `pres.getSlides().addClone()` طريقة لاستنساخ الشرائح الحالية أو إنشاء شرائح جديدة حسب الحاجة. تأكد من تخصيص محتوى هذه الشرائح وفقًا لاحتياجاتك.

### كيف يمكنني حفظ العرض التقديمي الذي قمت بإعداده في ملف؟

لحفظ العرض التقديمي المُهيأ في ملف، استخدم `pres.save()` حدد مسار ملف الإخراج والتنسيق المطلوب. على سبيل المثال، يمكنك حفظه بتنسيق PPTX باستخدام `pres.save(outPptxPath, SaveFormat.Pptx)`.

### كيف يمكنني تخصيص إعدادات عرض الشرائح بشكل أكبر؟

يمكنك استكشاف إعدادات عرض الشرائح الإضافية التي يوفرها Aspose.Slides لجافا لتخصيص تجربة عرض الشرائح بما يناسب احتياجاتك. راجع الوثائق على [هنا](https://reference.aspose.com/slides/java/) للحصول على معلومات مفصلة حول الخيارات والتكوينات المتاحة.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}