---
title: مصنف استرداد الرسم البياني في شرائح جافا
linktitle: مصنف استرداد الرسم البياني في شرائح جافا
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية استرداد المصنفات من المخططات في Java Slides باستخدام Aspose.Slides. دليل خطوة بخطوة لأتمتة PowerPoint.
weight: 17
url: /ar/java/data-manipulation/chart-recover-workbook-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## مقدمة إلى مصنف استرداد المخطط في شرائح جافا

عند العمل باستخدام عروض PowerPoint التقديمية في Java، قد تواجه سيناريوهات تحتاج فيها إلى استرداد بيانات المصنف من مخطط. يمكن أن تكون هذه مهمة حاسمة، خاصة عند التعامل مع العروض التقديمية المبنية على البيانات. يعمل Aspose.Slides for Java على تبسيط هذه العملية، وفي هذا الدليل، سنوضح لك كيفية القيام بذلك.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:

- تم تثبيت Java Development Kit (JDK) على نظامك.
-  Aspose.Slides لمكتبة جافا. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/java/).

## الخطوة 1: إعداد مشروعك

أنشئ مشروع Java جديدًا في بيئة التطوير المتكاملة (IDE) المفضلة لديك وأضف مكتبة Aspose.Slides for Java إلى تبعيات مشروعك.

## الخطوة 2: استيراد الفئات الضرورية

في كود Java الخاص بك، قم باستيراد الفئات المطلوبة من Aspose.Slides لـ Java:

```java
import com.aspose.slides.*;
```

## الخطوة 3: تحميل العرض التقديمي

قم بتحميل عرض PowerPoint التقديمي الذي يحتوي على المخطط الذي تريد استرداد بيانات المصنف منه:

```java
String dataDir = "Your Document Directory";
String pptxFile = dataDir + "ExternalWB.pptx";
String outPptxFile = "Path to Output File";
LoadOptions lo = new LoadOptions();
lo.getSpreadsheetOptions().setRecoverWorkbookFromChartCache(true);
Presentation pres = new Presentation(pptxFile, lo);
```

## الخطوة 4: الوصول إلى بيانات المخطط

يمكنك الآن الوصول إلى بيانات المخطط واسترداد المصنف:

```java
try
{
    IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    // قم بإجراء العمليات على بيانات المصنف هنا
    pres.save(outPptxFile, SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

## أكمل كود المصدر لمصنف استرداد المخطط في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
String pptxFile = dataDir + "ExternalWB.pptx";
String outPptxFile = RunExamples.OutPath + "ExternalWB_out.pptx";
LoadOptions lo = new LoadOptions();
lo.getSpreadsheetOptions().setRecoverWorkbookFromChartCache(true);
Presentation pres = new Presentation(pptxFile, lo);
try
{
	IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	pres.save(outPptxFile, SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## خاتمة

في هذا الدليل، تناولنا عملية استرداد مصنف من مخطط في Java Slides باستخدام Aspose.Slides لـ Java. تعمل هذه المكتبة على تبسيط المهمة، مما يسهل على المطورين العمل مع عروض PowerPoint التقديمية برمجياً. يمكنك الآن التعامل بثقة مع العروض التقديمية المستندة إلى البيانات واستخراج معلومات المصنف حسب الحاجة.

## الأسئلة الشائعة

### كيف أقوم بتثبيت Aspose.Slides لـ Java؟

 يمكن تثبيت Aspose.Slides for Java بسهولة عن طريق تنزيل المكتبة من موقع الويب على[هنا](https://releases.aspose.com/slides/java/). اتبع تعليمات التثبيت المقدمة لدمجها في مشروع Java الخاص بك.

### هل يمكنني استعادة بيانات المصنف من أي مخطط في عرض PowerPoint التقديمي؟

نعم، يمكنك استرداد بيانات المصنف من أي مخطط في عرض PowerPoint التقديمي طالما أن لديك مكتبة Aspose.Slides for Java ويمكن الوصول إلى المخطط من خلال العرض التقديمي. يوضح مقتطف التعليمات البرمجية المقدم كيفية تحقيق ذلك.

### هل هناك أي خيارات إضافية للعمل مع بيانات المخطط باستخدام Aspose.Slides لـ Java؟

نعم، يوفر Aspose.Slides for Java نطاقًا واسعًا من الخيارات للعمل مع بيانات المخطط. يمكنك معالجة خصائص المخطط واسترداد نقاط البيانات وتنفيذ عمليات متنوعة على المخططات لتلبية متطلباتك المحددة.

### هل Aspose.Slides for Java مناسب لأتمتة PowerPoint الاحترافية؟

قطعاً! Aspose.Slides for Java هي مكتبة قوية لأتمتة مهام PowerPoint، مما يجعلها مناسبة لحالات الاستخدام الاحترافي الأساسية والمتقدمة. فهو يوفر ميزات شاملة لإنشاء عروض PowerPoint التقديمية وتعديلها وإدارتها برمجيًا.

### كيف يمكنني الوصول إلى مزيد من الوثائق الخاصة بـ Aspose.Slides لـ Java؟

 للحصول على وثائق ومراجع مفصلة حول Aspose.Slides for Java، قم بزيارة صفحة الوثائق على[هنا](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
