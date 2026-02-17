---
date: '2026-02-17'
description: تعلم كيفية إضافة مخطط دائري إلى عروض PowerPoint باستخدام Aspose.Slides
  للـ Java. اتبع هذا الدليل خطوة بخطوة لإنشاء وتخصيص مخططات دائرية احترافية.
keywords:
- Create Pie Charts in PowerPoint Java
- Customize Pie Chart Aspose.Slides Java
- Aspose.Slides for Java Pie Chart
title: كيفية إضافة مخطط دائري إلى PowerPoint باستخدام Aspose.Slides للـ Java
url: /ar/java/charts-graphs/aspose-slides-java-create-pie-chart/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إنشاء وتخصيص مخططات دائرية في PowerPoint باستخدام Aspose.Slides for Java

## مقدمة

هل تواجه صعوبة في تصور البيانات بفعالية في عروض PowerPoint الخاصة بك؟ **Adding a pie chart PowerPoint** يمكن أن يحول الأرقام الخام إلى قصة بصرية واضحة على الفور. باستخدام Aspose.Slides for Java، يمكنك برمجيًا **add pie chart PowerPoint**، مما يمنحك تحكمًا كاملًا في التصميم والبيانات دون الحاجة إلى فتح PowerPoint يدويًا. في هذا الدرس سنستعرض العملية بالكامل — من إعداد المكتبة إلى تخصيص نقاط البيانات الفردية — حتى تتمكن من تقديم شرائح مصقولة مدعومة بالبيانات في دقائق.

### إجابات سريعة
- **ما المكتبة التي أحتاجها؟** Aspose.Slides for Java (الإصدار الأحدث).  
- **هل يمكنني إنشاء مخطط دون تثبيت PowerPoint؟** نعم، الـ API يعمل بالكامل دون اتصال.  
- **ما نسخة Java المطلوبة؟** يوصى بـ JDK 16 أو أحدث.  
- **كيف يمكن تغيير لون شريحة المخطط؟** استخدم طريقتي `setFillType` و `setSolidFillColor` على نقطة البيانات.  
- **هل الترخيص إلزامي؟** النسخة التجريبية تعمل للتطوير؛ الترخيص الدائم يزيل قيود التقييم.

### ما ستتعلمه
- طرق **add pie chart PowerPoint** برمجيًا باستخدام Java.  
- طرق لتخصيص انفجار الشريحة، الألوان، وغيرها من الخصائص البصرية.  
- أفضل الممارسات لإدارة الموارد والأداء عند التعامل مع عروض تقديمية كبيرة.

## لماذا إضافة مخطط دائري PowerPoint باستخدام Aspose.Slides for Java؟
يتيح تضمين مخطط دائري مباشرةً من الشيفرة إنشاء تقارير محدثة، أتمتة لوحات التحكم الشهرية، أو إنشاء مجموعات شرائح مخصصة في الوقت الفعلي. يزيل الأخطاء الناتجة عن النسخ واللصق اليدوي، يضمن التناسق عبر العروض، ويتكامل بسلاسة مع الأنظمة الخلفية Java الموجودة.

## المتطلبات المسبقة

- مكتبة **Aspose.Slides for Java** – الدرس يشير إلى الإصدار 25.4 (أحدث إصدار وقت كتابة المقال).  
- **Java Development Kit (JDK)** متوافق – يفضَّل JDK 16+.  
- إلمام أساسي بـ **Maven** أو **Gradle** لإدارة التبعيات.

## إعداد Aspose.Slides for Java

للبدء، قم بإضافة مكتبة Aspose.Slides إلى مشروعك.

### Maven
Add this dependency to your `pom.xml` file:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Include the following in your `build.gradle` file:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

