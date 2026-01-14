---
date: '2026-01-14'
description: تعلم كيفية تصدير المخطط إلى إكسل باستخدام Aspose.Slides للغة Java وإضافة
  شريحة مخطط دائري إلى العروض التقديمية. دليل خطوة بخطوة مع الشيفرة.
keywords:
- Aspose.Slides Java
- creating charts in Java
- exporting chart data with Aspose
title: تصدير المخطط إلى Excel باستخدام Aspose.Slides Java
url: /ar/java/charts-graphs/aspose-slides-java-chart-creation-exportation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# تصدير المخطط إلى Excel باستخدام Aspose.Slides for Java

**إتقان تقنيات تصور البيانات مع Aspose.Slides for Java**

في بيئة اليوم المعتمدة على البيانات، القدرة على **export chart to excel** مباشرةً من تطبيق Java الخاص بك يمكن أن تحول الرسوم التقديمية الثابتة في PowerPoint إلى مجموعات بيانات قابلة لإعادة الاستخدام والتحليل. سواء كنت تحتاج إلى إنشاء تقارير، أو تغذية خطوط التحليل، أو ببساطة السماح لمستخدمي الأعمال بتحرير بيانات المخطط في Excel، فإن Aspose.Slides يجعل ذلك بسيطًا. يوضح هذا البرنامج التعليمي كيفية إنشاء مخطط، إضافة شريحة مخطط دائري، وتصدير بيانات ذلك المخطط إلى مصنف Excel.

**ما ستتعلمه:**
- تحميل ومعالجة ملفات العرض بسهولة
- **Add pie chart slide** وأنواع مخططات أخرى إلى الشرائح
- **export chart to excel** (إنشاء Excel من المخطط) للتحليل اللاحق
- تعيين مسار مصنف خارجي لـ **embed chart in presentation** والحفاظ على تزامن البيانات

هيا نبدأ!

## إجابات سريعة
- **ما هو الهدف الأساسي؟** تصدير بيانات المخطط من شريحة PowerPoint إلى ملف Excel.  
- **ما نسخة المكتبة المطلوبة؟** Aspose.Slides for Java 25.4 أو أحدث.  
- **هل أحتاج إلى ترخيص؟** نسخة تجريبية مجانية تكفي للتقييم؛ الترخيص التجاري مطلوب للإنتاج.  
- **هل يمكنني إضافة شريحة مخطط دائري؟** نعم – يوضح البرنامج التعليمي كيفية إضافة Pie chart.  
- **هل Java 16 هو الحد الأدنى؟** نعم، يُنصح بـ JDK 16 أو أعلى.

## كيف تصدر المخطط إلى Excel باستخدام Aspose.Slides؟
تصدير بيانات المخطط إلى Excel بسيط مثل تحميل عرض تقديمي، إنشاء مخطط، ثم كتابة تدفق مصنف المخطط إلى ملف. الخطوات أدناه تقودك عبر العملية بالكامل، من إعداد المشروع إلى التحقق النهائي.

## المتطلبات المسبقة
قبل أن نبدأ، تأكد من توفر ما يلي:

### المكتبات والإصدارات المطلوبة
- **Aspose.Slides for Java** الإصدار 25.4 أو أحدث

### متطلبات إعداد البيئة
- مجموعة تطوير جافا (JDK) 16 أو أعلى
- محرر شفرة أو بيئة تطوير متكاملة مثل IntelliJ IDEA أو Eclipse

### المتطلبات المعرفية
- مهارات برمجة Java أساسية
- إلمام بأنظمة البناء Maven أو Gradle

## إعداد Aspose.Slides for Java
لبدء استخدام Aspose.Slides، أدرجه في مشروعك باستخدام Maven أو Gradle.

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

