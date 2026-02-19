---
date: '2026-02-19'
description: تعلم كيفية إنشاء مخطط دائري في جافا باستخدام Aspose.Slides وتخصيص ألوان
  المخطط الدائري، وإضافة سلاسل المخطط، والعمل مع ورقة بيانات المخطط، وتعيين زاوية
  الدوران.
keywords:
- Aspose.Slides Java
- Java pie charts
- data visualization in Java
title: كيفية تخصيص ألوان المخطط الدائري في جافا باستخدام Aspose.Slides – دليل شامل
url: /ar/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/
weight: 1
---

 code block placeholders as is.

Proceed.

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إنشاء مخططات دائرية باستخدام Aspose.Slides for Java: دليل شامل

## المقدمة
إن إنشاء عروض تقديمية ديناميكية وجذابة بصريًا أمر حيوي لتوصيل المعلومات بشكل مؤثر. مع Aspose.Slides for Java، يمكنك دمج مخططات معقدة مثل المخططات الدائرية في شرائحك بسهولة، **تخصيص ألوان المخطط الدائري**، وتعزيز تصور البيانات دون عناء. سيوجهك هذا الدليل الشامل خلال عملية إنشاء وتخصيص مخطط دائري باستخدام Aspose.Slides Java، مع حل التحديات الشائعة في العروض التقديمية بسهولة.

**ما ستتعلمه:**
- تهيئة عرض تقديمي وإضافة شرائح.
- إنشاء وتكوين مخطط دائري في شريحتك.
- ضبط عناوين المخطط، تسميات البيانات، و**تخصيص ألوان المخطط الدائري**.
- تحسين الأداء وإدارة الموارد بفعالية.
- دمج Aspose.Slides في مشاريع Java باستخدام Maven أو Gradle.

لنبدأ بالتأكد من أن لديك جميع الأدوات والمعارف اللازمة للمتابعة!

## إجابات سريعة
- **ما هو الصنف الأساسي لبدء عرض تقديمي؟** `Presentation` من `com.aspose.slides`.
- **أي طريقة تضيف مخططًا دائريًا إلى شريحة؟** `addChart(ChartType.Pie, …)`.
- **كيف تمكّن الألوان المتنوعة لكل شريحة؟** اضبط `setColorVaried(true)` على مجموعة السلسلة.
- **هل يمكن تدوير المخطط الدائري؟** نعم، استخدم `setRotationAngle(double)` على كائن المخطط.
- **هل أحتاج إلى ترخيص للاستخدام في الإنتاج؟** يلزم وجود ترخيص Aspose.Slides للنشر التجاري.

## ما معنى “تخصيص ألوان المخطط الدائري”؟
تخصيص ألوان المخطط الدائري يعني تعيين ألوان تعبئة مميزة لكل شريحة من الدائرة، مما يحسن القراءة والتأثير البصري. في Aspose.Slides يمكنك تحقيق ذلك بتمكين الألوان المتنوعة ثم ضبط ألوان تعبئة صلبة لنقاط البيانات الفردية.

## لماذا نستخدم Aspose.Slides for Java لإنشاء المخططات الدائرية؟
- **تحكم كامل** في مظهر المخطط دون الحاجة إلى Microsoft Office.
- **توافق متعدد المنصات** – يعمل على Windows وLinux وmacOS.
- **API غني** لربط البيانات، التنسيق، وتصدير إلى PPTX أو PDF أو صور.
- **مرونة الترخيص** – ابدأ بتجربة مجانية وارتقِ عندما تحتاج إلى المجموعة الكاملة من الميزات.

## المتطلبات المسبقة
قبل الغوص في هذا الدرس، تأكد من أن لديك الإعداد التالي جاهزًا:

### المكتبات المطلوبة والإصدارات والاعتمادات
- **Aspose.Slides for Java**: الإصدار 25.4 أو أحدث.
- **مجموعة تطوير جافا (JDK)**: الإصدار 16 أو أعلى.

### متطلبات إعداد البيئة
- بيئة تطوير تحتوي على Java مثبتة ومُعَدة.
- بيئة تطوير متكاملة (IDE) مثل IntelliJ IDEA أو Eclipse أو NetBeans.

### المتطلبات المعرفية
- فهم أساسي لبرمجة Java.
- إلمام بـ Maven أو Gradle لإدارة الاعتمادات.

