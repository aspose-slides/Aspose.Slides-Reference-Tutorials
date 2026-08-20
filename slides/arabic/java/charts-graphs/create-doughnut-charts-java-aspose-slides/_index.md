---
date: '2026-08-16'
description: تعلم كيفية إضافة doughnut charts في Java باستخدام Aspose.Slides. يغطي
  هذا الدليل خطوة بخطوة إعداد تبعية Maven، تكوين المخطط، الألوان، التسميات وحفظ ملف
  PPTX.
keywords:
- how to add doughnut
- java create chart pptx
- maven aspose slides dependency
- customize doughnut chart colors
lastmod: '2026-08-16'
og_description: كيفية إضافة doughnut charts في Java باستخدام Aspose.Slides. اتبع هذا
  الدليل لإعداد Maven، تخصيص الألوان، التسميات وإنشاء ملفات PPTX.
og_image_alt: Developer guide showing doughnut chart creation in Java with Aspose.Slides
og_title: كيفية إضافة doughnut chart في Java باستخدام Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-08-16'
  description: Learn how to add doughnut charts in Java using Aspose.Slides. This
    step‑by‑step guide covers Maven dependency setup, chart configuration, colors,
    labels and saving the PPTX.
  headline: How to add doughnut chart in Java with Aspose.Slides
  type: TechArticle
- questions:
  - answer: Yes, instantiate `new Presentation()` to start from a blank slide deck,
      then add a chart as shown above.
    question: Can I generate a doughnut chart without a pre‑existing PPTX file?
  - answer: Absolutely. After creating the chart, call `pres.save("output.pdf", SaveFormat.Pdf);`
      to get a PDF version of the slide.
    question: Does Aspose.Slides support exporting to PDF?
  - answer: Use `chart.getParentSeriesGroup().setDoughnutHoleSize((byte) value);`
      where `value` ranges from 0 to 100.
    question: How do I change the doughnut hole size?
  - answer: Yes, move the label‑formatting block outside the `if (i == ...)` condition
      and apply it to each `dataPoint`.
    question: Is it possible to add data labels to all series, not just the last one?
  - answer: Aspose.Slides 25.4 supports JDK 16 and newer. Earlier JDKs require the
      appropriate classifier in the Maven dependency.
    question: What versions of Java are supported?
  type: FAQPage
tags:
- doughnut chart
- Aspose.Slides
- Java PPTX
- data visualization
title: كيفية إضافة doughnut chart في Java باستخدام Aspose.Slides
url: /ar/java/charts-graphs/create-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية إضافة مخطط الدونات في Java باستخدام Aspose.Slides

## مقدمة

إنشاء **مخطط الدونات** برمجيًا يمكن أن يحول الأرقام الخام إلى تصور بصري جذاب يروي قصة على الفور. في Java، تجعل **Aspose.Slides** هذه العملية بسيطة، حيث تسمح لك بإنشاء مخططات جاهزة للعرض دون الحاجة لفتح PowerPoint. في هذا الدرس ستتعلم **كيفية إضافة مخططات الدونات** إلى ملف PPTX خطوة بخطوة — من إعداد تبعية Maven Aspose Slides إلى تخصيص السلاسل، الفئات، الألوان، والتسميات، وأخيرًا حفظ العرض التقديمي.

بنهاية هذا الدليل ستكون قادرًا على دمج مخططات الدونات الديناميكية في أي ملف PPTX، مثالية للتقارير، لوحات التحكم، أو عروض الشرائح الآلية.

### إجابات سريعة
- **ما المكتبة المستخدمة؟** Aspose.Slides for Java  
- **المهمة الأساسية؟** إضافة مخطط دونات في ملف PPTX  
- **كيف يتم إضافة المكتبة؟** استخدم تبعية Maven Aspose Slides (أو Gradle)  
- **الحد الأدنى لإصدار Java؟** JDK 16 أو أعلى  
- **هل يمكن تخصيص الألوان والتسميات؟** نعم، توفر API تحكمًا كاملًا في التنسيق  

## ما هو مخطط الدونات ولماذا يُستخدم؟

مخطط الدونات هو نسخة من مخطط الفطيرة مع مركز فارغ، مما يسمح بعرض سلاسل بيانات متعددة كحلقات متحدة المركز. **إنه يُظهر أجزاء من الكل عبر عدة فئات مع الحفاظ على مساحة للمعلومات الإضافية في المركز.** هذا يجعله مثاليًا لمقارنة المبيعات حسب المنطقة على مدار عدة أرباع، تخصيص الميزانيات بين الأقسام، أو أي سيناريو يتطلب إظهار بيانات نسبية هرمية.

