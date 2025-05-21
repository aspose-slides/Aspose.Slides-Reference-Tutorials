---
"description": "تعرّف على كيفية ضبط خصائص الخطوط في شرائح جافا باستخدام Aspose.Slides لجافا. يتضمن هذا الدليل خطوة بخطوة أمثلةً برمجيةً وأسئلةً شائعة."
"linktitle": "ضبط خصائص الخط في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "ضبط خصائص الخط في شرائح Java"
"url": "/ar/java/customization-and-formatting/setting-font-properties-java-slides/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# ضبط خصائص الخط في شرائح Java


## مقدمة لتعيين خصائص الخط في شرائح Java

في هذا البرنامج التعليمي، سنستكشف كيفية ضبط خصائص الخط في شرائح جافا باستخدام Aspose.Slides. يمكنك تخصيص خصائص الخط، مثل سماكة الخط وحجمه، لتحسين مظهر شرائحك.

## المتطلبات الأساسية

قبل البدء، تأكد من إضافة مكتبة Aspose.Slides لجافا إلى مشروعك. يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/java/).

## الخطوة 1: تهيئة العرض التقديمي

أولاً، عليك تهيئة كائن العرض التقديمي عن طريق تحميل ملف PowerPoint موجود. استبدل `"Your Document Directory"` مع المسار الفعلي إلى دليل المستند الخاص بك.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## الخطوة 2: إضافة مخطط

في هذا المثال، سنعمل على مخطط في الشريحة الأولى. يمكنك تغيير فهرس الشريحة حسب احتياجاتك. سنضيف مخططًا عموديًا مجمعًا ونفعّل جدول البيانات.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
chart.setDataTable(true);
```

## الخطوة 3: تخصيص خصائص الخط

الآن، لنُخصّص خصائص خط جدول بيانات الرسم البياني. سنضبط الخط ليكون عريضًا ونعدّل ارتفاعه (حجمه).

```java
chart.getChartDataTable().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
chart.getChartDataTable().getTextFormat().getPortionFormat().setFontHeight(20);
```

- `setFontBold(NullableBool.True)`:يعمل هذا السطر على ضبط الخط ليصبح غامقًا.
- `setFontHeight(20)`هذا السطر يُعيّن ارتفاع الخط إلى ٢٠ نقطة. يُمكنك تعديل هذه القيمة حسب الحاجة.

## الخطوة 4: حفظ العرض التقديمي

أخيرًا، احفظ العرض التقديمي المُعدَّل في ملف جديد. يمكنك تحديد صيغة الإخراج؛ في هذه الحالة، سنحفظه كملف PPTX.

```java
pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
```

## كود المصدر الكامل لتعيين خصائص الخط في شرائح Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	chart.setDataTable(true);
	chart.getChartDataTable().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
	chart.getChartDataTable().getTextFormat().getPortionFormat().setFontHeight(20);
	pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## خاتمة

في هذا البرنامج التعليمي، تعلمت كيفية ضبط خصائص الخط للنص في شرائح جافا باستخدام Aspose.Slides for Java. يمكنك تطبيق هذه التقنيات لتحسين مظهر النص في عروض PowerPoint التقديمية.

## الأسئلة الشائعة

### كيف يمكنني تغيير لون الخط؟

لتغيير لون الخط، استخدم `setFontColor` الطريقة وحدد اللون المطلوب. على سبيل المثال:

```java
chart.getChartDataTable().getTextFormat().getPortionFormat().setFontColor(Color.RED);
```

### هل يمكنني تغيير الخط للنصوص الأخرى في الشرائح؟

نعم، يمكنك تغيير خط عناصر نصية أخرى في الشرائح، مثل العناوين والملصقات. استخدم العناصر والأساليب المناسبة للوصول إلى خصائص الخط وتخصيصها لعناصر نصية محددة.

### كيف أقوم بتعيين نمط الخط المائل؟

لتعيين نمط الخط إلى مائل، استخدم `setFontItalic` طريقة:

```java
chart.getChartDataTable().getTextFormat().getPortionFormat().setFontItalic(NullableBool.True);
```

ضبط `NullableBool.True` المعلمة حسب الحاجة لتمكين أو تعطيل النمط المائل.

### كيف يمكنني تغيير الخط الخاص بتسميات البيانات في الرسم البياني؟

لتغيير خط تسميات البيانات في مخطط بياني، يجب الوصول إلى تنسيق نص تسميات البيانات بالطرق المناسبة. على سبيل المثال:

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0); // تغيير الفهرس حسب الحاجة
series.getLabels().getDefaultDataLabelFormat().getPortionFormat().setFontBold(NullableBool.True);
```

يقوم هذا الكود بتعيين خط تسميات البيانات في السلسلة الأولى إلى غامق.

### كيف يمكنني تغيير الخط لجزء معين من النص؟

إذا كنت تريد تغيير الخط لجزء معين من النص داخل عنصر النص، فيمكنك استخدام `PortionFormat` قم بالوصول إلى الجزء الذي تريد تعديله، ثم اضبط خصائص الخط المطلوبة.

```java
IAutoShape textShape = (IAutoShape)slide.getShapes().get_Item(0); // تغيير الفهرس حسب الحاجة
ITextFrame textFrame = textShape.getTextFrame();
IParagraph paragraph = textFrame.getParagraphs().get_Item(0); // تغيير الفهرس حسب الحاجة
IPortion portion = paragraph.getPortions().get_Item(0); // تغيير الفهرس حسب الحاجة

portion.getPortionFormat().setFontBold(NullableBool.True);
portion.getPortionFormat().setFontHeight(24);
```

يقوم هذا الكود بتعيين خط الجزء الأول من النص داخل الشكل إلى خط غامق وضبط ارتفاع الخط.

### كيف يمكنني تطبيق تغييرات الخط على كافة الشرائح في العرض التقديمي؟

لتطبيق تغييرات الخط على جميع شرائح العرض التقديمي، يمكنك التنقل بين الشرائح وتعديل خصائص الخط حسب الحاجة. استخدم حلقة للوصول إلى كل شريحة وعناصر النص فيها، ثم خصّص خصائص الخط.

```java
for (ISlide slide : pres.getSlides()) {
    // يمكنك الوصول إلى خصائص خطوط عناصر النص وتخصيصها هنا
}
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}