---
date: '2026-03-07'
description: تعلم كيفية إنشاء مخطط خطي في Java باستخدام Aspose.Slides، إضافة عنوان
  للمخطط، إضافة خطوط الشبكة، تنسيق تسميات المخطط وحفظ عروض تقديمية احترافية.
keywords:
- Aspose.Slides Java
- create charts in Java
- format PowerPoint charts
title: كيفية إنشاء مخطط خطي باستخدام Aspose.Slides في Java – دليل شامل
url: /ar/java/charts-graphs/create-format-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية إنشاء مخطط خطي باستخدام Aspose.Slides في Java

## كيفية إنشاء مخطط خطي في Java باستخدام Aspose.Slides

### المقدمة
إنشاء عروض تقديمية جذابة بصريًا أمر حاسم للتواصل الفعال. سواء كنت محترفًا في الأعمال أو معلمًا، غالبًا ما تحتاج إلى **إنشاء مخطط خطي** يكون معلوماتيًا وجذابًا من الناحية الجمالية. في هذا الدليل سنستعرض كيفية استخدام **Aspose.Slides for Java** لتوليد مخطط خطي، إضافة عنوان للمخطط، إضافة خطوط شبكة، تنسيق تسميات المخطط، وحفظ النتيجة كملف PowerPoint.

#### إجابات سريعة
- **ما هي المكتبة الأفضل لإنشاء المخططات في Java؟** Aspose.Slides for Java
- **ما هو نوع المخطط الذي يركز عليه هذا الدليل؟** مخطط خطي مع علامات
- **هل أحتاج إلى ترخيص لتشغيل العينة؟** ترخيص مؤقت مجاني يعمل للتقييم
- **ما هو بيئة التطوير المتكاملة (IDE) التي يمكنني استخدامها؟** أي IDE للـ Java مثل IntelliJ IDEA أو Eclipse أو NetBeans
- **كيف يتم تنسيق عناصر المخطط؟** باستخدام استدعاءات API متسلسلة للعناوين، المحاور، خطوط الشبكة، الأساطير، والخلفيات

### ما هو المخطط الخطي ولماذا نستخدم Aspose.Slides؟
يعرض المخطط الخطي نقاط البيانات المتصلة بخطوط مستقيمة، مما يجعله مثاليًا لإظهار الاتجاهات عبر الزمن. يتيح لك Aspose.Slides إنشاء وتخصيص هذه المخططات برمجيًا بالكامل، مما يلغي الحاجة إلى تحرير PowerPoint يدويًا.

### المتطلبات المسبقة
- **Java Development Kit (JDK) 8+** مثبت
- **IDE** (IntelliJ IDEA, Eclipse, NetBeans، إلخ)
- **Aspose.Slides for Java** المكتبة (مضافة عبر Maven أو Gradle)

#### المكتبات والاعتمادات المطلوبة
**Maven**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