## لماذا نستخدم Aspose.Slides for Java؟

يمكنك إضافة مخطط دونات دون تثبيت Microsoft Office، وتتعامل المكتبة مع **أكثر من 50 + صيغة إدخال وإخراج** مع معالجة عروض تقديمية تتجاوز 500 شريحة. تقدم Aspose.Slides **سرعة عرض تصل إلى 3× أسرع** مقارنةً بأتمتة Office الأصلية على نفس العتاد، وتعمل على Windows وLinux وmacOS. هذه الفوائد الكمية تعني أنه يمكنك توليد مجموعات شرائح كبيرة على خوادم بدون واجهة رسومية بأداء متوقع.

## المتطلبات المسبقة

- **المكتبات المطلوبة**  
  - Aspose.Slides for Java 25.4 أو أحدث (المكتبة التي تمكّنك من إضافة مخططات الدونات).  

- **البيئة**  
  - JDK 16 أو أعلى مثبت على جهازك.  
  - بيئة تطوير متكاملة مثل IntelliJ IDEA أو Eclipse أو NetBeans.  

- **المعرفة**  
  - أساسيات لغة Java ومفاهيم البرمجة الكائنية.  
  - الإلمام بـ Maven أو Gradle لإدارة التبعيات.  

## تبعية Maven Aspose Slides

أضف تبعية Maven التالية إلى ملف `pom.xml`. هذه هي **تبعيات Maven Aspose Slides** التي تحتاجها لجلب المكتبة إلى مشروعك.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

إذا كنت تفضل Gradle، استخدم المقتطف المكافئ أدناه.

```gradle
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

يمكنك أيضًا تنزيل ملف JAR مباشرةً من صفحة الإصدارات الرسمية:  
[ Aspose.Slides for Java releases ](https://releases.aspose.com/slides/java/)

### الحصول على ترخيص

لإزالة علامة التقييم المائية وفتح مجموعة الميزات الكاملة:

- **تجربة مجانية** – ابدأ بترخيص مؤقت.  
- **ترخيص مؤقت** – اطلب واحدًا من [موقع Aspose](https://purchase.aspose.com/temporary-license/).  
- **ترخيص تجاري** – اشترِه للاستخدام في الإنتاج.

طبق الترخيص في الكود الخاص بك:

```java
License license = new License();
license.setLicense("path/to/license.lic");
```

## دليل التنفيذ

### تهيئة عرض تقديمي وإضافة مخطط دونات

`Presentation` هي الفئة في Aspose.Slides التي تمثل عرض PowerPoint.  
حمّل ملف PPTX موجود أو أنشئ كائن `Presentation` جديد، ثم أضف مخطط دونات إلى الشريحة الأولى.

```java
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 50, 50, 500, 400);
```

### تكوين دفتر بيانات المخطط ومسح البيانات الموجودة

دفتر البيانات هو جدول بيانات داخلي يخزن بيانات المخطط.  
احصل على دفتر البيانات المرتبط بالمخطط، ثم امسح أي سلاسل أو فئات افتراضية لتبدأ من صفيحة نظيفة.

```java
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### إضافة سلاسل إلى المخطط

السلسلة تمثل مجموعة من نقاط البيانات المرسومة على المخطط.  
يمكنك إضافة ما يصل إلى 15 سلسلة. يمكن تخصيص كل سلسلة — هنا نحدد الانفجار، حجم ثقب الدونات، وزاوية الشريحة الأولى.

```java
for (int i = 0; i < 15; i++) {
    IChartSeries series = chart.getChartData().getSeries().add(wb.getCell(0, i + 1, 0), chart.getType());
    series.getParentSeriesGroup().setExplosion(i * 5);
}
chart.getParentSeriesGroup().setDoughnutHoleSize((byte) 50);
chart.getParentSeriesGroup().setFirstSliceAngle(30);
```

### إضافة فئات ونقاط بيانات

الفئات هي التسميات لكل نقطة بيانات على محور المخطط.  
أنشئ 15 فئة واملأ كل سلسلة بنقطة بيانات. السلسلة الأخيرة تحصل على تنسيق تسميات خاص.

```java
for (int i = 0; i < 15; i++) {
    IChartCategory category = chart.getChartData().getCategories().add(wb.getCell(0, 0, i + 1));
    for (int j = 0; j < 15; j++) {
        IChartDataPoint dp = chart.getChartData().getSeries().get_Item(j).getDataPoints().addDataPointForDoughnutSeries(wb.getCell(0, j + 1, i + 1));
        dp.getValue().setData(wb.getCell(0, j + 1, i + 1).getDoubleValue());
    }
}
```

