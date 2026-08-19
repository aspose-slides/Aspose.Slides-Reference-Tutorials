---
date: '2026-07-17'
description: تعلم كيفية تدوير Pie Chart، تخصيص ألوان Pie Chart، وتصدير الشريحة إلى
  PDF باستخدام Aspose.Slides for Java – دليل شامل لتصور البيانات.
keywords:
- rotate pie chart
- customize pie chart colors
- export slide to pdf
- chart data worksheet
- java data visualization
lastmod: '2026-07-17'
og_description: تدوير Pie Chart وتخصيص ألوان Pie Chart باستخدام Aspose.Slides for
  Java. تعلم كيفية تصدير الشريحة إلى PDF والعمل مع ورقة بيانات المخطط.
og_image_alt: Guide showing how to rotate a pie chart and set custom colors in Java
  with Aspose.Slides
og_title: تدوير Pie Chart وتخصيص الألوان في Java – دليل Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to rotate pie chart, customize pie chart colors, and export
    slide to PDF using Aspose.Slides for Java – a full data visualization guide.
  headline: How to Rotate Pie Chart and Customize Colors in Java with Aspose.Slides
  type: TechArticle
- questions:
  - answer: Request a free trial from the Aspose website, then purchase a permanent
      license. Load it at runtime as shown in the Common Issues table.
    question: How do I obtain an Aspose.Slides license for Java?
  - answer: The API requires JDK 16 or higher; older versions are not supported.
    question: Can I use this code with older JDK versions?
  - answer: Yes—after rendering, call `chart.getChartData().getChartDataWorkbook().save("chart.png",
      ImageFormat.Png);`.
    question: Is it possible to export the chart as an image instead of PPTX?
  - answer: Pie charts are designed for a single data series; for multiple series,
      consider using a doughnut chart.
    question: What if I need more than one series in a pie chart?
  - answer: Absolutely—Aspose.Slides for Java is platform‑independent and works on
      any OS with a compatible JDK.
    question: Does Aspose.Slides run on Linux servers?
  type: FAQPage
tags:
- rotate pie chart
- Aspose.Slides
- Java charting
- data visualization
title: كيفية تدوير Pie Chart وتخصيص الألوان في Java باستخدام Aspose.Slides
url: /ar/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إنشاء مخططات دائرية باستخدام Aspose.Slides للـ Java: دليل كامل

## مقدمة
في هذا الدليل ستتعلم كيفية **تدوير مخطط دائري**، تخصيص لون كل شريحة، وتصدير الشريحة النهائية إلى PDF — كل ذلك باستخدام Aspose.Slides للـ Java. سواءً كنت تبني لوحة تحكم مبيعات، تقريرًا ماليًا، أو أي عرض تقديمي يعتمد على البيانات، فإن إتقان هذه التقنيات يتيح لك تقديم مرئيات واضحة وجذابة دون الاعتماد على Microsoft Office. لنجهّز الأدوات ونبدأ.

## إجابات سريعة
- **ما هو الصنف الذي يبدأ عرض تقديمي جديد؟** `Presentation` من `com.aspose.slides`.
- **ما هو استدعاء API الذي يضيف مخططًا دائريًا؟** `slide.addChart(ChartType.Pie, …)`.
- **كيف يمكنك إعطاء كل شريحة لونًا فريدًا؟** استدعِ `series.setColorVaried(true)` وضع تعبئات صلبة لكل نقطة بيانات.
- **ما هي الطريقة التي تدور المخطط؟** `chart.setRotationAngle(double)` – استخدم درجات من 0 إلى 360.
- **هل يمكن تصدير الشريحة إلى PDF؟** نعم، استدعِ `presentation.save("output.pdf", SaveFormat.Pdf)`.

## ما هو “تخصيص ألوان المخطط الدائري”؟
تخصيص ألوان المخطط الدائري يعني تعيين ألوان تعبئة مميزة لكل شريحة من الدائرة، مما يحسن قابلية القراءة والتأثير البصري. في Aspose.Slides يمكنك تحقيق ذلك بتمكين الألوان المتنوعة ثم ضبط ألوان تعبئة صلبة لكل نقطة بيانات. يضمن هذا النهج بروز كل جزء من البيانات بوضوح في العرض التقديمي.

