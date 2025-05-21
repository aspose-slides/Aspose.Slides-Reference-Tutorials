---
"description": "حسّن خصائص خطوط المخططات في شرائح جافا باستخدام Aspose.Slides لجافا. خصّص حجم الخط ونمطه ولونه لعروض تقديمية مؤثرة."
"linktitle": "خصائص الخط للرسم البياني في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "خصائص الخط للرسم البياني في شرائح Java"
"url": "/ar/java/customization-and-formatting/font-properties-for-chart-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# خصائص الخط للرسم البياني في شرائح Java


## مقدمة لخصائص الخطوط للمخططات في شرائح Java

سيرشدك هذا الدليل إلى كيفية ضبط خصائص الخط في مخطط بياني في Java Slides باستخدام Aspose.Slides. يمكنك تخصيص حجم الخط ومظهر نص المخطط البياني لتحسين المظهر البصري لعروضك التقديمية.

## المتطلبات الأساسية

قبل البدء، تأكد من دمج واجهة برمجة تطبيقات Aspose.Slides لـ Java في مشروعك. إذا لم تكن قد فعلت ذلك بالفعل، يمكنك تنزيلها من [توثيق Aspose.Slides لـ Java](https://reference.aspose.com/slides/java/).

## الخطوة 1: إنشاء عرض تقديمي

أولاً، قم بإنشاء عرض تقديمي جديد باستخدام الكود التالي:

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## الخطوة 2: إضافة مخطط

الآن، دعنا نضيف مخططًا عموديًا مجمعًا إلى العرض التقديمي الخاص بك:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
```

هنا، نضيف مخططًا عموديًا مجمعًا إلى الشريحة الأولى عند الإحداثيات (100، 100) بعرض 500 وحدة وارتفاع 400 وحدة.

## الخطوة 3: تخصيص خصائص الخط

بعد ذلك، سنُخصّص خصائص خط الرسم البياني. في هذا المثال، سنضبط حجم الخط على 20 لجميع نصوص الرسم البياني:

```java
chart.getTextFormat().getPortionFormat().setFontHeight(20);
```

يقوم هذا الكود بتعيين حجم الخط إلى 20 نقطة لجميع النصوص الموجودة داخل الرسم البياني.

## الخطوة 4: إظهار تسميات البيانات

يمكنك أيضًا إظهار تسميات البيانات على الرسم البياني باستخدام الكود التالي:

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

يتيح لك هذا السطر من التعليمات البرمجية إنشاء تسميات بيانات للسلسلة الأولى في الرسم البياني، وعرض القيم على أعمدة الرسم البياني.

## الخطوة 5: حفظ العرض التقديمي

أخيرًا، احفظ العرض التقديمي باستخدام خصائص الخط المخطط المخصص لك:

```java
pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
```

سيقوم هذا الكود بحفظ العرض التقديمي في الدليل المحدد باسم الملف "FontPropertiesForChart.pptx".

## كود المصدر الكامل لخصائص الخطوط للرسم البياني في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
	chart.getTextFormat().getPortionFormat().setFontHeight(20);
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## خاتمة

في هذا البرنامج التعليمي، تعلمت كيفية تخصيص خصائص الخطوط لمخطط في شرائح جافا باستخدام Aspose.Slides لجافا. يمكنك تطبيق هذه التقنيات لتحسين مظهر مخططاتك وعروضك التقديمية. استكشف المزيد من الخيارات في [توثيق Aspose.Slides لـ Java](https://reference.aspose.com/slides/java/).

## الأسئلة الشائعة

### كيف يمكنني تغيير لون الخط؟

لتغيير لون الخط لنص الرسم البياني، استخدم `chart.getTextFormat().getPortionFormat().setFontColor(Color.RED);`، استبدال `Color.RED` مع اللون المطلوب.

### هل يمكنني تغيير نوع الخط (غامق، مائل، الخ)؟

نعم، يمكنك تغيير نمط الخط. استخدم `chart.getTextFormat().getPortionFormat().setFontBold(true);` لجعل الخط عريضًا. وبالمثل، يمكنك استخدام `setFontItalic(true)` لجعله مائلًا.

### كيف يمكنني تخصيص خصائص الخط لعناصر الرسم البياني المحددة؟

لتخصيص خصائص الخط لعناصر مخطط محددة، مثل تسميات المحور أو نص التسمية التوضيحية، يمكنك الوصول إلى هذه العناصر وتعيين خصائص الخط الخاصة بها باستخدام طرق مماثلة كما هو موضح أعلاه.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}