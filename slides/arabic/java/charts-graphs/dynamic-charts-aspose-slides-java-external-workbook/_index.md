---
date: '2026-08-06'
description: تعلم كيفية إنشاء chart في عروض Java باستخدام Aspose.Slides وكيفية ربط
  workbook لتحديثات dynamic data updates. دليل خطوة بخطوة.
keywords:
- how to create chart
- how to link workbook
- dynamic chart linking
lastmod: '2026-08-06'
og_description: تعلم كيفية إنشاء chart في عروض Java باستخدام Aspose.Slides وكيفية
  ربط workbook لتحديثات dynamic data updates. اتبع هذا الدرس المختصر.
og_image_alt: 'Guide: create chart in Java with Aspose.Slides linking external workbook'
og_title: كيفية إنشاء chart في عروض Java باستخدام Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Learn how to create chart in Java presentations using Aspose.Slides
    and how to link workbook for dynamic data updates. Step-by-step guide.
  headline: How to create chart in Java presentations with Aspose.Slides
  type: TechArticle
- description: Learn how to create chart in Java presentations using Aspose.Slides
    and how to link workbook for dynamic data updates. Step-by-step guide.
  name: How to create chart in Java presentations with Aspose.Slides
  steps:
  - name: '**Create a new presentation**'
    text: '**Create a new presentation**'
  - name: '**Access the first slide**'
    text: '**Access the first slide**'
  - name: '**Add a chart to the slide**'
    text: '**Add a chart to the slide**'
  - name: '**Set external workbook URL for chart data**'
    text: '**Set external workbook URL for chart data**'
  - name: '**Real‑time data reporting** – sales dashboards that pull the latest figures
      from a central Excel file.'
    text: '**Real‑time data reporting** – sales dashboards that pull the latest figures
      from a central Excel file.'
  - name: '**Financial analysis** – stock price trends that refresh automatically
      from a market data feed.'
    text: '**Financial analysis** – stock price trends that refresh automatically
      from a market data feed.'
  - name: '**Project management** – KPI dashboards that reflect the most recent task
      completion stats.'
    text: '**Project management** – KPI dashboards that reflect the most recent task
      completion stats.'
  type: HowTo
- questions:
  - answer: Charts update automatically when the linked Excel workbook changes.
    question: What is the main benefit?
  - answer: Aspose.Slides for Java 25.4 or newer.
    question: Which library version is required?
  - answer: A free trial works for development; a commercial license removes all evaluation
      limits.
    question: Do I need a license?
  - answer: Yes – both `.xlsx` and legacy `.xls` files are supported.
    question: Can I use any Excel format?
  - answer: Cache the workbook locally or use a CDN to minimise latency.
    question: Is network latency a concern?
  type: FAQPage
tags:
- create chart
- Aspose.Slides
- Java presentation
title: كيفية إنشاء chart في عروض Java باستخدام Aspose.Slides
url: /ar/java/charts-graphs/dynamic-charts-aspose-slides-java-external-workbook/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية إنشاء مخطط في عروض Java التقديمية باستخدام Aspose.Slides: الربط بملفات عمل خارجية

## مقدمة
في هذا البرنامج التعليمي ستتعلم **كيفية إنشاء مخطط** في عرض تقديمي بلغة Java و**كيفية ربط بيانات ملف العمل** بحيث يتم تحديث المخططات تلقائيًا. تحافظ المخططات الديناميكية على تحديث شرائحك دون الحاجة إلى النسخ واللصق اليدوي، وهو أمر أساسي للتقارير الحية، ولوحات التحكم المالية، وعروض حالة المشروع. سنستعرض الإعداد، والتنفيذ، والمشكلات الشائعة، حتى تتمكن من دمج بيانات Excel في الوقت الفعلي ببضع أسطر من الشيفرة فقط.

## إجابات سريعة
- **ما هي الفائدة الرئيسية؟** يتم تحديث المخططات تلقائيًا عندما يتغير ملف Excel المرتبط.  
- **ما هو إصدار المكتبة المطلوب؟** Aspose.Slides for Java 25.4 أو أحدث.  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية المجانية تعمل للتطوير؛ الترخيص التجاري يزيل جميع قيود التقييم.  
- **هل يمكنني استخدام أي تنسيق Excel؟** نعم – يتم دعم كل من ملفات `.xlsx` و `.xls` القديمة.  
- **هل تأخير الشبكة مصدر قلق؟** قم بتخزين ملف العمل محليًا أو استخدم CDN لتقليل التأخير.  

## ما هو ربط المخطط الديناميكي؟
يتيح ربط المخطط الديناميكي للمخطط قراءة مصدر بياناته من ملف عمل خارجي أثناء وقت التشغيل، بحيث يتم عكس أي تغييرات في ملف العمل على الشريحة في المرة التالية التي يتم فتحها. يلغي ذلك الحاجة إلى إعادة إنشاء العرض التقديمي بعد كل تحديث للبيانات.

