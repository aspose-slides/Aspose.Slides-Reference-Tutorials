---
date: '2026-06-13'
description: تعلم كيفية إضافة Excel إلى PowerPoint وإنشاء PowerPoint من Excel عن طريق
  إنشاء مخطط دائري ديناميكي باستخدام Aspose.Slides for Java.
keywords:
- add excel to powerpoint
- generate powerpoint from excel
- import excel into powerpoint
- create pie chart java
- set chart data range
schemas:
- author: Aspose
  dateModified: '2026-06-13'
  description: Learn how to add Excel to PowerPoint and generate PowerPoint from Excel
    by creating a dynamic pie chart with Aspose.Slides for Java.
  headline: 'Add Excel to PowerPoint: Dynamic Presentation with Pie Chart Using Aspose.Slides
    for Java'
  type: TechArticle
- description: Learn how to add Excel to PowerPoint and generate PowerPoint from Excel
    by creating a dynamic pie chart with Aspose.Slides for Java.
  name: 'Add Excel to PowerPoint: Dynamic Presentation with Pie Chart Using Aspose.Slides
    for Java'
  steps:
  - name: Initialize Presentation
    text: '- **Purpose:** Creates an empty PowerPoint file in memory.'
  - name: Access First Slide
    text: '- **Explanation:** Retrieves the automatically created first slide.'
  - name: Add Pie Chart to Slide
    text: The `IChart` object represents a chart shape on a slide. - **Parameters:**
      Position (`x`, `y`) and size (`width`, `height`). - **Purpose:** Places a pie
      chart shape on the slide.
  - name: Define Document Directory
    text: '- Set this to the folder containing `book1.xlsx`.'
  - name: Open Workbook
    text: The `Workbook` class from Aspose.Cells loads an Excel file into memory.
      - **Purpose:** Reads the Excel file into memory.
  - name: Create ByteArrayOutputStream
    text: '`ByteArrayOutputStream` provides an in‑memory buffer for binary data. -
      **Purpose:** Provides an in‑memory stream for temporary storage.'
  - name: Save Workbook to Stream
    text: '- **Explanation:** Writes the workbook as an XLSX byte stream.'
  - name: Feed Data into Chart
    text: '- **Purpose:** Links the chart to the Excel data.'
  - name: Define Data Range
    text: The `setRange` method defines the Excel cells used as the chart’s data source.
      - **Explanation:** Points the chart to the exact range on *Sheet2*.
  - name: Configure Series Properties
    text: '- **Purpose:** Enables varied colors for each slice of the pie chart.'
  type: HowTo
- questions:
  - answer: Yes, but evaluation mode adds watermarks and limits some features. For
      production, obtain a temporary or full license.
    question: Can I use Aspose.Slides without a license?
  - answer: Use efficient resource management, split the presentation into smaller
      parts, and dispose of unused objects promptly.
    question: How do I handle large presentations in Aspose.Slides?
  - answer: PPTX, PDF, XPS, ODP, HTML, and image formats such as PNG, JPEG, and BMP.
    question: What file formats can Aspose.Slides export to?
  - answer: Absolutely. Load an existing file with `new Presentation("existing.pptx")`,
      modify slides/charts, then save.
    question: Is it possible to update an existing PowerPoint file instead of creating
      a new one?
  - answer: Yes – after retrieving the series, you can set `series.getDataPoints().get_Item(i).getFormat().getFill().setFillType(FillType.Solid);`
      and assign a `Color`.
    question: Does the library support setting custom colors for individual pie slices?
  type: FAQPage
title: 'إضافة Excel إلى PowerPoint: عرض تقديمي ديناميكي مع مخطط دائري باستخدام Aspose.Slides
  for Java'
url: /ar/java/charts-graphs/aspose-slides-java-pie-chart-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إضافة Excel إلى PowerPoint: عرض تقديمي ديناميكي مع مخطط دائري باستخدام Aspose.Slides for Java

في بيئة اليوم التي تُقَدَّم فيها البيانات، **أضف Excel إلى PowerPoint** بسرعة وموثوقية حتى يتمكن جمهورك من رؤية الأرقام بصيغة مرئية. يشرح هذا الدرس كيفية إنشاء PowerPoint من Excel، وإنشاء مخطط دائري باستخدام Java، وتكوين نطاق بيانات المخطط — كل ذلك باستخدام Aspose.Slides for Java. في النهاية ستحصل على عرض تقديمي جاهز للاستخدام يسحب البيانات الحية مباشرةً من مصنف Excel.

