---
"description": "تعلّم كيفية تغيير ألوان الخطوط الرئيسية في مخططات PowerPoint باستخدام Aspose.Slides لجافا. دليل خطوة بخطوة مع أمثلة على الكود المصدري."
"linktitle": "لون الخط الرئيسي في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "لون الخط الرئيسي في شرائح Java"
"url": "/ar/java/data-manipulation/leader-line-color-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# لون الخط الرئيسي في شرائح Java


## مقدمة إلى لون الخط الرئيسي في Aspose.Slides لـ Java

في هذا البرنامج التعليمي، سنستكشف كيفية تغيير لون الخط الرئيسي لرسم بياني في عرض تقديمي على PowerPoint باستخدام Aspose.Slides لجافا. تُستخدم الخطوط الرئيسية في الرسوم البيانية لربط تسميات البيانات بنقاط البيانات المقابلة لها. سنستخدم شفرة جافا لإنجاز هذه المهمة.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- تم تثبيت Aspose.Slides لـ Java API. يمكنك تنزيله من [هنا](https://releases.aspose.com/slides/java/).

## الخطوة 1: تحميل العرض التقديمي

أولاً، عليك تحميل عرض PowerPoint الذي يحتوي على المخطط الذي تريد تعديله. استبدل `presentationName` مع المسار إلى ملف PowerPoint الخاص بك.

```java
String presentationName = "path/to/your/presentation.pptx";
String outPath = "output/path/output.pptx";
Presentation pres = new Presentation(presentationName);
```

## الخطوة 2: الوصول إلى تسميات المخطط والبيانات

بعد ذلك، سنصل إلى المخطط وتسميات البيانات داخل العرض التقديمي. في هذا المثال، نفترض أن المخطط موجود في الشريحة الأولى.

```java
// احصل على الرسم البياني من الشريحة الأولى
IChart chart = (IChart)pres.getSlides().get_Item(0).getShapes().get_Item(0);

// احصل على سلسلة من الرسم البياني
IChartSeriesCollection series = chart.getChartData().getSeries();

// احصل على ملصقات السلسلة الأولى
IDataLabelCollection labels = series.get_Item(0).getLabels();
```

## الخطوة 3: تغيير لون خط القائد

الآن، سنغيّر لون جميع خطوط القيادة في المجموعة إلى الأحمر. يمكنك تخصيص اللون حسب احتياجاتك.

```java
// تغيير لون جميع خطوط القادة في المجموعة إلى اللون الأحمر
labels.getLeaderLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

## الخطوة 4: حفظ العرض التقديمي المعدّل

أخيرًا، احفظ العرض التقديمي بألوان الخطوط الرئيسية المعدلة في ملف جديد.

```java
// حفظ العرض التقديمي المعدل
pres.save(outPath, SaveFormat.Pptx);
```

## كود المصدر الكامل للون خط القائد في شرائح Java

```java
        String presentationName = "Your Document Directory";
        String outPath = "Your Output Directory" + "LeaderLinesColor-out.pptx";
        Presentation pres = new Presentation(presentationName);
        try {
            // احصل على الرسم البياني من الشريحة الأولى
            IChart chart = (IChart)pres.getSlides().get_Item(0).getShapes().get_Item(0);
            // احصل على سلسلة من الرسم البياني
            IChartSeriesCollection series = chart.getChartData().getSeries();
            // احصل على تسميات السلسلة الأولى
            IDataLabelCollection labels = series.get_Item(0).getLabels();
            // تغيير لون جميع خطوط القادة في المجموعة
            labels.getLeaderLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
            // حفظ النتيجة
            pres.save(outPath, SaveFormat.Pptx);
        } finally {
            if (pres != null) pres.dispose();
        }
```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية تغيير لون الخط الرئيسي في مخطط PowerPoint باستخدام Aspose.Slides لجافا. يمكنك تخصيص اللون وخيارات التنسيق الأخرى لتلبية احتياجاتك الخاصة. يُعد هذا مفيدًا بشكل خاص عند إبراز نقاط بيانات معينة في مخططاتك لتحسين التصور.

## الأسئلة الشائعة

### هل يمكنني تغيير لون خط القائد إلى لون مخصص؟

نعم، يمكنك تغيير لون خطّ القيادة إلى لون مخصص. في مثال الكود المُرفق، عيّنّا لون خطّ القيادة إلى الأحمر (Color.RED). يمكنك استبدال "Color.RED" بأيّ لون آخر صالح في جافا للحصول على اللون المطلوب لخطوط القيادة.

### كيف يمكنني الوصول إلى خصائص الرسم البياني الأخرى وتعديلها باستخدام Aspose.Slides لـ Java؟

للوصول إلى خصائص المخططات الأخرى وتعديلها، يمكنك استكشاف الفئات والأساليب المتنوعة التي توفرها واجهة برمجة تطبيقات Aspose.Slides لجافا للمخططات. يمكنك معالجة بيانات المخططات، والتنسيق، والتسميات، والمزيد. راجع وثائق Aspose.Slides لجافا للحصول على معلومات مفصلة وأمثلة برمجية.

### هل هناك نسخة تجريبية من Aspose.Slides لـ Java متاحة؟

نعم، يمكنك طلب نسخة تجريبية مجانية من Aspose.Slides لجافا من موقع Aspose الإلكتروني. تتيح لك النسخة التجريبية تقييم ميزات المكتبة وإمكانياتها قبل اتخاذ قرار الشراء. تفضل بزيارة [صفحة النسخة التجريبية المجانية من Aspose.Slides لـ Java](https://products.aspose.com/slides/java) للبدء.

### كيف يمكنني معرفة المزيد حول استخدام Aspose.Slides لـ Java؟

يمكنك العثور على وثائق شاملة وأمثلة أكواد إضافية حول كيفية استخدام Aspose.Slides لجافا على موقع Aspose الإلكتروني. تفضل بزيارة [توثيق Aspose.Slides لـ Java](https://docs.aspose.com/slides/java/) للحصول على أدلة ودروس تعليمية مفصلة.

### هل أحتاج إلى ترخيص لاستخدام Aspose.Slides لـ Java في مشروع تجاري؟

نعم، عادةً ما تحتاج إلى ترخيص ساري المفعول لاستخدام Aspose.Slides لجافا في مشروع تجاري. يوفر Aspose خيارات ترخيص متنوعة، بما في ذلك ترخيص تقييم مجاني لأغراض الاختبار والتجربة. ومع ذلك، للاستخدام الإنتاجي، يجب عليك الحصول على الترخيص التجاري المناسب. تفضل بزيارة [صفحة شراء Aspose](https://purchase.aspose.com/) للحصول على تفاصيل الترخيص.

### كيف يمكنني الحصول على الدعم الفني لـ Aspose.Slides لـ Java؟

يمكنك الحصول على دعم فني لبرنامج Aspose.Slides لجافا بزيارة منتدى دعم Aspose، حيث يمكنك طرح الأسئلة والإبلاغ عن المشاكل والتفاعل مع مجتمع Aspose. بالإضافة إلى ذلك، إذا كان لديك ترخيص تجاري ساري المفعول، فقد يحق لك الحصول على دعم فني مباشر من Aspose.

### هل يمكنني استخدام Aspose.Slides لـ Java مع مكتبات Java وأطر العمل الأخرى؟

نعم، يمكنك دمج Aspose.Slides لجافا مع مكتبات وأطر عمل جافا أخرى حسب حاجة مشروعك. يوفر Aspose.Slides واجهات برمجة تطبيقات للعمل مع ميزات PowerPoint المتنوعة، مما يتيح دمجه مع أدوات وتقنيات أخرى لإنشاء تطبيقات فعّالة.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}