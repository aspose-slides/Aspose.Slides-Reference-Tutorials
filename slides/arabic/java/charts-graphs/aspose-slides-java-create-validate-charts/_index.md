---
date: '2026-07-22'
description: تعلم كيفية إضافة مخطط عمودي متجمع في Java باستخدام Aspose.Slides، مع
  تغطية إنشاء المخطط خطوة بخطوة، والتحقق من صحة التخطيط، وكيفية إضافة المخطط إلى الشريحة.
keywords:
- add clustered column chart
- how to add chart
- create chart in java
- add chart to slide
lastmod: '2026-07-22'
og_description: إضافة مخطط عمودي متجمع في Java باستخدام Aspose.Slides. يوضح هذا الدليل
  إنشاء المخطط خطوة بخطوة، والتحقق من الصحة، وكيفية إضافة المخطط إلى الشريحة في ملف
  PowerPoint.
og_image_alt: 'Developer guide: add clustered column chart in Java using Aspose.Slides'
og_title: إضافة مخطط عمودي متجمع في Java باستخدام Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-07-22'
  description: Learn how to add clustered column chart in Java with Aspose.Slides,
    covering step‑by‑step chart creation, layout validation, and how to add chart
    to slide.
  headline: How to add clustered column chart in Java with Aspose.Slides
  type: TechArticle
- description: Learn how to add clustered column chart in Java with Aspose.Slides,
    covering step‑by‑step chart creation, layout validation, and how to add chart
    to slide.
  name: How to add clustered column chart in Java with Aspose.Slides
  steps:
  - name: Set Up Your Presentation
    text: 'Load an existing file or start a new one:'
  - name: Add a clustered column chart
    text: '`ChartType.ClusteredColumn` specifies a clustered column chart type. Here
      we **add clustered column chart** to the first slide at a specific location:'
  - name: Validate the chart layout
    text: '`validateChartLayout()` checks the chart''s geometry and ensures elements
      are correctly positioned. After placing the chart, make sure everything lines
      up correctly:'
  type: HowTo
