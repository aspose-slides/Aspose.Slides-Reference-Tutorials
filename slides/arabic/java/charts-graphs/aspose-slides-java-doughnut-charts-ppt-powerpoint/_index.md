---
date: '2026-07-08'
description: تعلم كيفية استخدام Aspose لإنشاء مخطط doughnut chart في PowerPoint باستخدام
  Java. يوضح هذا الدليل خطوة بخطوة إضافة نقاط بيانات المخطط برمجياً، وتخصيص التسميات،
  وحفظ ملف PPTX بجودة عالية.
keywords:
- how to use aspose
- create doughnut chart powerpoint
- maven dependency aspose slides
lastmod: '2026-07-08'
og_description: يتيح لك استخدام Aspose إنشاء مخطط doughnut chart في PowerPoint باستخدام
  Java. اتبع هذا البرنامج التعليمي لإضافة نقاط البيانات، وتخصيص التسميات، وحفظ ملف
  PPTX بجودة عالية.
og_image_alt: 'Guide: Create doughnut chart PowerPoint with Aspose.Slides for Java'
og_title: 'كيفية استخدام Aspose: إنشاء مخطط doughnut chart في PowerPoint (Java)'
schemas:
- author: Aspose
  dateModified: '2026-07-08'
  description: Learn how to use Aspose to create a doughnut chart in PowerPoint with
    Java. This step‑by‑step guide shows adding chart data points programmatically,
    customizing labels, and saving the PPTX with high fidelity.
  headline: How to Use Aspose Create Doughnut Chart in PowerPoint (Java)
  type: TechArticle
- description: Learn how to use Aspose to create a doughnut chart in PowerPoint with
    Java. This step‑by‑step guide shows adding chart data points programmatically,
    customizing labels, and saving the PPTX with high fidelity.
  name: How to Use Aspose Create Doughnut Chart in PowerPoint (Java)
  steps:
  - name: Initialize the presentation
    text: Create a fresh presentation or open an existing file to obtain a slide collection.
      `Presentation` is the primary class that represents a PowerPoint file.
  - name: Add a doughnut chart to the slide
    text: Insert a chart shape, remove default series/categories, and configure basic
      visual settings like the doughnut hole size. `Chart` (or chart shape) represents
      a chart object placed on a slide.
  - name: Add chart data points and customize labels
    text: Populate category names, add data points for each series, and fine‑tune
      label formatting (font, color, position). This step demonstrates the “add chart
      data points” capability. `Workbook` provides access to the chart’s underlying
      spreadsheet data where cells are populated.
  - name: Save the updated presentation
    text: Persist the changes to a new PPTX file on disk. `save` writes the presentation
      to a file in the chosen format.
  type: HowTo
- questions:
  - answer: Yes, but you need a valid commercial license. A free trial is available
      for evaluation.
    question: Can I use Aspose.Slides for Java in commercial applications?
  - answer: Increase the loop limit in the “Add Doughnut Chart” step and ensure your
      data workbook contains enough rows.
    question: How do I add more than 15 series?
  - answer: Yes, call `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)`
      before saving.
    question: Is it possible to change the doughnut hole size after creation?
  - answer: Absolutely. Use `chart.getImage()` and save the returned `java.awt.image.BufferedImage`
      in your preferred format.
    question: Can I export the chart as an image instead of a PPTX?
  - answer: Animation can be added via the `ISlide.getTimeline()` API, though it’s
      beyond the scope of this tutorial.
    question: Does Aspose.Slides support animated charts?
  type: FAQPage
tags:
- doughnut chart
- Aspose.Slides
- Java PowerPoint
- chart generation
- presentation automation
title: كيفية استخدام Aspose لإنشاء مخطط doughnut chart في PowerPoint (Java)
url: /ar/java/charts-graphs/aspose-slides-java-doughnut-charts-ppt-powerpoint/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية استخدام Aspose لإنشاء مخطط دونات في PowerPoint (Java)

## المقدمة
إنشاء عروض تقديمية جذابة غالبًا ما يتطلب أكثر من مجرد نصوص وصور؛ فالمخططات يمكنها تعزيز السرد بشكل كبير من خلال تصور البيانات بفعالية. **كيفية استخدام Aspose** لتوليد المخططات يمنحك التحكم البرمجي دون الحاجة لفتح PowerPoint. يوضح هذا الدليل كيفية بناء مخطط دونات، وتكوين نقاط البيانات الخاصة به، وحفظ ملف PPTX عالي الدقة. كل ما تحتاجه هو معرفة أساسية بـ Java وبضع دقائق من إعداد البيئة.

`Aspose.Slides for Java` هي مكتبة Java تمكّن من إنشاء، تعديل، وتحويل ملفات PowerPoint دون الحاجة إلى Microsoft Office.

