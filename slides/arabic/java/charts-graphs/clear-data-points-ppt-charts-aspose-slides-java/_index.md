---
date: '2026-08-27'
description: تعرف على كيفية مسح نقاط البيانات في المخطط في PowerPoint باستخدام Aspose.Slides
  for Java. يوضح هذا الدليل خطوة بخطوة كيفية مسح قيم المخطط برمجيًا، وأفضل الممارسات،
  ومعالجة السلاسل بفعالية.
keywords:
- how to clear chart
- programmatically clear chart
- remove chart data points
- Aspose.Slides Java chart manipulation
- PowerPoint chart automation
lastmod: '2026-08-27'
og_description: تعرف على كيفية مسح نقاط البيانات في المخطط في PowerPoint باستخدام
  Aspose.Slides for Java. اتبع التعليمات خطوة بخطوة لإعادة ضبط المخططات برمجيًا وبكفاءة.
og_image_alt: Code example showing how to clear chart data points in a PowerPoint
  presentation using Aspose.Slides for Java
og_title: كيفية مسح نقاط البيانات في المخطط في PowerPoint باستخدام Aspose.Slides for
  Java
schemas:
- author: Aspose
  dateModified: '2026-08-27'
  description: Learn how to clear chart data points in PowerPoint using Aspose.Slides
    for Java. This step‑by‑step tutorial shows how to programmatically clear chart
    values, best practices, and efficient series handling.
  headline: 'How to clear data points in PowerPoint charts using Aspose.Slides for
    Java: a comprehensive guide'
  type: TechArticle
- description: Learn how to clear chart data points in PowerPoint using Aspose.Slides
    for Java. This step‑by‑step tutorial shows how to programmatically clear chart
    values, best practices, and efficient series handling.
  name: 'How to clear data points in PowerPoint charts using Aspose.Slides for Java:
    a comprehensive guide'
  steps:
  - name: '**Load the presentation** – create a `Presentation` instance pointing to
      your source file.'
    text: '**Load the presentation** – create a `Presentation` instance pointing to
      your source file.'
  - name: '**Access the slide and chart** – retrieve the slide (usually index 0) and
      cast the first shape to `IChart`.'
    text: '**Access the slide and chart** – retrieve the slide (usually index 0) and
      cast the first shape to `IChart`.'
  - name: '**Iterate through the target series** – select the series you want to clear
      (e.g., `chart.getChartData().getSeries().get_Item(0)`) and loop over its data
      points, setting both X and Y cell values to `null`.'
    text: '**Iterate through the target series** – select the series you want to clear
      (e.g., `chart.getChartData().getSeries().get_Item(0)`) and loop over its data
      points, setting both X and Y cell values to `null`.'
  - name: '**Save the modified presentation** – write the changes to a new file or
      overwrite the original.'
    text: '**Save the modified presentation** – write the changes to a new file or
      overwrite the original.'
  - name: '**Data refresh pipelines** – replace stale numbers with fresh analytics
      without rebuilding the chart layout.'
    text: '**Data refresh pipelines** – replace stale numbers with fresh analytics
      without rebuilding the chart layout.'
  - name: '**Template distribution** – provide PowerPoint templates that contain empty
      charts ready for user input.'
    text: '**Template distribution** – provide PowerPoint templates that contain empty
      charts ready for user input.'
  - name: '**Dynamic dashboards** – generate nightly presentations that pull data
      from APIs, clearing old values first.'
    text: '**Dynamic dashboards** – generate nightly presentations that pull data
      from APIs, clearing old values first.'
  - name: '**Automated reporting jobs** – integrate the clearing logic into CI/CD
      pipelines for automated report generation.'
    text: '**Automated reporting jobs** – integrate the clearing logic into CI/CD
      pipelines for automated report generation.'
  type: HowTo
