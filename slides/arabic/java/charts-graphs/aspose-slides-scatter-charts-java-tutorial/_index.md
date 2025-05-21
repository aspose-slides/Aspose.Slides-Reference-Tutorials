---
"date": "2025-04-17"
"description": "تعرّف على كيفية إنشاء مخططات تشتت ديناميكية باستخدام Aspose.Slides لجافا. حسّن عروضك التقديمية بميزات مخططات قابلة للتخصيص."
"title": "إنشاء وتخصيص مخططات التشتت في Java باستخدام Aspose.Slides"
"url": "/ar/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إنشاء وتخصيص مخططات التشتت في Java باستخدام Aspose.Slides

حسّن عروضك التقديمية بإضافة مخططات تشتت ديناميكية باستخدام جافا مع Aspose.Slides. سيرشدك هذا البرنامج التعليمي الشامل خلال إعداد الأدلة، وتهيئة العروض التقديمية، وإنشاء مخططات تشتت، وإدارة بيانات المخططات، وتخصيص أنواع السلاسل والعلامات، وحفظ عملك - كل ذلك بسهولة.

**ما سوف تتعلمه:**
- إعداد دليل لتخزين ملفات العرض التقديمي
- تهيئة العروض التقديمية ومعالجتها باستخدام Aspose.Slides
- إنشاء مخططات التشتت على الشرائح
- إدارة البيانات وإضافتها إلى سلسلة المخططات
- تخصيص أنواع وعلامات سلسلة المخططات
- حفظ العرض التقديمي الخاص بك مع التعديلات

دعونا نبدأ بالتأكد من أن لديك المتطلبات الأساسية اللازمة.

## المتطلبات الأساسية

لمتابعة هذا البرنامج التعليمي، تأكد من أن لديك:
- **Aspose.Slides لـ Java**:يجب أن يكون الإصدار 25.4 أو أحدث.
- **مجموعة تطوير جافا (JDK)**:مطلوب JDK 8 أو أعلى.
- المعرفة الأساسية ببرمجة Java والتعرف على أدوات بناء Maven أو Gradle.

## إعداد Aspose.Slides لـ Java

قبل أن نبدأ في الترميز، قم بدمج Aspose.Slides في مشروعك باستخدام إحدى الطرق التالية:

### مافن
قم بتضمين هذه التبعية في `pom.xml` ملف:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### جرادل
أضف هذا السطر إلى `build.gradle` ملف:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

بدلاً من ذلك، قم بتنزيل أحدث إصدار من Aspose.Slides لـ Java من [إصدارات Aspose](https://releases.aspose.com/slides/java/).

#### الحصول على الترخيص
- **نسخة تجريبية مجانية**:ابدأ بفترة تجريبية مجانية لمدة 30 يومًا لاستكشاف الميزات.
- **رخصة مؤقتة**:الحصول على ترخيص مؤقت للاختبار الموسع.
- **شراء**:قم بشراء ترخيص للحصول على الوصول الكامل والدعم.

الآن، قم بتهيئة Aspose.Slides في تطبيق Java الخاص بك عن طريق إضافة الواردات الضرورية كما هو موضح أدناه.

## دليل التنفيذ

### إعداد الدليل
أولاً، تأكد من وجود دليلنا لتخزين ملفات العروض التقديمية. هذه الخطوة تمنع حدوث أخطاء أثناء حفظ الملف.

#### إنشاء الدليل إذا لم يكن موجودًا
```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // إنشاء الدليل
    new File(dataDir).mkdirs();
}
```
يتحقق هذا المقطع من وجود دليل محدد ويُنشئه إذا لم يكن موجودًا. ويستخدم `File.exists()` للتحقق من الوجود و `File.mkdirs()` لإنشاء الدلائل.

### تهيئة العرض التقديمي

بعد ذلك، قم بتهيئة كائن العرض التقديمي الخاص بك حيث ستضيف مخطط التشتت.

#### تهيئة العرض التقديمي الخاص بك
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```
هنا، `new Presentation()` يُنشئ عرضًا تقديميًا فارغًا. نصل إلى الشريحة الأولى للعمل عليها مباشرةً.

### إنشاء المخطط
الخطوة التالية هي إنشاء مخطط تشتت على الشريحة الأولية لدينا.

#### إضافة مخطط التشتت إلى الشريحة
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
يُضيف هذا المقتطف من الكود مخططًا تشتتًا بخطوط ناعمة إلى الشريحة الأولى. تُحدد المعلمات موضع المخطط وحجمه.

### إدارة بيانات المخططات
الآن دعنا ندير بيانات الرسم البياني لدينا عن طريق مسح أي سلسلة موجودة وإضافة سلاسل جديدة.

#### إدارة سلسلة الرسوم البيانية
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeries;

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// إضافة سلسلة جديدة إلى الرسم البياني
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
```
يقوم هذا القسم بمسح البيانات الموجودة وإضافة سلسلتين جديدتين إلى مخطط التشتت الخاص بنا.

### إضافة نقاط البيانات لسلسلة التشتت
لتصور بياناتنا، نضيف نقاطًا إلى كل سلسلة في مخطط التشتت.

#### إضافة نقاط البيانات
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```
نحن نستخدم `addDataPointForScatterSeries()` لإضافة نقاط بيانات إلى سلسلتنا الأولى. تُعرّف المعلمات قيمتي X وY.

### تعديل نوع السلسلة والعلامة
قم بتخصيص مظهر الرسم البياني الخاص بك عن طريق تغيير نوع ونمط العلامات في كل سلسلة.

#### تخصيص السلسلة
```java
import com.aspose.slides.MarkerStyleType;

series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);

