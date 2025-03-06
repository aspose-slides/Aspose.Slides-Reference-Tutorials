---
title: قم بتعيين بيانات المخطط من المصنف في شرائح Java
linktitle: قم بتعيين بيانات المخطط من المصنف في شرائح Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية تعيين بيانات المخطط من مصنف Excel في Java Slides باستخدام Aspose.Slides. دليل خطوة بخطوة مع أمثلة التعليمات البرمجية للعروض التقديمية الديناميكية.
weight: 15
url: /ar/java/data-manipulation/set-chart-data-from-workbook-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## مقدمة لتعيين بيانات المخطط من المصنف في شرائح Java

Aspose.Slides for Java هي مكتبة قوية تسمح للمطورين بالعمل مع عروض PowerPoint التقديمية برمجياً. فهو يوفر ميزات شاملة لإنشاء شرائح PowerPoint ومعالجتها وإدارتها. أحد المتطلبات الشائعة عند العمل مع العروض التقديمية هو تعيين بيانات المخطط ديناميكيًا من مصدر بيانات خارجي، مثل مصنف Excel. في هذا البرنامج التعليمي، سنوضح كيفية تحقيق ذلك باستخدام Java.

## المتطلبات الأساسية

قبل أن نتعمق في التنفيذ، تأكد من أن لديك المتطلبات الأساسية التالية:

- تم تثبيت Java Development Kit (JDK) على نظامك.
- تمت إضافة مكتبة Aspose.Slides لـ Java إلى مشروعك.
- مصنف Excel يحتوي على البيانات التي تريد استخدامها للمخطط.

## الخطوة 1: إنشاء عرض تقديمي

```java
String outPath = "Your Output Directory" + "response2.pptx";
Presentation pres = new Presentation();
```

نبدأ بإنشاء عرض تقديمي جديد لبرنامج PowerPoint باستخدام Aspose.Slides لـ Java.

## الخطوة 2: إضافة مخطط

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
```

بعد ذلك، نقوم بإضافة مخطط إلى إحدى الشرائح في العرض التقديمي. في هذا المثال، نقوم بإضافة مخطط دائري، ولكن يمكنك اختيار نوع المخطط الذي يناسب احتياجاتك.

## الخطوة 3: مسح بيانات المخطط

```java
chart.getChartData().getChartDataWorkbook().clear(0);
```

نقوم بمسح أي بيانات موجودة من المخطط لإعدادها للبيانات الجديدة من مصنف Excel.

## الخطوة 4: تحميل مصنف Excel

```java
Workbook workbook = new Workbook("Your Document Directory";
```

 نقوم بتحميل مصنف Excel الذي يحتوي على البيانات التي نريد استخدامها للمخطط. يستبدل`"book1.xlsx"` مع المسار إلى ملف Excel الخاص بك.

## الخطوة 5: كتابة دفق المصنف إلى بيانات المخطط

```java
ByteArrayOutputStream mem = new ByteArrayOutputStream();
workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
mem.flush();
chart.getChartData().writeWorkbookStream(mem.toByteArray());
```

نقوم بتحويل بيانات مصنف Excel إلى دفق وكتابتها على بيانات المخطط.

## الخطوة 6: تعيين نطاق بيانات الرسم البياني

```java
chart.getChartData().setRange("Sheet2!$A$1:$B$3");
```

نحدد نطاق الخلايا من مصنف Excel الذي يجب استخدامه كبيانات للمخطط. اضبط النطاق حسب الحاجة لبياناتك.

## الخطوة 7: تخصيص سلسلة المخططات

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getParentSeriesGroup().setColorVaried(true);
```

يمكنك تخصيص خصائص متنوعة لسلسلة المخططات لتتوافق مع متطلباتك. في هذا المثال، نقوم بتمكين ألوان متنوعة لسلسلة المخططات.

## الخطوة 8: احفظ العرض التقديمي

```java
pres.save(outPath, SaveFormat.Pptx);
```

وأخيرًا، نقوم بحفظ العرض التقديمي مع بيانات المخطط المحدثة في مسار الإخراج المحدد.

## كود المصدر الكامل لتعيين بيانات المخطط من المصنف في شرائح Java

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

في هذا البرنامج التعليمي، تعلمنا كيفية تعيين بيانات المخطط من مصنف Excel في Java Slides باستخدام مكتبة Aspose.Slides for Java. باتباع الدليل التفصيلي واستخدام أمثلة التعليمات البرمجية المصدر المتوفرة، يمكنك بسهولة دمج بيانات المخطط الديناميكي في عروض PowerPoint التقديمية.

## الأسئلة الشائعة

### كيف يمكنني تخصيص مظهر المخطط في العرض التقديمي الخاص بي؟

يمكنك تخصيص مظهر المخطط عن طريق تعديل خصائص مثل الألوان والخطوط والتسميات والمزيد. راجع وثائق Aspose.Slides for Java للحصول على معلومات تفصيلية حول خيارات تخصيص المخطط.

### هل يمكنني استخدام بيانات من ملف Excel مختلف للمخطط؟

نعم، يمكنك استخدام البيانات من أي ملف Excel عن طريق تحديد مسار الملف الصحيح عند تحميل المصنف في التعليمات البرمجية.

### ما أنواع المخططات الأخرى التي يمكنني إنشاؤها باستخدام Aspose.Slides لـ Java؟

يدعم Aspose.Slides for Java أنواعًا مختلفة من المخططات، بما في ذلك المخططات الشريطية والمخططات الخطية والمخططات المبعثرة والمزيد. يمكنك اختيار نوع المخطط الذي يناسب احتياجات تمثيل البيانات الخاصة بك.

### هل من الممكن تحديث بيانات المخطط ديناميكيًا في عرض تقديمي قيد التشغيل؟

نعم، يمكنك تحديث بيانات المخطط ديناميكيًا في العرض التقديمي عن طريق تعديل المصنف الأساسي ثم تحديث بيانات المخطط.

### أين يمكنني العثور على المزيد من الأمثلة والموارد للعمل مع Aspose.Slides لـ Java؟

 يمكنك استكشاف أمثلة وموارد إضافية على[موقع أسبوز](https://www.aspose.com/). بالإضافة إلى ذلك، توفر وثائق Aspose.Slides for Java إرشادات شاملة حول العمل مع المكتبة.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
