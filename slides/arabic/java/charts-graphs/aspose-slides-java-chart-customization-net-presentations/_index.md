---
date: '2026-01-17'
description: تعلم كيفية إضافة سلاسل إلى المخطط وتخصيص مخططات الأعمدة المتكدسة في عروض
  .NET باستخدام Aspose.Slides للغة Java.
keywords:
- Aspose.Slides for Java
- .NET Presentations
- Chart Customization
title: إضافة سلسلة إلى المخطط باستخدام Aspose.Slides للـ Java في .NET
url: /ar/java/charts-graphs/aspose-slides-java-chart-customization-net-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إتقان تخصيص المخططات في عروض .NET باستخدام Aspose.Slides for Java

## مقدمة
في عالم العروض التقديمية للتعامل مع البيانات، والتي تشكل أدوات لا غنى عنها تُحوِّل أرقامًا بصرية إلى قصص بصرية جذابة. عندما تحتاج إلى ** إضافة سلسلة إلى Bebe** برمجيًا، خاصة داخل ملفات عرض .NET، قد يبدو الأمر مرهقًا. لحسن الحظ، توجد **Aspose.Slides for Java** برمجة تطبيقات قوية غير مفيدة بلغة معينة معينة وتسمح بإنشاء تطبيقات بسيطة وتعرفها بشكل بسيط — حتى عندما يكون المستهدف هو PPTX الخاص بـ .NET.

ستكتشف في هذا الدرس كيفية **إضافة سلسلة إلى نمط**، وكيفية **إضافة مخطط** من نوع العمود المتراكم، وكيفية ضبط الاستجابة البصرية مثل العرض الشامل. في النهاية، ستكون قادرة على توليد شرائح ديناميكية ديناميكية مصقولة ومهنية.

**ما ستتعلمه**
- كيفية إنشاء عرض كامل باستخدام Aspose.Slides
- كيفية ** إضافة مخطط تراكم ** إلى شريحة
- كيفية ** إضافة سلسلة إلى الفساد** وتحديد الفئات
- كيفية تجميع البيانات وضبط الإعدادات البصرية

لإنجاز بيئة التطوير الخاصة بك.

## إجابات سريعة
- **ما هو الصف الأساسي بداية عرض تقديمي؟** `Presentation`
- **أي طريقة تُضيف مخططًا إلى شريحة؟** `slide.getShapes().addChart(...)`
- **كيف تضيف سلسلة جديدة؟** `chart.getChartData().getSeries().add(...)`
- **هل يمكن تغيير العرض بين الأعمدة؟** نعم، باستخدام `setGapWidth()` على مجموعة السلاسل
- **هل أحتاج إلى ترخيص للإنتاج؟** نعم، يلزم وجود ترخيص صالح لـ Aspose.Slides for Java

## ما هو "إضافة سلسلة إلى الرسم البياني"؟
إضافة سلسلة إلى مخطط تعني مجموعة بيانات جديدة سيعرضها وتكون كعنصر بصري مميز (مثل عمود جديد، أو خط، أو شريحة). يمكن لكل سلسلة أن تمتلك قيمها، ألوانها، وتنسيقها الخاص، مما يتيح لك مقارنة مجموعات بيانات متعددة جنبًا إلى جنب.

## لماذا نستخدم Aspose.Slides لـ Java لتعديل العروض التقديمية بتنسيق .NET؟
- **متعددة المنصات**: اكتب كود Java مرة واحدة واستهدف ملفات PPTX المستخدمة في تطبيقات .NET.
- **بدون الاعتماد على COM أو Office**: يعمل على الموقع، خطوط CI، والحاويات.
- **واجهة مخططات واسعة النطاق**: تدعم 50 شخصًا من المشاهير، بما في ذلك مخططات أكثر العمود المتراكم.

## المتطلبات الأساسية
1. مكتبة **Aspose.Slides for Java** (الإصدار 25.4 أو أحدث).
2. أداة بناء Maven أو Gradle، أو تحميل JAR يدويًا.
3. معرفة قاعدة بـ Java وفهم قواعد ملفات PPTX.

