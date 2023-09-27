---
title: لون الخط القائد في شرائح جافا
linktitle: لون الخط القائد في شرائح جافا
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية تغيير ألوان الخطوط الرئيسية في مخططات PowerPoint باستخدام Aspose.Slides لـ Java. دليل خطوة بخطوة مع أمثلة التعليمات البرمجية المصدر.
type: docs
weight: 12
url: /ar/java/data-manipulation/leader-line-color-java-slides/
---

## مقدمة إلى لون خط القائد في Aspose.Slides لـ Java

في هذا البرنامج التعليمي، سوف نستكشف كيفية تغيير لون الخط الرئيسي للمخطط في عرض تقديمي لـ PowerPoint باستخدام Aspose.Slides for Java. يتم استخدام الخطوط الرئيسية في المخططات لتوصيل تسميات البيانات بنقاط البيانات المقابلة لها. سوف نستخدم كود Java لإنجاز هذه المهمة.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي:

-  تم تثبيت Aspose.Slides لـ Java API. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/java/).

## الخطوة 1: قم بتحميل العرض التقديمي

أولاً، تحتاج إلى تحميل عرض PowerPoint التقديمي الذي يحتوي على المخطط الذي تريد تعديله. يستبدل`presentationName` مع المسار إلى ملف PowerPoint الخاص بك.

```java
String presentationName = "path/to/your/presentation.pptx";
String outPath = "output/path/output.pptx";
Presentation pres = new Presentation(presentationName);
```

## الخطوة 2: الوصول إلى تسميات المخطط والبيانات

بعد ذلك، سوف نصل إلى تسميات المخطط والبيانات داخل العرض التقديمي. في هذا المثال، نفترض أن المخطط موجود في الشريحة الأولى.

```java
// احصل على المخطط من الشريحة الأولى
IChart chart = (IChart)pres.getSlides().get_Item(0).getShapes().get_Item(0);

// الحصول على سلسلة من الرسم البياني
IChartSeriesCollection series = chart.getChartData().getSeries();

// الحصول على تسميات السلسلة الأولى
IDataLabelCollection labels = series.get_Item(0).getLabels();
```

## الخطوة 3: تغيير لون خط القائد

الآن، سوف نقوم بتغيير لون جميع الخطوط الرئيسية في المجموعة إلى اللون الأحمر. يمكنك تخصيص اللون حسب متطلباتك.

```java
// تغيير لون جميع الخطوط الرئيسية في المجموعة إلى اللون الأحمر
labels.getLeaderLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

## الخطوة 4: احفظ العرض التقديمي المعدل

وأخيرًا، احفظ العرض التقديمي بألوان الخط الرئيسي المعدلة في ملف جديد.

```java
// احفظ العرض التقديمي المعدل
pres.save(outPath, SaveFormat.Pptx);
```

## أكمل كود المصدر للون خط القائد في شرائح جافا

```java
        String presentationName = RunExamples.getDataDir_Charts() + "LeaderLinesColor.pptx";
        String outPath = RunExamples.getOutPath() + "LeaderLinesColor-out.pptx";
        Presentation pres = new Presentation(presentationName);
        try {
            // احصل على المخطط من الشريحة الأولى
            IChart chart = (IChart)pres.getSlides().get_Item(0).getShapes().get_Item(0);
            // الحصول على سلسلة من الرسم البياني
            IChartSeriesCollection series = chart.getChartData().getSeries();
            // الحصول على lebels من السلسلة الأولى
            IDataLabelCollection labels = series.get_Item(0).getLabels();
            // تغيير لون جميع الخطوط الرائدة في المجموعة
            labels.getLeaderLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
            // حفظ النتيجة
            pres.save(outPath, SaveFormat.Pptx);
        } finally {
            if (pres != null) pres.dispose();
        }
