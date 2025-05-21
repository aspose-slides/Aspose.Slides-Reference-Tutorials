---
"description": "تعرّف على كيفية استرداد المصنفات من الرسوم البيانية في Java Slides باستخدام Aspose.Slides. دليل خطوة بخطوة لأتمتة PowerPoint."
"linktitle": "استعادة مصنف الرسم البياني في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "استعادة مصنف الرسم البياني في شرائح Java"
"url": "/ar/java/data-manipulation/chart-recover-workbook-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# استعادة مصنف الرسم البياني في شرائح Java


## مقدمة إلى Chart Recover Workbook في Java Slides

عند العمل على عروض PowerPoint التقديمية بلغة Java، قد تواجه حالات تتطلب استرداد بيانات المصنف من مخطط بياني. تُعد هذه مهمة بالغة الأهمية، خاصةً عند التعامل مع العروض التقديمية المعتمدة على البيانات. يُبسط Aspose.Slides لـ Java هذه العملية، وسنوضح لك في هذا الدليل كيفية القيام بذلك.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:

- تم تثبيت Java Development Kit (JDK) على نظامك.
- مكتبة Aspose.Slides لجافا. يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/java/).

## الخطوة 1: إعداد مشروعك

قم بإنشاء مشروع Java جديد في بيئة التطوير المتكاملة (IDE) المفضلة لديك وأضف مكتبة Aspose.Slides for Java إلى تبعيات مشروعك.

## الخطوة 2: استيراد الفئات الضرورية

في كود Java الخاص بك، قم باستيراد الفئات المطلوبة من Aspose.Slides لـ Java:

```java
import com.aspose.slides.*;
```

## الخطوة 3: تحميل العرض التقديمي

قم بتحميل عرض PowerPoint الذي يحتوي على المخطط الذي تريد استرداد بيانات المصنف منه:

```java
String dataDir = "Your Document Directory";
String pptxFile = dataDir + "ExternalWB.pptx";
String outPptxFile = "Path to Output File";
LoadOptions lo = new LoadOptions();
lo.getSpreadsheetOptions().setRecoverWorkbookFromChartCache(true);
Presentation pres = new Presentation(pptxFile, lo);
```

## الخطوة 4: الوصول إلى بيانات الرسم البياني

الآن، يمكنك الوصول إلى بيانات الرسم البياني واستعادة المصنف:

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

## كود المصدر الكامل لبرنامج Chart Recovery Workbook في Java Slides

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

في هذا الدليل، شرحنا عملية استرداد مصنف من مخطط في Java Slides باستخدام Aspose.Slides for Java. تُبسّط هذه المكتبة المهمة، مما يُسهّل على المطورين العمل مع عروض PowerPoint التقديمية برمجيًا. الآن، يمكنك التعامل بثقة مع العروض التقديمية القائمة على البيانات واستخراج معلومات المصنف حسب الحاجة.

## الأسئلة الشائعة

### كيف أقوم بتثبيت Aspose.Slides لـ Java؟

يمكن تثبيت Aspose.Slides for Java بسهولة عن طريق تنزيل المكتبة من موقع الويب على [هنا](https://releases.aspose.com/slides/java/)اتبع تعليمات التثبيت المقدمة لدمجها في مشروع Java الخاص بك.

### هل يمكنني استعادة بيانات المصنف من أي مخطط في عرض تقديمي في PowerPoint؟

نعم، يمكنك استرداد بيانات المصنف من أي مخطط في عرض تقديمي على PowerPoint، شريطة أن تكون لديك مكتبة Aspose.Slides لـ Java وأن يكون المخطط متاحًا داخل العرض التقديمي. يوضح مقتطف التعليمات البرمجية المرفق كيفية تحقيق ذلك.

### هل هناك أي خيارات إضافية للعمل مع بيانات الرسم البياني باستخدام Aspose.Slides لـ Java؟

نعم، يوفر Aspose.Slides لجافا مجموعة واسعة من الخيارات للتعامل مع بيانات المخططات. يمكنك تعديل خصائص المخطط، واسترجاع نقاط البيانات، وإجراء عمليات متنوعة عليه لتلبية احتياجاتك الخاصة.

### هل برنامج Aspose.Slides for Java مناسب لأتمتة PowerPoint الاحترافية؟

بالتأكيد! Aspose.Slides لجافا مكتبة فعّالة لأتمتة مهام PowerPoint، مما يجعلها مناسبة للاستخدامات المهنية الأساسية والمتقدمة. توفر ميزات شاملة لإنشاء عروض PowerPoint التقديمية وتعديلها وإدارتها برمجيًا.

### كيف يمكنني الوصول إلى مزيد من الوثائق الخاصة بـ Aspose.Slides لـ Java؟

للحصول على وثائق ومراجع مفصلة حول Aspose.Slides لـ Java، تفضل بزيارة صفحة الوثائق على [هنا](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}