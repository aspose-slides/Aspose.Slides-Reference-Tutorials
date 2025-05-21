---
"description": "تعرّف على كيفية إضافة أشرطة أخطاء إلى مخططات PowerPoint بلغة Java باستخدام Aspose.Slides. دليل خطوة بخطوة مع الكود المصدري لتخصيص أشرطة الأخطاء."
"linktitle": "إضافة أشرطة الخطأ في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "إضافة أشرطة الخطأ في شرائح Java"
"url": "/ar/java/chart-data-manipulation/add-error-bars-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إضافة أشرطة الخطأ في شرائح Java


## مقدمة حول إضافة أشرطة الأخطاء في شرائح Java باستخدام Aspose.Slides

في هذا البرنامج التعليمي، سنوضح كيفية إضافة أشرطة أخطاء إلى مخطط بياني في شريحة PowerPoint باستخدام Aspose.Slides لجافا. توفر أشرطة الأخطاء معلومات قيّمة حول تباين أو عدم يقين نقاط البيانات في المخطط. سننشئ مخططًا فقاعيًا ونضيف إليه أشرطة أخطاء. هيا بنا نبدأ!

## المتطلبات الأساسية

قبل البدء، تأكد من تثبيت مكتبة Aspose.Slides لجافا وإعدادها في مشروع جافا. يمكنك تنزيل المكتبة من [موقع Aspose](https://downloads.aspose.com/slides/java).

## الخطوة 1: إنشاء عرض تقديمي فارغ

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء عرض تقديمي فارغ
Presentation presentation = new Presentation();
```

في هذه الخطوة، نقوم بإنشاء عرض تقديمي فارغ حيث سنضيف مخططنا مع أشرطة الخطأ.

## الخطوة 2: إنشاء مخطط فقاعي

```java
// إنشاء مخطط فقاعي
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

هنا نقوم بإنشاء مخطط فقاعي وتحديد موضعه وأبعاده على الشريحة.

## الخطوة 3: إضافة أشرطة الخطأ وتعيين التنسيق

```java
// إضافة أشرطة الخطأ وتعيين تنسيقها
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

في هذه الخطوة، نضيف أشرطة الأخطاء إلى الرسم البياني ونضبط تنسيقها. يمكنك تخصيص أشرطة الأخطاء بتغيير القيم والأنواع والخصائص الأخرى.

- `errBarX` يمثل أشرطة الخطأ على طول المحور X.
- `errBarY` يمثل أشرطة الخطأ على طول المحور Y.
- نحن نجعل أشرطة الخطأ X و Y مرئية.
- `setValueType` يحدد نوع القيمة لأشرطة الخطأ (على سبيل المثال، ثابتة أو نسبة مئوية).
- `setValue` تعيين قيمة أشرطة الخطأ.
- `setType` يحدد نوع أشرطة الخطأ (على سبيل المثال، زائد أو ناقص).
- لقد قمنا بتعيين عرض خطوط شريط الخطأ باستخدام `getFormat().getLine().setWidth(2)`.
- `setEndCap` يحدد ما إذا كان سيتم تضمين أغطية نهاية على أشرطة الخطأ.

## الخطوة 4: حفظ العرض التقديمي

```java
// حفظ العرض التقديمي
presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
```

وأخيرًا، نقوم بحفظ العرض التقديمي مع أشرطة الخطأ المضافة في موقع محدد.

هذا كل شيء! لقد نجحت في إضافة أشرطة الخطأ إلى مخطط في شريحة PowerPoint باستخدام Aspose.Slides لـ Java.

## كود المصدر الكامل لإضافة أشرطة الخطأ في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء عرض تقديمي فارغ
Presentation presentation = new Presentation();
try
{
	// إنشاء مخطط فقاعي
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// إضافة أشرطة الخطأ وتعيين تنسيقها
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

في هذا البرنامج التعليمي، استكشفنا كيفية تحسين عروض PowerPoint التقديمية بإضافة أشرطة أخطاء إلى المخططات البيانية باستخدام Aspose.Slides لجافا. توفر أشرطة الأخطاء رؤى قيّمة حول تباين البيانات وعدم اليقين فيها، مما يجعل عروضك التقديمية أكثر إفادة وجاذبية بصريًا.

## الأسئلة الشائعة

### كيف يمكنني تخصيص مظهر أشرطة الخطأ بشكل أكبر؟

يمكنك تخصيص أشرطة الأخطاء عن طريق تعديل خصائصها، مثل نمط الخط واللون والعرض، كما هو موضح في الخطوة 3.

### هل يمكنني إضافة أشرطة الخطأ إلى أنواع مختلفة من المخططات؟

نعم، يمكنك إضافة أشرطة أخطاء إلى أنواع مختلفة من المخططات التي يدعمها Aspose.Slides لجافا. ما عليك سوى إنشاء نوع المخطط المطلوب واتباع خطوات تخصيص أشرطة الأخطاء نفسها.

### كيف يمكنني تعديل موضع وحجم الرسم البياني على الشريحة؟

يمكنك التحكم في موضع وأبعاد الرسم البياني عن طريق ضبط المعلمات في `addChart` الطريقة كما هو موضح في الخطوة 2.

### أين يمكنني العثور على مزيد من المعلومات حول Aspose.Slides لـ Java؟

يمكنك الرجوع إلى [توثيق Aspose.Slides لـ Java](https://reference.aspose.com/slides/java/) لمزيد من المعلومات التفصيلية حول استخدام المكتبة.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}