- questions:
  - answer: A free trial license is sufficient for development and testing. A commercial
      license is required for production deployments.
    question: Do I need a license for development builds?
  - answer: Yes, the library fully supports modern PPTX features, including advanced
      chart types and SmartArt.
    question: Does Aspose.Slides for Java support PowerPoint 2016/2019 features?
  - answer: Absolutely – just reference the series that belongs to the secondary axis
      and set its data points to `null` as described above.
    question: Can I clear data points in a chart that uses a secondary axis?
  - answer: Yes. Call `dataPoint.getYValue().setValue(null)` and leave the X cell
      untouched.
    question: Is it possible to clear only Y values while keeping X labels?
  - answer: Wrap the clearing code in a loop that iterates over a directory of PPTX
      files, applying the same logic to each file.
    question: How can I automate this for multiple presentations?
  type: FAQPage
tags:
- clear chart
- Aspose.Slides
- Java chart manipulation
- PowerPoint automation
- chart data points
title: 'كيفية مسح نقاط البيانات في مخططات PowerPoint باستخدام Aspose.Slides for Java:
  دليل شامل'
url: /ar/java/charts-graphs/clear-data-points-ppt-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# كيفية مسح نقاط البيانات في مخططات PowerPoint باستخدام Aspose.Slides for Java

## مقدمة

في العديد من خطوط تقارير البيانات تحتاج إلى **إعادة ضبط المخطط** دون إعادة إنشاء تخطيطه. سواءً كنت تقوم بتحديث لوحة معلومات، أو توزيع قالب، أو أتمتة التقارير الليلية، فإن معرفة **كيفية مسح نقاط المخطط** توفر الوقت وتقلل الأخطاء. يُظهر لك هذا الدليل كيفية استخدام **Aspose.Slides for Java** لمسح نقاط محددة أو سلسلة كاملة برمجياً، مع الحفاظ على تنسيق الشكل البصري.

**ما ستتعلمه**
- كيف يتيح لك Aspose.Slides التعامل مع مخططات PowerPoint من خلال Java.  
- إرشادات خطوة بخطوة لمسح نقاط البيانات في مخطط ضمن سلسلة.  
- نصائح أفضل الممارسات للأداء والترخيص.

## إجابات سريعة
- **ما المكتبة المطلوبة؟** Aspose.Slides for Java (v25.4+).  
- **ما الطريقة التي تمسح فعلياً نقطة البيانات؟** ضبط قيم خلايا X و Y إلى `null`.  
- **هل أحتاج إلى ترخيص للإنتاج؟** نعم – الترخيص التجاري يزيل حدود النسخة التجريبية.  
- **هل يدعم Java 16؟** بالتأكيد؛ المكتبة تعمل مع JDK 16 والإصدارات الأحدث.  
- **هل يمكنني استهداف سلسلة واحدة فقط؟** نعم – قم بالتكرار عبر السلسلة المحددة التي تريد مسحها.

## ما هو Aspose.Slides for Java؟

Aspose.Slides for Java هو API شامل يتيح إنشاء وتحرير وتحويل ملفات PowerPoint دون الحاجة إلى Microsoft Office. يدعم أكثر من 70 نوعًا من المخططات، وأكثر من 150 تنسيق ملف، ويمكنه معالجة العروض التقديمية حتى حجم 500 ميغابايت دون تحميل الملف بالكامل إلى الذاكرة.

## لماذا مسح نقاط البيانات في المخطط؟

مسح نقاط البيانات في المخطط يتيح لك الحفاظ على تخطيط المخطط الحالي — مثل الألوان، والوسائط، وإعدادات المحاور، والعلامات — مع استبدال القيم الرقمية الأساسية. هذا النهج مفيد عندما تحتاج إلى تحديث مخطط ببيانات جديدة، أو توفير قالب يحتوي على نواقل فارغة، أو إنشاء لوحات معلومات ديناميكية تتغير بشكل متكرر دون إعادة بناء التصميم البصري.

- تحديث مخطط بمجموعة بيانات جديدة مع الحفاظ على الألوان والوسائط وإعدادات المحاور.  
- توزيع قالب يحتوي على مخططات فارغة جاهزة لإدخال المستخدم.  
- إنشاء لوحات معلومات ديناميكية حيث تتغير البيانات بشكل متكرر.

