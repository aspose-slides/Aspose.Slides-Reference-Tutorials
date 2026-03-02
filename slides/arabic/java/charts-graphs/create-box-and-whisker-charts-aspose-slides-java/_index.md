---
date: '2026-03-02'
description: تعلم كيفية إنشاء مخطط الصندوق في جافا، إضافة مخطط إلى الشريحة، وإنشاء
  مخطط الصندوق والشارب في PowerPoint باستخدام Aspose.Slides for Java.
keywords:
- Aspose.Slides for Java
- Box-and-Whisker Charts
- PowerPoint Java
title: إنشاء مخطط الصندوق في جافا باستخدام Aspose.Slides لبرنامج PowerPoint
url: /ar/java/charts-graphs/create-box-and-whisker-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية إنشاء مخططات الصندوق والشارب في PowerPoint باستخدام Aspose.Slides للـ Java

في هذا الدليل ستقوم **create box plot java** باستخدام Aspose.Slides، ثم تضمين المخطط مباشرةً في شريحة PowerPoint. إنشاء عروض تقديمية بصرية جذابة للبيانات أمر حاسم في عالم اليوم القائم على البيانات، وتعد المخططات أدوات أساسية لهذا الغرض. إذا كنت ترغب في إنشاء مخططات الصندوق والشارب داخل PowerPoint باستخدام Java، فإن مكتبة Aspose.Slides توفر حلاً قويًا. سيوضح لك هذا البرنامج التعليمي كيفية إنشاء وتكوين هذه المخططات بسلاسة باستخدام Aspose.Slides للـ Java.

## ما ستتعلمه

- إعداد بيئتك لاستخدام Aspose.Slides للـ Java
- خطوات **add chart to slide** وإنشاء مخطط صندوق‑شارب في PowerPoint باستخدام Java
- أفضل الممارسات لتحسين الأداء عند العمل مع Aspose.Slides
- تطبيقات واقعية لمخططات الصندوق‑والشارب

## إجابات سريعة
- **ما المكتبة التي تنشئ مخطط صندوق في Java؟** Aspose.Slides for Java.
- **ما نوع المخطط المستخدم؟** `ChartType.BoxAndWhisker`.
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية المجانية تعمل للتقييم؛ يلزم ترخيص تجاري للإنتاج.
- **هل يمكنني إضافة سلاسل متعددة؟** نعم – كرّر كتلة إنشاء السلسلة لكل مجموعة بيانات.
- **ما هو تنسيق الملف النهائي؟** PowerPoint PPTX (`SaveFormat.Pptx`).

## المتطلبات المسبقة

للتبع هذا البرنامج التعليمي، تأكد من وجود:

- **Java Development Kit (JDK)**: يجب تثبيت JDK 8 أو أعلى.
- **Aspose.Slides for Java Library**: ضرورية لمعالجة عروض PowerPoint في Java.
- **IDE**: بيئة تطوير متكاملة مثل IntelliJ IDEA أو Eclipse لكتابة وتنفيذ الكود.

## إعداد Aspose.Slides للـ Java

لاستخدام Aspose.Slides، أضفه كاعتماد. يمكنك إدارة ذلك عبر Maven أو Gradle أو عن طريق التحميل المباشر.

### Maven

أضف الاعتماد التالي في ملف `pom.xml` الخاص بك:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle

في ملف `build.gradle`، أضف:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### التحميل المباشر

