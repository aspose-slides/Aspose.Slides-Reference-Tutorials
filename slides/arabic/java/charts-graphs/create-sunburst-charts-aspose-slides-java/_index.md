---
date: '2026-07-03'
description: تعلم كيفية إنشاء مخططات Sunburst خطوة بخطوة في Java باستخدام Aspose.Slides،
  مع خيارات تخصيص كاملة لعروض PowerPoint التقديمية.
keywords:
- how to create sunburst
- step by step sunburst
- Aspose.Slides Java sunburst
- Java chart library
- PowerPoint data visualization
schemas:
- author: Aspose
  dateModified: '2026-07-03'
  description: Learn how to create sunburst charts step by step in Java using Aspose.Slides,
    with full customization options for PowerPoint presentations.
  headline: How to Create Sunburst Charts in Java Using Aspose.Slides
  type: TechArticle
- description: Learn how to create sunburst charts step by step in Java using Aspose.Slides,
    with full customization options for PowerPoint presentations.
  name: How to Create Sunburst Charts in Java Using Aspose.Slides
  steps:
  - name: Set Up the Project
    text: Add the Aspose.Slides Maven dependency (or the equivalent Gradle snippet)
      to your `pom.xml`. This pulls in all required binaries and transitive libraries.
  - name: Load or Create a Presentation
    text: '`Presentation` is Aspose.Slides'' top‑level object that represents a single
      PowerPoint file in memory. Instantiate it with `new Presentation()` for a fresh
      deck or pass a file path to open an existing PPTX.'
  - name: Add a Sunburst Chart
    text: Insert a new chart shape onto a slide using `slide.getShapes().addChart(ChartType.Sunburst,
      x, y, width, height)`. This creates the Sunburst placeholder ready for data.
      `ChartType.Sunburst` specifies the Sunburst chart type when adding a chart to
      a slide.
  - name: Populate Hierarchical Data
    text: '`ChartData` holds the data series and categories for a chart. Access the
      chart’s `ChartData` collection and add series and categories that reflect your
      hierarchy. For each level, specify the parent‑child relationship via the `ParentSeries`
      property, allowing the chart to render concentric rings auto'
  - name: Customize Appearance
    text: Fine‑tune segment colors, border styles, and data labels through the `ChartSeries`
      and `ChartDataPoint` objects. `ChartSeries` represents a series of data points
      in a chart. `ChartDataPoint` represents an individual data point within a series.
      You can also enable 3‑D rotation or set the `Explode` pr
  - name: Save the Presentation
    text: '`SaveFormat` enum defines the file formats you can save a presentation
      as. Call `presentation.save("SunburstDemo.pptx", SaveFormat.Pptx)` to write
      the file to disk. You can also export to PDF or PNG by changing the `SaveFormat`
      enum value.'
  type: HowTo
- questions:
  - answer: Yes. Read the CSV, build the hierarchy in memory, and feed it to the chart’s
      `ChartData` collection before saving.
    question: Can I generate a Sunburst chart from a CSV file?
  - answer: It does. Apply a `SlideShowTransition` to the slide or use `ChartFormat.setAnimationEnabled(true)`
      for chart‑level animation.
    question: Does Aspose.Slides support animated transitions for Sunburst charts?
  - answer: Absolutely. Save the presentation with `SaveFormat.Svg` to obtain a scalable
      vector version of the Sunburst chart.
    question: Is it possible to export the chart as an SVG vector graphic?
  - answer: Aspose.Slides reliably processes up to **10,000** data points in a single
      Sunburst chart without performance degradation.
    question: What is the maximum number of data points a Sunburst chart can handle?
  - answer: A single commercial license covers all environments (development, staging,
      production) as long as the license terms are respected.
    question: Do I need a separate license for each deployment environment?
  type: FAQPage
title: كيفية إنشاء مخططات Sunburst في Java باستخدام Aspose.Slides
url: /ar/java/charts-graphs/create-sunburst-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية إنشاء مخططات Sunburst في Java باستخدام Aspose.Slides

## مقدمة
في العروض التقديمية المدفوعة بالبيانات اليوم، يمكن أن يميز **how to create sunburst** بصريًا سريعًا شرائحك. يشرح هذا الدليل كيفية بناء مخطط Sunburst باستخدام Aspose.Slides for Java، من إعداد المشروع حتى التصدير النهائي، بحيث يمكنك تقديم رسومات بيانية هرمية جذابة دون مغادرة بيئة Java.