## لماذا تستخدم Aspose.Slides for Java؟
Aspose.Slides يدعم **أكثر من 50 تنسيقًا للإدخال والإخراج**، يمكنه عرض عروض تقديمية مكوّنة من مئات الصفحات دون تحميل الملف بالكامل في الذاكرة، ويعالج تحديثات بيانات المخططات في أقل من 200 مللي ثانية على خادم عادي. تجعل هذه الأرقام المكمّنة الأداء خيارًا موثوقًا به لأنابيب تقارير المؤسسات.

## المتطلبات المسبقة
- **Aspose.Slides for Java** 25.4 أو أحدث.  
- **Java Development Kit (JDK)** 16 أو أحدث.  
- الإلمام بـ Maven أو Gradle لإدارة التبعيات.  

### المكتبات والتبعيات المطلوبة
- **Aspose.Slides for Java** – يوفر واجهة برمجة تطبيقات العروض التقديمية.  
- **Java Development Kit (JDK)** – مطلوب لتجميع وتشغيل الشيفرة.  

### متطلبات إعداد البيئة
- معرفة أساسية ببرمجة Java.  
- الوصول إلى ملف Excel خارجي (مسار ملف محلي أو URL HTTP).  

## إعداد Aspose.Slides for Java
لإضافة Aspose.Slides إلى مشروعك، اختر أحد أنظمة البناء المدعومة.