## لماذا تستخدم Aspose.Slides للـ Java لإنشاء مخططات دائرية؟
يدعم Aspose.Slides **أكثر من 150 نوعًا من المخططات** ويمكنه إنشاء عرض تقديمي مكوّن من 300 صفحة في أقل من **5 ثوانٍ** على خادم عادي، كل ذلك دون الحاجة إلى تثبيت Microsoft Office. تعمل المكتبة على Windows وLinux وmacOS، مما يمنحك مرونة عبر المنصات لأي مشروع تصور بيانات مبني على Java.

## المتطلبات المسبقة
- **Aspose.Slides للـ Java** ≥ 25.4
- **JDK** 16 أو أحدث
- بيئة تطوير متكاملة مثل IntelliJ IDEA أو Eclipse أو NetBeans
- معرفة أساسية بـ Java وإلمام بـ Maven أو Gradle

## إعداد Aspose.Slides للـ Java
أضف المكتبة إلى تكوين البناء الخاص بك.

**Maven**  
أضف هذا المقتطف إلى ملف `pom.xml` الخاص بك:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
أدرج ما يلي في ملف `build.gradle` الخاص بك:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

إذا كنت تفضّل طريقة يدوية، قم بتنزيل أحدث ملف JAR من [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### خطوات الحصول على الترخيص
- **Free Trial** – استكشف جميع الميزات دون تكلفة.  
- **Temporary License** – مدّ حدود التجربة لفترة قصيرة.  
- **Purchase** – احصل على ترخيص دائم للاستخدام الإنتاجي.

**التهيئة الأساسية والإعداد**  
يمثل الصنف `Presentation` ملف PowerPoint في الذاكرة ويوفر طرقًا للتعامل مع الشرائح.  
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## دليل التنفيذ
فيما يلي دليل خطوة بخطوة يغطي كل شيء من إنشاء شريحة إلى تدوير المخطط الدائري النهائي.

### تهيئة العرض التقديمي والشريحة
أنشئ كائن `Presentation` جديدًا واسترجع الشريحة الأولى لتكون لوحة الرسم للمخطط.  
```java
import com.aspose.slides.*;

// Create a new presentation instance.
Presentation presentation = new Presentation();
// Access the first slide in the presentation.
ISlide slide = presentation.getSlides().get_Item(0);
```

### إضافة مخطط دائري إلى الشريحة
`addChart` يضيف شكل مخطط من النوع المحدد إلى الشريحة عند الإحداثيات المحددة.  
```java
import com.aspose.slides.*;

// Add a pie chart at position (100, 100) with size (400, 400).
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### تعيين عنوان المخطط
`setTitle` يعيّن عنوانًا نصيًا للمخطط ويضعه في المركز.  
```java
import com.aspose.slides.*;

// Add a title to the pie chart.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### تكوين تسميات البيانات للسلسلة
`setShowValue(true)` يفعّل تسميات القيم الرقمية على كل نقطة بيانات في السلسلة.  
```java
import com.aspose.slides.*;

// Show data values on the first series.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### إعداد ورقة بيانات المخطط
`ChartDataWorkbook` يخزن جدول البيانات الأساسي الذي يزود سلسلة المخطط والفئات.  
```java
import com.aspose.slides.*;

// Prepare the chart data workbook.
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### إضافة فئات إلى المخطط
`addCategory` ينشئ تسمية فئة جديدة لسلسلة بيانات المخطط.  
```java
import com.aspose.slides.*;

// Add new categories.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### إضافة سلسلة وتعبئة نقاط البيانات
`addSeries` ينشئ سلسلة بيانات، و`addDataPointForBarSeries` يضيف قيمًا رقمية لكل فئة.  
```java
import com.aspose.slides.*;

// Add a new series and set its name.
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### تخصيص ألوان السلسلة والحدود
`setColorVaried(true)` يفعّل ألوانًا مختلفة لكل شريحة، و`setFillFormat` يعيّن تعبئة صلبة لكل نقطة بيانات.  
```java
import com.aspose.slides.*;

// Set varied colors for the series sectors.
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Repeat for other data points with different colors and styles.
```

### تكوين تسميات بيانات مخصصة
`setDataLabelFormat` يخصص مظهر التسمية، موقعها، والخط لتوضيح تعليقات المخطط.  
```java
import com.aspose.slides.*;

// Configure custom labels.
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

IDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);

IDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);

// Enable leader lines for labels.
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

### تعيين زاوية الدوران وحفظ العرض التقديمي
`setRotationAngle` يدور المخطط الدائري بالكامل، و`save` يكتب العرض التقديمي إلى ملف.  
```java
import com.aspose.slides.*;

// Set rotation angle.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Save the presentation to a file.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## كيف يتم تدوير المخطط الدائري؟
حمّل كائن المخطط، استدعِ `chart.setRotationAngle(45.0)` (أو أي قيمة بالدرجة)، ثم احفظ العرض التقديمي. تدوير المخطط الدائري يغيّر زاوية البداية، مما يتيح لك إبراز قطاع معين دون تعديل البيانات. هذا الاستدعاء الوحيد يعمل مع أي كائن `Chart` في Aspose.Slides. يمكنك أيضًا دمج الدوران مع ألوان شرائح مختلفة لجذب الانتباه إلى أهم نقطة بيانات.

## المشكلات الشائعة والحلول
| المشكلة | السبب | الحل |
|-------|-------|-----|
| **جميع الشرائح تظهر بنفس اللون** | `setColorVaried(true)` لم يتم استدعاؤه | تأكد من تمكين الألوان المتنوعة لمجموعة السلسلة. |
| **تسميات البيانات لا تظهر** | `showValue` غير مفعّل | استدعِ `setShowValue(true)` على تنسيق التسمية. |
| **الدوران لا يؤثر** | استخدام نسخة أقدم من Aspose.Slides | قم بالترقية إلى الإصدار 25.4 أو أحدث. |
| **استثناء الترخيص أثناء التشغيل** | ملف الترخيص مفقود أو غير صالح | حمّل الترخيص باستخدام `License license = new License(); license.setLicense("Aspose.Slides.lic");` قبل إنشاء كائن `Presentation`. |

## الأسئلة المتكررة

**س: كيف أحصل على ترخيص Aspose.Slides للـ Java؟**  
ج: اطلب نسخة تجريبية مجانية من موقع Aspose، ثم اشترِ ترخيصًا دائمًا. حمّله أثناء التشغيل كما هو موضح في جدول المشكلات الشائعة.

**س: هل يمكنني استخدام هذا الكود مع إصدارات JDK أقدم؟**  
ج: يتطلب الـ API JDK 16 أو أعلى؛ الإصدارات الأقدم غير مدعومة.

**س: هل يمكن تصدير المخطط كصورة بدلاً من PPTX؟**  
ج: نعم — بعد التصيير، استدعِ `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);`.

**س: ماذا لو احتجت إلى أكثر من سلسلة واحدة في المخطط الدائري؟**  
ج: المخططات الدائرية مصممة لسلسلة بيانات واحدة؛ إذا كنت تحتاج إلى عدة سلاسل، فكر في استخدام مخطط الدونات.

**س: هل يعمل Aspose.Slides على خوادم Linux؟**  
ج: بالتأكيد — Aspose.Slides للـ Java مستقل عن المنصة ويعمل على أي نظام تشغيل مع JDK متوافق.

---

**آخر تحديث:** 2026-07-17  
**تم الاختبار مع:** Aspose.Slides للـ Java 25.4 (JDK 16)  
**المؤلف:** Aspose  

{{< blocks/products/products-backtop-button >}}

## دروس ذات صلة

- [كيفية إنشاء مخططات دائرية في عروض Java باستخدام Aspose.Slides: دليل شامل](/slides/java/charts-graphs/creating-pie-charts-java-presentations-aspose-slides/)
- [إتقان المخططات الدائرية في Java باستخدام Aspose.Slides: دليل شامل](/slides/java/charts-graphs/master-pie-charts-aspose-slides-java/)
- [تدوير نصوص المخططات في Java باستخدام Aspose.Slides: دليل شامل](/slides/java/charts-graphs/rotate-chart-texts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}