## إجابات سريعة
- **ما هي الفئة الرئيسية لملف PowerPoint؟** `Presentation` – it represents the entire PPTX in memory.  
- **كم عدد أسطر الكود المطلوبة لإنشاء Sunburst أساسي؟** Typically 5–7 lines once the library is referenced.  
- **ما هي صيغ الإخراج المدعومة؟** PPTX, PDF, PNG, SVG, and HTML.  
- **هل يمكنني تنسيق القطاعات الفردية؟** Yes – fill colors, borders, and data labels are fully customizable.  
- **هل أحتاج إلى ترخيص للإنتاج؟** A free evaluation works for testing; a commercial license is required for deployment.

## ما هو مخطط Sunburst؟
مخطط Sunburst يعرض البيانات الهرمية كحلقات متحدة المركز، حيث تمثل كل حلقة مستوى من الهرمية. يتيح للمشاهدين فهم علاقات الأبوية‑الطفلية بنظرة واحدة، مما يجعله مثاليًا لمخططات التنظيم، وعروض التصنيف، والقياسات متعددة المستويات. وهو مفيد بشكل خاص لعرض الفئات متعددة المستويات مثل خطوط المنتجات، المناطق الجغرافية، أو الهياكل التنظيمية، مما يسمح للمشاهدين برؤية كل من التوزيع العام والتفصيل داخل كل قطاع.

## لماذا تستخدم Aspose.Slides لمخططات Sunburst؟
Aspose.Slides يدعم **30+ chart types**، يعالج الملفات حتى **500 MB** دون تحميل المستند بالكامل في الذاكرة، ويُظهر الرسومات بدقة **300 DPI** لإنتاج واضح كالكريستال. تضمن هذه القدرات الم quantifiable السرعة وجودة عالية حتى للعروض الكبيرة. بالإضافة إلى ذلك، توفر المكتبة عمليات آمنة للـ thread وتندمج بسلاسة مع أدوات بناء Java الشائعة، مما يجعلها مناسبة لإنشاء العروض على سطح المكتب أو الخادم على نطاق واسع.

## المتطلبات المسبقة
- Java Development Kit (JDK) 8 أو أحدث.  
- Maven أو Gradle لإدارة التبعيات.  
- Aspose.Slides for Java (الإصدار الأحدث).  
- فهم أساسي لهياكل البيانات الهرمية.

## كيفية إنشاء مخططات Sunburst خطوة بخطوة؟
حمّل بيئتك، أضف مخططًا، زوّد البيانات الهرمية، خصّصه، واحفظ الملف – كل ذلك في عدد قليل من الخطوات البسيطة. فيما يلي سير العمل الدقيق الذي يمكنك اتباعه دون كتابة أي كود إضافي. العملية مؤتمتة بالكامل، لا تتطلب تفاعلًا يدويًا مع الواجهة، ويمكن دمجها في وظائف الدُفعات أو الخدمات الويب لإنتاج المخططات عند الطلب.

### الخطوة 1: إعداد المشروع
أضف تبعية Aspose.Slides Maven (أو المقتطف المكافئ لـ Gradle) إلى ملف `pom.xml`. سيقوم ذلك بجلب جميع الثنائيات المطلوبة والمكتبات المتداخلة.

### الخطوة 2: تحميل أو إنشاء عرض تقديمي
`Presentation` هو الكائن الأعلى مستوى في Aspose.Slides الذي يمثل ملف PowerPoint واحد في الذاكرة. أنشئه باستخدام `new Presentation()` للحصول على مجموعة شرائح جديدة أو مرّر مسار ملف لفتح PPTX موجود.

### الخطوة 3: إضافة مخطط Sunburst
أدرج شكل مخطط جديد على شريحة باستخدام `slide.getShapes().addChart(ChartType.Sunburst, x, y, width, height)`. هذا ينشئ عنصر نائب لمخطط Sunburst جاهز للبيانات. `ChartType.Sunburst` يحدد نوع مخطط Sunburst عند إضافة المخطط إلى الشريحة.

### الخطوة 4: تعبئة البيانات الهرمية
`ChartData` يحمل سلسلة البيانات والفئات للمخطط. احصل على مجموعة `ChartData` للمخطط وأضف السلاسل والفئات التي تعكس هرمك. لكل مستوى، حدد علاقة الأبوية‑الطفلية عبر خاصية `ParentSeries`، مما يسمح للمخطط برسم الحلقات المتحدة تلقائيًا.

