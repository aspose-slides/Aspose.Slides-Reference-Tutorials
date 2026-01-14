---
date: '2026-01-14'
description: تعلم كيفية إضافة مخطط عمودي مجمع وإضافة المخطط إلى شريحة في عروض .NET
  باستخدام Aspose.Slides للغة Java. اتبع هذا الدليل خطوة بخطوة مع أمثلة شفرة كاملة.
keywords:
- Aspose.Slides for Java
- .NET presentations
- charts in .NET
title: إضافة مخطط أعمدة مجمع إلى شرائح .NET Aspose.Slides Java
url: /ar/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إنشاء مخططات في عروض .NET باستخدام Aspose.Slides for Java
## المقدمة
غالبًا ما يتطلب إنشاء عروض تقديمية جذابة دمج تمثيلات بصرية للبيانات مثل المخططات لتعزيز فهم الجمهور وتفاعلهم. إذا كنت مطورًا ترغب في إضافة مخططات ديناميكية وقابلة للتخصيص إلى عروض .NET الخاصة بك باستخدام Aspose.Slides for Java، فهذه الدورة مخصصة لك. سنستعرض كيفية تهيئة العروض، إضافة أنواع مختلفة من المخططات، إدارة بيانات المخطط، وتنسيق بيانات السلاسل بفعالية.

**ما ستتعلمه:**
- كيفية إعداد واستخدام Aspose.Slides for Java في بيئة .NET الخاصة بك.
- تهيئة عرض تقديمي جديد باستخدام Aspose.Slides.
- إضافة وتخصيص المخططات في الشرائح.
- إدارة دفاتر بيانات المخطط.
- تنسيق بيانات السلاسل، خاصةً التعامل مع القيم السالبة.

الانتقال إلى قسم المتطلبات المسبقة سيضمن أنك مستعد للمتابعة بسهولة.

## إجابات سريعة
- **ما هو الهدف الأساسي؟** إضافة مخطط عمودي مجمع إلى شريحة .NET.
- **ما المكتبة المطلوبة؟** Aspose.Slides for Java (الإصدار 25.4 فما فوق).
- **هل يمكنني استخدامها في مشروع .NET؟** نعم – تعمل مكتبة Java عبر جسر Java‑to‑.NET.
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية المجانية تكفي للتطوير؛ يتطلب الاستخدام في الإنتاج ترخيصًا تجاريًا.
- **كم يستغرق تنفيذ ذلك؟** حوالي 10‑15 دقيقة لإنشاء مخطط أساسي.

## ما هو المخطط العمودي المجمع؟
المخطط العمودي المجمع يعرض عدة سلاسل بيانات جنبًا إلى جنب لكل فئة، مما يسهل مقارنة القيم عبر المجموعات. هذا النوع من المخططات مثالي للوحة معلومات الأعمال، تقارير الأداء، وأي سيناريو يتطلب مقارنة عدة مؤشرات.

## لماذا نضيف مخططًا إلى شريحة باستخدام Aspose.Slides for Java؟
باستخدام Aspose.Slides يمكنك إنشاء وتعديل وحفظ العروض التقديمية دون الحاجة إلى تثبيت Microsoft PowerPoint. يمنحك تحكمًا كاملًا في أنواع المخططات والبيانات والتنسيق، مما يتيح لك أتمتة إنشاء التقارير مباشرة من تطبيقات .NET الخاصة بك.

## المتطلبات المسبقة
قبل الغوص في إنشاء المخططات باستخدام Aspose.Slides for Java، دعنا نحدد ما تحتاجه:

### المكتبات والإصدارات المطلوبة
- **Aspose.Slides for Java**: الإصدار 25.4 أو أحدث.

### متطلبات إعداد البيئة
- بيئة تطوير تدعم تطبيقات .NET.
- فهم أساسي لمفاهيم برمجة Java.

### المتطلبات المعرفية
- الإلمام بإنشاء العروض التقديمية في سياق تطبيق .NET.
- فهم إدارة تبعيات Java (Maven/Gradle).

## إعداد Aspose.Slides for Java
لبدء استخدام Aspose.Slides، تحتاج إلى إضافتها كاعتماد في مشروعك. إليك الطريقة:

