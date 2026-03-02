---
date: '2026-03-02'
description: تعلم كيفية إضافة Excel إلى PowerPoint وإنشاء PowerPoint من Excel عن طريق
  إنشاء مخطط دائري ديناميكي باستخدام Aspose.Slides for Java.
keywords:
- Aspose.Slides for Java
- Java PowerPoint automation
- Excel data integration
title: 'إضافة Excel إلى PowerPoint: عرض تقديمي ديناميكي مع مخطط دائري باستخدام Aspose.Slides
  للـ Java'
url: /ar/java/charts-graphs/aspose-slides-java-pie-chart-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إضافة Excel إلى PowerPoint: عرض تقديمي ديناميكي مع مخطط دائري باستخدام Aspose.Slides للـ Java

في بيئة اليوم المعتمدة على البيانات، **add Excel to PowerPoint** بسرعة وبشكل موثوق حتى يتمكن جمهورك من رؤية الأرقام بصيغة بصرية. يشرح هذا الدليل خطوة بخطوة كيفية إنشاء PowerPoint من Excel، وإنشاء مخطط دائري باستخدام Java، وتكوين نطاق بيانات المخطط — كل ذلك باستخدام Aspose.Slides للـ Java. في النهاية ستحصل على عرض تقديمي جاهز للاستخدام يسحب البيانات الحية مباشرةً من ملف Excel.

## إجابات سريعة
- **ما المكتبة التي تُنشئ المخططات في Java؟** Aspose.Slides for Java.
- **هل يمكنني سحب بيانات Excel مباشرةً إلى مخطط PowerPoint؟** Yes – use Aspose.Cells to read the workbook and feed it to the chart.
- **ما نوع المخطط الذي تم عرضه؟** A pie chart.
- **كيف يمكنني تعيين نطاق البيانات للمخطط؟** By calling `chart.getChartData().setRange("Sheet2!$A$1:$B$3")`.
- **ما الفائدة الأساسية من هذا النهج؟** Automates the “add Excel to PowerPoint” workflow, eliminating manual copy‑paste.

## ما هو **add Excel to PowerPoint**؟
إضافة Excel إلى PowerPoint تعني استيراد بيانات جداول البيانات برمجيًا وعرضها داخل مجموعة شرائح. باستخدام Aspose.Slides و Aspose.Cells، يمكنك قراءة أي ملف Excel، وربط الخلايا بسلاسل المخطط، وإنتاج عرض تقديمي مصقول دون الحاجة إلى فتح PowerPoint يدويًا.

## لماذا إنشاء PowerPoint من Excel باستخدام Aspose.Slides للـ Java؟
- **السرعة:** Build reports in seconds, not minutes.
- **الدقة:** Data is read directly from the source workbook, removing transcription errors.
- **المرونة:** Customize chart colors, styles, and data ranges on the fly.
- **القابلية للتوسع:** Integrate into batch jobs, web services, or scheduled reporting pipelines.

## المتطلبات المسبقة

قبل البدء، تأكد من أن لديك:

- **Java Development Kit (JDK) 1.8+** مثبت.
- **Aspose.Slides للـ Java** و **Aspose.Cells للـ Java** المكتبات (Maven أو Gradle أو تحميل JAR مباشرة).
- مصنف Excel (`book1.xlsx`) يحتوي على البيانات التي تريد تصورها.
- رخصة Aspose صالحة (الإصدار التجريبي المجاني يعمل للتقييم).

### المكتبات المطلوبة
ستحتاج إلى Aspose.Slides و Aspose.Cells. استخدم أحد أدوات إدارة التبعيات التالية:

**Maven:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

