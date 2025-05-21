---
"description": "إتقان التحقق من صحة تخطيط المخططات في PowerPoint باستخدام Aspose.Slides لجافا. تعلم كيفية التعامل مع المخططات برمجيًا للحصول على عروض تقديمية رائعة."
"linktitle": "التحقق من صحة تخطيط الرسم البياني المضاف في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "التحقق من صحة تخطيط الرسم البياني المضاف في شرائح Java"
"url": "/ar/java/data-manipulation/validate-chart-layout-added-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# التحقق من صحة تخطيط الرسم البياني المضاف في شرائح Java


## مقدمة للتحقق من صحة تخطيط المخطط في Aspose.Slides لـ Java

في هذا البرنامج التعليمي، سنستكشف كيفية التحقق من صحة تخطيط المخطط في عرض تقديمي على PowerPoint باستخدام Aspose.Slides لجافا. تتيح لك هذه المكتبة العمل مع عروض PowerPoint التقديمية برمجيًا، مما يُسهّل التعامل مع عناصر مختلفة والتحقق من صحتها، بما في ذلك المخططات.

## الخطوة 1: تهيئة العرض التقديمي

أولاً، نحتاج إلى تهيئة كائن عرض تقديمي وتحميل عرض تقديمي موجود في PowerPoint. استبدل `"Your Document Directory"` مع المسار الفعلي لملف العرض التقديمي الخاص بك (`test.pptx` في هذا المثال).

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## الخطوة 2: إضافة مخطط

بعد ذلك، سنضيف مخططًا إلى العرض التقديمي. في هذا المثال، نضيف مخططًا عموديًا مجمعًا، ولكن يمكنك تغيير `ChartType` حسب الحاجة.

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
```

## الخطوة 3: التحقق من صحة تخطيط الرسم البياني

الآن، سوف نتحقق من صحة تخطيط الرسم البياني باستخدام `validateChartLayout()` هذه الطريقة تضمن عرض المخطط بشكل صحيح داخل الشريحة.

```java
chart.validateChartLayout();
```

## الخطوة 4: استرجاع موضع الرسم البياني وحجمه

بعد التحقق من صحة تخطيط الرسم البياني، قد ترغب في استرجاع معلومات حول موقعه وحجمه. يمكننا الحصول على إحداثيات X وY الفعلية، بالإضافة إلى عرض وارتفاع منطقة الرسم البياني.

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();
```

## الخطوة 5: حفظ العرض التقديمي

أخيرًا، لا تنسَ حفظ العرض التقديمي المُعدَّل. في هذا المثال، سنحفظه باسم `Result.pptx`، ولكن يمكنك تحديد اسم ملف مختلف إذا لزم الأمر.

```java
pres.save(dataDir + "Result.pptx", SaveFormat.Pptx);
```

## تمت إضافة الكود المصدر الكامل للتحقق من صحة تخطيط الرسم البياني في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
	chart.validateChartLayout();
	double x = chart.getPlotArea().getActualX();
	double y = chart.getPlotArea().getActualY();
	double w = chart.getPlotArea().getActualWidth();
	double h = chart.getPlotArea().getActualHeight();
	// حفظ العرض التقديمي
	pres.save(dataDir + "Result.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## خاتمة

في هذا البرنامج التعليمي، تعمقنا في عالم العمل مع المخططات في عروض PowerPoint التقديمية باستخدام Aspose.Slides لجافا. غطينا الخطوات الأساسية للتحقق من صحة تخطيط المخطط، واسترجاع موقعه وحجمه، وحفظ العرض التقديمي المعدّل. إليك ملخص سريع:

## الأسئلة الشائعة

### كيف يمكنني تغيير نوع الرسم البياني؟

لتغيير نوع الرسم البياني، قم ببساطة باستبدال `ChartType.ClusteredColumn` مع نوع الرسم البياني المطلوب في `addChart()` طريقة.

### هل يمكنني تخصيص بيانات الرسم البياني؟

نعم، يمكنك تخصيص بيانات المخطط بإضافة وتعديل سلاسل البيانات والفئات والقيم. راجع وثائق Aspose.Slides لمزيد من التفاصيل.

### ماذا لو أردت تعديل خصائص الرسم البياني الأخرى؟

يمكنك الوصول إلى خصائص متنوعة للمخططات وتخصيصها وفقًا لاحتياجاتك. اطلع على وثائق Aspose.Slides للحصول على معلومات شاملة حول التعامل مع المخططات.


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}