## إجابات سريعة
- **ما المكتبة التي تُنشئ المخططات في Java؟** Aspose.Slides for Java.  
- **هل يمكنني سحب بيانات Excel مباشرةً إلى مخطط PowerPoint؟** نعم – استخدم Aspose.Cells لقراءة المصنف وتغذيته إلى المخطط.  
- **ما نوع المخطط الذي يتم عرضه؟** مخطط دائري.  
- **كيف أضبط نطاق البيانات للمخطط؟** عن طريق استدعاء `chart.getChartData().setRange("Sheet2!$A$1:$B$3")`.  
- **ما الفائدة الأساسية من هذا النهج؟** أتمتة سير عمل “إضافة Excel إلى PowerPoint”، مما يلغي النسخ‑اللصق اليدوي.

## ما هو **إضافة Excel إلى PowerPoint**؟
إضافة Excel إلى PowerPoint تعني استيراد بيانات الجدول إلكترونياً وعرضها داخل مجموعة شرائح. يتيح لك ذلك الحفاظ على البيانات الأصلية بصيغتها Excel مع تقديمها كمخطط مصقول، مما يضمن أن أي تحديث للمصنف ينعكس فوراً في العرض التقديمي.

## لماذا توليد PowerPoint من Excel باستخدام Aspose.Slides for Java؟
توليد PowerPoint من Excel باستخدام Aspose.Slides for Java يتيح لك بناء مجموعات الشرائح في ثوانٍ، سحب البيانات مباشرةً من المصنف دون نسخ‑لصق يدوي. تدعم المكتبة أكثر من 50 تنسيق إدخال وإخراج، وتعالج مصنفات مئات الصفحات دون تحميل الملف بالكامل في الذاكرة، وتوفر تحكمًا برمجيًا كاملاً في تنسيق المخطط، الألوان، ونطاقات البيانات.

## كيف تولد PowerPoint من Excel باستخدام Aspose.Slides for Java؟
حمّل مصنف Excel باستخدام Aspose.Cells، أنشئ `Presentation` جديدًا، أضف شكل مخطط دائري إلى شريحة، ثم اربط المخطط بنطاق بيانات المصنف. ببضع أسطر من كود Java يمكنك إنتاج ملف `.pptx` كامل يعكس أحدث قيم الجدول.

## كيف تستورد Excel إلى PowerPoint باستخدام Aspose.Slides؟
يتم استيراد Excel إلى PowerPoint بقراءة ملف Excel إلى كائن `Workbook`، تحويل المصنف إلى مصفوفة بايت، وتمرير تلك المصفوفة إلى مصدر بيانات المخطط. يقرأ المخطط النطاق المحدد تلقائيًا، وبالتالي يبقى الشكل متزامنًا مع الجدول.

## كيف تضبط نطاق بيانات المخطط في Aspose.Slides for Java؟
استخدم الطريقة `chart.getChartData().setRange("SheetName!$StartCell:$EndCell")` لتوجيه المخطط إلى الخلايا الدقيقة التي تحتوي على الفئات والقيم. هذه الدعوة الواحدة تحدد كلًا من مصدر البيانات وتخطيطه، مما يلغي الحاجة إلى بناء السلاسل يدويًا.

## المتطلبات المسبقة

قبل البدء، تأكد من وجود ما يلي:

- **Java Development Kit (JDK) 1.8+** مثبت.
- مكتبات **Aspose.Slides for Java** و **Aspose.Cells for Java** (Maven، Gradle، أو تحميل JAR مباشرة).
- مصنف Excel (`book1.xlsx`) يحتوي على البيانات التي تريد تصورها.
- ترخيص Aspose صالح (الإصدار التجريبي المجاني يكفي للتقييم).

### المكتبات المطلوبة
ستحتاج إلى Aspose.Slides و Aspose.Cells. استخدم أحد أدوات إدارة الاعتمادات التالية:

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