## كيفية مسح نقاط البيانات في مخطط PowerPoint باستخدام Aspose.Slides for Java

قم بتحميل العرض التقديمي، حدد موقع المخطط، واضبط خلايا X و Y لكل نقطة بيانات إلى `null`. هذه العملية تزيل القيم الرقمية ولكنها تترك السلسلة والعلامات والتنسيق دون تغيير. عادةً ما يكتمل العملية بأكملها في أقل من ثانية لملف PPTX قياسي مكوّن من 10 شرائح.

### إجابة مباشرة
لمسح نقاط البيانات في المخطط، افتح ملف PPTX باستخدام `new Presentation("input.pptx")`، استخرج كائن `IChart` المستهدف، قم بالتكرار عبر `IChartSeries` المطلوبة، واستدعِ `dataPoint.getXValue().setValue(null)` و `dataPoint.getYValue().setValue(null)` لكل نقطة. أخيرًا، احفظ العرض التقديمي باستخدام `pres.save("output.pptx", SaveFormat.Pptx)`. يتيح هذا النهج مسح البيانات برمجياً مع الحفاظ على التصميم البصري للمخطط.

### تعريف الروابط
- `Presentation` هو الكائن الأعلى مستوى في Aspose.Slides الذي يمثل ملف PowerPoint في الذاكرة.  
- `IChart` هو الواجهة التي توفر الوصول إلى سلاسل شكل المخطط، والمحاور، والتنسيق.  
- `IChartSeries` يمثل سلسلة واحدة داخل المخطط ويحتوي على مجموعة من كائنات `IDataPoint`.  
- `IDataPoint` يحمل القيم الفردية X و Y لنقطة على المخطط.

### تنفيذ خطوة بخطوة

1. **تحميل العرض التقديمي** – أنشئ مثيل `Presentation` يشير إلى ملف المصدر الخاص بك.  
   ```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

2. **الوصول إلى الشريحة والمخطط** – استخرج الشريحة (عادةً الفهرس 0) وحول الشكل الأول إلى `IChart`.  
   ```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

