---
title: إضافة أشرطة الخطأ في شرائح جافا
linktitle: إضافة أشرطة الخطأ في شرائح جافا
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية إضافة أشرطة الخطأ إلى مخططات PowerPoint في Java باستخدام Aspose.Slides. دليل خطوة بخطوة مع التعليمات البرمجية المصدر لتخصيص أشرطة الخطأ.
weight: 13
url: /ar/java/chart-data-manipulation/add-error-bars-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة أشرطة الخطأ في شرائح جافا


## مقدمة لإضافة أشرطة الأخطاء في شرائح Java باستخدام Aspose.Slides

في هذا البرنامج التعليمي، سنوضح كيفية إضافة أشرطة الخطأ إلى المخطط في شريحة PowerPoint باستخدام Aspose.Slides لـ Java. توفر أشرطة الخطأ معلومات قيمة حول التباين أو عدم اليقين في نقاط البيانات في المخطط. سنقوم بإنشاء مخطط فقاعي وإضافة أشرطة خطأ إليه. هيا بنا نبدأ!

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من تثبيت مكتبة Aspose.Slides for Java وإعدادها في مشروع Java الخاص بك. يمكنك تحميل المكتبة من[موقع أسبوز](https://downloads.aspose.com/slides/java).

## الخطوة 1: إنشاء عرض تقديمي فارغ

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء عرض تقديمي فارغ
Presentation presentation = new Presentation();
```

في هذه الخطوة، نقوم بإنشاء عرض تقديمي فارغ حيث سنضيف الرسم البياني الخاص بنا مع أشرطة الخطأ.

## الخطوة 2: إنشاء مخطط فقاعي

```java
// إنشاء مخطط فقاعي
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

هنا، نقوم بإنشاء مخطط فقاعي ونحدد موضعه وأبعاده على الشريحة.

## الخطوة 3: إضافة أشرطة الخطأ وإعداد التنسيق

```java
// إضافة أشرطة الخطأ وتحديد تنسيقها
IErrorBarsFormat errBarX = chart.getChartData().getSeries().get_Item(0).getErrorBarsXFormat();
IErrorBarsFormat errBarY = chart.getChartData().getSeries().get_Item(0).getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Fixed);
errBarX.setValue(0.1f);
errBarY.setValueType(ErrorBarValueType.Percentage);
errBarY.setValue(5);
errBarX.setType(ErrorBarType.Plus);
errBarY.getFormat().getLine().setWidth(2);
errBarX.setEndCap(true);
```

في هذه الخطوة، نضيف أشرطة الخطأ إلى المخطط ونحدد تنسيقها. يمكنك تخصيص أشرطة الأخطاء عن طريق تغيير القيم والأنواع والخصائص الأخرى.

- `errBarX` يمثل أشرطة الخطأ على طول المحور السيني.
- `errBarY` يمثل أشرطة الخطأ على طول المحور ص.
- نجعل أشرطة الخطأ X وY مرئية.
- `setValueType` يحدد نوع القيمة لأشرطة الخطأ (على سبيل المثال، ثابت أو نسبة مئوية).
- `setValue` يضبط قيمة أشرطة الخطأ.
- `setType` يحدد نوع أشرطة الخطأ (على سبيل المثال، زائد أو ناقص).
-  قمنا بتعيين عرض خطوط شريط الخطأ باستخدام`getFormat().getLine().setWidth(2)`.
- `setEndCap`يحدد ما إذا كان سيتم تضمين الأحرف الاستهلالية النهائية على أشرطة الخطأ.

## الخطوة 4: احفظ العرض التقديمي

```java
// حفظ العرض التقديمي
presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
```

وأخيرًا، نقوم بحفظ العرض التقديمي مع أشرطة الخطأ المضافة في موقع محدد.

هذا كل شيء! لقد نجحت في إضافة أشرطة الخطأ إلى مخطط في شريحة PowerPoint باستخدام Aspose.Slides لـ Java.

## أكمل كود المصدر لإضافة أشرطة الخطأ في شرائح جافا

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء عرض تقديمي فارغ
Presentation presentation = new Presentation();
try
{
	// إنشاء مخطط فقاعي
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// إضافة أشرطة الخطأ وتحديد تنسيقها
	IErrorBarsFormat errBarX = chart.getChartData().getSeries().get_Item(0).getErrorBarsXFormat();
	IErrorBarsFormat errBarY = chart.getChartData().getSeries().get_Item(0).getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Fixed);
	errBarX.setValue(0.1f);
	errBarY.setValueType(ErrorBarValueType.Percentage);
	errBarY.setValue(5);
	errBarX.setType(ErrorBarType.Plus);
	errBarY.getFormat().getLine().setWidth(2);
	errBarX.setEndCap(true);
	// حفظ العرض التقديمي
	presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## خاتمة

في هذا البرنامج التعليمي، اكتشفنا كيفية تحسين عروض PowerPoint التقديمية الخاصة بك عن طريق إضافة أشرطة الخطأ إلى المخططات باستخدام Aspose.Slides for Java. توفر أشرطة الخطأ رؤى قيمة حول تقلب البيانات والشكوك، مما يجعل العروض التقديمية الخاصة بك أكثر إفادة وجاذبية بصريًا.

## الأسئلة الشائعة

### كيف يمكنني تخصيص مظهر أشرطة الخطأ بشكل أكبر؟

يمكنك تخصيص أشرطة الأخطاء عن طريق تعديل خصائصها، مثل نمط الخط واللون والعرض، كما هو موضح في الخطوة 3.

### هل يمكنني إضافة أشرطة خطأ إلى أنواع مختلفة من المخططات؟

نعم، يمكنك إضافة أشرطة خطأ إلى أنواع المخططات المختلفة التي يدعمها Aspose.Slides لـ Java. ما عليك سوى إنشاء نوع المخطط المطلوب واتباع نفس خطوات تخصيص شريط الأخطاء.

### كيف يمكنني ضبط موضع وحجم المخطط على الشريحة؟

 يمكنك التحكم في موضع المخطط وأبعاده عن طريق ضبط المعلمات الموجودة في`addChart` الطريقة كما هو موضح في الخطوة 2.

### أين يمكنني العثور على مزيد من المعلومات حول Aspose.Slides لـ Java؟

 يمكنك الرجوع إلى[Aspose.Slides لتوثيق جافا](https://reference.aspose.com/slides/java/) للحصول على معلومات مفصلة حول استخدام المكتبة.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
