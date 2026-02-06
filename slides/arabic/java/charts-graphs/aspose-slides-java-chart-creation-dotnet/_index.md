---
date: '2026-02-06'
description: تعلم كيفية تهيئة عرض Aspose Slides وتخصيص مخطط الأعمدة المتجمعة في .NET
  باستخدام Aspose.Slides for Java. اتبع هذا الدليل خطوة بخطوة لتعزيز تصور البيانات.
keywords:
- Aspose.Slides for Java
- .NET presentations
- charts in .NET
title: 'تهيئة العرض التقديمي باستخدام Aspose Slides: مخططات .NET'
url: /ar/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إنشاء مخططات في عروض .NET باستخدام Aspose.Slides للـ Java

## المقدمة
في هذا الدرس ستقوم **بتهيئة عرض Aspose Slides** وتتعلم كيفية دمج مخططات ديناميكية وقابلة للتخصيص في شرائح .NET الخاصة بك. تساعد البيانات المرئية—مثل مخططات الأعمدة المتجمعة—الجمهور على استيعاب الاتجاهات فورًا، وتوفر لك Aspose.Slides للـ Java تحكمًا برمجيًا كاملاً حتى عندما تستهدف بيئة .NET. سنستعرض إعداد المكتبة، إنشاء عرض جديد، إضافة مخطط، تعبئة البيانات، وتطبيق حيل تنسيق مثل تلوين القيم السالبة.

**ما ستتعلمه**
- كيفية إعداد Aspose.Slides للـ Java في مشروع .NET.  
- كيفية **تهيئة عرض Aspose Slides** وإضافة مخطط.  
- كيفية **تخصيص مخطط الأعمدة المتجمعة** للسلاسل والفئات.  
- إدارة دفتر بيانات المخطط وتطبيق التنسيق الشرطي.  

### إجابات سريعة
- **ما هي الخطوة الأولى؟** تهيئة كائن `Presentation`.  
- **أي نوع مخطط يُستخدم في المثال؟** `ClusteredColumn`.  
- **هل يمكن تنسيق القيم السالبة بشكل مختلف؟** نعم، باستخدام ألوان تعبئة شرطية.  
- **هل أحتاج إلى ترخيص للاختبار؟** ترخيص تجريبي مجاني يكفي للتطوير.  
- **ما هو العنصر (artifact) المطلوب في Maven؟** `com.aspose:aspose-slides:25.4` مع المصنف `jdk16`.

## ما هو “تهيئة عرض Aspose Slides”؟
إنشاء عرض يخلق ملف PPTX في الذاكرة يمكنك التلاعب به قبل الحفظ. تقوم Aspose.Slides بتجريد تنسيق الملف، مما يتيح لك إضافة شرائح، أشكال، ومخططات دون الحاجة للتعامل مع هياكل OPC منخفضة المستوى.

## لماذا تخصيص مخطط الأعمدة المتجمعة؟
مخططات الأعمدة المتجمعة مثالية لمقارنة عدة سلاسل بيانات عبر الفئات. يتيح لك تخصيص الألوان، نقاط البيانات، والتسميات إبراز الرؤى الرئيسية—مثل تمييز القيم السالبة باللون الأحمر والإيجابية بالأخضر—مما يجعل شرائحك أكثر إقناعًا.

## المتطلبات المسبقة
- **Aspose.Slides للـ Java** ≥ 25.4  
- بيئة تطوير .NET (Visual Studio، .NET 6+ موصى بها)  
- معرفة أساسية بـ Java (ستكتب كود Java يعمل على JVM ويُستدعى من .NET عبر JNI أو طبقة جسر)

### المكتبات والإصدارات المطلوبة
- **Aspose.Slides للـ Java**: الإصدار 25.4 أو أحدث.

### متطلبات إعداد البيئة
- بيئة تشغيل Java متوافقة مع .NET (مثل AdoptOpenJDK 16).  
- Maven أو Gradle لإدارة الاعتمادات.

### المتطلبات المعرفية
- الإلمام بإنشاء عروض في سياق .NET.  
- فهم تكوين مشروع Java (Maven/Gradle).

## إعداد Aspose.Slides للـ Java
أضف المكتبة إلى مشروعك باستخدام أداة البناء المفضلة.

### Maven
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### التحميل المباشر
يمكنك أيضًا تنزيل أحدث ملف JAR من صفحة الإصدار الرسمية: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### خطوات الحصول على الترخيص
- **تجريبي مجاني** – أنشئ ملف ترخيص مؤقت للتطوير.  
- **شراء** – احصل على ترخيص كامل للنشر في بيئات الإنتاج.