3. **التكرار عبر السلسلة المستهدفة** – اختر السلسلة التي تريد مسحها (مثلاً `chart.getChartData().getSeries().get_Item(0)`) وتكرّر عبر نقاط البيانات الخاصة بها، مع ضبط قيم خلايا X و Y إلى `null`.  
   ```java
import com.aspose.slides.*;

public class ChartManipulation {
    public static void main(String[] args) {
        Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/TestChart.pptx");
        try {
            // Your code here
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

4. **حفظ العرض التقديمي المعدل** – اكتب التغييرات إلى ملف جديد أو استبدل الملف الأصلي.  
   ```java
   Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/TestChart.pptx");
   ```

## إعداد Aspose.Slides for Java

### تثبيت Maven

```java
   ISlide sl = pres.getSlides().get_Item(0);
   IChart chart = (IChart) sl.getShapes().get_Item(0);
   ```

### تثبيت Gradle

```java
   for (IChartDataPoint dataPoint : chart.getChartData().getSeries().get_Item(0).getDataPoints()) {
       dataPoint.getXValue().getAsCell().setValue(null);
       dataPoint.getYValue().getAsCell().setValue(null);
   }
   ```

### التحميل المباشر

بدلاً من ذلك، قم بتحميل أحدث نسخة من [إصدارات Aspose.Slides for Java](https://releases.aspose.com/slides/java/).

### الحصول على الترخيص

لاستخدام Aspose.Slides بما يتجاوز حدود النسخة التجريبية:
- احصل على ترخيص **تجريبي مجاني**.  
- قدّم طلبًا للحصول على **ترخيص مؤقت** للتقييم.  
- اشترِ **ترخيصًا تجاريًا** للاستخدام في الإنتاج.

#### التهيئة الأساسية والإعداد

```java
   pres.save("YOUR_DOCUMENT_DIRECTORY/UpdatedTestChart.pptx", SaveFormat.Pptx);
   ```

## تطبيقات عملية

مسح نقاط البيانات في المخطط مفيد في العديد من السيناريوهات الواقعية:

1. **خطوط تجديد البيانات** – استبدال الأرقام القديمة بتحليلات جديدة دون إعادة بناء تخطيط المخطط.  
2. **توزيع القوالب** – توفير قوالب PowerPoint تحتوي على مخططات فارغة جاهزة لإدخال المستخدم.  
3. **لوحات معلومات ديناميكية** – إنشاء عروض تقديمية ليلية تستخرج البيانات من APIs، مع مسح القيم القديمة أولاً.  
4. **وظائف تقارير مؤتمتة** – دمج منطق المسح في خطوط CI/CD لتوليد تقارير مؤتمتة.

## اعتبارات الأداء

- **تحرير الكائنات**: استدعِ `pres.dispose()` بعد الحفظ لإطلاق الموارد الأصلية.  
- **معالجة دفعات**: أعد استخدام مثيل `License` واحد عبر عدة ملفات لتقليل الحمل.  
- **ضبط JVM**: زيادة حجم الذاكرة (`-Xmx2g` أو أعلى) عند التعامل مع عروض تقديمية أكبر من 200 ميغابايت.  
- **وضع كفاءة الذاكرة**: يمكن لـ Aspose.Slides بث ملفات PPTX الكبيرة، مما يسمح بمعالجة ما يصل إلى 10 000 شريحة دون تحميل كامل في الذاكرة.

## الأسئلة المتكررة

**س: هل أحتاج إلى ترخيص لإصدارات التطوير؟**  
ج: ترخيص تجريبي مجاني يكفي للتطوير والاختبار. يلزم ترخيص تجاري للنشر في بيئة الإنتاج.

**س: هل يدعم Aspose.Slides for Java ميزات PowerPoint 2016/2019؟**  
ج: نعم، المكتبة تدعم بالكامل ميزات PPTX الحديثة، بما في ذلك أنواع المخططات المتقدمة وSmartArt.

**س: هل يمكنني مسح نقاط البيانات في مخطط يستخدم محورًا ثانويًا؟**  
ج: بالتأكيد – ما عليك سوى الإشارة إلى السلسلة التي تنتمي إلى المحور الثانوي وضبط نقاط البيانات الخاصة بها إلى `null` كما هو موضح أعلاه.

**س: هل يمكن مسح قيم Y فقط مع الحفاظ على تسميات X؟**  
ج: نعم. استدعِ `dataPoint.getYValue().setValue(null)` واترك خلية X دون تعديل.

**س: كيف يمكنني أتمتة ذلك لعدة عروض تقديمية؟**  
ج: ضع كود المسح داخل حلقة تتكرر عبر دليل يحتوي على ملفات PPTX، وتطبق نفس المنطق على كل ملف.

## موارد

- [توثيق Aspose.Slides](https://reference.aspose.com/slides/java/)
- [تحميل Aspose.Slides for Java](https://releases.aspose.com/slides/java/)
- [شراء ترخيص](https://purchase.aspose.com/buy)
- [نسخة تجريبية مجانية](https://releases.aspose.com/slides/java/)
- [طلب ترخيص مؤقت](https://purchase.aspose.com/temporary-license/)
- [منتدى مجتمع Aspose](https://forum.aspose.com/c/slides/11)

مع هذه الموارد، أنت جاهز لبدء مسح نقاط البيانات في المخططات في تطبيقات Java الخاصة بك. برمجة سعيدة!

---

**آخر تحديث:** 2026-08-27  
**تم الاختبار مع:** Aspose.Slides for Java 25.4 (JDK 16)  
**المؤلف:** Aspose

## دروس ذات صلة

- [كيفية تحرير بيانات مخطط PowerPoint باستخدام Aspose.Slides for Java: دليل شامل](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [كيفية إضافة مخطط إلى PowerPoint باستخدام Aspose.Slides for Java: دليل خطوة بخطوة](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [مسح نقاط بيانات سلسلة مخطط محددة في Java Slides](/slides/java/java-slides-chart-data-manipulation/clear-specific-chart-series-data-points-java-slides/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}