### الخطوة 5: تخصيص المظهر
قم بضبط ألوان القطاعات، أنماط الحدود، وعناوين البيانات عبر كائنات `ChartSeries` و `ChartDataPoint`. `ChartSeries` يمثل سلسلة من نقاط البيانات في المخطط. `ChartDataPoint` يمثل نقطة بيانات فردية داخل السلسلة. يمكنك أيضًا تمكين الدوران ثلاثي الأبعاد أو ضبط خاصية `Explode` لتسليط الضوء على شرائح معينة.

### الخطوة 6: حفظ العرض التقديمي
تحدد تعداد `SaveFormat` صيغ الملفات التي يمكنك حفظ العرض بها. استدعِ `presentation.save("SunburstDemo.pptx", SaveFormat.Pptx)` لكتابة الملف إلى القرص. يمكنك أيضًا التصدير إلى PDF أو PNG بتغيير قيمة تعداد `SaveFormat`.

## كيف تُخصّص ألوان مخطط Sunburst؟
حدد لون تعبئة لكل `ChartDataPoint` باستخدام `point.getFillFormat().setFillType(FillType.Solid)` ثم `point.getFillFormat().getSolidFillColor().setColor(Color.fromArgb(…))`. يتيح لك هذا النهج المباشر مطابقة هوية العلامة التجارية أو إبراز نقاط البيانات الرئيسية. يمكنك أيضًا تطبيق تعبئات تدرجية، تعديل الشفافية، أو استخدام ألوان السمة لضمان التناسق مع تصميم الشريحة بأكمله.

## المشكلات الشائعة والحلول
- **Problem:** Hierarchy appears flat.  
  **Solution:** Ensure each child series correctly references its `ParentSeries`. Missing links cause the chart to treat all data as a single level.  
- **Problem:** Exported PNG looks blurry.  
  **Solution:** Increase the export DPI by setting `presentation.getSlides().get(0).getSlideShowTransition().setTransitionDuration(300)`.  
- **Problem:** Large PPTX files cause OutOfMemoryError.  
  **Solution:** Use `Presentation.setMemoryOptimization(true)` to stream data and keep memory usage low.

## الأسئلة المتكررة

**Q: Can I generate a Sunburst chart from a CSV file?**  
A: Yes. Read the CSV, build the hierarchy in memory, and feed it to the chart’s `ChartData` collection before saving.

**Q: Does Aspose.Slides support animated transitions for Sunburst charts?**  
A: It does. Apply a `SlideShowTransition` to the slide or use `ChartFormat.setAnimationEnabled(true)` for chart‑level animation.

**Q: Is it possible to export the chart as an SVG vector graphic?**  
A: Absolutely. Save the presentation with `SaveFormat.Svg` to obtain a scalable vector version of the Sunburst chart.

**Q: What is the maximum number of data points a Sunburst chart can handle?**  
A: Aspose.Slides reliably processes up to **10,000** data points in a single Sunburst chart without performance degradation.

**Q: Do I need a separate license for each deployment environment?**  
A: A single commercial license covers all environments (development, staging, production) as long as the license terms are respected.

## الخلاصة
أنت الآن تمتلك دليلًا كاملاً خطوة بخطوة حول **how to create sunburst** في Java باستخدام Aspose.Slides. باتباع سير العمل أعلاه، يمكنك إنشاء تصورات هرمية عالية الجودة وقابلة للتخصيص بالكامل لأي عرض PowerPoint.

---

**Last Updated:** 2026-07-03  
**Tested With:** Aspose.Slides for Java 24.12  
**Author:** Aspose

## دروس ذات صلة

- [كيفية إضافة مخططات إلى PowerPoint باستخدام Aspose.Slides for Java: دليل خطوة بخطوة](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [إتقان تخصيص مخططات PowerPoint باستخدام Aspose.Slides Java للعروض التقديمية الديناميكية](/slides/java/charts-graphs/master-powerpoint-chart-customization-aspose-slides-java/)
- [تحريك فئات مخططات PowerPoint باستخدام Aspose.Slides for Java | دليل خطوة بخطوة](/slides/java/charts-graphs/animate-ppt-chart-categories-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}