بدلاً من ذلك، قم بتحميل أحدث نسخة من [إصدارات Aspose.Slides للـ Java](https://releases.aspose.com/slides/java/).

#### الحصول على الترخيص

- **Free Trial**: ابدأ بنسخة تجريبية مجانية لاستكشاف الميزات.  
- **Temporary License**: احصل على ترخيص مؤقت لأغراض التقييم.  
- **Purchase**: للحصول على جميع الوظائف، فكر في شراء ترخيص.

لتهيئة Aspose.Slides، تأكد من وجود المكتبة في مسار الفئة (classpath) وضبط أي متطلبات ترخيص حسب الحاجة.

## دليل التنفيذ

الآن دعنا نتعمق في الكود خطوة بخطوة. يتم شرح كل كتلة قبل المقتطف حتى تعرف بالضبط ما تقوم به.

### ما هو مخطط الصندوق ولماذا نستخدمه في Java؟

مخطط الصندوق والشارب (يُطلق عليه غالبًا *box plot*) يُظهر توزيع البيانات—الوسيط، الأرباع، والقيم المتطرفة—في شكل مضغوط. في Java، إنشاء هذا المخطط برمجيًا يتيح لك دمج الرؤى الإحصائية مباشرةً في عروض PowerPoint، مما يلغي الحاجة لإنشاء المخطط يدويًا.

### لماذا إضافة مخطط إلى شريحة باستخدام Aspose.Slides؟

Aspose.Slides يُجرد تفاصيل OpenXML منخفضة المستوى، ويُوفر لك API سهل لإنشاء وتنسيق وتصدير المخططات. هذا يعني أنه يمكنك أتمتة إنشاء التقارير، وإنتاج علامة تجارية متسقة، ودمج المخططات في سير عمل Java أكبر.

### الخطوة 1: إنشاء أو فتح عرض تقديمي

أولاً، افتح ملف PPTX موجود أو ابدأ ملفًا جديدًا:

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

> **نصيحة احترافية:** إذا لم يكن الملف موجودًا، سيقوم Aspose.Slides بإنشاء عرض تقديمي فارغ جديد لك.

### الخطوة 2: إضافة مخطط صندوق‑وشارب إلى الشريحة

ضع المخطط في المكان المطلوب عن طريق تحديد الموضع والحجم (بالنقاط):

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.BoxAndWhisker, 50, 50, 500, 400);
```

### الخطوة 3: مسح البيانات الحالية

قبل إدخال بيانات جديدة، امسح أي فئات أو سلاسل placeholder:

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();

IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0); // Clears content starting from cell "A1"
```

### الخطوة 4: تكوين الفئات

أضف الفئات (تسميات المحور X) التي ستظهر تحت كل صندوق:

```java
for (int i = 1; i <= 6; i++) {
    chart.getChartData().getCategories()
        .add(wb.getCell(0, "A" + i, "Category 1"));
}
```

> **ملاحظة:** اضبط نص التسمية ليتطابق مع نطاق بياناتك (مثال: “Q1”، “Product A”).

### الخطوة 5: إنشاء وتخصيص السلسلة

الآن أنشئ سلسلة، اضبط خيارات العرض، وأدخل نقاط البيانات الرقمية:

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
series.setQuartileMethod(QuartileMethodType.Exclusive); // Set quartile method to Exclusive
series.setShowMeanLine(true); // Display mean line
series.setShowMeanMarkers(true); // Show markers for mean values
series.setShowInnerPoints(true); // Display inner points on the chart
series.setShowOutlierPoints(true); // Show outlier points on the chart