بدلاً من ذلك، قم بتحميل أحدث إصدار مباشرةً من [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### الترخيص
To use Aspose.Slides without limitations:

- ابدأ بـ **نسخة تجريبية مجانية** لتقييم الـ API.  
- اطلب **ترخيصًا مؤقتًا** للاختبار الموسع عبر صفحة [Temporary License](https://purchase.aspose.com/temporary-license/).  
- اشترِ اشتراكًا كاملًا عبر [Purchase page](https://purchase.aspose.com/buy).

## كيفية إضافة مخطط دائري PowerPoint باستخدام Aspose.Slides for Java

أدناه دليل خطوة بخطوة يوضح بالضبط كيفية إنشاء وتخصيص مخطط دائري.

### الخطوة 1: تهيئة العرض التقديمي
أولاً، أنشئ كائن `Presentation` جديد. يمثل هذا ملف PowerPoint فارغ.
```java
Presentation pres = new Presentation();
```

### الخطوة 2: إضافة المخطط الدائري
أدخل مخططًا دائريًا على الشريحة الأولى. الإحداثيات (50, 50) والحجم (600 × 400) يناسبان شريحة قياسية بنسبة 16:9.
```java
pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
```

### الخطوة 3: حفظ العرض التقديمي
احفظ العرض التقديمي إلى القرص. استبدل `YOUR_OUTPUT_DIRECTORY` بالمجلد الذي تريد حفظ الملف فيه.
```java
pres.save("YOUR_OUTPUT_DIRECTORY/output.pptx", SaveFormat.Pptx);
```

### الخطوة 4: تنظيف الموارد
حرّر كائن `Presentation` لتحرير الموارد الأصلية.
```java
if (pres != null) pres.dispose();
```

## تخصيص انفجار نقطة البيانات واللون

تخصيص الشرائح الفردية يجعل المخطط أسهل للقراءة، خاصةً عندما تريد إبراز قيمة معينة.

### الخطوة 1: تحميل عرض تقديمي موجود (أو إعادة استخدام العرض الذي أنشأته للتو)
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

### الخطوة 2: الوصول إلى المخطط ونقطة البيانات المستهدفة
هنا نسترجع نقطة البيانات الثانية (الفهرس 1) من السلسلة الأولى.
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
IChartDataPoint point = chart.getChartData().getSeries().get_Item(0).getDataPoints().get_Item(1);
```

### الخطوة 3: تطبيق الانفجار واللون
افصل الشريحة بصريًا وغير لون التعبئة إلى اللون الأزرق.
```java
point.setExplosion(30); // Set explosion distance
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE); // Change fill color
```

### الخطوة 4: حفظ وتحرير
```java
pres.save("YOUR_OUTPUT_DIRECTORY/customized.pptx", SaveFormat.Pptx);
if (pres != null) pres.dispose();
```

## تطبيقات عملية
- **تقارير المبيعات:** إبراز المنتجات الأكثر مبيعًا باستخدام شرائح منفصلة.  
- **تحليل الميزانية:** تخصيص ألوان مميزة للأقسام للمقارنة البصرية السريعة.  
- **شرائح تعليمية:** تقسيم المفاهيم المعقدة إلى أقسام مخطط سهلة الفهم.

## اعتبارات الأداء
- **تحرير الكائنات** فورًا لتجنب تسرب الذاكرة، خاصةً عند إنشاء العديد من الشرائح داخل حلقة.  
- **مراقبة استهلاك الذاكرة** للعروض الكبيرة؛ فكر في بث الإخراج باستخدام تجاوزات `Save` التي تقبل `OutputStream`.  
- التزم بـ **JDK 16+** للاستفادة من أحدث تحسينات جمع القمامة.

## الخلاصة
لديك الآن سير عمل كامل وجاهز للإنتاج لإضافة ملفات **add pie chart PowerPoint** باستخدام Aspose.Slides for Java. جرب مسافات انفجار مختلفة، ألوان، ومجموعات بيانات لتتناسب مع علامتك التجارية. عندما تكون مستعدًا، استكشف أنواع مخططات أخرى — شريطية، خطية، أو مبعثرة — لبناء لوحة تحكم تحليلية كاملة داخل PowerPoint.

## قسم الأسئلة المتكررة
1. **ما هي الميزة الأساسية لاستخدام Aspose.Slides for Java؟**  
   - يبسط إنشاء ومعالجة ملفات PowerPoint برمجيًا، ويقدم مجموعة واسعة من الميزات.  
2. **هل يمكنني تخصيص أنواع مخططات أخرى باستخدام Aspose.Slides؟**  
   - بالتأكيد! يدعم Aspose.Slides أنواعًا مختلفة من المخططات مثل المخططات الشريطية، الخطية، والمبعثرة.  
3. **كيف يمكنني التعامل مع عدة شرائح عند إنشاء المخططات؟**  
   - يمكنك الوصول إلى كل شريحة عبر الفهرس باستخدام طريقة `get_Item()` لتطبيق التغييرات عبر الشرائح المختلفة.  
4. **ماذا أفعل إذا لم يظهر المخطط الدائري بشكل صحيح بعد التخصيص؟**  
   - تحقق من الإحداثيات والأبعاد المستخدمة في `addChart()`، وتأكد من أنها تناسب تخطيط الشريحة.  
5. **أين يمكنني العثور على ميزات متقدمة أكثر لـ Aspose.Slides؟**  
   - استكشف [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/) لتتعرف على وظائف وخيارات إضافية.

## الموارد
- **Documentation:** [Aspose.Slides Java Docs](https://reference.aspose.com/slides/java/)  
- **Download Library:** [Aspose Releases](https://releases.aspose.com/slides/java/)  
- **Purchase License:** [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **Free Trial:** [Try Aspose.Slides](https://releases.aspose.com/slides/java/)  
- **Temporary License:** [Request Temporary License](https://purchase.aspose.com/temporary-license/)  
- **Support Forum:** [Aspose Support](https://forum.aspose.com/c/slides/11)

---

**آخر تحديث:** 2026-02-17  
**تم الاختبار مع:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}