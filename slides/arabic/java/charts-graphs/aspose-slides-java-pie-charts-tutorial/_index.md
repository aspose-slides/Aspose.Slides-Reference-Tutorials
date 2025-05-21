---
"date": "2025-04-17"
"description": "تعرّف على كيفية إنشاء وتخصيص المخططات الدائرية باستخدام Aspose.Slides لجافا. يغطي هذا البرنامج التعليمي كل شيء، من الإعداد إلى التخصيص المتقدم."
"title": "إنشاء مخططات دائرية في جافا باستخدام Aspose.Slides - دليل شامل"
"url": "/ar/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إنشاء مخططات دائرية باستخدام Aspose.Slides لـ Java: برنامج تعليمي كامل

## مقدمة
يُعد إنشاء عروض تقديمية ديناميكية وجذابة بصريًا أمرًا بالغ الأهمية لتقديم معلومات مؤثرة. مع Aspose.Slides لجافا، يمكنك دمج مخططات معقدة، مثل المخططات الدائرية، بسلاسة في شرائحك، مما يُحسّن من تصوّر البيانات بسهولة. سيرشدك هذا الدليل الشامل خلال عملية إنشاء مخطط دائري وتخصيصه باستخدام Aspose.Slides لجافا، مما يُساعدك على حلّ تحديات العروض التقديمية الشائعة بسهولة.

**ما سوف تتعلمه:**
- تهيئة العرض التقديمي وإضافة الشرائح.
- إنشاء مخطط دائري وتكوينه على الشريحة الخاصة بك.
- تعيين عناوين المخططات، وعلامات البيانات، والألوان.
- تحسين الأداء وإدارة الموارد بشكل فعال.
- دمج Aspose.Slides في مشاريع Java باستخدام Maven أو Gradle.

لنبدأ بالتأكد من أن لديك كل الأدوات والمعرفة اللازمة للمتابعة!

## المتطلبات الأساسية
قبل الغوص في هذا البرنامج التعليمي، تأكد من أن لديك الإعداد التالي جاهزًا:

### المكتبات والإصدارات والتبعيات المطلوبة
- **Aspose.Slides لـ Java**:تأكد من أن لديك الإصدار 25.4 أو أحدث.
- **مجموعة تطوير جافا (JDK)**:يجب أن يكون الإصدار 16 أو أعلى.

### متطلبات إعداد البيئة
- بيئة تطوير مع تثبيت Java وتكوينه.
- بيئة تطوير متكاملة (IDE) مثل IntelliJ IDEA، أو Eclipse، أو NetBeans.

### متطلبات المعرفة
- فهم أساسيات برمجة جافا.
- المعرفة بـ Maven أو Gradle لإدارة التبعيات.

## إعداد Aspose.Slides لـ Java
لبدء استخدام Aspose.Slides في مشاريع جافا، عليك إضافة المكتبة كاعتمادية. إليك كيفية القيام بذلك باستخدام أدوات بناء مختلفة:

**مافن**
أضف هذه القطعة إلى `pom.xml` ملف:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**جرادل**
قم بتضمين ما يلي في `build.gradle` ملف:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**التحميل المباشر**
إذا كنت تفضل عدم استخدام أداة البناء، قم بتنزيل الإصدار الأحدث من [إصدارات Aspose.Slides لـ Java](https://releases.aspose.com/slides/java/).

### خطوات الحصول على الترخيص
- **نسخة تجريبية مجانية**:ابدأ بالتجربة المجانية لاستكشاف ميزات Aspose.Slides.
- **رخصة مؤقتة**:الحصول على ترخيص مؤقت للاستخدام الموسع دون قيود.
- **شراء**:فكر في الشراء إذا كنت بحاجة إلى الوصول على المدى الطويل.

**التهيئة والإعداد الأساسي**
لبدء استخدام Aspose.Slides، قم بتهيئة مشروعك عن طريق إنشاء كائن عرض تقديمي جديد:
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## دليل التنفيذ
الآن دعنا نقوم بتقسيم عملية إضافة مخطط دائري وتخصيصه إلى خطوات قابلة للإدارة.

### تهيئة العرض التقديمي والشريحة
ابدأ بإعداد عرض تقديمي جديد والوصول إلى الشريحة الأولى. هذه هي لوحتك لإنشاء المخططات البيانية:
```java
import com.aspose.slides.*;

// إنشاء مثيل عرض تقديمي جديد.
Presentation presentation = new Presentation();
// قم بالوصول إلى الشريحة الأولى في العرض التقديمي.
islide slides = presentation.getSlides().get_Item(0);
```

### إضافة مخطط دائري إلى الشريحة
إدراج مخطط دائري في الموضع المحدد بمجموعة بيانات افتراضية:
```java
import com.aspose.slides.*;

// أضف مخططًا دائريًا في الموضع (100، 100) بالحجم (400، 400).
ischart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### تعيين عنوان الرسم البياني
قم بتخصيص الرسم البياني الخاص بك عن طريق تعيين العنوان وتمركزه:
```java
import com.aspose.slides.*;

// أضف عنوانًا إلى المخطط الدائري.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### تكوين تسميات البيانات للسلسلة
تأكد من أن تسميات البيانات تعرض القيم من أجل الوضوح:
```java
import com.aspose.slides.*;

// إظهار قيم البيانات في السلسلة الأولى.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### إعداد ورقة عمل بيانات الرسم البياني
قم بإعداد ورقة عمل بيانات الرسم البياني الخاص بك عن طريق مسح السلاسل والفئات الموجودة:
```java
import com.aspose.slides.*;

// تحضير مصنف بيانات الرسم البياني.
int defaultWorksheetIndex = 0;
isChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### إضافة فئات إلى الرسم البياني
قم بتحديد الفئات لمخططك الدائري:
```java
import com.aspose.slides.*;

// إضافة فئات جديدة.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### إضافة سلسلة وملء نقاط البيانات
إنشاء سلسلة وملئها بنقاط البيانات:
```java
import com.aspose.slides.*;

// أضف سلسلة جديدة وحدد اسمها.
ischartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### تخصيص ألوان السلسلة والحدود
قم بتعزيز المظهر البصري من خلال تعيين الألوان وتخصيص الحدود:
```java
import com.aspose.slides.*;

// تعيين ألوان متنوعة لقطاعات السلسلة.
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

isChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// كرر ذلك لنقاط البيانات الأخرى بألوان وأنماط مختلفة.
```

### تكوين تسميات البيانات المخصصة
قم بضبط العلامات لكل نقطة بيانات:
```java
import com.aspose.slides.*;

// تكوين العلامات المخصصة.
isDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

isDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);

isDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);

// تمكين خطوط القائد للعلامات.
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

### تعيين زاوية الدوران وحفظ العرض التقديمي
قم بإنهاء مخطط الفطيرة الخاص بك عن طريق تعيين زاوية الدوران وحفظ العرض التقديمي:
```java
import com.aspose.slides.*;

// ضبط زاوية الدوران.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// حفظ العرض التقديمي في ملف.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## خاتمة
في هذا البرنامج التعليمي، تعلمت كيفية إنشاء وتخصيص المخططات الدائرية باستخدام Aspose.Slides لجافا. باتباع هذه الخطوات، يمكنك تحسين عروضك التقديمية بتصورات بيانات جذابة بصريًا. إذا كانت لديك أي أسئلة أو كنت بحاجة إلى مزيد من المساعدة، فلا تتردد في التواصل معنا.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}