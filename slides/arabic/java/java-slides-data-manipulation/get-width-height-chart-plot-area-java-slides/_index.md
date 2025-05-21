---
"description": "تعلّم كيفية استرجاع أبعاد مساحة الرسم البياني في شرائح جافا باستخدام Aspose.Slides لجافا. حسّن مهاراتك في أتمتة PowerPoint."
"linktitle": "الحصول على العرض والارتفاع من منطقة رسم المخطط في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "الحصول على العرض والارتفاع من منطقة رسم المخطط في شرائح Java"
"url": "/ar/java/data-manipulation/get-width-height-chart-plot-area-java-slides/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# الحصول على العرض والارتفاع من منطقة رسم المخطط في شرائح Java


## مقدمة

تُعد المخططات البيانية وسيلة فعّالة لعرض البيانات في عروض PowerPoint التقديمية. قد تحتاج أحيانًا إلى معرفة أبعاد مساحة الرسم البياني لأسباب مختلفة، مثل تغيير حجم العناصر أو تعديل مواقعها. يوضح هذا الدليل كيفية الحصول على عرض وارتفاع مساحة الرسم البياني باستخدام Java وAspose.Slides for Java.

## المتطلبات الأساسية

قبل التعمق في الكود، تأكد من تثبيت مكتبة Aspose.Slides لجافا وإعدادها في مشروع جافا. يمكنك تنزيل المكتبة من موقع Aspose الإلكتروني. [هنا](https://releases.aspose.com/slides/java/).

## الخطوة 1: إعداد البيئة

تأكد من إضافة مكتبة Aspose.Slides لجافا إلى مشروع جافا. يمكنك القيام بذلك عن طريق تضمين المكتبة في تبعيات مشروعك أو عن طريق إضافة ملف JAR يدويًا.

## الخطوة 2: إنشاء عرض تقديمي في PowerPoint

لنبدأ بإنشاء عرض تقديمي على PowerPoint وإضافة شريحة إليه. ستكون هذه الشريحة بمثابة حاوية لمخططنا.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
```

يستبدل `"Your Document Directory"` مع المسار إلى دليل المستند الخاص بك.

## الخطوة 3: إضافة مخطط

الآن، لنُضِف مخططًا عموديًا مُجمّعًا إلى الشريحة. سنتحقق أيضًا من صحة تخطيط المخطط.

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
chart.validateChartLayout();
```

يقوم هذا الكود بإنشاء مخطط عمودي مجمع في الموضع (100، 100) بأبعاد (500، 350).

## الخطوة 4: الحصول على أبعاد مساحة الأرض

لاسترداد عرض وارتفاع منطقة رسم الرسم البياني، يمكننا استخدام الكود التالي:

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();
```

الآن، المتغيرات `x`، `y`، `w`، و `h` تحتوي على القيم المقابلة لإحداثيات X، وإحداثيات Y، والعرض، والارتفاع لمنطقة الرسم البياني.

## الخطوة 5: حفظ العرض التقديمي

وأخيرًا، احفظ العرض التقديمي مع الرسم البياني.

```java
pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
```

تأكد من الاستبدال `"Chart_out.pptx"` مع اسم ملف الإخراج المطلوب.

## كود المصدر الكامل للحصول على العرض والارتفاع من منطقة رسم الرسم البياني في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
try
{
	Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
	chart.validateChartLayout();
	double x = chart.getPlotArea().getActualX();
	double y = chart.getPlotArea().getActualY();
	double w = chart.getPlotArea().getActualWidth();
	double h = chart.getPlotArea().getActualHeight();
	// حفظ العرض التقديمي مع الرسم البياني
	pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## خاتمة

في هذه المقالة، تناولنا كيفية الحصول على عرض وارتفاع منطقة رسم بياني في شرائح جافا باستخدام واجهة برمجة تطبيقات Aspose.Slides لجافا. تُعدّ هذه المعلومات قيّمة عند الحاجة إلى تعديل تخطيط مخططاتك ديناميكيًا ضمن عروض PowerPoint التقديمية.

## الأسئلة الشائعة

### كيف يمكنني تغيير نوع الرسم البياني إلى شيء آخر غير الأعمدة المجمعة؟

يمكنك تغيير نوع الرسم البياني عن طريق استبدال `ChartType.ClusteredColumn` مع نوع الرسم البياني المطلوب، مثل `ChartType.Line` أو `ChartType.Pie`.

### هل يمكنني تعديل خصائص أخرى للرسم البياني؟

نعم، يمكنك تعديل خصائص مختلفة للمخطط، مثل البيانات والتسميات والتنسيق، باستخدام واجهة برمجة تطبيقات Aspose.Slides لـ Java. راجع الوثائق لمزيد من التفاصيل.

### هل برنامج Aspose.Slides for Java مناسب لأتمتة PowerPoint الاحترافية؟

نعم، Aspose.Slides لجافا مكتبة فعّالة لأتمتة مهام PowerPoint في تطبيقات جافا. توفر ميزات شاملة للعمل مع العروض التقديمية والشرائح والأشكال والرسوم البيانية وغيرها.

### كيف يمكنني معرفة المزيد عن Aspose.Slides لـ Java؟

يمكنك العثور على وثائق وأمثلة موسعة على صفحة وثائق Aspose.Slides لـ Java [هنا](https://reference.aspose.com/slides/java/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}