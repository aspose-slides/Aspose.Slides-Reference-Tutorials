---
title: حساب الصيغ في شرائح جافا
linktitle: حساب الصيغ في شرائح جافا
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية حساب الصيغ في Java Slides باستخدام Aspose.Slides لـ Java. دليل خطوة بخطوة مع التعليمات البرمجية المصدر لعروض PowerPoint التقديمية الديناميكية.
type: docs
weight: 10
url: /ar/java/data-manipulation/calculate-formulas-java-slides/
---

## مقدمة لحساب الصيغ في شرائح Java باستخدام Aspose.Slides

في هذا الدليل، سنوضح كيفية حساب الصيغ في Java Slides باستخدام Aspose.Slides for Java API. Aspose.Slides هي مكتبة قوية للعمل مع عروض PowerPoint التقديمية، وتوفر ميزات لمعالجة المخططات وإجراء حسابات الصيغة داخل الشرائح.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- بيئة تطوير جافا
-  Aspose.Slides لمكتبة Java (يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/java/)
- المعرفة الأساسية ببرمجة جافا

## الخطوة 1: إنشاء عرض تقديمي جديد

أولاً، لنقم بإنشاء عرض تقديمي جديد لبرنامج PowerPoint وإضافة شريحة إليه. سنعمل مع شريحة واحدة في هذا المثال.

```java
String resultPath = "Your Output Directory" + "CalculateFormulas_out.pptx";
Presentation presentation = new Presentation();
```

## الخطوة 2: إضافة مخطط إلى الشريحة

الآن، دعونا نضيف مخططًا عموديًا متفاوت المسافات إلى الشريحة. سوف نستخدم هذا الرسم البياني لتوضيح حسابات الصيغة.

```java
IChart s_chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 10, 10, 600, 300);
```

## الخطوة 3: تعيين الصيغ والقيم

بعد ذلك، سنقوم بتعيين الصيغ والقيم لخلايا بيانات المخطط باستخدام Aspose.Slides API. سنقوم بحساب الصيغ لهذه الخلايا.

```java
IChartDataWorkbook workbook = s_chart.getChartData().getChartDataWorkbook();

// قم بتعيين الصيغة للخلية A1
IChartDataCell cell = workbook.getCell(0, "A1");
cell.setFormula("ABS(A2) + MAX(B2:C2)");

// قم بتعيين القيمة للخلية A2
workbook.getCell(0, "A2").setValue(-1);
workbook.calculateFormulas();

// قم بتعيين الصيغة للخلية B2
workbook.getCell(0, "B2").setFormula("2");
workbook.calculateFormulas();

// قم بتعيين الصيغة للخلية C2
workbook.getCell(0, "C2").setFormula("A2 + 4");
workbook.calculateFormulas();

// قم بتعيين الصيغة للخلية A1 مرة أخرى
cell.setFormula("MAX(2:2)");
workbook.calculateFormulas();
```

## الخطوة 4: احفظ العرض التقديمي

وأخيرا، دعونا نحفظ العرض التقديمي المعدل بالصيغ المحسوبة.

```java
presentation.save(resultPath, SaveFormat.Pptx);
```

## كود المصدر الكامل لحساب الصيغ في شرائح جافا

```java
String resultPath = "Your Output Directory" + "CalculateFormulas_out.pptx";
Presentation presentation = new Presentation();
try {
	IChart s_chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 10, 10, 600, 300);
	IChartDataWorkbook workbook = s_chart.getChartData().getChartDataWorkbook();
	IChartDataCell cell = workbook.getCell(0, "A1");
	cell.setFormula("ABS(A2) + MAX(B2:C2)");
	workbook.getCell(0, "A2").setValue(-1);
	workbook.calculateFormulas();
	workbook.getCell(0, "B2").setFormula("2");
	workbook.calculateFormulas();
	workbook.getCell(0, "C2").setFormula("A2 + 4");
	workbook.calculateFormulas();
	cell.setFormula("MAX(2:2)");
	workbook.calculateFormulas();
	presentation.save(resultPath, SaveFormat.Pptx);
} finally {
	if (presentation != null) presentation.dispose();
}
```

## خاتمة

في هذا الدليل، تعلمنا كيفية حساب الصيغ في Java Slides باستخدام Aspose.Slides لـ Java. لقد أنشأنا عرضًا تقديميًا جديدًا، وأضفنا مخططًا إليه، وقمنا بتعيين الصيغ والقيم لخلايا بيانات المخطط، وحفظنا العرض التقديمي بالصيغ المحسوبة.

## الأسئلة الشائعة

### كيف أقوم بتعيين الصيغ لخلايا بيانات المخطط؟

 يمكنك تعيين الصيغ لخلايا بيانات المخطط باستخدام`setFormula` طريقة`IChartDataCell` في Aspose.Slides.

### كيف أقوم بتعيين قيم لخلايا بيانات المخطط؟

 يمكنك تعيين قيم لخلايا بيانات المخطط باستخدام`setValue` طريقة`IChartDataCell` في Aspose.Slides.

### كيف يمكنني حساب الصيغ في مصنف؟

 يمكنك حساب الصيغ في مصنف باستخدام`calculateFormulas` طريقة`IChartDataWorkbook` في Aspose.Slides.
