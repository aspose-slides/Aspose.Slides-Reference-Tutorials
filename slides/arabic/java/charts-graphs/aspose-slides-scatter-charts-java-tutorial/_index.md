---
date: '2026-02-24'
description: تعلم كيفية تخصيص مخطط التشتت باستخدام Aspose.Slides للغة Java. يوضح لك
  هذا الدليل خطوات إنشاء وتنسيق وحفظ مخططات التشتت الديناميكية في عروضك التقديمية.
keywords:
- Aspose.Slides for Java
- create scatter charts in Java
- customize Java charts with Aspose
title: تخصيص مخطط التشتت Aspose في Java
url: /ar/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# تخصيص مخطط التشتت Aspose في Java

في هذا الدرس ستتعلم كيفية **تخصيص مخطط التشتت Aspose** باستخدام مكتبة Aspose.Slides for Java القوية. سنستعرض إعداد المشروع، إنشاء مخطط التشتت، تعديل أنواع السلاسل والمؤشرات، وأخيرًا حفظ العرض التقديمي. في النهاية، ستكون قادرًا على توليد مخططات تشتت ذات مظهر احترافي برمجيًا وتخصيص كل تفاصيلها لتتناسب مع علامتك التجارية أو احتياجات التقارير.

## إجابات سريعة
- **ما المكتبة التي أحتاجها؟** Aspose.Slides for Java (الإصدار 25.4 فما فوق).  
- **ما نسخة Java المدعومة؟** JDK 8 أو أعلى.  
- **هل يمكنني تغيير أشكال المؤشرات؟** نعم – استخدم `MarkerStyleType` لاختيار النجوم أو الدوائر وغيرها.  
- **كيف أحفظ الملف؟** استدعِ `pres.save("output.pptx", SaveFormat.Pptx)`.  
- **هل يلزم وجود ترخيص؟** نسخة تجريبية مجانية تكفي للتطوير؛ يلزم ترخيص تجاري للإنتاج.

## ما هو “تخصيص مخطط التشتت Aspose”؟
تخصيص مخطط التشتت باستخدام Aspose يعني تعريف بيانات المخطط ومظهره وسلوكه برمجيًا—من إحداثيات النقاط إلى رموز المؤشرات—دون الحاجة لفتح PowerPoint يدويًا. هذا الأسلوب مثالي للتقارير الآلية، العروض التقديمية المدفوعة بالبيانات، أو أي سيناريو يتطلب تصورات عالية الجودة قابلة للتكرار.

## لماذا نخصص مخططات التشتت باستخدام Aspose.Slides؟
- **تحكم كامل** – تعديل أنواع السلاسل، أنماط المؤشرات، الألوان، وأكثر عبر كود Java.  
- **أتمتة** – توليد عشرات المخططات في الوقت الفعلي للوحة معلومات أو تقارير دفعة.  
- **متعدد المنصات** – يعمل على أي نظام تشغيل يدعم Java، دون الحاجة لتثبيت Office.  
- **أداء** – API خفيف الوزن يتعامل مع مجموعات بيانات كبيرة بكفاءة.

## المتطلبات المسبقة

للمتابعة، تأكد من وجود:

- **Aspose.Slides for Java** (الإصدار 25.4 أو أحدث).  
- **مجموعة تطوير Java (JDK)** 8 + مثبتة.  
- Maven أو Gradle لإدارة الاعتمادات (أو يمكنك تنزيل ملف JAR يدويًا).  
- معرفة أساسية بـ Java وإلمام بأداة البناء التي تفضلها.

## إعداد Aspose.Slides for Java

دمج المكتبة في مشروعك باستخدام إحدى الطرق أدناه.

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