- questions:
  - answer: It’s a powerful Java library for creating, editing, and converting PowerPoint
      files without Microsoft Office.
    question: What is Aspose.Slides?
  - answer: Visit [Aspose Temporary License](https://purchase.aspose.com/temporary-license/)
      and follow the request steps.
    question: How do I obtain a temporary license?
  - answer: Yes, Aspose.Slides supports bar, line, pie, area, and many more chart
      types.
    question: Can I create other chart types besides clustered column?
  - answer: Absolutely. Use `chart.getChartData().getSeries().add(...)` and `chart.getChartData().getCategories().add(...)`.
    question: Is there a way to add data to the chart programmatically?
  - answer: The Java version is cross‑platform and runs on Windows, Linux, and macOS.
    question: Does the library work on all operating systems?
  type: FAQPage
tags:
- add clustered column chart
- Aspose.Slides
- Java charting
- create chart in java
- add chart to slide
title: كيفية إضافة مخطط عمودي متجمع في Java باستخدام Aspose.Slides
url: /ar/java/charts-graphs/aspose-slides-java-create-validate-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية إضافة مخطط عمودي متجمع في Java باستخدام Aspose.Slides

في عالم اليوم القائم على البيانات، يعتبر تصور المعلومات عبر المخططات أمرًا أساسيًا لتحويل الأرقام الخام إلى رؤى واضحة. إذا كنت بحاجة إلى **إضافة مخطط عمودي متجمع** إلى عرض PowerPoint برمجيًا، فإن Aspose.Slides for Java يوفر واجهة برمجة تطبيقات نظيفة ومُدارة بالكامل تتيح لك إنشاء المخططات وتكوينها والتحقق منها دون الحاجة لفتح PowerPoint. سواء كنت تبني محرك تقارير، أو تطبيقًا تعليميًا، أو لوحة تحكم في الوقت الفعلي، فإن هذا الدرس يرافقك في كل خطوة—من إعداد المكتبة إلى حفظ العرض النهائي.

## إجابات سريعة
- **ما المكتبة التي تتيح لك إضافة مخطط عمودي متجمع في Java؟** Aspose.Slides for Java.  
- **ما نوع المخطط الذي يتم عرضه؟** مخطط عمودي متجمع.  
- **كيف تتحقق من تخطيط المخطط؟** استدعِ `validateChartLayout()` على كائن المخطط.  
- **هل يمكنك استرجاع حجم مساحة الرسم؟** نعم، عبر `chart.getPlotArea().getActualX()` والطرق ذات الصلة.  
- **ما هي الخطوة النهائية؟** حفظ العرض باستخدام `pres.save(...)`.

## ما ستتعلمه
- كيفية إعداد Aspose.Slides for Java في مشروعك  
- **كيفية إضافة مخطط** — تحديدًا مخطط عمودي متجمع — وإدراجه في شريحة  
- **كيفية التحقق من تخطيط المخطط** برمجيًا  
- استرجاع وتفسير أبعاد مساحة الرسم  
- حفظ العرض مع المخطط المحدث  

## المتطلبات المسبقة
- **Java Development Kit (JDK)** – JDK 16 أو أحدث.  
- **Aspose.Slides for Java** – المكتبة (سنستخدم الإصدار 25.4 في الأمثلة).  
- **IDE** – IntelliJ IDEA أو Eclipse أو أي محرر يدعم Java.  

## إعداد Aspose.Slides لـ Java
يمكنك إضافة Aspose.Slides إلى مشروعك باستخدام Maven أو Gradle أو تحميل مباشر.

### Maven
يضيف مقطع Maven مكتبة Aspose.Slides إلى مسار الفئة في مشروعك.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
أدرج هذا السطر في ملف `build.gradle` لجلب المكتبة من Maven Central.

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### تحميل مباشر
بدلاً من ذلك، قم بتحميل المكتبة مباشرة من [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### الحصول على الترخيص
- **Free Trial** – ميزات محدودة للتقييم السريع.  
- **[Aspose Temporary License](https://purchase.aspose.com/temporary-license/)** – اطلب مفتاحًا قصير الأمد للاختبار الكامل.  
- **Purchase** – اشترِ اشتراكًا للاستخدام الإنتاجي.

#### التهيئة الأساسية والإعداد
`Presentation` هي الفئة الأساسية في Aspose.Slides التي تمثل ملف PowerPoint في الذاكرة. بعد إنشاء نسخة يمكنك البدء في إضافة شرائح أو أشكال أو مخططات.

```java
import com.aspose.slides.Presentation;

public class Main {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        // Your chart creation logic will go here
        presentation.dispose();  // Clean up resources
    }
}
```

## كيفية إضافة مخطط إلى الشريحة وإنشاء مخطط عمودي متجمع
`Presentation` تمثل مستند PowerPoint الذي تقوم بتحريره. حمّل أو أنشئ `Presentation`، وصول إلى الشريحة الأولى، واستدعِ `addChart` مع `ChartType.ClusteredColumn`. هذا يُدرج مخططًا عموديًا متجمعًا بالكامل في الإحداثيات المحددة، ثم يمكنك ملء السلاسل والفئات قبل الحفظ. سيتبنى المخطط تلقائيًا سمة الشريحة، ويمكنك تخصيص الألوان والعناوين والوسائط حسب الحاجة.

إنشاء المخططات في العروض التقديمية سهل مع Aspose.Slides. الأقسام التالية تفصل كل خطوة.

### الخطوة 1: إعداد العرض التقديمي
حمّل ملفًا موجودًا أو ابدأ ملفًا جديدًا:

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;

Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.Pptx");
```

### الخطوة 2: إضافة مخطط عمودي متجمع
`ChartType.ClusteredColumn` يحدد نوع المخطط العمودي المتجمع. هنا ن **نضيف مخطط عمودي متجمع** إلى الشريحة الأولى في موقع محدد:

```java
import com.aspose.slides.ShapeType;

Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.ClusteredColumn, 100, 100, 500, 350
);
```

### الخطوة 3: التحقق من تخطيط المخطط
`validateChartLayout()` يتحقق من هندسة المخطط ويضمن أن العناصر موضوعة بشكل صحيح. بعد وضع المخطط، تأكد من أن كل شيء مصطف بشكل سليم:

```java
chart.validateChartLayout();
```

#### لماذا التحقق مهم
`validateChartLayout()` يتحقق من تداخل العناصر، أو فقدان المحاور، وأي تناقضات بصرية أخرى، لضمان أن يرى جمهورك مخططًا مصقولًا.

## كيفية الحصول على أبعاد مساحة الرسم من المخطط
`Chart` هو الكائن الذي يضم جميع الجوانب البصرية والبيانية للمخطط. `getPlotArea()` تُعيد مستطيل مساحة الرسم للمخطط، مما يتيح محاذاة دقيقة للأشكال الإضافية. احصل على كائن المخطط لقراءة مقاييس مساحة الرسم:

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
```

استرجاع مقاييس مساحة الرسم:

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();

System.out.println("Plot Area: X=" + x + ", Y=" + y + ", Width=" + w + ", Height=" + h);
```

هذه القيم مفيدة عندما تحتاج إلى محاذاة أشكال أخرى أو حساب هوامش مخصصة.

## كيفية حفظ العرض التقديمي مع المخطط الجديد
`Presentation` هو الحاوية التي تحتفظ بجميع الشرائح والأشكال والمخططات. استدعِ `save` على نسخة `Presentation`، مع تحديد صيغة الإخراج (مثل PPTX). هذا يكتب العرض المعدل إلى القرص، محافظًا على المخطط المضاف حديثًا وأي تحقق من التخطيط قمت به، مع تحرير الموارد الأصلية عند التخلص.

```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/Chart_out.pptx", SaveFormat.Pptx);
```

## تطبيقات عملية
- **Business Reporting** – أتمتة عروض الربع السنوية بمخططات محدثة.  
- **Educational Tools** – إنشاء شرائح محاضرات توضح اتجاهات البيانات مباشرة.  
- **Dashboard Integration** – تصدير التحليلات في الوقت الفعلي إلى PowerPoint لتقارير الإدارة.

## اعتبارات الأداء
- تخلص من كائن `Presentation` (`pres.dispose()`) لتحرير الموارد الأصلية.  
- عند معالجة عروض كبيرة، أعد استخدام كائنات المخطط حيثما أمكن لتقليل استهلاك الذاكرة.  
- فضل واجهات برمجة التطبيقات المتدفقة لمجموعات البيانات الضخمة لتجنب تحميل كل شيء في الذاكرة مرة واحدة.  
- يدعم Aspose.Slides **أكثر من 40 نوعًا من المخططات** ويمكنه رسم مخططات بـ **حتى 10,000 نقطة بيانات لكل سلسلة** دون تأخير ملحوظ.

## المشكلات الشائعة واستكشاف الأخطاء
| Symptom | Likely Cause | Fix |
|---------|--------------|-----|
| يظهر المخطط فارغًا | لم تُضاف سلاسل البيانات | استخدم `chart.getChartData().getSeries().add(...)` قبل التحقق. |
| التحقق من التخطيط يُظهر أخطاء | تداخل أشكال على الشريحة | عدّل إحداثيات X/Y أو زد أبعاد المخطط. |
| `OutOfMemoryError` على ملفات كبيرة | عدم تحرير الكائنات | استدعِ `presentation.dispose()` داخل كتلة `finally`. |

## الأسئلة المتكررة

**س: ما هو Aspose.Slides؟**  
ج: إنها مكتبة Java قوية لإنشاء وتحرير وتحويل ملفات PowerPoint دون الحاجة إلى Microsoft Office.

**س: كيف أحصل على ترخيص مؤقت؟**  
ج: زر [Aspose Temporary License](https://purchase.aspose.com/temporary-license/) واتبع خطوات الطلب.

**س: هل يمكنني إنشاء أنواع مخططات أخرى غير المخطط العمودي المتجمع؟**  
ج: نعم، يدعم Aspose.Slides المخططات الشريطية، الخطية، الدائرية، المساحية، والعديد من الأنواع الأخرى.

**س: هل هناك طريقة لإضافة بيانات إلى المخطط برمجيًا؟**  
ج: بالتأكيد. استخدم `chart.getChartData().getSeries().add(...)` و `chart.getChartData().getCategories().add(...)`.

**س: هل تعمل المكتبة على جميع أنظمة التشغيل؟**  
ج: نسخة Java متعددة المنصات وتعمل على Windows وLinux وmacOS.

## الموارد
- [Documentation](https://reference.aspose.com/slides/java/)
- [Download Aspose.Slides for Java](https://releases.aspose.com/slides/java/)
- [Purchase Subscription](https://purchase.aspose.com/buy)
- [Free Trial](https://releases.aspose.com/slides/java/)
- [Temporary License Request](https://purchase.aspose.com/temporary-license/)
- [Support Forum](https://forum.aspose.com/c/slides/11)

---

**آخر تحديث:** 2026-07-22  
**تم الاختبار مع:** Aspose.Slides for Java 25.4  
**المؤلف:** Aspose  

{{< blocks/products/products-backtop-button >}}

## دروس ذات صلة

- [How to Create Chart in Java with Aspose.Slides: A Comprehensive Guide](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)
- [Create and Validate Chart Layouts in PowerPoint Using Aspose.Slides for Java | SEO-Optimized Guide](/slides/java/charts-graphs/create-validate-chart-layouts-aspose-slides-java/)
- [How to Add and Configure Charts in Presentations Using Aspose.Slides for Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}