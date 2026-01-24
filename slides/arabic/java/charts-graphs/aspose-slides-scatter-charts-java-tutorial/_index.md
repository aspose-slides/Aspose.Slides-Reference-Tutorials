---
date: '2026-01-24'
description: دليل خطوة بخطوة لإنشاء مخطط مبعثر بلغة Java باستخدام Aspose.Slides، إضافة
  نقاط البيانات للمبعثر والعمل مع مخطط مبعثر متعدد السلاسل.
keywords:
- Aspose.Slides for Java
- create scatter charts in Java
- customize Java charts with Aspose
title: إنشاء مخطط مبعثر Java باستخدام Aspose.Slides – تخصيص وحفظ
url: /ar/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إنشاء مخطط مبعثر Java باستخدام Aspose.Slides

في هذا الدرس ستقوم **بإنشاء مخطط مبعثر Java** منعثر متعدد السلاسل — كل ذلك باستخدام Aspose.Slides for Java. سنستعرض إعداد الدليل، تهيئة العرض التقديمي، إنشاء المخطط، إدارة البيانات، تخصيص العلامات، وأخيرًا حفظ العرض التقديمي نقاط البيانات لكل سلسلة  
- تخص تحتاج تر الم- معرفة أساسية بـ Java وإلمام بـ Maven أو Gradle.  

## إعداد Aspose.Slides for Java

دمج Aspose.Slides في مشروعك باستخدام إحدى الطرق التالية.

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

أو قم بتحميل أحدث حزمة من [Aspose Releases](https://releases.aspose.com/slides/java/).

#### الحصول على الترخيص
- تجربة مجانية – تقييم لمدة 30 يومًا.  
- ترخيص مؤقت – اختبار ممتد.  
- ترخيص تجاري – للاستخدام الكامل في الإنتاج.

الآن دعنا نتعمق في الكود.

## دليل التنفيذ

### الخطوة 1: إعداد الدليل
أولاً، تأكد من وجود مجلد الإخراج حتى يمكن حفظ العرض التقديمي دون أخطاء.

```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Create the directory
    new File(dataDir).mkdirs();
}
```

### الخطوة 2: تهيئة العرض التقديمي
إنشاء عرض تقديمي جديد والحصول على الشريحة الأولى.

```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### الخطوة 3: إضافة مخطط مبعثر
إدراج مخطط مبعثر بخطوط ناعمة على الشريحة.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

### الخطوة 4: إدارة بيانات المخطط (مسح وإضافة سلاسل)
مسح أي سلاسل افتراضية وإضافة سلاسلنا الخاصة لمخطط **multiple series scatter chart**.

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

### الخطوة 5: إضافة نقاط البيانات المبعثرة
ملء كل سلسلة بقيم X‑Y باستخدام **add data points scatter**.

```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```

### الخطوة 6: تخصيص أنواع السلاسل والعلامات
ضبط النمط البصري — التحويل إلى خطوط مستقيمة مع علامات وتعيين رموز علامات مميزة.

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

### الخطوة 7: حفظ العرض التقديمي
حفظ الملف على القرص.

```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## التطبيقات العملية
- **التحليل المالي** – رسم تحركات أسعار الأسهم باستخدام مخطط مبعثر متعدد السلاسل.  
- **البحث العلمي** – تصور القياسات التجريبية باستخدام add data points scatter لتمثيل بيانات دقيقة.  
- **إدارة المشاريع** – إظهار اتجاهات تخصيص الموارد عبر عدة مشاريع على مخطط مبعثر واحد.  

## اعتبارات الأداء
- تخلص من كائن `Presentation` بعد الحفظ لتحرير الذاكرة.  
- للمجموعات الكبيرة من البيانات، املأ دفتر العمل على دفعات بدلاً من إدخال كل عنصر على حدة.  
- تجنب التنسيق المفرط داخل الحلقات الضيقة؛ قم بتطبيق الأنماط بعد إدخال البيانات.  

## المشكلات الشائعة والحلول

| المشكلة | الحل |
|-------|----------|
| **المخطط يظهر فارغًا** | تحقق من أن نقاط البيانات قد أضيفت إلى السلسلة الصحيحة وأن مؤشرات دفتر العمل متطابقة. |
| **العلامات غير مرئية** | تأكد من أن `series.getMarker().setSize()` تم تعيينه إلى قيمة أكبر من 0 وأن رمز العلامة محدد. |
| **خطأ OutOf وفكر في زيادة حجم اللمي ت")`.

### كيف يمكنني تحريك سلسلة المخطط المبعثر؟
استخدم_Item(i).getFormat().getEffectFormat().setPresetEffect(PresetEffectType.Appear)` لإضافة تأثير ظهور بسيط.

**آخر تحديث:** 2026-01-24  
**تم الاختبار مع:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}