أو احصل على أحدث إصدار من [Aspose Releases](https://releases.aspose.com/slides/java/).

#### الحصول على الترخيص
- **نسخة تجريبية** – تقييم لمدة 30 يومًا.  
- **ترخيص مؤقت** – فترة اختبار ممتدة.  
- **ترخيص كامل** – للاستخدام الإنتاجي مع دعم مميز.

## دليل خطوة بخطوة لتخصيص مخطط التشتت Aspose

### 1️⃣ إعداد مجلد لملفات العرض التقديمي
```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Create the directory
    new File(dataDir).mkdirs();
}
```
*لماذا هذا مهم:* ضمان وجود مجلد الإخراج يمنع حدوث `FileNotFoundException` عند حفظ ملف PPTX لاحقًا.

### 2️⃣ إنشاء عرض تقديمي جديد والحصول على الشريحة الأولى
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```
إنشاء كائن `Presentation` جديد يمنحك لوحة رسم نظيفة؛ الشريحة الأولى هي المكان الذي سنضع فيه المخطط.

### 3️⃣ إضافة مخطط تشتت بخطوط ناعمة
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
`ChartType.ScatterWithSmoothLines` ينشئ مخطط تشتت بخطوط ناعمة، مثالي لتصوير الاتجاهات.

### 4️⃣ مسح أي سلاسل افتراضية وإضافة السلاسل الخاصة بك
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeries;

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Adding new series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
```
إزالة السلاسل الافتراضية يمنحك تحكمًا كاملًا في البيانات المعروضة.

### 5️⃣ تعبئة السلسلة الأولى بنقاط البيانات
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```
`addDataPointForScatterSeries` يأخذ خلية قيمة X وخلية قيمة Y، ويبني نقطة التشتت نقطة بنقطة.

### 6️⃣ تخصيص نوع السلسلة ومظهر المؤشرات
```java
import com.aspose.slides.MarkerStyleType;

series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);

// Modifying second series
series = chart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```
هنا نقوم **بتخصيص مخطط التشتت Aspose** عبر التحويل إلى خطوط مستقيمة، تكبير المؤشرات، واختيار رموز مميزة (نجم مقابل دائرة) لتحسين الوضوح البصري.

### 7️⃣ حفظ العرض التقديمي
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```
الحفظ بصيغة `Pptx` يحافظ على جميع تخصيصات المخطط ويجعل الملف جاهزًا للمشاركة أو التعديل الإضافي.

## حالات الاستخدام الشائعة للمخططات المخصصة
- **لوحات معلومات مالية** – رسم سعر السهم مقابل الحجم.  
- **البحوث العلمية** – عرض القياسات التجريبية مع مؤشرات الخطأ.  
- **إدارة المشاريع** – مقارنة الجهد المخطط مقابل الفعلي عبر المهام.  

## نصائح الأداء
- حرّر كائن `Presentation` (`pres.dispose()`) بعد الحفظ لتحرير الموارد الأصلية.  
- للمجموعات الكبيرة، عبئ دفتر العمل أولاً ثم اربط السلسلة لتجنب تحديثات الواجهة المتكررة.  
- أعد استخدام نسخة واحدة من `IChartDataWorkbook` عند إضافة العديد من السلاسل.

## الأسئلة المتكررة

### كيف يمكنني تغيير لون المؤشرات؟
استخدم `series.getMarker().getFillFormat().setFillColor(Color)` حيث `Color` هو كائن من `java.awt.Color` (مثال: `Color.RED`).

### هل يمكنني إضافة أكثر من سلسلتين إلى مخطط التشتت؟
بالطبع. كرّر استدعاء `chart.getChartData().getSeries().add(...)` لكل سلسلة إضافية واملأ نقاط بياناتها وفقًا لذلك.

### هل يمكن تعيين وسيلة إيضاح مخصصة لكل سلسلة؟
نعم. بعد إنشاء السلسلة، استدعِ `series.getLegend().setText("Your Legend Text")` لتجاوز الاسم الافتراضي.

### كيف يمكنني تصدير المخطط كصورة بدلاً من PPTX؟
استدعِ `chart.getImage().save("chart.png", ImageFormat.Png)` بعد تكوين المخطط. سيعطيك ذلك ملف PNG مستقل.

### ماذا لو أردت تحريك نقاط التشتت؟
يدعم Aspose.Slides تأثيرات الرسوم المتحركة. استخدم `chart.getTimeline().getMainSequence().addEffect(...)` لإضافة تأثيرات دخول أو تأكيد للمخطط أو للسلاسل الفردية.

---

**آخر تحديث:** 2026-02-24  
**تم الاختبار مع:** Aspose.Slides for Java 25.4 (مصنف jdk16)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}