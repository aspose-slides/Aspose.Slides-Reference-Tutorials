---
date: '2026-02-09'
description: تعلم كيفية إنشاء مخطط وتصديره إلى Excel باستخدام Aspose.Slides للغة Java.
  إتقان تصور البيانات، شرائح تقارير الأعمال، وإنشاء المصنفات.
keywords:
- Aspose.Slides Java
- creating charts in Java
- exporting chart data with Aspose
title: كيفية إنشاء مخطط باستخدام Aspose.Slides Java
url: /ar/java/charts-graphs/aspose-slides-java-chart-creation-exportation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية إنشاء مخطط باستخدام Aspose.Slides for Java

**إتقان تقنيات تصور البيانات مع Aspose.Slides for Java**

في مشهد اليوم القائم على البيانات، *كيفية إنشاء مخطط* برمجياً هي مهارة يمكنها تحويل الأرقام الخام إلى قصص بصرية جذابة. سواء كنت تُعد مجموعة شرائح تقرير أعمال أو لوحة تحكم تحليلات تفاعلية، يمنحك Aspose.Slides for Java القدرة على إنشاء وتخصيص وتصدير المخططات مباشرةً من الشيفرة الخاصة بك. في هذا الدرس ستتعلم كيفية إنشاء كائنات المخطط، وتصدير بيانات المخطط إلى Excel، وربط المخططات بملفات عمل خارجية لإدارة البيانات بسلاسة.

## إجابات سريعة
- **ما المكتبة المطلوبة؟** Aspose.Slides for Java (v25.4+).  
- **هل يمكنني تصدير بيانات المخطط إلى Excel؟** نعم – استخدم `readWorkbookStream()` واكتب البايتات إلى ملف *.xlsx*.  
- **ما نسخة Java المطلوبة؟** JDK 16 أو أعلى.  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية المجانية تكفي للتقييم؛ يتطلب الترخيص الدائم للإنتاج.  
- **ما نوع المخطط المعروض؟** مخطط دائري (Pie chart)، لكن نفس النهج يعمل مع المخططات الشريطية، الخطية، وغيرها.

## ما هو Aspose.Slides for Java؟
Aspose.Slides for Java هو واجهة برمجة تطبيقات pure‑Java تتيح للمطورين إنشاء وتحرير وتحويل عروض PowerPoint دون الحاجة إلى Microsoft Office. يدعم مجموعة كاملة من أنواع المخططات، وربط البيانات، وإمكانيات التصدير، مما يجعله مثالياً لمشاريع **data visualization java**.

## لماذا تستخدم Aspose.Slides لإنشاء مخطط وتصديره إلى Excel؟
- **بدون تثبيت Office** – يعمل على أي خادم أو بيئة سحابية.  
- **مكتبة مخططات غنية** – عشرات أنواع المخططات والتحكم الكامل في التصميم.  
- **تصدير مباشر إلى Excel** – إنشاء ملف عمل خارجي للتحليل اللاحق.  
- **موجه للأداء** – استهلاك منخفض للذاكرة ومعالجة سريعة للشرائح الكبيرة.

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من أن لديك ما يلي:

### المكتبات المطلوبة والإصدارات
- **Aspose.Slides for Java** الإصدار 25.4 أو أحدث

### متطلبات إعداد البيئة
- مجموعة تطوير Java (JDK) 16 أو أعلى  
- بيئة تطوير متكاملة مثل IntelliJ IDEA أو Eclipse (أو أي محرر نصوص تفضله)

### المتطلبات المعرفية
- مهارات برمجة Java الأساسية  
- الإلمام بأدوات بناء Maven أو Gradle

## إعداد Aspose.Slides for Java
أضف المكتبة إلى مشروعك باستخدام نظام البناء المفضل لديك.

**Maven**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

بدلاً من ذلك، يمكنك [قم بتنزيل أحدث إصدار مباشرة](https://releases.aspose.com/slides/java/).

### خطوات الحصول على الترخيص
يوفر Aspose.Slides ترخيص تجريبي مجاني لاستكشاف جميع إمكاناته. يمكنك أيضًا طلب ترخيص مؤقت أو شراء واحد للاستخدام الممتد. اتبع الخطوات التالية:

1. زر [صفحة شراء Aspose](https://purchase.aspose.com/buy) للحصول على الترخيص الخاص بك.  
2. للحصول على نسخة تجريبية مجانية، قم بتنزيلها من [الإصدارات](https://releases.aspose.com/slides/java/).  
3. قدّم طلبًا للحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).

بمجرد حصولك على ملف الترخيص، قم بتهيئته في تطبيق Java الخاص بك:

```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## دليل خطوة بخطوة

### كيفية إنشاء مخطط – تحميل عرض تقديمي
تحميل ملف PowerPoint موجود هو الخطوة الأولى قبل أن تتمكن من إضافة أو تعديل المخططات.

```java
import com.aspose.slides.Presentation;

public class Feature1 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        // Load an existing presentation
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        
        // Clean up resources
        if (pres != null) pres.dispose();
    }
}
```

**شرح:**  
- `Presentation` تمثل ملف PowerPoint.  
- دائمًا استدعِ `dispose()` لتحرير الموارد الأصلية.

### كيفية إنشاء مخطط – إضافة مخطط دائري إلى شريحة
الآن سنضيف مخططًا دائريًا، وهو مثالي لعرض البيانات النسبية.

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature2 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Add a Pie chart at position (50, 50) with width 400 and height 600
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                ChartType.Pie, 50, 50, 400, 600);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

**شرح:**  
- `addChart` يضيف المخطط إلى الشريحة الأولى.  
- المعلمات تحدد نوع المخطط، موقع X/Y، والحجم.

### كيفية تصدير المخطط إلى Excel – تصدير بيانات المخطط
تصدير بيانات المخطط يتيح للمحللين العمل بالأرقام في Excel، مما يتيح رؤى أعمق.

```java
import com.aspose.slides.IChart;
import java.io.File;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.FileNotFoundException;
import com.aspose.slides.Presentation;