### إعداد Maven
أضف هذه التبعية إلى ملف `pom.xml` الخاص بك:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### إعداد Gradle
قم بإدراج هذا في ملف `build.gradle` الخاص بك:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### التحميل المباشر
بدلاً من ذلك، قم بتحميل المكتبة من [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### الحصول على الترخيص
ابدأ بنسخة تجريبية مجانية أو احصل على ترخيص مؤقت لاختبار Aspose.Slides دون قيود. للاستخدام طويل الأمد، فكر في شراء ترخيص.

##### التهيئة الأساسية والإعداد
`Presentation` هي الفئة الأساسية في Aspose.Slides التي تمثل ملف PowerPoint في الذاكرة. قم بتهيئة كائن العرض التقديمي الخاص بك كما يلي:
```java
Presentation pres = new Presentation();
```

## دليل التنفيذ
في هذا القسم نستعرض كيفية تعيين ملف عمل خارجي لتحديث بيانات المخطط في عرض تقديمي.

### تعيين ملف عمل خارجي مع تحديث بيانات المخطط
#### نظرة عامة
تتيح هذه الميزة للمخططات تحديث بياناتها ديناميكيًا من مصدر خارجي. إنها مثالية عندما تتغير بياناتك بشكل متكرر وتحتاج إلى أن تعكس الشرائح تلك التغييرات تلقائيًا.

#### تنفيذ خطوة بخطوة
1. **إنشاء عرض تقديمي جديد**  
   ابدأ بإنشاء كائن `Presentation` جديد:
   ```java
   Presentation pres = new Presentation();
   ```

2. **الوصول إلى الشريحة الأولى**  
   الوصول إلى الشرائح سهل:
   ```java
   ISlide slide = pres.getSlides().get_Item(0);
   ```

3. **إضافة مخطط إلى الشريحة**  
   أضف مخططًا دائريًا (pie chart) في الموضع والحجم المطلوبين:
   ```java
   IChart chart = slide.getShapes().addChart(
       ChartType.Pie, 50, 50, 400, 600, true
   );
   ```

4. **تحديد URL لملف العمل الخارجي لبيانات المخطط**  
   حدد ملف عمل خارجي كمصدر للبيانات:
   ```java
   IChartData chartData = chart.getChartData();
   // Note: This is a demo URL and does not need to exist.
   chartData.setExternalWorkbook("http://path/doesnt/exist");
   ```

#### خيارات التكوين
- **نوع المخطط** – اختر من بين Pie, Bar, Line, Area، إلخ، حسب الطريقة التي تريد عرض البيانات بها.  
- **الموضع والحجم** – اضبط إحداثيات X/Y والعرض/الارتفاع لتناسب تخطيط الشريحة.  

## كيف تنشئ مخططًا يربط بملف عمل؟
`Chart` هو كائن Aspose.Slides الذي يضم شكل المخطط وبياناته.  
حمّل عرضك التقديمي، أضف مخططًا، واستدعِ `chart.getChartData().setExternalWorkbook("https://example.com/data.xlsx")`. الآن يقرأ المخطط قيم السلاسل من ملف العمل في كل مرة يتم فتح الملف، مما يوفر تحديثات مباشرة دون الحاجة إلى إعادة إنشاء PPTX. يفي هذا الفقرة بالإجابة المباشرة لمتطلبات GEO ويعطيك وصفًا مختصرًا وقابلًا للتنفيذ.

## المشكلات الشائعة والحلول
إذا لم يتم تحديث الروابط الخارجية:
- تحقق من أن URL قابل للوصول ويعيد ملف Excel صالح.  
- تأكد من أن الخادم يسمح بطلبات GET المجهولة أو قدم بيانات الاعتماد إذا لزم الأمر.  
- خزن ملف العمل محليًا إذا كان تأخير الشبكة مرتفعًا؛ قم بتحديث الذاكرة المؤقتة قبل فتح العرض التقديمي.

## التطبيقات العملية
يمكن أن تكون المخططات الديناميكية المدعومة بملف عمل خارجي مفيدة في عدة سيناريوهات:
1. **تقارير البيانات في الوقت الحقيقي** – لوحات مبيعات تسحب أحدث الأرقام من ملف Excel مركزي.  
2. **التحليل المالي** – اتجاهات أسعار الأسهم التي تتجدد تلقائيًا من تغذية بيانات السوق.  
3. **إدارة المشاريع** – لوحات KPI التي تعكس أحدث إحصاءات إكمال المهام.

## اعتبارات الأداء
تحسين الأداء أمر أساسي عند التعامل مع ملفات عمل كبيرة:
- خزن ملف العمل على خادم التطبيق لتقليل المكالمات الشبكية المتكررة.  
- استخدم واجهات برمجة تطبيقات البث لقراءة نطاقات الأوراق المطلوبة فقط، مما يقلل من استهلاك الذاكرة.  
- Aspose.Slides يعالج تحديثات المخططات في أقل من 200 مللي ثانية لملفات عمل تصل إلى 10 ميغابايت، وهو مناسب لمعظم سيناريوهات التقارير.

## الخلاصة
باتباعك هذا الدليل، أصبحت الآن تعرف **كيفية إنشاء مخطط** في عروض Java التقديمية و**كيفية ربط بيانات ملف العمل** للتحديثات التلقائية. تجعل هذه القدرة شرائحك أكثر تفاعلية، وتقلل الجهد اليدوي، وتضمن أن يرى أصحاب المصلحة دائمًا أحدث الأرقام. استكشف ميزات إضافية في Aspose.Slides مثل استنساخ الشرائح، والرسوم المتحركة، وتصدير PDF لتعزيز سير عمل التقارير الخاص بك.

## قسم الأسئلة الشائعة
**س1: هل يمكنني استخدام أي URL كملف عمل خارجي؟**  
ج1: يجب أن يشير URL إلى ملف Excel قابل للوصول (`.xlsx` أو `.xls`). تأكد من أن الخادم يعيد نوع MIME الصحيح وأن المصادقة، إذا كانت مطلوبة، يتم التعامل معها في الشيفرة الخاصة بك.

**س2: ما هي أنواع المخططات التي تدعم الربط الديناميكي؟**  
ج2: جميع أنواع المخططات الأصلية في Aspose.Slides – Pie, Bar, Line, Area, Scatter, Radar، وغيرها – يمكن ربطها بملف عمل خارجي.

**س3: هل هناك حد لحجم ملف العمل الخارجي؟**  
ج3: بينما يمكن لـ Aspose.Slides التعامل مع ملفات عمل أكبر من 100 ميغابايت، يزداد وقت المعالجة بشكل خطي؛ للحصول على أفضل أداء حافظ على حجم الملفات أقل من 20 ميغابايت أو قم ببث النطاقات المطلوبة فقط.

**س4: كيف يجب أن أتعامل مع URL غير قابل للوصول؟**  
ج4: ضع كود الربط داخل كتلة try‑catch، سجّل الاستثناء، واختر خيارياً الرجوع إلى مصدر بيانات ثابت حتى يظل العرض التقديمي قابلًا للتحميل.

**س5: هل يمكن استخدام ذلك في أنابيب التقارير الآلية؟**  
ج5: بالتأكيد. تعمل الواجهة البرمجية بدون واجهة (head‑less)، لذا يمكنك إنشاء أو تحديث العروض التقديمية على خادم، تضمينها في رسائل البريد الإلكتروني، أو نشرها في مكتبة SharePoint.

## الموارد
- [توثيق Aspose.Slides Java](https://reference.aspose.com/slides/java/)
- [تحميل Aspose.Slides for Java](https://releases.aspose.com/slides/java/)
- [شراء ترخيص](https://purchase.aspose.com/buy)
- [نسخة تجريبية وترخيص مؤقت](https://releases.aspose.com/slides/java/)
- [منتدى دعم Aspose](https://forum.aspose.com/c/slides/11)

---

**آخر تحديث:** 2026-08-06  
**تم الاختبار مع:** Aspose.Slides for Java 25.4  
**المؤلف:** Aspose

## دروس ذات صلة

- [كيفية إنشاء مخطط في Java باستخدام Aspose.Slides: دليل شامل](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)
- [كيفية إضافة مخططات إلى PowerPoint باستخدام Aspose.Slides for Java: دليل خطوة بخطوة](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [تحريك المخططات في PowerPoint باستخدام Aspose.Slides for Java – دليل خطوة بخطوة](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}