// تعديل السلسلة الثانية
series = chart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```
تُعدّل هذه التغييرات نوع السلسلة لاستخدام الخطوط المستقيمة والعلامات. كما نحدد حجم العلامة ورمزها للتمييز البصري.

### حفظ العرض التقديمي
وأخيرًا، احفظ العرض التقديمي الخاص بك مع جميع التعديلات التي أجريتها.

#### احفظ عرضك التقديمي
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```
يستخدم `SaveFormat.Pptx` لتحديد تنسيق PowerPoint لحفظ ملفك. هذه الخطوة ضرورية لحفظ جميع التغييرات.

## التطبيقات العملية
وفيما يلي بعض حالات الاستخدام في العالم الحقيقي:
1. **التحليل المالي**:استخدم مخططات التشتت لعرض اتجاهات الأسهم بمرور الوقت.
2. **البحث العلمي**:تمثل نقاط البيانات التجريبية للتحليل.
3. **إدارة المشاريع**:تصور تخصيص الموارد ومقاييس التقدم.

يتيح لك دمج Aspose.Slides في نظامك أتمتة إنشاء التقارير، مما يعزز الإنتاجية والدقة.

## اعتبارات الأداء
للحصول على الأداء الأمثل:
- إدارة استخدام الذاكرة عن طريق التخلص من العروض التقديمية بعد الحفظ.
- استخدم هياكل بيانات فعالة لمجموعات البيانات الكبيرة.
- تقليل العمليات التي تتطلب موارد كثيفة داخل الحلقات.

تضمن أفضل الممارسات التنفيذ السلس حتى مع عمليات التلاعب المعقدة بالمخططات.

## خاتمة
في هذا البرنامج التعليمي، تعلمت كيفية إعداد المجلدات، وتهيئة عروض Aspose.Slides التقديمية، وإنشاء مخططات التشتت وتخصيصها، وإدارة بيانات السلسلة، وتعديل العلامات، وحفظ عملك. لمزيد من الاستكشاف حول إمكانيات Aspose.Slides، ننصحك بالتعمق في ميزات أكثر تقدمًا مثل الرسوم المتحركة وانتقالات الشرائح.

**الخطوات التالية**:جرب أنواعًا مختلفة من المخططات أو قم بدمج هذه التقنيات في مشروع Java أكبر.

## التعليمات

### كيف يمكنني تغيير لون العلامات؟
لتغيير لون العلامة، استخدم `series.getMarker().getFillFormat().setFillColor(ColorObject)`، أين `ColorObject` هو اللون الذي تريده.

### هل يمكنني إضافة أكثر من سلسلتين إلى مخطط التشتت؟
نعم، يمكنك إضافة عدد كبير من السلاسل حسب الحاجة عن طريق تكرار عملية إضافة سلاسل ونقاط بيانات جديدة.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}