بدلاً من ذلك، قم بتنزيل أحدث ملف JAR من [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### الحصول على الترخيص
- احصل على [ترخيص تجريبي مجاني](https://purchase.aspose.com/temporary-license/) للاختبار.
- اشترِ ترخيصًا كاملاً من [الموقع الرسمي لـ Aspose](https://purchase.aspose.com/buy) للاستخدام في الإنتاج.

### إعداد Aspose.Slides for Java
1. **أضف الاعتماد** المعروض أعلاه إلى مشروعك.
2. **طبق الترخيص** (إذا كان لديك) قبل إنشاء أي كائنات عرض تقديمي.

```java
import com.aspose.slides.Presentation;
// Initialize the Presentation object
Presentation pres = new Presentation();
```

## تنفيذ خطوة بخطوة

### الخطوة 1: إنشاء دليل الإخراج (create directory java)
```java
import java.io.File;
// Define the target directory
String dataDir = "YOUR_DOCUMENT_DIRECTORY";

// Check if directory exists; create it if not
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    new File(dataDir).mkdirs(); // Create directories recursively
}
```
*لماذا هذا مهم:* التأكد من وجود المجلد يمنع حدوث `FileNotFoundException` عند حفظ العرض لاحقًا.

### الخطوة 2: إضافة شريحة وإدراج مخطط خطي
```java
import com.aspose.slides.*;
// Create a new presentation
Presentation pres = new Presentation();
try {
    // Access the first slide
    ISlide slide = pres.getSlides().get_Item(0);

    // Add a chart to the slide
    IChart chart = slide.getShapes().addChart(
        ChartType.LineWithMarkers, 50, 50, 500, 400);
```
*شرح:* هذا ينشئ شريحة جديدة ويضع **مخططًا خطيًا مع علامات** في الإحداثيات المحددة.

### الخطوة 3: إضافة عنوان للمخطط (add chart title)
```java
// Enable and format the title
chart.setTitle(true);
IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding()
    .getParagraphs().get_Item(0).getPortions().get_Item(0);

chartTitle.setText("Sample Line Chart");
chartTitle.getPortionFormat().setFontBold(NullableBool.True);
chartTitle.getPortionFormat().setFillType(FillType.Solid);
chartTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
chartTitle.getPortionFormat().setFontHeight(20);
```
*نصيحة:* استخدام عنوان غامق ورمادي يجعل المخطط قابلًا للتعرف عليه فورًا.

### الخطوة 4: تنسيق المحاور وإضافة خطوط شبكة (add grid lines)
#### تنسيق المحور العمودي
```java
IChartAxis verticalAxis = chart.getAxes().getVerticalAxis();

// Format major grid lines
verticalAxis.getMajorGridLinesFormat().getLine()
    .setFillType(FillType.Solid)
    .getFillFormat().getSolidFillColor().setColor(Color.BLUE);
verticalAxis.getMajorGridLinesFormat().getLine().setWidth(5);

// Configure axis properties
verticalAxis.setNumberFormat("0.0%");
verticalAxis.setMaxValue(15f);
verticalAxis.setMinValue(-2f);
```

#### تنسيق المحور الأفقي
```java
IChartAxis horizontalAxis = chart.getAxes().getHorizontalAxis();

// Format major grid lines
horizontalAxis.getMajorGridLinesFormat().getLine()
    .setFillType(FillType.Solid)
    .getFillFormat().getSolidFillColor().setColor(Color.GREEN);
horizontalAxis.getMajorGridLinesFormat().getLine().setWidth(5);

// Set label positions and rotations
horizontalAxis.setTickLabelPosition(TickLabelPositionType.Low);
horizontalAxis.setTickLabelRotationAngle(45);
```
*لماذا هذا مهم:* خطوط الشبكة الواضحة والتسميات المدورة تحسن قابلية القراءة، خاصةً عندما تكون نقاط البيانات كثيفة.

### الخطوة 5: تخصيص الأسطورة (add chart title – already covered, but legend is part of overall formatting)
```java
IChartPortionFormat txtLeg = chart.getLegend().getTextFormat().getPortionFormat();
txtLeg.setFontBold(NullableBool.True);
txtLeg.getFillFormat().setFillType(FillType.Solid)
    .getSolidFillColor().setColor(Color.RED);

// Prevent overlap with the chart area
chart.getLegend().setOverlay(true);
```

### الخطوة 6: تعيين ألوان الخلفية (format chart labels – part of overall visual styling)
```java
chart.getBackWall().setThickness(1);
chart.getBackWall().getFormat().getFill()
    .setFillType(FillType.Solid)
    .getSolidFillColor().setColor(Color.ORANGE);

chart.getPlotArea().getFormat().getFill()
    .setFillType(FillType.Solid)
    .getSolidFillColor().setColor(new Color(PresetColor.LightCyan));
```

### الخطوة 7: حفظ العرض التقديمي
```java
// Save the presentation to disk
pres.save("YOUR_OUTPUT_DIRECTORY/FormattedChart_out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose(); // Clean up resources
}
```
*النتيجة:* لديك الآن ملف PowerPoint (`FormattedChart_out.pptx`) يحتوي على مخطط خطي مُنسق بالكامل.

## التطبيقات العملية
- **تقارير الأعمال:** عرض الأداء ربع السنوي باستخدام خطوط الاتجاه.
- **شرائح تعليمية:** تصور البيانات العلمية للمحاضرات.
- **اقتراحات المشاريع:** إبراز المعالم والتوقعات.
- **تحليل التسويق:** تقديم اتجاهات عائد الاستثمار للحملات.
- **دمج لوحة التحكم:** تصدير البيانات الحية إلى PowerPoint لاجتماعات أصحاب المصلحة.

## اعتبارات الأداء
- **إدارة الذاكرة:** دائمًا استدعِ `dispose()` على كائن `Presentation` لتحرير الموارد الأصلية بسرعة.

## المشكلات الشائعة والحلول
| المشكلة | الحل |
|-------|----------|
| **License not applied** | Load the trial/full license before creating any `Presentation` objects. |
| **Chart appears blank** | Verify that the slide actually contains data series; add series if needed. |
| **File not saved** | Ensure the output directory exists (use the “create directory java” step). |
| **Colors not applied** | Use `Color` constants from `java.awt.Color` or `PresetColor`. |

## الأسئلة المتكررة

**س: هل يمكنني إنشاء أنواع مخططات أخرى غير المخططات الخطية؟**  
ج: نعم، يدعم Aspose.Slides المخططات الشريطية، الدائرية، المبعثرة، والعديد من أنواع المخططات الأخرى.

**س: كيف يمكنني إضافة سلاسل بيانات متعددة إلى المخطط الخطي؟**  
ج: استخدم `chart.getChartData().getSeries().add(...)` لإدراج سلاسل إضافية قبل التنسيق.

**س: هل يمكن تصدير المخطط كصورة؟**  
ج: بالتأكيد. استدعِ `chart.getChartData().getChartDataWorkbook().save(...)` أو قم بتحويل الشريحة إلى تنسيق صورة.

**س: هل أحتاج إلى ترخيص مدفوع للتطوير؟**  
ج: ترخيص مؤقت مجاني يكفي للتقييم؛ يلزم ترخيص تجاري للنشر في بيئات الإنتاج.

**س: ما إصدارات Java المدعومة؟**  
ج: تعمل المكتبة مع JDK 8 حتى JDK 22 (استخدم المصنف المناسب، مثل `jdk16`).

---

**آخر تحديث:** 2026-03-07  
**تم الاختبار مع:** Aspose.Slides for Java 25.4 (مصنف jdk16)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}