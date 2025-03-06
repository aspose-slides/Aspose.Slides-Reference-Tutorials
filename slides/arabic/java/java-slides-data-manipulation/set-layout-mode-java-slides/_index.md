---
title: اضبط وضع التخطيط في شرائح Java
linktitle: اضبط وضع التخطيط في شرائح Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية تعيين أوضاع التخطيط لشرائح Java باستخدام Aspose.Slides. قم بتخصيص موضع الرسم البياني وحجمه في هذا الدليل المفصّل خطوة بخطوة باستخدام التعليمات البرمجية المصدر.
weight: 23
url: /ar/java/data-manipulation/set-layout-mode-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## مقدمة لتعيين وضع التخطيط في شرائح جافا

في هذا البرنامج التعليمي، سوف نتعلم كيفية تعيين وضع التخطيط لمخطط في شرائح Java باستخدام Aspose.Slides for Java. يحدد وضع التخطيط موضع المخطط وحجمه داخل الشريحة.

## المتطلبات الأساسية

 قبل أن نبدأ، تأكد من تثبيت مكتبة Aspose.Slides for Java وإعدادها في مشروع Java الخاص بك. يمكنك تحميل المكتبة من[هنا](https://releases.aspose.com/slides/java/).

## الخطوة 1: إنشاء عرض تقديمي

أولاً، نحتاج إلى إنشاء عرض تقديمي جديد.

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## الخطوة 2: إضافة شريحة ومخطط

بعد ذلك، سنضيف شريحة ومخططًا إليها. في هذا المثال، سنقوم بإنشاء مخطط عمودي متفاوت المسافات.

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

## الخطوة 3: تعيين تخطيط الرسم البياني

 الآن، دعونا نضبط التخطيط للمخطط. سنقوم بضبط موضع وحجم المخطط داخل الشريحة باستخدام`setX`, `setY`, `setWidth`, `setHeight` طُرق. بالإضافة إلى ذلك، سوف نقوم بتعيين`LayoutTargetType` لتحديد وضع التخطيط.

```java
chart.getPlotArea().setX(0.2f);
chart.getPlotArea().setY(0.2f);
chart.getPlotArea().setWidth(0.7f);
chart.getPlotArea().setHeight(0.7f);
chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
```

في هذا المثال، قمنا بتعيين المخطط بحيث يكون نوع تخطيطه المستهدف هو "داخلي"، مما يعني أنه سيتم تحديد موضعه وحجمه بالنسبة للمنطقة الداخلية للشريحة.

## الخطوة 4: احفظ العرض التقديمي

وأخيرًا، لنحفظ العرض التقديمي باستخدام إعدادات تخطيط المخطط.

```java
presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
```

## أكمل كود المصدر لتعيين وضع التخطيط في شرائح Java

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

 في هذا البرنامج التعليمي، تعلمنا كيفية تعيين وضع التخطيط لمخطط في شرائح Java باستخدام Aspose.Slides for Java. يمكنك تخصيص موضع المخطط وحجمه وفقًا لمتطلباتك المحددة عن طريق ضبط القيم في`setX`, `setY`, `setWidth`, `setHeight` ، و`setLayoutTargetType`طُرق. ويمنحك هذا التحكم في موضع المخططات داخل شرائحك.

## الأسئلة الشائعة

### كيف يمكنني تغيير وضع التخطيط لمخطط في Aspose.Slides لـ Java؟

 لتغيير وضع التخطيط لمخطط في Aspose.Slides لـ Java، يمكنك استخدام`setLayoutTargetType` الطريقة على منطقة رسم المخطط. يمكنك ضبطه على أي منهما`LayoutTargetType.Inner` أو`LayoutTargetType.Outer` اعتمادا على التخطيط المطلوب.

### هل يمكنني تخصيص موضع وحجم المخطط داخل الشريحة؟

 نعم، يمكنك تخصيص موضع وحجم المخطط داخل الشريحة باستخدام`setX`, `setY`, `setWidth` ، و`setHeight` طرق على منطقة رسم المخطط. اضبط هذه القيم لتحديد موضع المخطط وحجمه وفقًا لمتطلباتك.

### أين يمكنني العثور على مزيد من المعلومات حول Aspose.Slides لـ Java؟

 يمكنك العثور على مزيد من المعلومات حول Aspose.Slides for Java في[توثيق](https://reference.aspose.com/slides/java/). يتضمن مراجع وأمثلة تفصيلية لواجهة برمجة التطبيقات (API) لمساعدتك في العمل مع الشرائح والمخططات بشكل فعال في Java.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