## إعداد Aspose.Slides for Java
لبدء استخدام Aspose.Slides في مشاريع Java الخاصة بك، تحتاج إلى إضافة المكتبة كاعتماد. إليك كيفية القيام بذلك باستخدام أدوات بناء مختلفة:

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
ضمن الملف `build.gradle` الخاص بك:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**تحميل مباشر**  
إذا كنت تفضل عدم استخدام أداة بناء، حمّل أحدث إصدار من [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### خطوات الحصول على الترخيص
- **تجربة مجانية**: ابدأ بتجربة مجانية لاستكشاف ميزات Aspose.Slides.  
- **ترخيص مؤقت**: احصل على ترخيص مؤقت للاستخدام الممتد دون قيود.  
- **شراء**: فكر في الشراء إذا كنت تحتاج إلى وصول طويل الأمد.

**التهيئة الأساسية والإعداد**  
لبدء استخدام Aspose.Slides، قم بتهيئة مشروعك بإنشاء كائن عرض تقديمي جديد:
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## دليل التنفيذ
الآن لنقسم عملية إضافة وتخصيص مخطط دائري إلى خطوات قابلة للإدارة.

### تهيئة العرض التقديمي والشريحة
ابدأ بإعداد عرض تقديمي جديد والوصول إلى الشريحة الأولى. هذه هي مساحة العمل لإنشاء المخططات:
```java
import com.aspose.slides.*;

// Create a new presentation instance.
Presentation presentation = new Presentation();
// Access the first slide in the presentation.
ISlide slide = presentation.getSlides().get_Item(0);
```

### إضافة مخطط دائري إلى الشريحة
أدرج مخططًا دائريًا في الموضع المحدد مع مجموعة بيانات افتراضية:
```java
import com.aspose.slides.*;

// Add a pie chart at position (100, 100) with size (400, 400).
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### ضبط عنوان المخطط
خصص مخططك بضبط العنوان وتوسيطه:
```java
import com.aspose.slides.*;

// Add a title to the pie chart.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### تكوين تسميات البيانات للسلسلة
تأكد من أن تسميات البيانات تعرض القيم لتوضيح أفضل:
```java
import com.aspose.slides.*;

// Show data values on the first series.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### إعداد ورقة عمل بيانات المخطط
قم بإعداد ورقة عمل بيانات المخطط عن طريق مسح السلاسل والفئات الحالية:
```java
import com.aspose.slides.*;

// Prepare the chart data workbook.
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### إضافة فئات إلى المخطط
عرّف الفئات لمخططك الدائري:
```java
import com.aspose.slides.*;

// Add new categories.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### إضافة سلسلة وتعبئة نقاط البيانات
أنشئ سلسلة واملأها بنقاط البيانات – هنا نضيف **سلسلة المخطط**:
```java
import com.aspose.slides.*;

// Add a new series and set its name.
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### تخصيص ألوان السلسلة والحدود
عزز المظهر البصري بضبط الألوان وتخصيص الحدود – هذا يخص **تخصيص ألوان المخطط الدائري** مباشرةً:
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
قم بضبط التسميات لكل نقطة بيانات:
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

### ضبط زاوية الدوران وحفظ العرض التقديمي
أكمل مخططك الدائري بـ **ضبط زاوية الدوران** وحفظ الملف:
```java
import com.aspose.slides.*;

// Set rotation angle.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Save the presentation to a file.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## المشكلات الشائعة والحلول
| المشكلة | السبب | الحل |
|-------|-------|-----|
| **جميع الشرائح تظهر بنفس اللون** | لم يتم استدعاء `setColorVaried(true)` | تأكد من تمكين الألوان المتنوعة على مجموعة السلسلة. |
| **تسميات البيانات لا تظهر** | تم تعطيل علم `showValue` | استدعِ `setShowValue(true)` على تنسيق التسمية المناسب. |
| **الدوران لا يؤثر** | استخدام إصدار أقدم من Aspose.Slides | حدّث إلى الإصدار 25.4 أو أحدث. |
| **استثناء الترخيص أثناء التشغيل** | ملف الترخيص مفقود أو غير صالح | حمّل الترخيص باستخدام `License license = new License(); license.setLicense("Aspose.Slides.lic");` قبل إنشاء `Presentation`. |

## الأسئلة المتكررة

**س: كيف أحصل على ترخيص Aspose.Slides لجافا؟**  
ج: يمكنك طلب تجربة مجانية من موقع Aspose، ثم شراء ترخيص دائم. حمّله وقت التشغيل كما هو موضح في جدول المشكلات الشائعة.

**س: هل يمكنني استخدام هذا الكود مع إصدارات JDK أقدم؟**  
ج: يتطلب الـ API JDK 16 أو أعلى؛ الإصدارات الأقدم غير مدعومة.

**س: هل يمكن تصدير المخطط كصورة بدلاً من PPTX؟**  
ج: نعم، استدعِ `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);` بعد عملية الرسم.

**س: ماذا لو احتجت لإضافة أكثر من سلسلة إلى مخطط دائري؟**  
ج: عادةً ما يعرض المخطط الدائري سلسلة واحدة؛ إذا كنت تحتاج إلى عدة سلاسل ففكّر في استخدام مخطط الدونات بدلاً من ذلك.

**س: هل تعمل المكتبة على خوادم Linux؟**  
ج: بالتأكيد – Aspose.Slides for Java مستقل عن المنصة ويعمل على أي نظام تشغيل يدعم JDK متوافق.

---

**آخر تحديث:** 2026-02-19  
**تم الاختبار مع:** Aspose.Slides for Java 25.4 (jdk16)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}