public class Feature3 {
    public static void main(String[] args) {
        // Set the path to your document directory and output directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Access the first slide's chart
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Define the path for the external workbook
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            File file = new File(externalWbPath);
            if (file.exists()) file.delete();
            
            // Export chart data to an Excel stream
            byte[] workbookData = chart.getChartData().readWorkbookStream();
            FileOutputStream outputStream = new FileOutputStream(file);
            outputStream.write(workbookData);
            outputStream.close();
        } catch (FileNotFoundException e) {
            e.printStackTrace();
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

**شرح:**  
- `readWorkbookStream()` يستخرج ملف Excel الأساسي للمخطط كمصفوفة بايت.  
- تُكتب مصفوفة البايت إلى `externalWorkbook1.xlsx`، لتمنحك ملف Excel جاهز للاستخدام.

### كيفية إنشاء مخطط – تعيين ملف عمل خارجي للبيانات الديناميكية
ربط المخطط بملف عمل خارجي يتيح لك تحديث المخطط ببساطة عن طريق تعديل ملف Excel.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature4 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Access the first slide's chart
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Define and set the path for the external workbook
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            chart.getChartData().setExternalWorkbook(externalWbPath);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

**شرح:**  
- `setExternalWorkbook` يربط المخطط بملف Excel المحدد، مما يتيح تحديثات بيانات مباشرة دون الحاجة لإعادة بناء الشريحة.

## تطبيقات عملية
يوفر Aspose.Slides حلولًا متعددة الاستخدامات لمختلف السيناريوهات الواقعية:

1. **شرائح تقارير الأعمال:** إنشاء مخططات الأداء ربع السنوية تلقائيًا من خطوط بياناتك.  
2. **العروض الأكاديمية:** تحويل بيانات البحث إلى تصورات واضحة دون الحاجة إلى إنشاء مخططات يدويًا.  
3. **التحليل المالي:** تصدير بيانات المخطط إلى Excel لتتيح للمراجعين التحقق من الأرقام.  
4. **تحليلات التسويق:** تصور مقاييس الحملات ومشاركة ملفات العمل القابلة للتعديل مع أصحاب المصلحة.

## المشكلات الشائعة وإجراءات استكشاف الأخطاء
- **`FileNotFoundException`** – تحقق من أن `dataDir` يشير إلى مجلد صالح وأن مسار الإخراج قابل للكتابة.  
- **تسربات الذاكرة** – استدعِ دائمًا `pres.dispose()` داخل كتلة `finally` لتحرير الموارد الأصلية.  
- **المخطط لا يظهر** – تأكد من أن فهرس الشريحة (`get_Item(0)`) يتطابق مع شريحة موجودة فعليًا.

## الأسئلة المتكررة

**س: هل يمكنني استخدام نوع مخطط مختلف (مثل شريطي، خطي) مع نفس الكود؟**  
ج: نعم. استبدل `ChartType.Pie` بأي قيمة أخرى من تعداد `ChartType` مثل `ChartType.Bar` أو `ChartType.Line`.

**س: هل يمكن تحديث ملف العمل الخارجي بعد إنشاء المخطط؟**  
ج: بالتأكيد. عدل ملف Excel مباشرة؛ سيعكس المخطط المرتبط التغييرات في المرة التالية التي يتم فيها فتح العرض.

**س: هل أحتاج إلى ترخيص منفصل لميزة تصدير Excel؟**  
ج: لا. قدرة تصدير Excel مضمونة في ترخيص Aspose.Slides for Java القياسي.

**س: ما إصدارات Java المدعومة؟**  
ج: يدعم Aspose.Slides for Java JDK 16 وما بعده؛ قد تعمل الإصدارات الأقدم لكنها غير مختبرة رسميًا.

**س: كيف يمكنني تضمين ملف Excel المُولد داخل ملف PPTX؟**  
ج: استخدم `chart.getChartData().setExternalWorkbook(null)` لتضمين ملف العمل، أو احتفظ بالرابط الخارجي للتحديثات الديناميكية.

---

**آخر تحديث:** 2026-02-09  
**تم الاختبار مع:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}