```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية تغيير لون الخط الرئيسي في مخطط PowerPoint باستخدام Aspose.Slides لـ Java. يمكنك تخصيص اللون وخيارات التنسيق الأخرى لتلبية احتياجاتك الخاصة. يمكن أن يكون هذا مفيدًا بشكل خاص عندما تريد تمييز نقاط بيانات معينة في مخططاتك للحصول على تصور أفضل.

## الأسئلة الشائعة

### هل يمكنني تغيير لون الخط الرئيسي إلى لون مخصص؟

نعم، يمكنك تغيير لون الخط الرئيسي إلى لون مخصص. في مثال التعليمات البرمجية المقدم، قمنا بتعيين لون الخط الرئيسي إلى اللون الأحمر (Color.RED). يمكنك استبدال "Color.RED" بأي لون آخر صالح في Java لتحقيق اللون المطلوب للخطوط الرائدة.

### كيف يمكنني الوصول إلى خصائص المخطط الأخرى وتعديلها باستخدام Aspose.Slides لـ Java؟

للوصول إلى خصائص المخطط الأخرى وتعديلها، يمكنك استكشاف الفئات والأساليب المتنوعة التي توفرها Aspose.Slides لـ Java Chart API. يمكنك التعامل مع بيانات المخطط والتنسيق والتسميات والمزيد. راجع وثائق Aspose.Slides for Java للحصول على معلومات تفصيلية وأمثلة على التعليمات البرمجية.

### هل تتوفر نسخة تجريبية من Aspose.Slides لـ Java؟

 نعم، يمكنك طلب نسخة تجريبية مجانية من Aspose.Slides for Java من موقع Aspose. تتيح لك النسخة التجريبية تقييم مميزات وإمكانيات المكتبة قبل اتخاذ قرار الشراء. قم بزيارة[Aspose.Slides لصفحة النسخة التجريبية المجانية من Java](https://products.aspose.com/slides/java) للبدء.

### كيف يمكنني معرفة المزيد حول استخدام Aspose.Slides لـ Java؟

 يمكنك العثور على وثائق شاملة وأمثلة تعليمات برمجية إضافية حول كيفية استخدام Aspose.Slides for Java على موقع Aspose الإلكتروني. قم بزيارة[Aspose.Slides لتوثيق جافا](https://docs.aspose.com/slides/java/) للحصول على أدلة وبرامج تعليمية مفصلة.

### هل أحتاج إلى ترخيص لاستخدام Aspose.Slides for Java في مشروع تجاري؟

نعم، تحتاج بشكل عام إلى ترخيص صالح لاستخدام Aspose.Slides for Java في مشروع تجاري. يقدم Aspose خيارات ترخيص متنوعة، بما في ذلك ترخيص التقييم المجاني لأغراض الاختبار والتجربة. ومع ذلك، لاستخدام الإنتاج، يجب عليك الحصول على الترخيص التجاري المناسب. قم بزيارة[Aspose صفحة الشراء](https://purchase.aspose.com/) للحصول على تفاصيل الترخيص.

### كيف يمكنني الحصول على الدعم الفني لـ Aspose.Slides لـ Java؟

يمكنك الحصول على الدعم الفني لـ Aspose.Slides for Java من خلال زيارة منتدى دعم Aspose، حيث يمكنك طرح الأسئلة والإبلاغ عن المشكلات والتفاعل مع مجتمع Aspose. بالإضافة إلى ذلك، إذا كان لديك ترخيص تجاري صالح، فقد يحق لك الحصول على الدعم الفني المباشر من Aspose.

### هل يمكنني استخدام Aspose.Slides لـ Java مع مكتبات وأطر عمل Java الأخرى؟

نعم، يمكنك دمج Aspose.Slides for Java مع مكتبات وأطر عمل Java الأخرى حسب الحاجة لمشروعك. يوفر Aspose.Slides واجهات برمجة التطبيقات للعمل مع ميزات PowerPoint المتنوعة، مما يجعل من الممكن دمجها مع أدوات وتقنيات أخرى لإنشاء تطبيقات قوية.