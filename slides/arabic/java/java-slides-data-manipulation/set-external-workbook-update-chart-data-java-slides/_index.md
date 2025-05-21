---
"description": "تعلّم كيفية إعداد مصنفات خارجية وتحديث بيانات المخططات في شرائح جافا باستخدام Aspose.Slides لجافا. حسّن مهاراتك في أتمتة PowerPoint."
"linktitle": "تعيين مصنف خارجي مع تحديث بيانات الرسم البياني في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "تعيين مصنف خارجي مع تحديث بيانات الرسم البياني في شرائح Java"
"url": "/ar/java/data-manipulation/set-external-workbook-update-chart-data-java-slides/"
"weight": 20
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تعيين مصنف خارجي مع تحديث بيانات الرسم البياني في شرائح Java


## مقدمة لتعيين مصنف خارجي مع تحديث بيانات الرسم البياني في شرائح Java

في هذا الدليل الشامل، سنشرح لك عملية إعداد مصنف خارجي ببيانات مخططات مُحدثة في Java Slides باستخدام واجهة برمجة تطبيقات Aspose.Slides for Java. تتيح لك هذه المكتبة القوية التعامل مع عروض PowerPoint التقديمية برمجيًا، مما يُسهّل أتمتة مهام مثل تحديث بيانات المخططات من مصدر خارجي. بنهاية هذا البرنامج التعليمي، ستفهم كيفية تحقيق هذه المهمة بوضوح من خلال تعليمات خطوة بخطوة وأكواد Java المُرفقة.

## المتطلبات الأساسية

قبل أن نتعمق في التنفيذ، تأكد من توفر المتطلبات الأساسية التالية:

1. Aspose.Slides لجافا: يجب أن تكون مكتبة Aspose.Slides لجافا مثبتة لديك. يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/java/).

2. بيئة تطوير Java: تأكد من إعداد بيئة تطوير Java على نظامك.

## الخطوة 1: إنشاء عرض تقديمي جديد

للبدء، لنُنشئ عرضًا تقديميًا جديدًا على PowerPoint باستخدام Aspose.Slides لجافا. إليك كود جافا للقيام بذلك:

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## الخطوة 2: إضافة مخطط

الآن، لنُضِف مخططًا لعرضنا التقديمي. سنُنشئ مخططًا دائريًا في هذا المثال:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
```

## الخطوة 3: تعيين مصنف خارجي

هنا نُعيّن المصنف الخارجي كمصدر بيانات لمخططنا. يجب عليك توفير رابط URL للمصنف الخارجي، حتى لو لم يكن موجودًا حاليًا:

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook("http://المسار/غير/موجود"، خطأ)؛
```

## الخطوة 4: حفظ العرض التقديمي

وأخيرًا، احفظ العرض التقديمي باستخدام بيانات الرسم البياني المحدثة:

```java
pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
```

## كود المصدر الكامل لتعيين مصنف خارجي مع تحديث بيانات الرسم البياني في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
	IChartData chartData = chart.getChartData();
	chartData.setExternalWorkbook("http://المسار/غير/موجود"، خطأ)؛
	pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## خاتمة

تهانينا! لقد تعلمت كيفية إعداد مصنف خارجي ببيانات مخطط مُحدثة في شرائح جافا باستخدام Aspose.Slides لجافا. يُعد هذا مفيدًا للغاية لتحديث المخططات ديناميكيًا في عروض PowerPoint التقديمية من مصادر بيانات خارجية.

## الأسئلة الشائعة

### كيف يمكنني تحديث بيانات المصنف الخارجي للرسم البياني؟

لتحديث بيانات المصنف الخارجي للمخطط، ما عليك سوى تعديل بياناته على عنوان URL المحدد. في المرة التالية التي تفتح فيها العرض التقديمي، سيجلب Aspose.Slides for Java البيانات المُحدثة من المصنف الخارجي ويُحدّث المخطط وفقًا لذلك.

### هل يمكنني استخدام ملف محلي كمصنف خارجي؟

نعم، يمكنك استخدام ملف محلي كمصنف خارجي عن طريق توفير مسار الملف بدلاً من عنوان URL. فقط تأكد من صحة مسار الملف وإمكانية الوصول إليه من تطبيق Java.

### هل هناك أي قيود على استخدام المصنفات الخارجية مع Aspose.Slides لـ Java؟

مع أن استخدام المصنفات الخارجية ميزة فعّالة، تذكّر أن توفر بيانات المصنف الخارجي يعتمد على إمكانية الوصول إليها عبر عنوان URL أو مسار الملف المُقدّم. تأكد من توفر مصدر البيانات الخارجي عند فتح العرض التقديمي لتجنب مشاكل استرجاع البيانات.

### هل يمكنني تخصيص مظهر الرسم البياني بعد إعداد المصنف الخارجي؟

نعم، يمكنك تخصيص مظهر المخطط، بما في ذلك عنوانه وتسمياته وألوانه والمزيد، حتى بعد إعداد المصنف الخارجي. يوفر Aspose.Slides لـ Java خيارات تنسيق شاملة للمخططات لتلبية احتياجاتك.

### أين يمكنني العثور على مزيد من الوثائق والموارد الخاصة بـ Aspose.Slides لـ Java؟

للحصول على توثيق مفصل وموارد إضافية، قم بزيارة توثيق Aspose.Slides لـ Java على [هنا](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}