بدلاً من ذلك، يمكنك [تحميل أحدث نسخة مباشرةً](https://releases.aspose.com/slides/java/).

### خطوات الحصول على الترخيص
توفر Aspose.Slides ترخيصًا تجريبيًا مجانيًا لاستكشاف جميع إمكانياتها. يمكنك أيضًا طلب ترخيص مؤقت أو شراء ترخيص للاستخدام الممتد. اتبع الخطوات التالية:
1. زر صفحة [Aspose Purchase](https://purchase.aspose.com/buy) للحصول على الترخيص.  
2. للحصول على نسخة تجريبية مجانية، حمّلها من [Releases](https://releases.aspose.com/slides/java/).  
3. قدّم طلبًا للحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).

بعد الحصول على ملف الترخيص، قم بتهيئته في تطبيق Java الخاص بك:
```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## دليل التنفيذ

### الميزة 1: تحميل العرض التقديمي
تحميل العرض هو الخطوة الأولى لأي مهمة تعديل.

#### نظرة عامة
توضح هذه الميزة كيفية تحميل ملف PowerPoint موجود باستخدام Aspose.Slides for Java.

#### التنفيذ خطوة بخطوة
**Load Presentation**
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
**Explanation:**  
- يتم تهيئة `Presentation` بمسار ملف `.pptx` الخاص بك.  
- احرص دائمًا على تحرير كائن `Presentation` لتحرير الموارد الأصلية.

### الميزة 2: إضافة شريحة مخطط دائري
إضافة مخطط يمكن أن تعزز بشكل كبير من عرض البيانات، ويسأل العديد من المطورين **how to add chart slide** في Java.

#### نظرة عامة
تظهر هذه الميزة كيفية إضافة **pie chart slide** (سيناريو “add pie chart slide” الكلاسيكي) إلى الشريحة الأولى من العرض.

#### التنفيذ خطوة بخطوة
**Add Pie Chart**
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
**Explanation:**  
- `addChart` يدرج مخططًا دائريًا.  
- المعلمات تحدد نوع المخطط وموقعه/حجمه على الشريحة.

### الميزة 3: إنشاء Excel من المخطط
تصدير بيانات المخطط يتيح لك **generate excel from chart** للتحليل المتعمق.

#### نظرة عامة
توضح هذه الميزة كيفية تصدير بيانات المخطط من عرض تقديمي إلى مصنف Excel خارجي.

#### التنفيذ خطوة بخطوة
**Export Data**
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
**Explanation:**  
- `readWorkbookStream` يستخرج بيانات مصنف المخطط.  
- يتم كتابة مصفوفة البايت إلى ملف `.xlsx` باستخدام `FileOutputStream`.

### الميزة 4: تضمين المخطط في العرض مع مصنف خارجي
ربط المخطط بمصنف خارجي يساعدك على **embed chart in presentation** والحفاظ على تزامن البيانات.

#### نظرة عامة
توضح هذه الميزة كيفية تعيين مسار مصنف خارجي بحيث يمكن للمخطط قراءة/كتابة البيانات مباشرةً من Excel.

#### التنفيذ خطوة بخطوة
**Set External Workbook Path**
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
**Explanation:**  
- `setExternalWorkbook` يربط المخطط بملف Excel، مما يسمح بالتحديثات الديناميكية دون إعادة بناء الشريحة.

## التطبيقات العملية
توفر Aspose.Slides حلولًا متعددة للسيناريوهات المختلفة:

1. **تقارير الأعمال:** إنشاء تقارير مفصلة مع مخططات مباشرةً من تطبيقات Java.  
2. **العروض الأكاديمية:** تحسين المحاضرات بشرائح مخطط دائري تفاعلية.  
3. **التحليل المالي:** **export chart to excel** للنمذجة المالية المتعمقة.  
4. **تحليلات التسويق:** تصور أداء الحملات و**generate excel from chart** لفريق التحليل.

## الأسئلة المتكررة

**س: هل يمكنني استخدام هذا النهج مع أنواع مخططات أخرى (مثل Bar, Line)؟**  
ج: بالتأكيد. استبدل `ChartType.Pie` بأي قيمة أخرى من تعداد `ChartType`.

**س: هل أحتاج إلى مكتبة Excel منفصلة لقراءة الملف المصدر؟**  
ج: لا. ملف `.xlsx` المصدر هو مصنف Excel قياسي يمكن فتحه بأي تطبيق جداول بيانات.

**س: كيف يؤثر المصنف الخارجي على حجم الشريحة؟**  
ج: ربط المصنف الخارجي لا يزيد حجم ملف PPTX بشكل ملحوظ؛ المخطط يراجع المصنف وقت التشغيل.

**س: هل يمكن تحديث بيانات Excel وجعل الشريحة تعكس التغييرات تلقائيًا؟**  
ج: نعم. بعد استدعاء `setExternalWorkbook`، أي تغييرات تُحفظ في المصنف ستظهر عند فتح العرض مرة أخرى.

**س: ماذا لو احتجت لتصدير عدة مخططات من نفس العرض؟**  
ج: قم بالتكرار عبر مجموعة المخططات في كل شريحة، استدعِ `readWorkbookStream()` لكل منها، واكتبها إلى ملفات مصنف منفصلة.

---

**آخر تحديث:** 2026-01-14  
**تم الاختبار مع:** Aspose.Slides 25.4 for Java  
**المؤلف:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}