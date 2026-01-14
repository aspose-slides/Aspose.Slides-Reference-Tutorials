---
date: '2026-01-14'
description: تعلم كيفية إنشاء مخطط عمودي مجمع في Java باستخدام Aspose.Slides. دليل
  خطوة بخطوة يغطي إنشاء عرض تقديمي فارغ، إضافة المخطط إلى العرض التقديمي، وإدارة السلاسل.
keywords:
- Aspose.Slides for Java
- Java charts
- clustered column chart
title: كيفية إنشاء مخطط أعمدة متجميع في Java باستخدام Aspose.Slides
url: /ar/java/charts-graphs/aspose-slides-java-chart-creation-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إتقان إنشاء المخططات في Java باستخدام Aspose.Slides

## كيفية إنشاء وإدارة المخططات باستخدام Aspose.Slides للـ Java

### مقدمة
غالبًا ما يتضمن إنشاء عروض تقديمية ديناميكية تصور البيانات عبر المخططات. باستخدام **Aspose.Slides for Java**، يمكنك بسهولة **إنشاء مخطط عمودي مجمع** وإدارة أنواع مختلفة من المخططات، مما يعزز كلًا من الوضوح والتأثير. سيوجهك هذا الدليل خلال إنشاء عرض تقديمي فارغ، إضافة مخطط عمودي مجمع، إدارة السلاسل، وتخصيص عكس نقاط البيانات—كل ذلك باستخدام Aspose.Slides للـ Java.

**ما ستتعلمه:**
- كيفية إعداد Aspose.Slides للـ Java.
- خطوات **إنشاء عرض تقديمي فارغ** وإضافة مخطط إلى العرض.
- تقنيات إدارة سلاسل المخطط ونقاط البيانات بفعالية.
- طرق عكس القيم السلبية بشكل شرطي لتحسين التصور.
- كيفية حفظ العرض التقديمي بأمان.

لنبدأ بالمتطلبات الأساسية قبل الشروع في التنفيذ.

## إجابات سريعة
- **ما هو الصنف الأساسي للبدء؟** `Presentation` من `com.aspose.slides`.
- **أي نوع مخطط يُنشئ مخطط عمودي مجمع؟** `ChartType.ClusteredColumn`.
- **كيف تضيف مخططًا إلى شريحة؟** استخدم `addChart()` على مجموعة الأشكال في الشريحة.
- **هل يمكنك عكس القيم السلبية؟** نعم، باستخدام `invertIfNegative(true)` على نقطة البيانات.
- **ما الإصدار المطلوب؟** Aspose.Slides for Java 25.4 أو أحدث.

## ما هو المخطط العمودي المجمع؟
المخطط العمودي المجمع يعرض عدة سلاسل بيانات جنبًا إلى جنب لكل فئة، مما يجعله مثاليًا لمقارنة القيم عبر المجموعات. يتيح لك Aspose.Slides إنشاء هذا المخطط برمجيًا دون الحاجة لفتح PowerPoint.

## لماذا تستخدم Aspose.Slides للـ Java لإضافة مخطط إلى العرض التقديمي؟
- **تحكم كامل** في بيانات المخطط ومظهره وتنسيقه.
- **لا حاجة لتثبيت Office** على الخادم.
- **يدعم جميع أنواع المخططات الرئيسية**، بما في ذلك المخططات العمودية المجمعة.
- **تكامل سهل** مع بنى Maven/Gradle.

## المتطلبات المسبقة
قبل البدء، تأكد من توفر ما يلي:

1. **المكتبات المطلوبة:**
   - Aspose.Slides للـ Java (الإصدار 25.4 أو أحدث).

2. **متطلبات إعداد البيئة:**
   - نسخة JDK متوافقة (مثل JDK 16).
   - Maven أو Gradle مثبت إذا كنت تفضل إدارة الاعتمادات.

3. **المعرفة المسبقة:**
   - فهم أساسي لبرمجة Java.
   - إلمام بالتعامل مع الاعتمادات في بيئة التطوير الخاصة بك.

## إعداد Aspose.Slides للـ Java
لبدء استخدام Aspose.Slides، اتبع الخطوات التالية:

