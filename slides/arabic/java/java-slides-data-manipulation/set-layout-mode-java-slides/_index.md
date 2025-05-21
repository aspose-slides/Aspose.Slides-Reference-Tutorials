---
"description": "تعرّف على كيفية ضبط أوضاع تخطيط شرائح جافا باستخدام Aspose.Slides. خصّص موضع وحجم المخطط في هذا الدليل المفصّل مع الكود المصدري."
"linktitle": "تعيين وضع التخطيط في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "تعيين وضع التخطيط في شرائح Java"
"url": "/ar/java/data-manipulation/set-layout-mode-java-slides/"
"weight": 23
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تعيين وضع التخطيط في شرائح Java


## مقدمة لتعيين وضع التخطيط في شرائح Java

في هذا البرنامج التعليمي، سنتعلم كيفية ضبط وضع تخطيط مخطط في شرائح جافا باستخدام Aspose.Slides لجافا. يحدد وضع التخطيط موضع المخطط وحجمه داخل الشريحة.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من تثبيت مكتبة Aspose.Slides لجافا وإعدادها في مشروع جافا. يمكنك تنزيل المكتبة من [هنا](https://releases.aspose.com/slides/java/).

## الخطوة 1: إنشاء عرض تقديمي

أولاً، نحتاج إلى إنشاء عرض تقديمي جديد.

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## الخطوة 2: إضافة شريحة ومخطط

بعد ذلك، سنضيف شريحةً ومخططًا بيانيًا إليها. في هذا المثال، سننشئ مخططًا بيانيًا عموديًا مجمعًا.

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

## الخطوة 3: تعيين تخطيط الرسم البياني

الآن، لنُحدد تخطيط الرسم البياني. سنضبط موضع وحجم الرسم البياني داخل الشريحة باستخدام `setX`، `setY`، `setWidth`، `setHeight` الأساليب. بالإضافة إلى ذلك، سنقوم بتعيين `LayoutTargetType` لتحديد وضع التخطيط.

```java
chart.getPlotArea().setX(0.2f);
chart.getPlotArea().setY(0.2f);
chart.getPlotArea().setWidth(0.7f);
chart.getPlotArea().setHeight(0.7f);
chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
```

في هذا المثال، قمنا بتعيين الرسم البياني ليكون نوع هدف التخطيط الخاص به "داخلي"، مما يعني أنه سيتم وضعه وحجمه بالنسبة للمنطقة الداخلية للشريحة.

## الخطوة 4: حفظ العرض التقديمي

وأخيرًا، دعنا نحفظ العرض التقديمي بإعدادات تخطيط الرسم البياني.

```java
presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
```

## كود المصدر الكامل لوضع التخطيط المحدد في شرائح Java

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
try
{
	ISlide slide = presentation.getSlides().get_Item(0);
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
	chart.getPlotArea().setX(0.2f);
	chart.getPlotArea().setY(0.2f);
	chart.getPlotArea().setWidth(0.7f);
	chart.getPlotArea().setHeight(0.7f);
	chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
	presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية ضبط وضع تخطيط مخطط في شرائح جافا باستخدام Aspose.Slides لجافا. يمكنك تخصيص موضع وحجم المخطط وفقًا لاحتياجاتك الخاصة عن طريق ضبط القيم في `setX`، `setY`، `setWidth`، `setHeight`، و `setLayoutTargetType` الأساليب. يتيح لك هذا التحكم في وضع المخططات داخل الشرائح الخاصة بك.

## الأسئلة الشائعة

### كيف يمكنني تغيير وضع التخطيط للرسم البياني في Aspose.Slides لـ Java؟

لتغيير وضع التخطيط للرسم البياني في Aspose.Slides لـ Java، يمكنك استخدام `setLayoutTargetType` طريقة على منطقة رسم المخطط. يمكنك ضبطها على أيٍّ من `LayoutTargetType.Inner` أو `LayoutTargetType.Outer` اعتمادًا على التصميم المطلوب.

### هل يمكنني تخصيص موضع وحجم الرسم البياني داخل الشريحة؟

نعم، يمكنك تخصيص موضع وحجم الرسم البياني داخل الشريحة باستخدام `setX`، `setY`، `setWidth`، و `setHeight` استخدم الطرق على مساحة رسم المخطط. اضبط هذه القيم لتحديد موضع وحجم المخطط وفقًا لمتطلباتك.

### أين يمكنني العثور على مزيد من المعلومات حول Aspose.Slides لـ Java؟

يمكنك العثور على مزيد من المعلومات حول Aspose.Slides لـ Java في [التوثيق](https://reference.aspose.com/slides/java/)إنه يتضمن مراجع API مفصلة وأمثلة لمساعدتك على العمل مع الشرائح والمخططات بشكل فعال في Java.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}