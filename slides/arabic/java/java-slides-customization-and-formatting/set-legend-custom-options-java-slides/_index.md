---
"description": "تعرّف على كيفية تخصيص خيارات التسمية التوضيحية في شرائح جافا باستخدام Aspose.Slides لجافا. خصّص موضع وحجم التسمية التوضيحية في مخططات PowerPoint."
"linktitle": "تعيين خيارات الأسطورة المخصصة في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "تعيين خيارات الأسطورة المخصصة في شرائح Java"
"url": "/ar/java/customization-and-formatting/set-legend-custom-options-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تعيين خيارات الأسطورة المخصصة في شرائح Java


## مقدمة لتعيين خيارات الأسطورة المخصصة في شرائح Java

في هذا البرنامج التعليمي، سنوضح كيفية تخصيص خصائص التسمية التوضيحية للمخطط في عرض تقديمي على PowerPoint باستخدام Aspose.Slides لجافا. يمكنك تعديل موضع التسمية التوضيحية وحجمها وخصائصها الأخرى لتناسب احتياجات عرضك التقديمي.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- تم تثبيت Aspose.Slides لـ Java API.
- تم إعداد بيئة تطوير Java.

## الخطوة 1: استيراد الفئات الضرورية:

```java
// استيراد Aspose.Slides لفئات Java
import com.aspose.slides.*;
```

## الخطوة 2: حدد المسار إلى دليل المستند الخاص بك:

```java
String dataDir = "Your Document Directory";
```

## الخطوة 3: إنشاء مثيل لـ `Presentation` فصل:

```java
Presentation presentation = new Presentation();
```

## الخطوة 4: إضافة شريحة إلى العرض التقديمي:

```java
try {
    ISlide slide = presentation.getSlides().get_Item(0);
```

## الخطوة 5: إضافة مخطط عمودي مجمع إلى الشريحة:

```java
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
```

## الخطوة 6. تعيين خصائص الأسطورة:

- تعيين موضع X للأسطورة (بالنسبة لعرض الرسم البياني):

```java
chart.getLegend().setX(50 / chart.getWidth());
```

- تعيين موضع Y للأسطورة (بالنسبة لارتفاع الرسم البياني):

```java
chart.getLegend().setY(50 / chart.getHeight());
```

- تعيين عرض الأسطورة (بالنسبة لعرض الرسم البياني):

```java
chart.getLegend().setWidth(100 / chart.getWidth());
```

- تعيين ارتفاع الأسطورة (بالنسبة لارتفاع الرسم البياني):

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

هذا كل شيء! لقد نجحت في تخصيص خصائص التسمية التوضيحية للمخطط في عرض تقديمي على PowerPoint باستخدام Aspose.Slides لـ Java.

## كود المصدر الكامل لخيارات تعيين الأسطورة المخصصة في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء مثيل لفئة العرض التقديمي
Presentation presentation = new Presentation();
try
{
	// احصل على مرجع الشريحة
	ISlide slide = presentation.getSlides().get_Item(0);
	// أضف مخططًا عموديًا مجمعًا على الشريحة
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
	// تعيين خصائص الأسطورة
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

في هذا البرنامج التعليمي، تعلمنا كيفية تخصيص خصائص التسمية التوضيحية للمخطط في عرض تقديمي على PowerPoint باستخدام Aspose.Slides لجافا. يمكنك تعديل موضع التسمية التوضيحية وحجمها وخصائص أخرى لإنشاء عروض تقديمية جذابة بصريًا وغنية بالمعلومات.

## الأسئلة الشائعة

## كيف يمكنني تغيير موضع الأسطورة؟

لتغيير موضع الأسطورة، استخدم `setX` و `setY` طرق كائن الأسطورة. يتم تحديد القيم وفقًا لعرض وارتفاع الرسم البياني.

## كيف يمكنني تعديل حجم الأسطورة؟

يمكنك تعديل حجم الأسطورة باستخدام `setWidth` و `setHeight` طرق كائن الأسطورة. هذه القيم مرتبطة أيضًا بعرض وارتفاع الرسم البياني.

## هل يمكنني تخصيص سمات الأسطورة الأخرى؟

نعم، يمكنك تخصيص سمات متنوعة للتوضيح، مثل نمط الخط، والحدود، ولون الخلفية، وغيرها. اطلع على وثائق Aspose.Slides لمزيد من المعلومات حول تخصيص التوضيحات.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}