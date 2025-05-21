---
"description": "تعلّم كيفية حساب الصيغ في عروض جافا التقديمية باستخدام Aspose.Slides لجافا. دليل خطوة بخطوة مع الكود المصدري لعروض PowerPoint التقديمية الديناميكية."
"linktitle": "حساب الصيغ في شرائح جافا"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "حساب الصيغ في شرائح جافا"
"url": "/ar/java/data-manipulation/calculate-formulas-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# حساب الصيغ في شرائح جافا


## مقدمة لحساب الصيغ في شرائح Java باستخدام Aspose.Slides

في هذا الدليل، سنوضح كيفية حساب الصيغ في شرائح جافا باستخدام واجهة برمجة تطبيقات Aspose.Slides لجافا. Aspose.Slides هي مكتبة فعّالة للعمل مع عروض PowerPoint التقديمية، وتوفر ميزات لمعالجة المخططات وإجراء حسابات الصيغ داخل الشرائح.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- بيئة تطوير جافا
- Aspose.Slides لمكتبة Java (يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/java/)
- المعرفة الأساسية ببرمجة جافا

## الخطوة 1: إنشاء عرض تقديمي جديد

أولاً، لنُنشئ عرضًا تقديميًا جديدًا في PowerPoint ونُضيف إليه شريحة. سنعمل على شريحة واحدة في هذا المثال.

```java
String resultPath = "Your Output Directory" + "CalculateFormulas_out.pptx";
Presentation presentation = new Presentation();
```

## الخطوة 2: إضافة مخطط إلى الشريحة

الآن، لنُضِف مخططًا عموديًا مُجمّعًا إلى الشريحة. سنستخدمه لعرض حسابات الصيغ.

```java
IChart s_chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 10, 10, 600, 300);
```

## الخطوة 3: تعيين الصيغ والقيم

بعد ذلك، سنُعيّن صيغًا وقيمًا لخلايا بيانات الرسم البياني باستخدام واجهة برمجة تطبيقات Aspose.Slides. سنحسب الصيغ لهذه الخلايا.

```java
IChartDataWorkbook workbook = s_chart.getChartData().getChartDataWorkbook();

// تعيين الصيغة للخلية A1
IChartDataCell cell = workbook.getCell(0, "A1");
cell.setFormula("ABS(A2) + MAX(B2:C2)");

// تعيين قيمة للخلية A2
workbook.getCell(0, "A2").setValue(-1);
workbook.calculateFormulas();

// تعيين صيغة للخلية B2
workbook.getCell(0, "B2").setFormula("2");
workbook.calculateFormulas();

// تعيين صيغة للخلية C2
workbook.getCell(0, "C2").setFormula("A2 + 4");
workbook.calculateFormulas();

// تعيين الصيغة للخلية A1 مرة أخرى
cell.setFormula("MAX(2:2)");
workbook.calculateFormulas();
```

## الخطوة 4: حفظ العرض التقديمي

وأخيرًا، دعنا نحفظ العرض التقديمي المعدّل باستخدام الصيغ المحسوبة.

```java
presentation.save(resultPath, SaveFormat.Pptx);
```

## كود المصدر الكامل لحساب الصيغ في شرائح Java

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

في هذا الدليل، تعلمنا كيفية حساب الصيغ في شرائح جافا باستخدام Aspose.Slides لجافا. أنشأنا عرضًا تقديميًا جديدًا، وأضفنا إليه مخططًا بيانيًا، وحددنا صيغًا وقيمًا لخلايا بيانات المخطط، وحفظنا العرض التقديمي بالصيغ المحسوبة.

## الأسئلة الشائعة

### كيف أقوم بتعيين الصيغ لخلايا بيانات الرسم البياني؟

يمكنك تعيين صيغ لخلايا بيانات الرسم البياني باستخدام `setFormula` طريقة `IChartDataCell` في Aspose.Slides.

### كيف أقوم بتعيين قيم خلايا بيانات الرسم البياني؟

يمكنك تعيين قيم لخلايا بيانات الرسم البياني باستخدام `setValue` طريقة `IChartDataCell` في Aspose.Slides.

### كيف أحسب الصيغ في مصنف؟

يمكنك حساب الصيغ في مصنف باستخدام `calculateFormulas` طريقة `IChartDataWorkbook` في Aspose.Slides.


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}