## إجابات سريعة
- **ما المكتبة التي تنشئ مخطط دونات في PowerPoint؟** Aspose.Slides for Java  
- **هل يمكن إضافة نقاط بيانات المخطط برمجيًا؟** نعم، باستخدام واجهة برمجة تطبيقات المخطط  
- **هل أحتاج إلى ترخيص للإنتاج؟** يلزم وجود ترخيص صالح لـ Aspose.Slides  
- **ما إصدارات Java المدعومة؟** Java 8 وما فوق (المصنف JDK 16 موضح)  
- **كم عدد السلاسل التي يمكنني إضافتها؟** المثال يضيف حتى 15 سلسلة، ويمكنك تعديل ذلك حسب الحاجة  

## ما هو مخطط الدونات في PowerPoint؟
مخطط الدونات هو مخطط دائري يشبه مخطط الفطيرة لكنه يحتوي على مركز مجوف، مما يسمح بعرض عدة سلاسل في آنٍ واحد. يبرز العلاقات بين الجزء والكل مع الحفاظ على تخطيط بصري مدمج وسهل القراءة.

## لماذا نستخدم Aspose.Slides for Java لإنشاء مخططات الدونات؟
Aspose.Slides for Java يدعم أكثر من 50 صيغة إدخال وإخراج ويمكنه توليد عروض تقديمية تصل إلى 500 ميغابايت دون تحميل الملف بالكامل في الذاكرة. يمنحك تحكمًا برمجيًا كاملاً في مظهر المخطط، البيانات، وتخطيطه على أي منصة Java، ويقضي على الحاجة إلى COM interop، ويمكنه إنشاء 100 شريحة غنية بالمخططات في أقل من ثانيتين على خادم عادي.

## المتطلبات المسبقة
- معرفة أساسية ببرمجة Java.  
- بيئة تطوير متكاملة مثل IntelliJ IDEA أو Eclipse.  
- Maven أو Gradle لإدارة الاعتمادات.  
- ترخيص صالح لـ Aspose.Slides for Java (يتوفر نسخة تجريبية مجانية).

## إعداد Aspose.Slides for Java
اختر مدير الاعتمادات الذي يناسب مشروعك.

**Maven**  
أضف الاعتماد التالي إلى ملف `pom.xml` (استبدل الإصدار بأحدث إصدار):

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
أضف هذا السطر إلى ملف `build.gradle`:

```gradle
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

إذا كنت تفضّل التحميل المباشر، زر صفحة [إصدارات Aspose.Slides for Java](https://releases.aspose.com/slides/java/).

### الحصول على الترخيص
يمكنك البدء بنسخة تجريبية مجانية لاستكشاف ميزات Aspose.Slides. للاستخدام الموسع، اشترِ ترخيصًا أو اطلب ترخيصًا مؤقتًا من [موقع Aspose](https://purchase.aspose.com/temporary-license/). اتبع التعليمات المقدمة لإعداد بيئتك وتهيئة Aspose.Slides في تطبيقك.

## كيفية إنشاء مخطط دونات في PowerPoint باستخدام Aspose.Slides for Java
لبناء مخطط دونات، ابدأ بتحميل أو إنشاء كائن `Presentation`، أضف شكل مخطط من النوع `ChartType.Doughnut`، احذف السلاسل الافتراضية، اضبط حجم الفتحة، ثم املأ دفتر عمل المخطط بأسماء الفئات والقيم الرقمية. أخيرًا، عدّل تنسيق التسميات واحفظ الملف بصيغة PPTX.

### الخطوة 1: تهيئة العرض التقديمي
أنشئ عرضًا تقديميًا جديدًا أو افتح ملفًا موجودًا للحصول على مجموعة الشرائح.

`Presentation` هو الصنف الأساسي الذي يمثل ملف PowerPoint.  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### الخطوة 2: إضافة مخطط دونات إلى الشريحة
أدرج شكل مخطط، احذف السلاسل/الفئات الافتراضية، واضبط الإعدادات البصرية الأساسية مثل حجم فتحة الدونات.

`Chart` (أو شكل المخطط) يمثل كائن المخطط الموضوع على الشريحة.  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### الخطوة 3: إضافة نقاط بيانات المخطط وتخصيص التسميات
املأ أسماء الفئات، أضف نقاط البيانات لكل سلسلة، واضبط تنسيق التسميات (الخط، اللون، الموضع). تُظهر هذه الخطوة قدرة “إضافة نقاط بيانات المخطط”.

`Workbook` يوفر الوصول إلى بيانات جدول البيانات الأساسي للمخطط حيث تُملأ الخلايا.  
```java
import com.aspose.slides.*;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);

// Verify successful loading by saving the initial presentation
pres.save(dataDir + "/initialized_chart.pptx", SaveFormat.Pptx);
```

### الخطوة 4: حفظ العرض التقديمي المحدث
احفظ التغييرات إلى ملف PPTX جديد على القرص.

`save` يكتب العرض التقديمي إلى ملف بالصيغ المختارة.  
```java
import com.aspose.slides.*;

ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// Configure the series properties
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

