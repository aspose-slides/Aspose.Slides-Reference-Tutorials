---
title: صيغ خلايا بيانات الرسم البياني في شرائح جافا
linktitle: صيغ خلايا بيانات الرسم البياني في شرائح جافا
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية تعيين صيغ خلايا بيانات المخطط في عروض Java PowerPoint التقديمية باستخدام Aspose.Slides لـ Java. إنشاء مخططات ديناميكية باستخدام الصيغ.
type: docs
weight: 11
url: /ar/java/data-manipulation/chart-data-cell-formulas-java-slides/
---

## مقدمة إلى صيغ خلايا بيانات المخطط في Aspose.Slides لـ Java

في هذا البرنامج التعليمي، سوف نستكشف كيفية العمل مع صيغ خلايا بيانات المخطط باستخدام Aspose.Slides لـ Java. باستخدام Aspose.Slides، يمكنك إنشاء المخططات ومعالجتها في عروض PowerPoint التقديمية، بما في ذلك إعداد الصيغ لخلايا البيانات.

## المتطلبات الأساسية

 قبل أن تبدأ، تأكد من تثبيت مكتبة Aspose.Slides for Java. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/java/).

## الخطوة 1: إنشاء عرض تقديمي لـ PowerPoint

أولاً، لنقم بإنشاء عرض تقديمي جديد لبرنامج PowerPoint ونضيف إليه مخططًا.

```java
String outpptxFile = RunExamples.getOutPath() + File.separator + "ChartDataCell_Formulas_out.pptx";
Presentation presentation = new Presentation();
try
{
    // أضف مخططًا إلى الشريحة الأولى
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 150, 150, 500, 300);
    
    // احصل على المصنف الخاص ببيانات المخطط
    IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    
    // متابعة عمليات خلية البيانات
    // ...
    
    // احفظ العرض التقديمي
    presentation.save(outpptxFile, SaveFormat.Pptx);
}
finally
{
    if (presentation != null) presentation.dispose();
}
```

## الخطوة 2: تعيين الصيغ لخلايا البيانات

الآن، لنقم بتعيين الصيغ لخلايا بيانات محددة في المخطط. في هذا المثال، سنقوم بتعيين صيغ لخليتين مختلفتين.

### الخلية 1: استخدام تدوين A1

```java
IChartDataCell cell1 = workbook.getCell(0, "B2");
cell1.setFormula("1 + SUM(F2:H5)");
```

في الكود أعلاه، قمنا بتعيين صيغة للخلية B2 باستخدام تدوين A1. تحسب الصيغة مجموع الخلايا من F2 إلى H5 وتضيف 1 إلى النتيجة.

### الخلية 2: استخدام تدوين R1C1

```java
IChartDataCell cell2 = workbook.getCell(0, "C2");
cell2.setR1C1Formula("MAX(R2C6:R5C8) / 3");
```

هنا، قمنا بتعيين صيغة للخلية C2 باستخدام تدوين R1C1. تحسب الصيغة الحد الأقصى للقيمة ضمن النطاق R2C6 إلى R5C8 ثم تقسمها على 3.

## الخطوة 3: حساب الصيغ

بعد تعيين الصيغ، من الضروري حسابها باستخدام الكود التالي:

```java
workbook.calculateFormulas();
```

تضمن هذه الخطوة أن يعكس المخطط القيم المحدثة بناءً على الصيغ.

## الخطوة 4: احفظ العرض التقديمي

وأخيرًا، احفظ العرض التقديمي المعدل في ملف.

```java
presentation.save(outpptxFile, SaveFormat.Pptx);
```

## كود المصدر الكامل لصيغ خلايا بيانات الرسم البياني في شرائح جافا

```java
String outpptxFile = RunExamples.getOutPath() + File.pathSeparator + "ChartDataCell_Formulas_out.pptx";
Presentation presentation = new Presentation();
try
{
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 150, 150, 500, 300);
	IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
	IChartDataCell cell1 = workbook.getCell(0, "B2");
	cell1.setFormula("1 + SUM(F2:H5)");
	IChartDataCell cell2 = workbook.getCell(0, "C2");
	cell2.setR1C1Formula("MAX(R2C6:R5C8) / 3");
	workbook.calculateFormulas();
	presentation.save(outpptxFile, SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## خاتمة

في هذا البرنامج التعليمي، اكتشفنا كيفية العمل مع صيغ خلايا بيانات المخطط في Aspose.Slides لـ Java. لقد قمنا بتغطية إنشاء عرض تقديمي لـ PowerPoint، وإضافة مخطط، وتعيين الصيغ لخلايا البيانات، وحساب الصيغ، وحفظ العرض التقديمي. يمكنك الآن الاستفادة من هذه الإمكانات لإنشاء مخططات ديناميكية تعتمد على البيانات في عروضك التقديمية.

## الأسئلة الشائعة

### كيف أقوم بإضافة مخطط إلى شريحة معينة؟

 لإضافة مخطط إلى شريحة معينة، يمكنك استخدام`getSlides().get_Item(slideIndex)` للوصول إلى الشريحة المطلوبة، ثم استخدم`addChart` طريقة إضافة الرسم البياني.

### هل يمكنني استخدام أنواع مختلفة من الصيغ في خلايا البيانات؟

نعم، يمكنك استخدام أنواع مختلفة من الصيغ، بما في ذلك العمليات الحسابية والوظائف والمراجع إلى خلايا أخرى، في صيغ خلايا البيانات.

### كيف يمكنني تغيير نوع المخطط؟

 يمكنك تغيير نوع المخطط باستخدام`setChartType` الطريقة على`IChart` الكائن وتحديد المطلوب`ChartType`.