بدلاً من ذلك، حمّل ملفات JAR مباشرةً من [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### الحصول على الترخيص
- **الإصدار التجريبي:** متاح على [صفحة تنزيل Aspose](https://releases.aspose.com/slides/java/).  
- **ترخيص مؤقت:** للاختبار دون قيود التقييم، قدّم طلبًا عبر [صفحة الترخيص المؤقت لـ Aspose](https://purchase.aspose.com/temporary-license/).  
- **شراء الترخيص:** لاستخدام منتجات Aspose في الإنتاج، اشترِ الترخيص الكامل.

## إعداد Aspose.Slides for Java

أضف اعتماد Aspose.Slides إلى مشروعك (انظر مقتطفات Maven/Gradle أعلاه) وضع ملفات JAR على مسار الفئة إذا لم تستخدم أداة بناء.

### التهيئة الأساسية والإعداد
استورد الفئة الأساسية التي تمثل ملف PowerPoint:  
```java
import com.aspose.slides.Presentation;
```  

## دليل التنفيذ

فيما يلي شرح خطوة‑بخطوة يغطي **إنشاء مخطط دائري Java**، **ضبط نطاق بيانات المخطط**، و**إضافة Excel إلى PowerPoint** في تدفق واحد.

### إنشاء وإضافة مخطط إلى العرض التقديمي

**نظرة عامة:** تهيئة عرض تقديمي جديد، الحصول على الشريحة الأولى، وإدراج مخطط دائري.

#### الخطوة 1: تهيئة العرض التقديمي  
```java
Presentation pres = new Presentation();
```  
- **الغرض:** إنشاء ملف PowerPoint فارغ في الذاكرة.

#### الخطوة 2: الوصول إلى الشريحة الأولى  
```java
ISlide slide = pres.getSlides().get_Item(0);
```  
- **التفسير:** استرجاع الشريحة الأولى التي تم إنشاؤها تلقائيًا.

#### الخطوة 3: إضافة مخطط دائري إلى الشريحة  
كائن `IChart` يمثل شكل مخطط على الشريحة.  
```java
IChart chart = slide.getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
```  
- **المعلمات:** الموضع (`x`, `y`) والحجم (`width`, `height`).  
- **الغرض:** وضع شكل مخطط دائري على الشريحة.

### تحميل المصنف من ملف

**نظرة عامة:** تحميل مصنف Excel الذي يحتوي على بيانات المخطط.

#### الخطوة 1: تعريف دليل المستندات  
```java
String documentDirectory = "YOUR_DOCUMENT_DIRECTORY";
```  
- اضبط هذا على المجلد الذي يحتوي على `book1.xlsx`.

#### الخطوة 2: فتح المصنف  
فئة `Workbook` من Aspose.Cells تقوم بتحميل ملف Excel إلى الذاكرة.  
```java
Workbook workbook = new Workbook(documentDirectory + "/book1.xlsx");
```  
- **الغرض:** قراءة ملف Excel إلى الذاكرة.

### حفظ المصنف إلى ByteArrayOutputStream

**نظرة عامة:** تحويل المصنف إلى مصفوفة بايت حتى يتمكن Aspose.Slides من استهلاكها.

#### الخطوة 1: إنشاء ByteArrayOutputStream  
`ByteArrayOutputStream` يوفر مخزنًا في الذاكرة للبيانات الثنائية.  
```java
ByteArrayOutputStream mem = new ByteArrayOutputStream();
```  
- **الغرض:** توفير تدفق في الذاكرة لتخزين مؤقت.

#### الخطوة 2: حفظ المصنف إلى التدفق  
```java
workbook.save(mem, SaveFormat.XLSX);
mem.flush();
```  
- **التفسير:** يكتب المصنف كتيار بايت XLSX.

### كتابة بيانات المصنف إلى المخطط

**نظرة عامة:** تغذية مصفوفة بايت الخاصة بـ Excel إلى المخطط كمصدر بيانات له.

#### الخطوة 1: تغذية البيانات إلى المخطط  
```java
chart.getChartData().writeWorkbookStream(mem.toByteArray());
```  
- **الغرض:** ربط المخطط ببيانات Excel.

### ضبط نطاق بيانات المخطط وتكوين السلاسل

**نظرة عامة:** تحديد الخلايا التي يجب أن يقرأها المخطط وتحسين التنسيق البصري.

#### الخطوة 1: تعريف نطاق البيانات  
طريقة `setRange` تحدد خلايا Excel المستخدمة كمصدر بيانات للمخطط.  
```java
chart.getChartData().setRange("Sheet2!$A$1:$B$3");
```  
- **التفسير:** يوجه المخطط إلى النطاق الدقيق في *Sheet2*.

#### الخطوة 2: تكوين خصائص السلسلة  
```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getParentSeriesGroup().setColorVaried(true);
```  
- **الغرض:** تمكين ألوان مختلفة لكل شريحة من المخطط الدائري.

### حفظ العرض التقديمي إلى ملف

**نظرة عامة:** حفظ العرض التقديمي المكتمل على القرص.

#### الخطوة 1: تعريف مسار الإخراج  
```java
String outPath = "YOUR_OUTPUT_DIRECTORY/response2.pptx";
```  
- اختر مجلدًا تريد حفظ ملف PowerPoint النهائي فيه.

#### الخطوة 2: حفظ العرض التقديمي  
```java
pres.save(outPath, SaveFormat.Pptx);
```  
- **التفسير:** يكتب العرض التقديمي كملف `.pptx`.

## التطبيقات العملية

1. **تقارير الأعمال:** تحويل جداول المبيعات الشهرية إلى عروض شرائح مصقولة بأمر واحد.  
2. **الأدوات التعليمية:** عرض تحليلات إحصائية للعرض في الفصول الدراسية دون إنشاء مخططات يدويًا.  
3. **دمج لوحة التحكم:** أتمتة إنشاء لوحات تحكم على شكل شرائح تسحب البيانات الحية من مصنفات Excel.

## اعتبارات الأداء

- **إدارة الذاكرة:** غلف التدفقات بـ `try‑with‑resources` أو أغلقها في كتلة `finally` لتجنب التسربات.  
- **مجموعات البيانات الكبيرة:** عالج البيانات على دفعات أو استخدم `Workbook.getWorksheets().clear()` بعد استخراج القيم المطلوبة.  
- **التحميل الكسول:** حمّل المصنف فقط عندما تحتاج إلى تعبئة المخطط، وليس عند بدء تشغيل التطبيق.

## المشكلات الشائعة والحلول

| المشكلة | الحل |
|-------|----------|
| **المخطط لا يظهر بيانات** | تحقق من أن سلسلة النطاق تطابق اسم الورقة وعناوين الخلايا بدقة (`Sheet2!$A$1:$B$3`). |
| **OutOfMemoryError** | استخدم `try (ByteArrayOutputStream mem = new ByteArrayOutputStream()) { … }` لضمان تحرير التدفق بسرعة. |
| **الترخيص غير مُطبق** | حمّل الترخيص قبل إنشاء أي كائن Aspose: `License lic = new License(); lic.setLicense("Aspose.Slides.lic");` |

## الأسئلة المتكررة

**س: هل يمكنني استخدام Aspose.Slides بدون ترخيص؟**  
ج: نعم، لكن وضع التقييم يضيف علامات مائية ويقيد بعض الميزات. للإنتاج، احصل على ترخيص مؤقت أو كامل.

**س: كيف أتعامل مع عروض تقديمية كبيرة في Aspose.Slides؟**  
ج: استخدم إدارة موارد فعّالة، قسّم العرض إلى أجزاء أصغر، وتخلص من الكائنات غير المستخدمة بسرعة.

**س: ما صيغ الملفات التي يمكن لـ Aspose.Slides تصديرها؟**  
ج: PPTX، PDF، XPS، ODP، HTML، وصيغ الصور مثل PNG، JPEG، و BMP.

**س: هل يمكن تحديث ملف PowerPoint موجود بدلاً من إنشاء ملف جديد؟**  
ج: بالتأكيد. حمّل الملف الموجود بـ `new Presentation("existing.pptx")`، عدّل الشرائح/المخططات، ثم احفظه.

**س: هل تدعم المكتبة تعيين ألوان مخصصة لشريحة الدائرة الفردية؟**  
ج: نعم – بعد استرجاع السلسلة، يمكنك تعيين `series.getDataPoints().get_Item(i).getFormat().getFill().setFillType(FillType.Solid);` وتحديد `Color`.

## الموارد
- **التوثيق:** [Aspose.Slides Java API Reference](https://reference.aspose.com/slides/java/)
- **التنزيل:** [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)
- **شراء الترخيص:** [Buy Aspose Products](https://purchase.aspose.com/buy)
- **الإصدار التجريبي المجاني:** [Try Aspose.Slides Free](https://releases.aspose.com/slides/java/)
- **الترخيص المؤقت:** [Get a Temporary License](https://purchase.aspose.com/temporary-license/)

---

**آخر تحديث:** 2026-06-13  
**تم الاختبار مع:** Aspose.Slides 25.4 for Java (JDK 16) & Aspose.Cells 25.4  
**المؤلف:** Aspose  

{{< blocks/products/products-backtop-button >}}

## دروس ذات صلة

- [How to Update PowerPoint Chart Data Range Using Aspose.Slides for Java](/slides/java/charts-graphs/aspose-slides-java-modify-chart-data-range/)
- [How to add pie chart PowerPoint with Aspose.Slides for Java](/slides/java/charts-graphs/aspose-slides-java-create-pie-chart/)
- [How to Add Charts to PowerPoint Using Aspose.Slides for Java: A Step-by-Step Guide](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}