**تثبيت Maven:**  
أضف الاعتماد التالي إلى ملف `pom.xml` الخاص بك:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**تثبيت Gradle:**  
أضف السطر التالي إلى ملف `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**التنزيل المباشر:**  
بدلاً من ذلك، قم بتحميل أحدث نسخة من [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### الحصول على الترخيص
- **تجربة مجانية:** يمكنك البدء بتجربة مجانية لاستكشاف الميزات.  
- **ترخيص مؤقت:** احصل على ترخيص مؤقت للوصول الكامل خلال فترة التقييم.  
- **شراء:** فكر في الشراء إذا وجدت أنه يلبي احتياجاتك على المدى الطويل.

### التهيئة الأساسية
فيما يلي الحد الأدنى من الشيفرة المطلوبة لإنشاء كائن عرض تقديمي جديد:

```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
// Your code here...
pres.dispose(); // Always dispose of the presentation object when done.
```

## دليل التنفيذ
الآن، لنقسم كل ميزة إلى خطوات يمكن إدارتها.

### إنشاء عرض تقديمي مع مخطط عمودي مجمع
#### نظرة عامة
يوضح هذا القسم كيفية **إنشاء عرض تقديمي فارغ**، إضافة **مخطط عمودي مجمع**، وتحديد موقعه على الشريحة الأولى.

**الخطوات:**
1. **تهيئة كائن Presentation** – إنشاء `Presentation` جديد.
2. **إضافة مخطط عمودي مجمع** – استدعاء `addChart()` مع النوع والأبعاد المناسبين.

**مثال الشيفرة:**
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

### إدارة سلاسل المخطط
#### نظرة عامة
تعلم كيفية مسح أي سلسلة افتراضية، إضافة سلسلة جديدة، وتعبئتها بقيم إيجابية وسلبية.

**الخطوات:**
1. **مسح السلاسل الموجودة** – إزالة أي بيانات مُعبأة مسبقًا.
2. **إضافة سلسلة جديدة** – استخدام خلية دفتر العمل كاسم للسلسلة.
3. **إدراج نقاط البيانات** – إضافة قيم، بما في ذلك السلبية، لتوضيح عملية العكس لاحقًا.

**مثال الشيفرة:**
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

### عكس نقاط بيانات السلسلة بناءً على الشروط
#### نظرة عامة
بشكل افتراضي، قد يقوم Aspose.Slides بعكس القيم السلبية. يمكنك التحكم في هذا السلوك على مستوى السلسلة بالكامل وعلى مستوى كل نقطة بيانات.

**الخطوات:**
1. **تعيين العكس العام** – تعطيل العكس التلقائي للسلسلة بأكملها.
2. **تطبيق العكس الشرطي** – تمكين العكس فقط للنقاط السلبية المحددة.

**مثال الشيفرة:**
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

### المشكلات الشائعة والحلول
| المشكلة | الحل |
|-------|----------|
| المخطط يظهر فارغًا | تأكد من وجود فهرس الشريحة (`0`) وأن أبعاد المخطط ضمن حدود الشريحة. |
| القيم السلبية لم تُعكس | تحقق من ضبط `invertIfNegative(false)` على السلسلة و`invertIfNegative(true)` على نقطة البيانات المحددة. |
| استثناء الترخيص | قم بتطبيق ترخيص Aspose صالح قبل إنشاء كائن `Presentation`. |

## الأسئلة المتكررة

**س: هل يمكنني إضافة أنواع مخططات أخرى غير العمودي المجمع؟**  
ج: نعم، يدعم Aspose.Slides المخططات الخطية، الدائرية، الشريطية، المساحية، والعديد غيرها.

**س: هل أحتاج إلى ترخيص للتطوير؟**  
ج: التجربة المجانية تكفي للتقييم، لكن الترخيص التجاري مطلوب للاستخدام في بيئة الإنتاج.

**س: كيف يمكنني تصدير المخطط كصورة؟**  
ج: استخدم `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);` بعد عملية التصيير.

**س: هل يمكن تنسيق المخطط (الألوان، الخطوط)؟**  
ج: بالتأكيد. كل من `IChartSeries` و `IChartDataPoint` يوفران خصائص تنسيق.

**س: ماذا لو أردت إضافة مخطط إلى ملف PPTX موجود؟**  
ج: حمّل الملف باستخدام `new Presentation("existing.pptx")`، ثم أضف المخطط إلى الشريحة المطلوبة.

## الخاتمة
في هذا الدليل، تعلمت كيفية **إنشاء مخطط عمودي مجمع** في Java، إدارة السلاسل، وعكس نقاط البيانات السلبية بشكل شرطي باستخدام Aspose.Slides. armed with these techniques, you can build compelling, data‑driven presentations programmatically.

**الخطوات التالية:**
- جرّب أنواع مخططات أخرى تقدمها Aspose.Slides للـ Java.  
- استكشف خيارات التنسيق المتقدمة مثل الألوان المخصصة، تسميات البيانات، وتنسيق المحاور.  
- دمج توليد المخططات في خطوط تقاريرك أو أنابيب التحليل الخاصة بك.

---

**آخر تحديث:** 2026-01-14  
**تم الاختبار مع:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}