## تطبيقات عملية
مخططات الدونات مثالية لـ:
- **التقارير المالية:** تصور تخصيص الميزانية أو توزيع النفقات.  
- **تحليل السوق:** إظهار توزيع حصة السوق بين المنافسين.  
- **نتائج الاستبيانات:** عرض بيانات الاستبيان الفئوية بشكل مدمج.  
- **إنشاء لوحات التحكم:** دمجها مع استعلامات قاعدة البيانات لإنتاج شرائح محدثة تلقائيًا.

## اعتبارات الأداء
- **تحرير الموارد:** استدعِ `pres.dispose()` بعد الحفظ لتحرير الذاكرة الأصلية.  
- **حد عدد المخططات:** إضافة مئات المخططات قد يزيد من استهلاك الذاكرة؛ قم بالمعالجة على دفعات إذا لزم الأمر.  
- **استخدام البث:** للمجموعات الضخمة من البيانات، املأ دفتر العمل مباشرةً من التدفقات بدلاً من المصفوفات في الذاكرة.  

## المشكلات الشائعة والحلول
| المشكلة | السبب | الحل |
|-------|-------|-----|
| **المخطط يظهر فارغًا** | الخلايا غير مملوءة بشكل صحيح | تحقق من أن `workBook.getCell(...)` يشير إلى الصف/العمود الصحيح. |
| **تداخل التسميات** | عدد كبير من الفئات في مساحة محدودة | زد `DoughnutHoleSize` أو عدّل `FirstSliceAngle`. |
| **OutOfMemoryError** | عروض تقديمية كبيرة دون تحرير الموارد | استدعِ `pres.dispose()` بعد الحفظ وفكّر في زيادة حجم heap للـ JVM. |

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.Slides for Java في التطبيقات التجارية؟**  
ج: نعم، لكن يلزم وجود ترخيص تجاري صالح. تتوفر نسخة تجريبية مجانية للتقييم.

**س: كيف يمكنني إضافة أكثر من 15 سلسلة؟**  
ج: زد حد الحلقة في خطوة “إضافة مخطط دونات” وتأكد من أن دفتر عمل البيانات يحتوي على عدد كافٍ من الصفوف.

**س: هل يمكن تغيير حجم فتحة الدونات بعد الإنشاء؟**  
ج: نعم، استدعِ `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)` قبل الحفظ.

**س: هل يمكنني تصدير المخطط كصورة بدلاً من PPTX؟**  
ج: بالتأكيد. استخدم `chart.getImage()` واحفظ الـ `java.awt.image.BufferedImage` المسترجعة بالصيغ التي تفضلها.

**س: هل يدعم Aspose.Slides المخططات المتحركة؟**  
ج: يمكن إضافة الرسوم المتحركة عبر واجهة `ISlide.getTimeline()`، رغم أن ذلك خارج نطاق هذا الدليل.

## الخلاصة
أصبح لديك الآن طريقة كاملة وجاهزة للإنتاج **لإنشاء ملفات PowerPoint بمخططات دونات** باستخدام Aspose.Slides for Java، بما في ذلك كيفية **إضافة نقاط بيانات المخطط**، تخصيص التسميات، ومعالجة اعتبارات الأداء. جرّب ألوانًا مختلفة، مصادر بيانات متنوعة، وأنواع مخططات أخرى لجعل عروضك التقديمية متميزة حقًا.

---

**آخر تحديث:** 2026-07-08  
**تم الاختبار باستخدام:** Aspose.Slides for Java 25.4 (المصنف JDK 16)  
**المؤلف:** Aspose

```java
import com.aspose.slides.*;
import java.awt.Color;

int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        
        // Format the data point
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
        dataPoint.getFormat().getLine().setWidth(1);
        dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
        dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

        // Customize label properties for the last series in each category
        if (i == chart.getChartData().getSeries().size() - 1) {
            IDataLabel lbl = dataPoint.getLabel();
            lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
            lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
            lbl.getDataLabelFormat().setShowValue(false);
            lbl.getDataLabelFormat().setShowCategoryName(true);
            lbl.getDataLabelFormat().setShowSeriesName(false);
            lbl.getDataLabelFormat().setShowLeaderLines(true);
            lbl.getX() += 0.5f;
            lbl.getY() += 0.5f;
        }
        i++;
    }
    categoryIndex++;
}
```

```java
import com.aspose.slides.*;

pres.save(dataDir + "/chart.pptx", SaveFormat.Pptx);
```

## دروس ذات صلة

- [كيفية إضافة مخططات إلى PowerPoint باستخدام Aspose.Slides for Java: دليل خطوة بخطوة](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [كيفية تحرير بيانات مخطط PowerPoint باستخدام Aspose.Slides for Java: دليل شامل](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [تحريك المخططات في PowerPoint باستخدام Aspose.Slides for Java – دليل خطوة بخطوة](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}