### Maven
أضف الاعتماد التالي إلى ملف `pom.xml` الخاص بك:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
قم بتضمينه في ملف `build.gradle` الخاص بك:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### التحميل المباشر
بدلاً من ذلك، يمكنك تنزيل أحدث إصدار من [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### خطوات الحصول على الترخيص
- **نسخة تجريبية**: ابدأ بترخيص مؤقت لاستكشاف الميزات.
- **شراء**: فكر في شراء ترخيص للاستخدام المكثف.

#### التهيئة الأساسية والإعداد
إليك كيفية تهيئة Aspose.Slides في الكود الخاص بك:
```java
import com.aspose.slides.Presentation;
// Initialize a new Presentation object
Presentation pres = new Presentation();
try {
    // Your logic here...
} finally {
    if (pres != null) pres.dispose();
}
```
هذا الإعداد يضمن إدارة الموارد بفعالية.

## دليل التنفيذ
سنرشدك خطوة بخطوة لتنفيذ الميزات.

### تهيئة العرض التقديمي
**نظرة عامة:**  
إنشاء كائن عرض تقديمي يضع الأساس لجميع العمليات اللاحقة. يوضح هذا الجزء كيفية البدء من الصفر باستخدام Aspose.Slides.

#### الخطوة 1: استيراد الحزم الضرورية
```java
import com.aspose.slides.Presentation;
```

#### الخطوة 2: إنشاء كائن عرض تقديمي جديد
إليك الطريقة:
```java
Presentation pres = new Presentation();
try {
    // Your code logic here...
} finally {
    if (pres != null) pres.dispose(); // Ensures resources are freed
}
```
*هذا يضمن التخلص من كائن العرض التقديمي بشكل صحيح بعد الاستخدام، مما يمنع تسرب الذاكرة.*

### إضافة مخطط إلى الشريحة
**نظرة عامة:**  
إضافة مخطط إلى شريحتك يمكن أن تجعل تصور البيانات أكثر فاعلية وجاذبية.

#### الخطوة 1: استيراد الحزم الضرورية
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlide;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
```

#### الخطوة 2: تهيئة العرض وإضافة المخطط
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    // Additional logic for chart customization...
} finally {
    if (pres != null) pres.dispose();
}
```
*هنا نضيف مخطط عمودي مجمع إلى الشريحة الأولى عند إحداثيات وأبعاد محددة.*

### إدارة دفتر بيانات المخطط
**نظرة عامة:**  
إدارة دفتر بيانات المخطط بفعالية تتيح لك تعديل السلاسل والفئات بسهولة.

#### الخطوة 1: استيراد الحزم الضرورية
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartDataWorkbook;
```

#### الخطوة 2: الوصول إلى دفتر البيانات وتفريغه
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing data
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Your customization logic here...
} finally {
    if (pres != null) pres.dispose();
}
```
*تفريغ دفتر البيانات ضروري للبدء من صفيحة نظيفة عند إضافة سلاسل وفئات جديدة.*

### إضافة سلاسل وفئات إلى المخطط
**نظرة عامة:**  
يوضح هذا الجزء كيفية إضافة نقاط بيانات ذات معنى عبر إدارة السلاسل والفئات.

#### الخطوة 1: إضافة سلاسل وفئات
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing series and categories
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Add new series and categories
    chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
    chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));

    // Further customization logic...
} finally {
    if (pres != null) pres.dispose();
}
```
*إضافة السلاسل والفئات يساهم في تنظيم عرض البيانات بشكل أفضل.*

### تعبئة بيانات السلسلة وتنسيقها
**نظرة عامة:**  
املأ مخططك بنقاط البيانات وقم بتنسيق المظهر لتعزيز قابلية القراءة، خاصةً عند التعامل مع القيم السالبة.

#### الخطوة 1: تعبئة بيانات السلسلة
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
import com.aspose.slides.Color;
import com.aspose.slides.FillType;
import com.aspose.slides.SaveFormat;

Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Add series and categories (reuse previous logic)
    
    IChartSeries series = chart.getChartData().getSeries().get_Item(0);
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 30));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, 10));

    // Format series for negative values
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
    
    Color positiveColor = Color.GREEN;
    Color negativeColor = Color.RED;
    for (IDataPoint dataPoint : series.getDataPoints()) {
        if (((Number)dataPoint.getValue()).doubleValue() < 0) {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(negativeColor);
        } else {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(positiveColor);
        }
    }

    // Save the presentation
    pres.save("output.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```
*هذا القسم يوضح كيفية تعبئة البيانات وتطبيق تنسيق اللون لتحسين التصور.*

## المشكلات الشائعة والحلول
- **تسرب الذاكرة:** احرص دائمًا على استدعاء `dispose()` على كائن `Presentation` داخل كتلة `finally`.
- **نوع المخطط غير صحيح:** تأكد من استخدام `ChartType.ClusteredColumn` عندما تريد مخططًا عموديًا مجمعًا؛ الأنواع الأخرى ستنتج مظهرًا بصريًا مختلفًا.
- **عدم تطبيق ألوان القيم السالبة:** تحقق من أن قيمة `IDataPoint` تم تحويلها إلى `Number` بشكل صحيح قبل المقارنة.

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.Slides for Java في مشروع .NET نقي دون Java؟**  
ج: نعم. تعمل المكتبة عبر جسر Java‑to‑.NET، مما يتيح لك استدعاء واجهات برمجة تطبيقات Java من لغات .NET.

**س: هل تدعم النسخة التجريبية إنشاء المخططات؟**  
ج: النسخة التجريبية تشمل جميع وظائف المخططات، لكن الملفات المولدة تحتوي على علامة مائية صغيرة للتقييم.

**س: ما إصدارات .NET المتوافقة؟**  
ج: أي إصدار .NET يمكنه التفاعل مع Java 16+، بما في ذلك .NET Framework 4.6+، .NET Core 3.1+، و .NET 5/6/7.

**س: كيف أتعامل مع عروض تقديمية كبيرة تحتوي على العديد من المخططات؟**  
ج: أعد استخدام نفس مثيل `IChartDataWorkbook` قدر الإمكان وتأكد من التخلص من كل `Presentation` فورًا لتحرير الذاكرة.

**س: هل يمكن تصدير المخطط كصورة؟**  
ج: نعم. استخدم طرق `chart.getImage()` أو `chart.exportChartImage()` للحصول على تمثيلات PNG/JPEG.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**آخر تحديث:** 2026-01-14  
**تم الاختبار مع:** Aspose.Slides for Java 25.4  
**المؤلف:** Aspose  

---