int[] data = {15, 41, 16, 10, 23, 16}; // Sample data points
for (int i = 0; i < data.length; i++) {
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(
        wb.getCell(0, "B" + (i + 1), data[i]));
}
```

يمكنك استبدال مصفوفة `int[] data` بالقيم المقروءة من قاعدة بيانات، ملف CSV، أو أي مصدر آخر.

### الخطوة 6: حفظ العرض التقديمي

احفظ التغييرات في ملف PPTX جديد:

```java
pres.save("YOUR_OUTPUT_DIRECTORY/BoxAndWhisker.pptx", SaveFormat.Pptx);
```

### الخطوة 7: تنظيف الموارد

دائمًا قم بتحرير كائن `Presentation` لتحرير الموارد الأصلية:

```java
finally {
    if (pres != null) pres.dispose();
}
```

## تطبيقات عملية

مخططات الصندوق والشارب لا تقدر بثمن في التحليل الإحصائي وعرض البيانات. إليك بعض السيناريوهات التي تتألق فيها:

1. **Financial Analysis** – تصور توزيع الإيرادات عبر المناطق.  
2. **Quality Control** – اكتشاف القيم المتطرفة في قياسات التصنيع.  
3. **Academic Research** – إظهار تباين نتائج التجارب.  
4. **Market Research** – مقارنة أداء المنتجات عبر الفئات السكانية.

دمج هذه المخططات في عروض PowerPoint يتيح لأصحاب المصلحة فهم البيانات المعقدة بنظرة واحدة.

## اعتبارات الأداء

عند العمل مع Aspose.Slides في Java، ضع هذه النصائح في اعتبارك:

- **Memory Management** – حرّر كائنات `Presentation` بسرعة.  
- **Data Handling** – حمّل فقط البيانات التي تحتاجها؛ تجنّب إدخال مجموعات بيانات ضخمة مباشرةً إلى دفتر عمل المخطط.  
- **Lazy Loading** – إذا كنت تُنشئ العديد من الشرائح، فكر في إنشاء المخططات فقط للشرائح التي سيتم عرضها.

## المشكلات الشائعة والحلول

| المشكلة | السبب | الحل |
|---------|-------|------|
| المخطط يظهر فارغًا | خلايا البيانات لم تُملأ بشكل صحيح | تحقق من أن `wb.getCell` يشير إلى الصف/العمود الصحيح وأن القيمة ليست `null`. |
| القيم المتطرفة غير معروضة | `setShowOutlierPoints` تم تعيينه إلى `false` | تأكد من استدعاء `series.setShowOutlierPoints(true)`. |
| تسرب الذاكرة | لم يتم تحرير Presentation | دائمًا غلف الاستخدام بـ try/finally واستدعِ `dispose()`. |
| الرباعيات غير صحيحة | استخدام الطريقة الافتراضية `Inclusive` | غيّر إلى `Exclusive` عبر `setQuartileMethod(QuartileMethodType.Exclusive)`. |

## الأسئلة المتكررة

**س1: ما هو مخطط الصندوق والشارب؟**  
مخطط الصندوق والشارب، المعروف أيضًا باسم مخطط الصندوق، يعرض توزيع البيانات بناءً على خمس إحصاءات ملخصة: الحد الأدنى، الربع الأول، الوسيط، الربع الثالث، والحد الأقصى، بالإضافة إلى أي قيم متطرفة.

**س2: هل يمكنني تخصيص مظهر مخطط الصندوق والشارب؟**  
نعم. يتيح لك Aspose.Slides تغيير الألوان، أنماط الخطوط، أشكال العلامات، وحتى إضافة تسميات البيانات عبر واجهة برمجة تطبيقات تنسيق المخطط.

**س3: هل يمكن التعامل مع سلاسل متعددة في مخطط واحد؟**  
بالطبع. كرّر كتلة إنشاء السلسلة لكل مجموعة بيانات تريد تصورها.

**س4: كيف أحل مشاكل عدم عرض البيانات بشكل صحيح؟**  
تأكد من كتابة البيانات بشكل صحيح إلى خلايا دفتر العمل وأن خصائص الرؤية مثل `setShowMeanLine` مفعلة.

**س5: أين يمكنني الحصول على الدعم إذا واجهت مشاكل؟**  
قم بزيارة [منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) للحصول على مساعدة المجتمع، أو راجع الوثائق الرسمية.

**س6: هل يدعم Aspose.Slides أنواع مخططات أخرى؟**  
نعم، يدعم المخططات الخطية، الشريطية، الدائرية، النقطية، الرادارية، والعديد من الأنواع الأخرى.

**س7: هل يمكنني إنشاء مخططات في بيئة خادم بدون واجهة (headless)؟**  
المكتبة تعمل بالكامل في سيناريوهات الخادم؛ لا يلزم وجود واجهة مستخدم.

## الموارد

- **Documentation**: استكشف مراجع API التفصيلية على [توثيق Aspose.Slides](https://reference.aspose.com/slides/java/)  
- **Download**: احصل على إصدارات Aspose.Slides [هنا](https://releases.aspose.com/slides/java/)  
- **Purchase**: اشترِ ترخيصًا لفتح جميع الميزات على [شراء Aspose](https://purchase.aspose.com/buy)  
- **Free Trial & Temporary License**: ابدأ بنسخة تجريبية مجانية أو اطلب ترخيصًا مؤقتًا [هنا](https://releases.aspose.com/slides/java/)

باتباعك هذا الدليل، أصبحت الآن مجهزًا لإنشاء مخططات الصندوق والشارب ببرمجة في تطبيقات Java الخاصة بك وتضمينها مباشرةً في عروض PowerPoint. برمجة سعيدة!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**آخر تحديث:** 2026-03-02  
**تم الاختبار مع:** Aspose.Slides 25.4 (JDK 16 classifier)  
**المؤلف:** Aspose