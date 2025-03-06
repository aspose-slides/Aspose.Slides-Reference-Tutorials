---
title: قم بتعيين خيارات Legend المخصصة في شرائح Java
linktitle: قم بتعيين خيارات Legend المخصصة في شرائح Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية تعيين خيارات وسيلة الإيضاح المخصصة في Java Slides باستخدام Aspose.Slides لـ Java. قم بتخصيص موضع وسيلة الإيضاح وحجمها في مخططات PowerPoint الخاصة بك.
weight: 14
url: /ar/java/customization-and-formatting/set-legend-custom-options-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## مقدمة لتعيين خيارات وسيلة الإيضاح المخصصة في شرائح Java

في هذا البرنامج التعليمي، سنوضح كيفية تخصيص خصائص وسيلة الإيضاح للمخطط في عرض تقديمي لـ PowerPoint باستخدام Aspose.Slides for Java. يمكنك تعديل موضع وسيلة الإيضاح وحجمها وسماتها الأخرى لتناسب احتياجات العرض التقديمي الخاص بك.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- تم تثبيت Aspose.Slides لـ Java API.
- إعداد بيئة تطوير جافا.

## الخطوة 1: استيراد الفئات الضرورية:

```java
// استيراد Aspose.Slides لفئات Java
import com.aspose.slides.*;
```

## الخطوة 2: حدد المسار إلى دليل المستند الخاص بك:

```java
String dataDir = "Your Document Directory";
```

##  الخطوة 3: إنشاء مثيل لـ`Presentation` class:

```java
Presentation presentation = new Presentation();
```

## الخطوة 4: إضافة شريحة إلى العرض التقديمي:

```java
try {
    ISlide slide = presentation.getSlides().get_Item(0);
```

## الخطوة 5: إضافة مخطط عمودي متفاوت المسافات إلى الشريحة:

```java
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
```

## الخطوة 6. تعيين خصائص وسيلة الإيضاح:

- قم بتعيين موضع X لوسيلة الإيضاح (بالنسبة لعرض المخطط):

```java
chart.getLegend().setX(50 / chart.getWidth());
```

- قم بتعيين موضع Y لوسيلة الإيضاح (بالنسبة لارتفاع المخطط):

```java
chart.getLegend().setY(50 / chart.getHeight());
```

- قم بتعيين عرض وسيلة الإيضاح (بالنسبة لعرض المخطط):

```java
chart.getLegend().setWidth(100 / chart.getWidth());
```

- قم بتعيين ارتفاع وسيلة الإيضاح (بالنسبة لارتفاع المخطط):

```java
chart.getLegend().setHeight(100 / chart.getHeight());
```

## الخطوة 7: حفظ العرض التقديمي على القرص:

```java
    presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
} finally {
    if (presentation != null) presentation.dispose();
}
```

هذا كل شيء! لقد نجحت في تخصيص خصائص وسيلة الإيضاح للمخطط في عرض PowerPoint التقديمي باستخدام Aspose.Slides لـ Java.

## أكمل كود المصدر لتعيين خيارات Legend المخصصة في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء مثيل لفئة العرض التقديمي
Presentation presentation = new Presentation();
try
{
	// الحصول على مرجع الشريحة
	ISlide slide = presentation.getSlides().get_Item(0);
	// أضف مخططًا عموديًا متفاوت المسافات على الشريحة
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
	// تعيين خصائص وسيلة الإيضاح
	chart.getLegend().setX(50 / chart.getWidth());
	chart.getLegend().setY(50 / chart.getHeight());
	chart.getLegend().setWidth(100 / chart.getWidth());
	chart.getLegend().setHeight(100 / chart.getHeight());
	// كتابة العرض التقديمي على القرص
	presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```
## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية تخصيص خصائص وسيلة الإيضاح للمخطط في عرض PowerPoint التقديمي باستخدام Aspose.Slides لـ Java. يمكنك تعديل موضع وسيلة الإيضاح وحجمها وسماتها الأخرى لإنشاء عروض تقديمية جذابة وغنية بالمعلومات.

## الأسئلة الشائعة

## كيف يمكنني تغيير موضع الأسطورة؟

 لتغيير موضع وسيلة الإيضاح، استخدم`setX` و`setY` طرق كائن الأسطورة. يتم تحديد القيم نسبةً إلى عرض المخطط وارتفاعه.

## كيف يمكنني ضبط حجم وسيلة الإيضاح؟

 يمكنك ضبط حجم وسيلة الإيضاح باستخدام`setWidth` و`setHeight` طرق كائن الأسطورة. ترتبط هذه القيم أيضًا بعرض المخطط وارتفاعه.

## هل يمكنني تخصيص سمات وسيلة الإيضاح الأخرى؟

نعم، يمكنك تخصيص سمات مختلفة لوسيلة الإيضاح، مثل نمط الخط والحدود ولون الخلفية والمزيد. استكشف وثائق Aspose.Slides للحصول على معلومات تفصيلية حول تخصيص وسائل الإيضاح بشكل أكبر.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
