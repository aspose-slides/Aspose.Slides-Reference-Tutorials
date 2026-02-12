---
date: '2026-02-12'
description: تعرّف على كيفية إنشاء المخططات وإدارتها باستخدام Aspose.Slides للغة Java.
  يوضح هذا الدليل كيفية إنشاء مخطط عمودي مجمع، ومعالجة سلاسل البيانات، وتخصيص العرض
  البصري.
keywords:
- Aspose.Slides for Java
- Java charts
- clustered column chart
title: 'كيفية إنشاء مخطط في جافا باستخدام Aspose.Slides: دليل شامل'
url: /ar/java/charts-graphs/aspose-slides-java-chart-creation-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية إنشاء مخطط في Java باستخدام Aspose.Slides

## كيفية إنشاء مخطط في Java: مقدمة
إنشاء عروض تقديمية ديناميكية غالبًا ما يتضمن تصور البيانات عبر المخططات. باستخدام **Aspose.Slides for Java**، يمكنك بسهولة **how to create chart** الكائنات، تحسين الوضوح، وإحداث تأثير أقوى على جمهورك. يشرح هذا البرنامج التعليمي كيفية إعداد المكتبة، إضافة **create clustered column chart**، إدارة السلاسل، وعكس نقاط البيانات السلبية بشكل شرطي.

**ما ستتعلمه**
- كيفية إعداد Aspose.Slides for Java.
- خطوات **create clustered column chart** في عرضك التقديمي.
- تقنيات لإدارة سلاسل المخطط ونقاط البيانات.
- طرق لعكس نقاط البيانات السلبية بشكل شرطي لتحسين التصور.
- كيفية حفظ العرض التقديمي بأمان.

### إجابات سريعة
- **ما المكتبة المستخدمة؟** Aspose.Slides for Java.
- **ما نوع المخطط المعروض؟** Clustered column chart.
- **هل يمكن عكس القيم السلبية؟** نعم، باستخدام `invertIfNegative`.
- **ما نسخة Java المطلوبة؟** JDK 16 أو أحدث.
- **هل تحتاج إلى ترخيص للإنتاج؟** نعم، ترخيص Aspose صالح.

## ما هو مخطط العمود المتجمع؟
يعرض مخطط العمود المتجمع عدة سلاسل بيانات جنبًا إلى جنب لكل فئة، مما يجعل من السهل مقارنة القيم عبر المجموعات. إنه مثالي للتقارير المالية، لوحات مبيعات، وأي سيناريو تحتاج فيه إلى مقارنة عدة مؤشرات.

## لماذا استخدام Aspose.Slides لإنشاء المخططات؟
- **تحكم كامل** في مظهر المخطط دون الاعتماد على واجهة PowerPoint.
- **إنشاء برمجي** يتيح خطوط تقارير آلية.
- **دعم متعدد المنصات** يضمن تشغيل الكود على أي نظام متوافق مع Java.
- **API غني** لتخصيص دقيق (الألوان، تسميات البيانات، العكس، إلخ).

## المتطلبات المسبقة
1. **المكتبات المطلوبة**
   - Aspose.Slides for Java (الإصدار 25.4 أو أحدث).

2. **البيئة**
   - JDK 16 أو أحدث.
   - Maven أو Gradle لإدارة التبعيات.

3. **المعرفة**
   - برمجة Java الأساسية.
   - الإلمام بأدوات البناء (Maven/Gradle).

## إعداد Aspose.Slides for Java
### تثبيت Maven
أضف التبعية التالية إلى ملف `pom.xml` الخاص بك:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### تثبيت Gradle
أضف السطر التالي إلى ملف `build.gradle` الخاص بك:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### التحميل المباشر
بدلاً من ذلك، قم بتحميل أحدث نسخة من [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### الحصول على الترخيص
- **Free Trial:** استكشاف الميزات بدون ترخيص.
- **Temporary License:** الاستخدام أثناء التقييم.
- **Full License:** الشراء للاستخدام في بيئات الإنتاج.

### التهيئة الأساسية
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
// Your code here...
pres.dispose(); // Always dispose of the presentation object when done.
```

## دليل خطوة بخطوة

### الخطوة 1: إنشاء عرض تقديمي وإضافة مخطط عمود متجمع
في هذه الخطوة نقوم **how to create chart** الكائنات ونضع **create clustered column chart** على الشريحة الأولى.

```java
import com.aspose.slides.*;

String YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation();
try {
    // Add a clustered column chart at (50, 50) with width 600 and height 400.
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### الخطوة 2: إدارة سلاسل المخطط
سنقوم الآن بمسح أي سلاسل افتراضية، إضافة سلسلة جديدة، وتعبئتها بالقيم الإيجابية والسلبية.

```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    // Clear existing series and add a new one.
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Add data points with varying values (positive and negative).
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1)
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### الخطوة 3: عكس نقاط البيانات السلبية بشكل شرطي
بشكل افتراضي، لا يقوم Aspose.Slides بعكس القيم السلبية. سنفعل العكس فقط لتلك النقاط التي تحتاج ذلك.

```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Add data points with varying values (positive and negative).
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1)
    );
    
    // Set default inversion behavior
    series.get_Item(0).invertIfNegative(false);
    
    // Conditionally invert a specific data point
    IChartDataPoint dataPoint = series.get_Item(0).getDataPoints().get_Item(0);
    if (dataPoint.getValue() < 0) {
        dataPoint.invertIfNegative(true);
    }
} finally {
    if (pres != null) pres.dispose();
}
```

### الأخطاء الشائعة والنصائح
- **نسيت إتلاف كائن `Presentation`؟** دائمًا استدعِ `dispose()` داخل كتلة `finally` لتحرير الموارد الأصلية.
- **القيم السلبية لا تظهر معكوسة؟** تأكد من استدعاء `invertIfNegative(true)` **بعد** إضافة نقطة البيانات.
- **مشكلات حجم المخطط:** الإحداثيات (X, Y) والأبعاد (العرض، الارتفاع) بوحدات النقاط؛ اضبطها لتناسب تخطيط الشريحة.

## الأسئلة المتكررة

**س: هل يمكنني إنشاء أنواع مخططات أخرى بنفس النهج؟**  
**ج:** نعم، ما عليك سوى استبدال `ChartType.ClusteredColumn` بأي قيمة أخرى من تعداد `ChartType` (مثل `Line`، `Pie`).

**س: هل أحتاج إلى ترخيص لبنات التطوير؟**  
**ج:** يلزم ترخيص مؤقت أو تجريبي للوصول الكامل إلى الميزات؛ وإلا، تعمل المكتبة في وضع التجربة مع قيود العلامة المائية.

**س: كيف يمكنني تصدير العرض التقديمي إلى PDF بعد إضافة المخططات؟**  
**ج:** استخدم `pres.save("output.pdf", SaveFormat.Pdf);` بعد الانتهاء من تعديل المخطط.

**س: هل يمكن تنسيق أعمدة فردية (لون، حد)؟**  
**ج:** نعم، كل `IChartDataPoint` يوفر خيارات تنسيق مثل `getFillFormat().setFillType(FillType.Solid)` و `getLineFormat()`.

**س: ماذا لو احتجت لتحديث بيانات المخطط بعد حفظ العرض التقديمي؟**  
**ج:** حمّل العرض مرة أخرى باستخدام `new Presentation("file.pptx")`، عدّل بيانات المخطط، ثم أعد الحفظ.

---

**آخر تحديث:** 2026-02-12  
**تم الاختبار مع:** Aspose.Slides for Java 25.4 (JDK 16)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}