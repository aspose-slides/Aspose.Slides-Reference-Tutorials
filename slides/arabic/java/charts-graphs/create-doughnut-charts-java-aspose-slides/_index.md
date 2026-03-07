---
date: '2026-03-07'
description: تعلم كيفية إنشاء مخطط دونات في جافا باستخدام Aspose.Slides. يغطي هذا
  الدليل خطوة بخطوة إعداد تبعية Maven لـ Aspose Slides، تكوين المخطط، وحفظ العروض
  التقديمية.
keywords:
- create doughnut charts Java
- Aspose.Slides Java guide
- Java data visualization
title: إنشاء مخطط دونات Java باستخدام دليل Aspose.Slides
url: /ar/java/charts-graphs/create-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إنشاء مخطط الدونات Java باستخدام دليل Aspose.Slides

## المقدمة

إنشاء **مخطط الدونات** برمجياً يمكن أن يحول الأرقام الخام إلى تصور جذاب يروي قصة على الفور. في Java، تجعل **Aspose.Slides** هذه العملية بسيطة، مما يتيح لك توليد مخططات جاهزة للعرض التقديمي دون الحاجة لفتح PowerPoint. في هذا الدليل ستتعلم كيفية **إنشاء مخطط الدونات Java** خطوة بخطوة — بدءاً من إعداد تبعية Maven Aspose Slides إلى تخصيص السلاسل والفئات، وأخيراً حفظ العرض التقديمي.

بنهاية هذا الدليل ستكون قادرًا على تضمين مخططات الدونات الديناميكية في أي ملف PPTX، وهو مثالي للتقارير، ولوحات المعلومات، أو عروض الشرائح الآلية.

### إجابات سريعة
- **ما المكتبة المستخدمة؟** Aspose.Slides for Java  
- **المهمة الأساسية؟** إنشاء مخطط الدونات Java في ملف PPTX  
- **كيف يتم إضافة المكتبة؟** استخدم تبعية Maven Aspose Slides (أو Gradle)  
- **الحد الأدنى لإصدار Java؟** JDK 16 أو أعلى  
- **هل يمكنني تخصيص الألوان والتسميات؟** نعم، توفر API تحكمًا كاملاً في التنسيق  

## ما هو مخطط الدونات ولماذا يُستخدم؟

مخطط الدونات هو نسخة من مخطط الفطيرة مع مركز فارغ، مما يتيح لك عرض عدة سلاسل بيانات في حلقات متحدة المركز. هذا يجعله مثاليًا لمقارنة أجزاء من الكل عبر فئات متعددة — فكر في المبيعات حسب المنطقة على مدار عدة أرباع أو تخصيصات الميزانية عبر الأقسام.

## لماذا نستخدم Aspose.Slides for Java؟

- **لا حاجة لتثبيت Office** – توليد ملفات PPTX على أي خادم.  
- **API غني** – تحكم كامل في أنواع المخططات، نقاط البيانات، والتنسيق.  
- **أداء عالي** – مُحسّن للعروض التقديمية الكبيرة.  
- **متعدد المنصات** – يعمل على Windows وLinux وmacOS.  

## المتطلبات المسبقة

- **المكتبات المطلوبة:**  
  - Aspose.Slides for Java الإصدار 25.4 أو أحدث.  

- **إعداد البيئة:**  
  - JDK 16 أو أعلى.  
  - بيئة التطوير المتكاملة المفضلة لديك (IntelliJ IDEA، Eclipse، NetBeans، إلخ).  

- **المعرفة المطلوبة مسبقًا:**  
  - برمجة Java الأساسية.  
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
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

يمكنك أيضًا تنزيل ملف JAR مباشرةً من صفحة الإصدارات الرسمية:  
[ Aspose.Slides for Java releases ](https://releases.aspose.com/slides/java/)

### الحصول على ترخيص

لإزالة علامة التقييم المائية وإتاحة مجموعة الميزات الكاملة:

- **تجربة مجانية** – ابدأ بترخيص مؤقت.  
- **ترخيص مؤقت** – اطلب واحدًا من [Aspose website](https://purchase.aspose.com/temporary-license/).  
- **ترخيص تجاري** – اشترِ للاستخدام في الإنتاج.

طبق الترخيص في الكود الخاص بك:

```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

## دليل التنفيذ

### تهيئة العرض التقديمي وإضافة مخطط الدونات

أولاً، أنشئ أو حمّل عرضًا تقديميًا وأضف مخطط الدونات إلى الشريحة الأولى.

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### تكوين دفتر عمل بيانات المخطط ومسح البيانات الموجودة

بعد ذلك، احصل على دفتر العمل الذي يدعم المخطط وامسح أي سلاسل أو فئات افتراضية.

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

### إضافة سلاسل إلى المخطط

الآن سنضيف ما يصل إلى 15 سلسلة. يمكن تخصيص كل سلسلة — هنا نحدد الانفجار، حجم فتحة الدونات، وزاوية الشريحة الأولى.

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

### إضافة فئات ونقاط بيانات

سننشئ 15 فئة ونملأ كل سلسلة بنقطة بيانات. السلسلة الأخيرة تتلقى تنسيقًا خاصًا للتسمية.

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

### حفظ العرض التقديمي

أخيرًا، احفظ العرض التقديمي المحدث إلى القرص.

```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## المشكلات الشائعة والحلول

- **الترخيص غير موجود** – تحقق من أن مسار `license.lic` صحيح والملف قابل للقراءة.  
- **المخطط يظهر فارغًا** – تأكد من مسح السلاسل/الفئات الموجودة قبل إضافة جديدة.  
- **الألوان غير صحيحة** – تحقق من أن `FillType.Solid` مُعيّن لكل من تنسيقات التعبئة والخط.  
- **الأداء مع عدد كبير من السلاسل** – قلل عدد السلاسل/الفئات أو أعد استخدام خلايا دفتر العمل.  

## الأسئلة المتكررة

**س: هل يمكنني إنشاء مخطط الدونات دون ملف PPTX موجود مسبقًا؟**  
**ج:** نعم، أنشئ كائنًا بـ `new Presentation()` للبدء من مجموعة شرائح فارغة.

**س: هل يدعم Aspose.Slides التصدير إلى PDF؟**  
**ج:** بالتأكيد. بعد إنشاء المخطط، استدعِ `pres.save("output.pdf", SaveFormat.Pdf);`.

**س: كيف أغيّر حجم فتحة الدونات؟**  
**ج:** استخدم `series.getParentSeriesGroup().setDoughnutHoleSize((byte) value);` حيث القيمة بين 0‑100.

**س: هل يمكن إضافة تسميات بيانات لجميع السلاسل، وليس فقط الأخيرة؟**  
**ج:** نعم، انقل كتلة تنسيق التسمية خارج شرط `if (i == ...)` وطبقها على كل `dataPoint`.

**س: ما إصدارات Java المدعومة؟**  
**ج:** يدعم Aspose.Slides 25.4 JDK 16 وما بعده. الإصدارات الأقدم من JDK تتطلب المصنف المناسب.

---

**آخر تحديث:** 2026-03-07  
**تم الاختبار مع:** Aspose.Slides for Java 25.4 (مصنف jdk16)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}