بدلاً من ذلك، قم بتحميل ملفات JAR مباشرةً من [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### الحصول على الترخيص
- **Free Trial:** متاح على [صفحة تحميل Aspose](https://releases.aspose.com/slides/java/).  
- **Temporary License:** للاختبار دون قيود التقييم، قدِّم طلبًا للحصول على ترخيص مؤقت عبر [صفحة الترخيص المؤقت لـ Aspose](https://purchase.aspose.com/temporary-license/).  
- **Purchase License:** لاستخدام منتجات Aspose في الإنتاج، اشترِ الترخيص الكامل.

## إعداد Aspose.Slides للـ Java

أضف تبعية Aspose.Slides إلى مشروعك (انظر مقتطفات Maven/Gradle أعلاه) وضع ملفات JAR في مسار الفئة (classpath) إذا لم تكن تستخدم أداة بناء.

### التهيئة الأساسية والإعداد
استورد الفئة الأساسية التي تمثل ملف PowerPoint:

```java
import com.aspose.slides.Presentation;
```

## دليل التنفيذ

فيما يلي دليل خطوة بخطوة يغطي **create pie chart java**، **set chart data range**، و **add Excel to PowerPoint** في تدفق واحد.

### إنشاء وإضافة مخطط إلى العرض التقديمي

**نظرة عامة:** تهيئة عرض تقديمي جديد، الحصول على الشريحة الأولى، وإدراج مخطط دائري.

#### الخطوة 1: تهيئة العرض التقديمي
```java
Presentation pres = new Presentation();
```
- **الغرض:** ينشئ ملف PowerPoint فارغ في الذاكرة.

#### الخطوة 2: الوصول إلى الشريحة الأولى
```java
ISlide slide = pres.getSlides().get_Item(0);
```
- **التفسير:** يسترجع الشريحة الأولى التي تم إنشاؤها تلقائيًا.

#### الخطوة 3: إضافة مخطط دائري إلى الشريحة
```java
IChart chart = slide.getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
```
- **المعلمات:** الموضع (`x`, `y`) والحجم (`width`, `height`).  
- **الغرض:** يضع شكل مخطط دائري على الشريحة.

### تحميل مصنف من ملف

**نظرة عامة:** تحميل مصنف Excel الذي يحتوي على بيانات المخطط.

#### الخطوة 1: تحديد دليل المستند
```java
String documentDirectory = "YOUR_DOCUMENT_DIRECTORY";
```
- اضبطه على المجلد الذي يحتوي على `book1.xlsx`.

#### الخطوة 2: فتح المصنف
```java
Workbook workbook = new Workbook(documentDirectory + "/book1.xlsx");
```
- **الغرض:** يقرأ ملف Excel إلى الذاكرة.

### حفظ المصنف إلى ByteArrayOutputStream

**نظرة عامة:** تحويل المصنف إلى مصفوفة بايت حتى يتمكن Aspose.Slides من استهلاكها.

#### الخطوة 1: إنشاء ByteArrayOutputStream
```java
ByteArrayOutputStream mem = new ByteArrayOutputStream();
```
- **الغرض:** يوفر تدفقًا في الذاكرة للتخزين المؤقت.

#### الخطوة 2: حفظ المصنف إلى التدفق
```java
workbook.save(mem, SaveFormat.XLSX);
mem.flush();
```
- **التفسير:** يكتب المصنف كتيار بايت بصيغة XLSX.

### كتابة بيانات المصنف إلى المخطط

**نظرة عامة:** إمداد المخطط بمصفوفة بايت Excel كمصدر للبيانات.

#### الخطوة 1: إمداد البيانات إلى المخطط
```java
chart.getChartData().writeWorkbookStream(mem.toByteArray());
```
- **الغرض:** يربط المخطط ببيانات Excel.

### تعيين نطاق بيانات المخطط وتكوين السلاسل

**نظرة عامة:** تحديد الخلايا التي يجب على المخطط قراءتها وتعزيز التنسيق البصري.

#### الخطوة 1: تعريف نطاق البيانات
```java
chart.getChartData().setRange("Sheet2!$A$1:$B$3");
```
- **التفسير:** يوجه المخطط إلى النطاق الدقيق في *Sheet2*.

#### الخطوة 2: تكوين خصائص السلسلة
```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getParentSeriesGroup().setColorVaried(true);
```
- **الغرض:** يتيح ألوانًا مختلفة لكل شريحة من المخطط الدائري.

### حفظ العرض التقديمي إلى ملف

**نظرة عامة:** حفظ العرض التقديمي المكتمل على القرص.

#### الخطوة 1: تحديد مسار الإخراج
```java
String outPath = "YOUR_OUTPUT_DIRECTORY/response2.pptx";
```
- اختر مجلدًا حيث تريد حفظ ملف PowerPoint النهائي.

#### الخطوة 2: حفظ العرض التقديمي
```java
pres.save(outPath, SaveFormat.Pptx);
```
- **التفسير:** يكتب العرض التقديمي كملف `.pptx`.

## التطبيقات العملية

1. **Business Reporting:** تحويل جداول مبيعات شهرية إلى مجموعات شرائح مصقولة بأمر واحد.  
2. **Educational Tools:** عرض التحليلات الإحصائية للعروض الصفية دون إنشاء مخطط يدويًا.  
3. **Dashboard Integration:** أتمتة إنشاء لوحات معلومات مبنية على الشرائح تسحب البيانات الحية من مصنفات Excel.

## اعتبارات الأداء

- **Memory Management:** غلف التدفقات باستخدام try‑with‑resources أو أغلقها في كتلة `finally` لتجنب التسريبات.  
- **Large Datasets:** عالج البيانات على دفعات أو استخدم `Workbook.getWorksheets().clear()` بعد استخراج القيم المطلوبة.  
- **Lazy Loading:** حمّل المصنف فقط عندما تحتاج إلى ملء المخطط، وليس عند بدء تشغيل التطبيق.

## المشكلات الشائعة والحلول

| المشكلة | الحل |
|-------|----------|
| **المخطط لا يظهر بيانات** | تحقق من أن سلسلة النطاق تطابق اسم الورقة وعناوين الخلايا تمامًا (`Sheet2!$A$1:$B$3`). |
| **OutOfMemoryError** | استخدم `try (ByteArrayOutputStream mem = new ByteArrayOutputStream()) { … }` لضمان تحرير التدفق على الفور. |
| **الترخيص غير مُطبق** | حمّل الترخيص قبل إنشاء أي كلاس من Aspose: `License lic = new License(); lic.setLicense("Aspose.Slides.lic");` |

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.Slides بدون ترخيص؟**  
ج: نعم، لكن وضع التقييم يضيف علامات مائية ويقيد بعض الميزات. للإنتاج، احصل على ترخيص مؤقت أو كامل.

**س: كيف أتعامل مع عروض تقديمية كبيرة في Aspose.Slides؟**  
ج: استخدم إدارة موارد فعّالة، قسّم العرض إلى أجزاء أصغر، وتخلص من الكائنات غير المستخدمة على الفور.

**س: ما صيغ الملفات التي يمكن لـ Aspose.Slides تصديرها؟**  
ج: PPTX، PDF، XPS، ODP، HTML، وصيغ الصور مثل PNG، JPEG، و BMP.

**س: هل يمكن تحديث ملف PowerPoint موجود بدلاً من إنشاء ملف جديد؟**  
ج: بالتأكيد. حمّل ملفًا موجودًا باستخدام `new Presentation("existing.pptx")`، عدّل الشرائح/المخططات، ثم احفظه.

**س: هل تدعم المكتبة تعيين ألوان مخصصة لكل شريحة من المخطط الدائري؟**  
ج: نعم – بعد استرجاع السلسلة، يمكنك تعيين `series.getDataPoints().get_Item(i).getFormat().getFill().setFillType(FillType.Solid);` وتعيين `Color`.

## الموارد
- **الوثائق:** [Aspose.Slides Java API Reference](https://reference.aspose.com/slides/java/)
- **التنزيل:** [Aspose.Slides for Java Releases](https://releases.aspose.com/slides/java/)
- **شراء الترخيص:** [Buy Aspose Products](https://purchase.aspose.com/buy)
- **الإصدار التجريبي المجاني:** [Try Aspose.Slides Free](https://releases.aspose.com/slides/java/)
- **الترخيص المؤقت:** [Get a Temporary License](https://purchase.aspose.com/temporary-license)

---

**آخر تحديث:** 2026-03-02  
**تم الاختبار مع:** Aspose.Slides 25.4 للـ Java (JDK 16) & Aspose.Cells 25.4  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}