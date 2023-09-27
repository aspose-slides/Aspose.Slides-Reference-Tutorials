---
title: إعداد عرض شرائح العرض التقديمي في شرائح Java
linktitle: إعداد عرض شرائح العرض التقديمي في شرائح Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: قم بتحسين عرض شرائح Java الخاص بك باستخدام Aspose.Slides. قم بإنشاء عروض تقديمية جذابة باستخدام إعدادات مخصصة. استكشف الأدلة والأسئلة الشائعة خطوة بخطوة.
type: docs
weight: 16
url: /ar/java/presentation-properties/presentation-slide-show-setup-in-java-slides/
---

## مقدمة لإعداد عرض شرائح العرض التقديمي في شرائح Java

في هذا البرنامج التعليمي، سوف نستكشف كيفية إعداد عرض شرائح العرض التقديمي باستخدام Aspose.Slides لـ Java. سنتعرف على العملية خطوة بخطوة لإنشاء عرض تقديمي لـ PowerPoint وتكوين إعدادات عرض الشرائح المختلفة.

## المتطلبات الأساسية

 قبل أن تبدأ، تأكد من إضافة مكتبة Aspose.Slides for Java إلى مشروعك. يمكنك تنزيله من[موقع أسبوز](https://releases.aspose.com/slides/java/).

## الخطوة 1: إنشاء عرض تقديمي لـ PowerPoint

أولاً، نحتاج إلى إنشاء عرض تقديمي جديد لبرنامج PowerPoint. إليك كيفية القيام بذلك في جافا:

```java
String outPptxPath = RunExamples.getOutPath() + "PresentationSlideShowSetup.pptx";
Presentation pres = new Presentation();
```

 في الكود أعلاه، نحدد مسار ملف الإخراج لعرضنا التقديمي وننشئ ملفًا جديدًا`Presentation` هدف.

## الخطوة 2: تكوين إعدادات عرض الشرائح

بعد ذلك، سنقوم بتكوين إعدادات عرض الشرائح المختلفة لعرضنا التقديمي. 

### استخدام معلمة التوقيت

يمكننا ضبط معلمة "استخدام التوقيت" للتحكم في تقدم الشرائح تلقائيًا أو يدويًا أثناء عرض الشرائح.

```java
SlideShowSettings slideShow = pres.getSlideShowSettings();
slideShow.setUseTimings(false); // اضبط على خطأ للتقدم اليدوي
```

 في هذا المثال، قمنا بتعيينه على`false` للسماح بالتقدم اليدوي للشرائح.

### ضبط لون القلم

يمكنك أيضًا تخصيص لون القلم المستخدم أثناء عرض الشرائح. في هذا المثال، سنقوم بتعيين لون القلم إلى اللون الأخضر.

```java
IColorFormat penColor = (ColorFormat)slideShow.getPenColor();
penColor.setColor(Color.GREEN);
```

### إضافة شرائح

دعونا نضيف بعض الشرائح إلى العرض التقديمي لدينا. سنقوم باستنساخ شريحة موجودة لتبسيط الأمور.

```java
pres.getSlides().addClone(pres.getSlides().get_Item(0));
pres.getSlides().addClone(pres.getSlides().get_Item(0));
pres.getSlides().addClone(pres.getSlides().get_Item(0));
pres.getSlides().addClone(pres.getSlides().get_Item(0));
```

في هذا الكود، نقوم باستنساخ الشريحة الأولى أربع مرات. يمكنك تعديل هذا الجزء لإضافة المحتوى الخاص بك.

## الخطوة 3: تحديد نطاق الشرائح لعرض الشرائح

يمكنك تحديد الشرائح التي يجب تضمينها في عرض الشرائح. في هذا المثال، سنقوم بتعيين نطاق من الشرائح من الشريحة الثانية إلى الشريحة الخامسة.

```java
SlidesRange slidesRange = new SlidesRange();
slidesRange.setStart(2);
slidesRange.setEnd(5);
slideShow.setSlides(slidesRange);
```

من خلال تعيين أرقام شرائح البداية والنهاية، يمكنك التحكم في الشرائح التي ستكون جزءًا من عرض الشرائح.

## الخطوة 4: احفظ العرض التقديمي

وأخيرًا، سنقوم بحفظ العرض التقديمي الذي تم تكوينه في ملف.

```java
pres.save(outPptxPath, SaveFormat.Pptx);
```

تأكد من توفير مسار ملف الإخراج المطلوب.

## أكمل كود المصدر لإعداد عرض شرائح العرض التقديمي في شرائح Java

```java
String outPptxPath = RunExamples.getOutPath() + "PresentationSlideShowSetup.pptx";
Presentation pres = new Presentation();
try {
	// يحصل على إعدادات عرض الشرائح
	SlideShowSettings slideShow = pres.getSlideShowSettings();
	// يضبط معلمة "استخدام التوقيت".
	slideShow.setUseTimings(false);
	// يحدد لون القلم
	IColorFormat penColor = (ColorFormat)slideShow.getPenColor();
	penColor.setColor(Color.GREEN);
	// يضيف شرائح ل
	pres.getSlides().addClone(pres.getSlides().get_Item(0));
	pres.getSlides().addClone(pres.getSlides().get_Item(0));
	pres.getSlides().addClone(pres.getSlides().get_Item(0));
	pres.getSlides().addClone(pres.getSlides().get_Item(0));
	// يضبط إظهار معلمة الشريحة
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

في هذا البرنامج التعليمي، تعلمنا كيفية إعداد عرض شرائح العرض التقديمي في Java باستخدام Aspose.Slides for Java. يمكنك تخصيص إعدادات عرض الشرائح المختلفة، بما في ذلك التوقيت ولون القلم ونطاق الشرائح لإنشاء عروض تقديمية تفاعلية وجذابة.

## الأسئلة الشائعة

### كيف يمكنني تغيير توقيت انتقالات الشرائح؟

 لتغيير توقيت انتقالات الشرائح، يمكنك تعديل معلمة "استخدام التوقيت" في إعدادات عرض الشرائح. اضبطه على`true` للتقدم التلقائي مع توقيتات محددة مسبقا أو`false`للتقدم اليدوي أثناء عرض الشرائح.

### كيف يمكنني تخصيص لون القلم المستخدم أثناء عرض الشرائح؟

 يمكنك تخصيص لون القلم عن طريق الوصول إلى إعدادات لون القلم في إعدادات عرض الشرائح. استخدم ال`setColor` طريقة تحديد اللون المطلوب . على سبيل المثال، لتعيين لون القلم إلى اللون الأخضر، استخدم`penColor.setColor(Color.GREEN)`.

### كيف أقوم بإضافة شرائح معينة إلى عرض الشرائح؟

 لتضمين شرائح معينة في عرض الشرائح، قم بإنشاء ملف`SlidesRange` الكائن وقم بتعيين أرقام شرائح البداية والنهاية باستخدام`setStart` و`setEnd` طُرق. ثم قم بتعيين هذا النطاق لإعدادات عرض الشرائح باستخدام`slideShow.setSlides(slidesRange)`.

### هل يمكنني إضافة المزيد من الشرائح إلى العرض التقديمي؟

 نعم، يمكنك إضافة شرائح إضافية إلى العرض التقديمي الخاص بك. استخدم ال`pres.getSlides().addClone()` طريقة لاستنساخ الشرائح الموجودة أو إنشاء شرائح جديدة حسب الحاجة. تأكد من تخصيص محتوى هذه الشرائح وفقًا لمتطلباتك.

### كيف يمكنني حفظ العرض التقديمي الذي تم تكوينه في ملف؟

 لحفظ العرض التقديمي الذي تم تكوينه في ملف، استخدم الملف`pres.save()`الطريقة وحدد مسار ملف الإخراج بالإضافة إلى التنسيق المطلوب. على سبيل المثال، يمكنك حفظه بتنسيق PPTX باستخدام`pres.save(outPptxPath, SaveFormat.Pptx)`.

### كيف يمكنني تخصيص إعدادات عرض الشرائح بشكل أكبر؟

 يمكنك استكشاف إعدادات عرض الشرائح الإضافية التي يوفرها Aspose.Slides لـ Java لتخصيص تجربة عرض الشرائح وفقًا لاحتياجاتك. الرجوع إلى الوثائق في[هنا](https://reference.aspose.com/slides/java/) للحصول على معلومات مفصلة حول الخيارات والتكوينات المتاحة.