#### التهيئة الأساسية والإعداد
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
يضمن كتلة `try/finally` تحرير الموارد الأصلية، مما يمنع تسرب الذاكرة.

## كيفية تهيئة عرض Aspose Slides
فيما يلي نغوص في الخطوات العملية لإنشاء عرض جديد وتحضيره لإدراج مخطط.

### تهيئة العرض
**نظرة عامة:**  
إنشاء نسخة من العرض يضع الأساس لجميع العمليات اللاحقة.

#### الخطوة 1: استيراد الحزم الضرورية
```java
import com.aspose.slides.Presentation;
```

#### الخطوة 2: إنشاء كائن عرض جديد
```java
Presentation pres = new Presentation();
try {
    // Your code logic here...
} finally {
    if (pres != null) pres.dispose(); // Ensures resources are freed
}
```
*يضمن هذا أن كائن العرض يتم تحريره بشكل صحيح بعد الاستخدام، مما يمنع تسرب الذاكرة.*

## كيفية تخصيص مخطط الأعمدة المتجمعة
الآن بعد أن أصبح العرض جاهزًا، لنضيف مخططًا متجمعًا ونخصصه.

### إضافة مخطط إلى الشريحة
**نظرة عامة:**  
إضافة مخطط تُحيي البيانات على الشريحة.

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
*هنا نضيف مخطط أعمدة متجمع إلى الشريحة الأولى عند إحداثيات وأبعاد محددة.*

### إدارة دفتر بيانات المخطط
**نظرة عامة:**  
إدارة دفتر بيانات المخطط بفعالية يتيح لك تعديل السلاسل والفئات بسلاسة.

#### الخطوة 1: استيراد الحزم الضرورية
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartDataWorkbook;
```

#### الخطوة 2: الوصول إلى دفتر البيانات ومسحه
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
*مسح دفتر البيانات ضروري للبدء من نقطة صافية عند إضافة سلاسل وفئات جديدة.*

### إضافة سلاسل وفئات إلى المخطط
**نظرة عامة:**  
توضح هذه الخطوة كيفية إضافة نقاط بيانات ذات معنى عبر إدارة السلاسل والفئات.

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
املأ مخططك بنقاط البيانات وقم بتنسيق المظهر لتحسين القابلية للقراءة، خاصة عند التعامل مع القيم السالبة.

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
*يوضح هذا القسم كيفية تعبئة البيانات وتطبيق تنسيق اللون لتحسين التصور.*

## المشكلات الشائعة والحلول
- **تسرب الذاكرة** – احرص دائمًا على تغليف كائن `Presentation` بكتلة `try/finally` كما هو موضح لضمان تحريره.  
- **إحداثيات الخلايا غير صحيحة** – تذكر أن الصفوف والأعمدة تبدأ من الصفر؛ الأخطاء في الفهارس تؤدي إلى `NullPointerException`.  
- **الترخيص غير موجود** – ضع ملف الترخيص في دليل عمل التطبيق أو عيّن المسار صراحةً عبر `License.setLicense("Aspose.Slides.Java.lic")`.

## الأسئلة المتكررة

**س: هل يمكنني استخدام هذا النهج مع .NET Core؟**  
ج: نعم. يعمل Aspose.Slides للـ Java على أي JVM، ويمكنك استدعاء كود Java من .NET Core عبر جسر مثل IKVM أو JNI.

**س: هل أحتاج إلى ترخيص مدفوع للتطوير؟**  
ج: ترخيص تجريبي مجاني يكفي للتطوير والاختبار. تتطلب عمليات النشر في الإنتاج ترخيصًا مُشتَرًى.

**س: كيف أغيّر نوع المخطط بعد إنشائه؟**  
ج: يمكنك استدعاء `chart.getChartData().setChartType(ChartType.Pie)` لتغيير النوع إلى مخطط آخر.

**س: هل يمكن إضافة تسميات البيانات برمجيًا؟**  
ج: نعم. استخدم `series.getDataPoints().get_Item(i).getLabel().setShowValue(true)` لعرض القيم على المخطط.

**س: ما الصيغ التي يمكن حفظ العرض بها؟**  
ج: يدعم Aspose.Slides صيغ PPTX، PPT، PDF، XPS، وعدة صيغ صور مثل PNG و JPEG.

---

**آخر تحديث:** 2026-02-06  
**تم الاختبار مع:** Aspose.Slides للـ Java 25.4 (مصنف jdk16)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}