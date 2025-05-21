---
"description": "تعرّف على كيفية إعداد صيغ خلايا بيانات المخططات في عروض PowerPoint التقديمية بلغة جافا باستخدام Aspose.Slides لجافا. أنشئ مخططات ديناميكية باستخدام الصيغ."
"linktitle": "صيغ خلايا بيانات الرسم البياني في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "صيغ خلايا بيانات الرسم البياني في شرائح Java"
"url": "/ar/java/data-manipulation/chart-data-cell-formulas-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# صيغ خلايا بيانات الرسم البياني في شرائح Java


## مقدمة إلى صيغ خلايا بيانات المخطط في Aspose.Slides لـ Java

في هذا البرنامج التعليمي، سنستكشف كيفية التعامل مع صيغ خلايا بيانات المخططات باستخدام Aspose.Slides لجافا. باستخدام Aspose.Slides، يمكنك إنشاء المخططات ومعالجتها في عروض PowerPoint التقديمية، بما في ذلك إعداد صيغ خلايا البيانات.

## المتطلبات الأساسية

قبل البدء، تأكد من تثبيت مكتبة Aspose.Slides لجافا. يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/java/).

## الخطوة 1: إنشاء عرض تقديمي في PowerPoint

أولاً، دعنا ننشئ عرض تقديمي جديد في PowerPoint ونضيف إليه مخططًا.

```java
String outpptxFile = "Your Output Directory" + File.separator + "ChartDataCell_Formulas_out.pptx";
Presentation presentation = new Presentation();
try
{
    // أضف مخططًا إلى الشريحة الأولى
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 150, 150, 500, 300);
    
    // احصل على مصنف بيانات الرسم البياني
    IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    
    // متابعة عمليات خلية البيانات
    // ...
    
    // حفظ العرض التقديمي
    presentation.save(outpptxFile, SaveFormat.Pptx);
}
finally
{
    if (presentation != null) presentation.dispose();
}
```

## الخطوة 2: تعيين الصيغ لخلايا البيانات

الآن، لنُعِدُّ صيغًا لخلايا بيانات مُحدَّدة في الرسم البياني. في هذا المثال، سنُعِدُّ صيغًا لخليتين مُختلفتين.

### الخلية 1: استخدام تدوين A1

```java
IChartDataCell cell1 = workbook.getCell(0, "B2");
cell1.setFormula("1 + SUM(F2:H5)");
```

في الكود أعلاه، وضعنا صيغة للخلية B2 باستخدام الصيغة A1. تحسب الصيغة مجموع الخلايا من F2 إلى H5، ثم تضيف 1 إلى النتيجة.

### الخلية 2: استخدام تدوين R1C1

```java
IChartDataCell cell2 = workbook.getCell(0, "C2");
cell2.setR1C1Formula("MAX(R2C6:R5C8) / 3");
```

هنا، وضعنا صيغة للخلية C2 باستخدام صيغة R1C1. تحسب الصيغة القيمة القصوى ضمن النطاق R2C6 إلى R5C8، ثم تقسمها على 3.

## الخطوة 3: حساب الصيغ

بعد تعيين الصيغ، من الضروري حسابها باستخدام الكود التالي:

```java
workbook.calculateFormulas();
```

تضمن هذه الخطوة أن يعكس الرسم البياني القيم المحدثة استنادًا إلى الصيغ.

## الخطوة 4: حفظ العرض التقديمي

وأخيرًا، احفظ العرض التقديمي المعدّل في ملف.

```java
presentation.save(outpptxFile, SaveFormat.Pptx);
```

## كود المصدر الكامل لصيغ بيانات خلايا الرسم البياني في شرائح Java

```java
String outpptxFile = "Your Output Directory" + File.pathSeparator + "ChartDataCell_Formulas_out.pptx";
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

في هذا البرنامج التعليمي، استكشفنا كيفية التعامل مع صيغ خلايا بيانات المخططات البيانية في Aspose.Slides لجافا. تناولنا إنشاء عرض تقديمي في PowerPoint، وإضافة مخطط بياني، وتعيين صيغ لخلايا البيانات، وحساب الصيغ، وحفظ العرض التقديمي. يمكنك الآن الاستفادة من هذه الإمكانيات لإنشاء مخططات بيانية ديناميكية ومبنية على البيانات في عروضك التقديمية.

## الأسئلة الشائعة

### كيف أضيف مخططًا إلى شريحة معينة؟

لإضافة مخطط إلى شريحة معينة، يمكنك استخدام `getSlides().get_Item(slideIndex)` الطريقة للوصول إلى الشريحة المطلوبة، ثم استخدم `addChart` طريقة إضافة الرسم البياني.

### هل يمكنني استخدام أنواع مختلفة من الصيغ في خلايا البيانات؟

نعم، يمكنك استخدام أنواع مختلفة من الصيغ، بما في ذلك العمليات الرياضية والوظائف والمراجع إلى خلايا أخرى، في صيغ خلايا البيانات.

### كيف يمكنني تغيير نوع الرسم البياني؟

يمكنك تغيير نوع الرسم البياني باستخدام `setChartType` الطريقة على `IChart` الكائن وتحديد المطلوب `ChartType`.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}