## إعداد Aspose.Slides لـ Java
### تثبيت مخضرم
أضف الاعتماد التالي إلى ملف `pom.xml` الخاص بك:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### تركيب Gradle
أدرج هذا السطر في ملف `build.gradle` الخاص بك:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### تحميل مباشر
أقل من ذلك، يمكنك الحصول على أحدث JAR من صفحة الاختلافات الرسمية: [Aspose.Slides for Java Releases](https://releases.aspose.com/slides/Java/).

** الحصول على الترخيص **
ابدأ مجانًا عن طريق تنزيل الترخيص المؤقت من [هنا](https://purchase.aspose.com/temporary-license/). للاستخدام في الإنتاج، اشترِ ترخيصًا كاملاً لفتح جميع الميزات.

## دليل التنفيذ خطوة بخطوة
ستجد أسفل كل خطوة مقتطفًا موجزًا ​​للتعليمات البرمجية (لم يتغير عن البرنامج التعليمي الأصلي) متبوعًا بشرح لما يفعله.

### الخطوة 1: إنشاء عرض تقديمي فارغ
```java
import com.aspose.slides.*;

// Initialize an empty presentation
Presentation presentation = new Presentation();

// Access the first slide (automatically created)
ISlide slide = presentation.getSlides().get_Item(0);

// Save the presentation to a specified path
presentation.save("YOUR_OUTPUT_DIRECTORY/Empty_Presentation.pptx", SaveFormat.Pptx);
```
*نبدأ بملف PPTX نظيف، وهو يوفر لنا لوحة رسم لإضافة المخططات.*

### الخطوة 2: أضف مخططًا عموديًا مكدسًا إلى الشريحة
```java
// Import necessary Aspose.Slides classes
import com.aspose.slides.*;

// Add a chart of type StackedColumn
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);

// Save the presentation with the new chart
presentation.save("YOUR_OUTPUT_DIRECTORY/Chart_Added.pptx", SaveFormat.Pptx);
```
*طريقة `addChart` تُنشئ **مخطط عمود متراكم** وتضعه في الزاوية العليا اليسرى من الشريحة.*

### الخطوة 3: أضف السلاسل إلى المخطط (الهدف الرئيسي)
```java
// Accessing the default worksheet index for chart data
int defaultWorksheetIndex = 0;

// Adding series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Save the presentation after adding series
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Added.pptx", SaveFormat.Pptx);
```
*هنا نقوم **بإضافة سلسلة إلى المخطط** – كل استدعاء يُنشئ سلسلة بيانات جديدة ستظهر كمجموعة أعمدة منفصلة.*

### الخطوة 4: أضف الفئات إلى المخطط
```java
// Adding categories to the chart
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));

// Save the presentation after adding categories
presentation.save("YOUR_OUTPUT_DIRECTORY/Categories_Added.pptx", SaveFormat.Pptx);
```
*الفئات تعمل كعناوين لمحور X، مما يمنح كل عمود معنىً واضحًا.*

### الخطوة 5: املأ بيانات السلاسل
```java
// Accessing a particular series for data population
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Adding data points to the series
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Save the presentation with populated data
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Data_Populated.pptx", SaveFormat.Pptx);
```
*نقاط البيانات تُعطي كل سلسلة قيمها الرقمية، والتي سيعرضها المخطط كارتفاعات للأعمدة.*

### الخطوة 6: حدد عرض الفجوة لمجموعة سلاسل المخطط
```java
// Setting the gap width between bars
series.getParentSeriesGroup().setGapWidth(50);

// Save the presentation after adjusting the gap width
presentation.save("YOUR_OUTPUT_DIRECTORY/Set_GapWidth.pptx", SaveFormat.Pptx);
```
*ضبط عرض الفجوة يحسن قابلية القراءة، خاصةً عندما تكون هناك فئات كثيرة.*

## حالات الاستخدام الشائعة
- **التقارير المالية** – مقارنة الإيرادات السنوية عبر وحدات الأعمال.
- **لوحات العلوم** – شرح نسبي أو لكل فريق.
- **تحليلات التسويق** – تصور الحملات إلى جنب إلى جنب.

## نصائح الأداء
- **أعد استخدام كائن `العرض التقديمي`** عند إنشاء مخططات متعددة رئيسية لاستهلاك الذاكرة.
- **قلل عدد البيانات نقاط** إلى الحد الضروري فقط للقصة البصرية.
- **حرّر الكائنات** (`presentation.dispose()`) بعد الحفظ لتحرير الموارد.

## الأسئلة المتداولة
**س: هل يمكنني إضافة خطط أخرى غير العمود المتراكم؟**
ج: نعم، يدعم Aspose.Slides الأنواع الخطية، الدائرية، المساحية، والعديد من الأنواع الأخرى.

**س: هل أحتاج إلى ترخيص بشكل منفصل لإخراج .NET؟**
ج: لا، لتشغيل نفسه لـ Java يعمل مع صيغ الصوت، بما في ذلك ملفات PPTX الخاصة بـ .NET.

**س: كيف غيّر لوحة الألوان؟**
ج: استخدم `chart.getChartData().getSeries().get_Item(i).getFormat().getFill().setFillType(FillType.Solid)` وتحديد اللون المطلوب عبر `Color`.

**س: هل يمكن إضافة تسميات البيانات برمجياً؟**
ج: مؤكد. حتماً `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)` لعرض القيم.

**س: ماذا لو الخارجية إلى تحديث عرض تقديمي الموجود؟**
ج: أخرى نتنياهو الملف باستخدام `new Presentation("existing.pptx")`، لعدة جيدة، ثم احفظه مرة أخرى.

## خاتمة
أصبح لديك الآن دليل شامل من البداية إلى النهاية حول كيفية **إضافة سلسلة إلى المخطط**، وإنشاء **مخطط عمود متراكم**، وضبط مظهره في عروض .NET باستخدام Aspose.Slides for Java. جرّب أنواع مخططات مختلفة، ألوانًا متعددة، ومصادر بيانات متنوعة لتصنع تقارير بصرية مقنعة تُبهِر أصحاب المصلحة.

---

**Last Updated:** 2026-01-17  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