### تخصيص الألوان وتسميات البيانات

`FillType.Solid` يحدد تعبئة صلبة للون عناصر المخطط.  
عيّن لون تعبئة صلب لكل سلسلة وفعل تسميات البيانات. بالنسبة للسلسلة النهائية نغيّر أيضًا لون خط التسمية.

```java
for (int i = 0; i < 15; i++) {
    IChartSeries series = chart.getChartData().getSeries().get_Item(i);
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getFill().getSolidFillColor().setColor(Color.fromArgb(255, (i * 15) % 256, (i * 30) % 256));
    series.getDataPoints().forEach(dp -> dp.getLabel().setShowValue(true));
}
IChartSeries lastSeries = chart.getChartData().getSeries().get_Item(14);
lastSeries.getDataPoints().forEach(dp -> dp.getLabel().getFont().setColor(Color.Red));
```

### حفظ العرض التقديمي

`save` يكتب العرض التقديمي إلى ملف بالتنسيق المختار.  
اكتب العرض المحدث إلى القرص بصيغة PPTX، أو صدّره إلى PDF إذا لزم الأمر.

```java
pres.save("DoughnutChartDemo.pptx", SaveFormat.Pptx);
```

## المشكلات الشائعة والحلول

- **الترخيص غير موجود** – تحقق من أن مسار `license.lic` صحيح وأن الملف قابل للقراءة.  
- **المخطط يظهر فارغًا** – تأكد من مسح السلاسل/الفئات الموجودة قبل إضافة جديدة.  
- **الألوان غير صحيحة** – تأكد من ضبط `FillType.Solid` لكل من تعبئة الخط وتنسيق الخط.  
- **الأداء مع عدد كبير من السلاسل** – قلل عدد السلاسل/الفئات أو أعد استخدام خلايا دفتر البيانات للحفاظ على استهلاك الذاكرة تحت السيطرة.  

## الأسئلة المتكررة

**س: هل يمكنني إنشاء مخطط دونات دون ملف PPTX موجود مسبقًا؟**  
ج: نعم، أنشئ `new Presentation()` للبدء من مجموعة شرائح فارغة، ثم أضف المخطط كما هو موضح أعلاه.

**س: هل تدعم Aspose.Slides التصدير إلى PDF؟**  
ج: بالتأكيد. بعد إنشاء المخطط، استدعِ `pres.save("output.pdf", SaveFormat.Pdf);` للحصول على نسخة PDF من الشريحة.

**س: كيف أغيّر حجم ثقب الدونات؟**  
ج: استخدم `chart.getParentSeriesGroup().setDoughnutHoleSize((byte) value);` حيث يتراوح `value` بين 0 إلى 100.

**س: هل يمكن إضافة تسميات بيانات لجميع السلاسل، وليس الأخيرة فقط؟**  
ج: نعم، انقل كتلة تنسيق التسميات خارج شرط `if (i == ...)` وطبّقها على كل `dataPoint`.

**س: ما إصدارات Java المدعومة؟**  
ج: تدعم Aspose.Slides 25.4 JDK 16 وما فوق. الإصدارات الأقدم تتطلب المصنف المناسب في تبعية Maven.

---

**آخر تحديث:** 2026-08-16  
**تم الاختبار مع:** Aspose.Slides for Java 25.4 (مصنف jdk16)  
**المؤلف:** Aspose

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

```java
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(
        workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
        chart.getType()
    );

    // Customize the series
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(
        workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex)
    );
```

```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints()
        .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

    // Data point format settings
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
    dataPoint.getFormat().getLine().setWidth(1);
    dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
    dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

    // Label formatting for the last series
    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .setFillType(FillType.Solid);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .getSolidFillColor().setColor(Color.LIGHT_GRAY);

        // Adjust display options
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);

        // Adjust label position
        chart.validateChartLayout();
        lbl.setX(lbl.getX() + (float) 0.5);
        lbl.setY(lbl.getY() + (float) 0.5);
    }
    i++;
}
categoryIndex++;
```

```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## دروس ذات صلة

- [How to Add Chart to PowerPoint Using Aspose.Slides for Java: A Step‑By‑Step Guide](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [How to Customize Pie Chart Colors in Java with Aspose.Slides – A Complete Guide](/slides/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/)
- [Animate PowerPoint Chart Categories with Aspose.Slides for Java | Step-by-Step Guide](/slides/java/charts-graphs/animate-ppt-chart-categories-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}