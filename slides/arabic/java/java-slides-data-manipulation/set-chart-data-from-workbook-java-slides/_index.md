---
"description": "تعرّف على كيفية إعداد بيانات مخطط بياني من مصنف Excel في Java Slides باستخدام Aspose.Slides. دليل خطوة بخطوة مع أمثلة برمجية للعروض التقديمية الديناميكية."
"linktitle": "تعيين بيانات الرسم البياني من المصنف في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "تعيين بيانات الرسم البياني من المصنف في شرائح Java"
"url": "/ar/java/data-manipulation/set-chart-data-from-workbook-java-slides/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تعيين بيانات الرسم البياني من المصنف في شرائح Java


## مقدمة لتعيين بيانات الرسم البياني من المصنف في شرائح Java

Aspose.Slides for Java هي مكتبة فعّالة تُمكّن المطورين من العمل مع عروض PowerPoint التقديمية برمجيًا. تُوفّر ميزات شاملة لإنشاء شرائح PowerPoint ومعالجتها وإدارتها. من المتطلبات الشائعة عند العمل مع العروض التقديمية ضبط بيانات المخططات ديناميكيًا من مصدر بيانات خارجي، مثل مصنف Excel. في هذا البرنامج التعليمي، سنشرح كيفية تحقيق ذلك باستخدام Java.

## المتطلبات الأساسية

قبل أن نتعمق في التنفيذ، تأكد من أن لديك المتطلبات الأساسية التالية:

- تم تثبيت Java Development Kit (JDK) على نظامك.
- تمت إضافة مكتبة Aspose.Slides for Java إلى مشروعك.
- مصنف Excel يحتوي على البيانات التي تريد استخدامها للرسم البياني.

## الخطوة 1: إنشاء عرض تقديمي

```java
String outPath = "Your Output Directory" + "response2.pptx";
Presentation pres = new Presentation();
```

نبدأ بإنشاء عرض تقديمي جديد في PowerPoint باستخدام Aspose.Slides لـ Java.

## الخطوة 2: إضافة مخطط

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
```

بعد ذلك، نضيف مخططًا بيانيًا إلى إحدى شرائح العرض التقديمي. في هذا المثال، نضيف مخططًا دائريًا، ولكن يمكنك اختيار نوع المخطط الذي يناسب احتياجاتك.

## الخطوة 3: مسح بيانات الرسم البياني

```java
chart.getChartData().getChartDataWorkbook().clear(0);
```

نقوم بمسح أي بيانات موجودة من الرسم البياني لتحضيره للبيانات الجديدة من مصنف Excel.

## الخطوة 4: تحميل مصنف Excel

```java
Workbook workbook = new Workbook("Your Document Directory";
```

نقوم بتحميل مصنف Excel الذي يحتوي على البيانات التي نريد استخدامها للرسم البياني. استبدل `"book1.xlsx"` مع المسار إلى ملف Excel الخاص بك.

## الخطوة 5: كتابة تدفق المصنف إلى بيانات الرسم البياني

```java
ByteArrayOutputStream mem = new ByteArrayOutputStream();
workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
mem.flush();
chart.getChartData().writeWorkbookStream(mem.toByteArray());
```

نقوم بتحويل بيانات مصنف Excel إلى تدفق ونكتبها في بيانات الرسم البياني.

## الخطوة 6: تعيين نطاق بيانات الرسم البياني

```java
chart.getChartData().setRange("Sheet2!$A$1:$B$3");
```

نحدد نطاق الخلايا من مصنف Excel الذي يجب استخدامه كبيانات للمخطط. عدّل النطاق حسب احتياجات بياناتك.

## الخطوة 7: تخصيص سلسلة المخططات

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getParentSeriesGroup().setColorVaried(true);
```

يمكنك تخصيص خصائص متنوعة لسلسلة المخططات لتناسب احتياجاتك. في هذا المثال، نُمكّن ألوانًا متنوعة لسلسلة المخططات.

## الخطوة 8: حفظ العرض التقديمي

```java
pres.save(outPath, SaveFormat.Pptx);
```

وأخيرًا، نقوم بحفظ العرض التقديمي ببيانات الرسم البياني المحدثة إلى مسار الإخراج المحدد.

## كود المصدر الكامل لتعيين بيانات الرسم البياني من المصنف في شرائح Java

```java
String outPath = "Your Output Directory" + "response2.pptx";
Presentation pres = new Presentation();
try {
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
	chart.getChartData().getChartDataWorkbook().clear(0);
	Workbook workbook = null;
	try {
		workbook = new Workbook("Your Document Directory";
	} catch (Exception ex) {
		System.out.println(ex);
	}
	ByteArrayOutputStream mem = new ByteArrayOutputStream();
	workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
	mem.flush();
	chart.getChartData().writeWorkbookStream(mem.toByteArray());
	chart.getChartData().setRange("Sheet2!$A$1:$B$3");
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	series.getParentSeriesGroup().setColorVaried(true);
	pres.save(outPath, SaveFormat.Pptx);
} catch(Exception e) {
} finally {
	if (pres != null) pres.dispose();
}
```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية ضبط بيانات المخططات البيانية من مصنف Excel في Java Slides باستخدام مكتبة Aspose.Slides لـ Java. باتباع هذا الدليل التفصيلي واستخدام أمثلة الكود المصدري المُرفقة، يمكنك بسهولة دمج بيانات المخططات البيانية الديناميكية في عروض PowerPoint التقديمية.

## الأسئلة الشائعة

### كيف يمكنني تخصيص مظهر الرسم البياني في العرض التقديمي الخاص بي؟

يمكنك تخصيص مظهر الرسم البياني بتعديل خصائص مثل الألوان والخطوط والتسميات وغيرها. راجع وثائق Aspose.Slides لـ Java لمزيد من المعلومات حول خيارات تخصيص الرسم البياني.

### هل يمكنني استخدام البيانات من ملف Excel مختلف للرسم البياني؟

نعم، يمكنك استخدام البيانات من أي ملف Excel عن طريق تحديد مسار الملف الصحيح عند تحميل المصنف في الكود.

### ما هي أنواع المخططات الأخرى التي يمكنني إنشاؤها باستخدام Aspose.Slides لـ Java؟

يدعم Aspose.Slides لجافا أنواعًا مختلفة من المخططات، بما في ذلك المخططات الشريطية، والمخططات الخطية، ومخططات التشتت، وغيرها. يمكنك اختيار نوع المخطط الأنسب لاحتياجات تمثيل بياناتك.

### هل من الممكن تحديث بيانات الرسم البياني بشكل ديناميكي في عرض تقديمي قيد التشغيل؟

نعم، يمكنك تحديث بيانات الرسم البياني بشكل ديناميكي في العرض التقديمي عن طريق تعديل المصنف الأساسي ثم تحديث بيانات الرسم البياني.

### أين يمكنني العثور على المزيد من الأمثلة والموارد للعمل مع Aspose.Slides لـ Java؟

يمكنك استكشاف أمثلة وموارد إضافية على [موقع Aspose](https://www.aspose.com/)بالإضافة إلى ذلك، توفر وثائق Aspose.Slides for Java إرشادات شاملة حول كيفية العمل مع المكتبة.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}