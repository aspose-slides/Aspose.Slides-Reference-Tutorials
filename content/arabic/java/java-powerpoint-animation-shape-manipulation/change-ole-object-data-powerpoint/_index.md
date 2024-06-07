---
title: تغيير بيانات كائن OLE في PowerPoint
linktitle: تغيير بيانات كائن OLE في PowerPoint
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية تغيير بيانات كائن OLE في PowerPoint باستخدام Aspose.Slides لـ Java. دليل خطوة بخطوة للحصول على تحديثات فعالة وسهلة.
type: docs
weight: 14
url: /ar/java/java-powerpoint-animation-shape-manipulation/change-ole-object-data-powerpoint/
---
## مقدمة
يمكن أن يكون تغيير بيانات كائن OLE في عروض PowerPoint التقديمية مهمة بالغة الأهمية عندما تحتاج إلى تحديث المحتوى المضمن دون تحرير كل شريحة يدويًا. سيرشدك هذا الدليل الشامل خلال العملية باستخدام Aspose.Slides for Java، وهي مكتبة قوية مصممة للتعامل مع عروض PowerPoint التقديمية. سواء كنت مطورًا متمرسًا أو بدأت للتو، ستجد هذا البرنامج التعليمي مفيدًا وسهل المتابعة.
## المتطلبات الأساسية
قبل أن نتعمق في الكود، دعنا نتأكد من أن لديك كل ما تحتاجه للبدء.
1.  Java Development Kit (JDK): تأكد من تثبيت JDK على نظامك. يمكنك تنزيله من[موقع أوراكل](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides لـ Java: قم بتنزيل أحدث إصدار من[صفحة تنزيل Aspose.Slides](https://releases.aspose.com/slides/java/).
3. بيئة التطوير المتكاملة (IDE): يمكنك استخدام أي Java IDE مثل IntelliJ IDEA أو Eclipse أو NetBeans.
4.  Aspose.Cells for Java: هذا مطلوب لتعديل البيانات المضمنة داخل كائن OLE. قم بتنزيله من[صفحة تنزيل Aspose.Cells](https://releases.aspose.com/cells/java/).
5. ملف العرض التقديمي: قم بإعداد ملف PowerPoint مع كائن OLE مضمن. بالنسبة لهذا البرنامج التعليمي، دعنا نسميه`ChangeOLEObjectData.pptx`.
## حزم الاستيراد
أولاً، لنستورد الحزم الضرورية في مشروع Java الخاص بك.
```java
import com.aspose.cells.OoxmlSaveOptions;
import com.aspose.cells.Workbook;
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import java.io.ByteArrayInputStream;
import java.io.ByteArrayOutputStream;
```

الآن، دعونا نقسم العملية إلى خطوات بسيطة يمكن التحكم فيها.
## الخطوة 1: قم بتحميل عرض PowerPoint التقديمي
للبدء، تحتاج إلى تحميل عرض PowerPoint التقديمي الذي يحتوي على كائن OLE.
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx");
```
## الخطوة 2: الوصول إلى الشريحة التي تحتوي على كائن OLE
بعد ذلك، احصل على الشريحة التي تم تضمين كائن OLE فيها.
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## الخطوة 3: ابحث عن كائن OLE في الشريحة
قم بالتكرار عبر الأشكال الموجودة في الشريحة لتحديد موقع كائن OLE.
```java
OleObjectFrame ole = null;
// اجتياز جميع الأشكال لإطار Ole
for (IShape shape : slide.getShapes()) {
    if (shape instanceof OleObjectFrame) {
        ole = (OleObjectFrame) shape;
        break;
    }
}
```
## الخطوة 4: استخراج البيانات المضمنة من كائن OLE
إذا تم العثور على كائن OLE، فاستخرج بياناته المضمنة.
```java
if (ole != null) {
    ByteArrayInputStream msln = new ByteArrayInputStream(ole.getEmbeddedData().getEmbeddedFileData());
```
## الخطوة 5: تعديل البيانات المضمنة باستخدام Aspose.Cells
الآن، استخدم Aspose.Cells لقراءة البيانات المضمنة وتعديلها، والتي من المحتمل أن تكون في هذه الحالة مصنف Excel.
```java
    Workbook wb = new Workbook(msln);
    // تعديل بيانات المصنف
    wb.getWorksheets().get(0).getCells().get(0, 4).putValue("E");
    wb.getWorksheets().get(0).getCells().get(1, 4).putValue(12);
    wb.getWorksheets().get(0).getCells().get(2, 4).putValue(14);
    wb.getWorksheets().get(0).getCells().get(3, 4).putValue(15);
```
## الخطوة 6: احفظ البيانات المعدلة مرة أخرى إلى كائن OLE
بعد إجراء التغييرات الضرورية، قم بحفظ المصنف المعدل مرة أخرى في كائن OLE.
```java
    ByteArrayOutputStream msout = new ByteArrayOutputStream();
    OoxmlSaveOptions so1 = new OoxmlSaveOptions(SaveFormat.XLSX);
    wb.save(msout, so1);
    IOleEmbeddedDataInfo newData = new OleEmbeddedDataInfo(msout.toByteArray(), ole.getEmbeddedData().getEmbeddedFileExtension());
    ole.setEmbeddedData(newData);
```
## الخطوة 7: احفظ العرض التقديمي المحدث
وأخيرًا، احفظ عرض PowerPoint التقديمي المحدث.
```java
    pres.save(dataDir + "OleEdit_out.pptx", SaveFormat.Pptx);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## خاتمة
يعد تحديث بيانات كائن OLE في عروض PowerPoint التقديمية باستخدام Aspose.Slides for Java عملية مباشرة بمجرد تقسيمها إلى خطوات بسيطة. يرشدك هذا الدليل خلال تحميل العرض التقديمي، والوصول إلى بيانات OLE المضمنة وتعديلها، وحفظ العرض التقديمي المحدث. باستخدام هذه الخطوات، يمكنك إدارة المحتوى المضمن وتحديثه بكفاءة في شرائح PowerPoint الخاصة بك برمجيًا.
## الأسئلة الشائعة
### ما هو كائن OLE في PowerPoint؟
يسمح كائن OLE (ربط الكائنات وتضمينها) بدمج محتوى من تطبيقات أخرى، مثل جداول بيانات Excel، في شرائح PowerPoint.
### هل يمكنني استخدام Aspose.Slides مع لغات البرمجة الأخرى؟
نعم، يدعم Aspose.Slides العديد من اللغات بما في ذلك .NET وPython وC++.
### هل أحتاج إلى Aspose.Cells لتعديل كائنات OLE في PowerPoint؟
نعم، إذا كان كائن OLE عبارة عن جدول بيانات Excel، فستحتاج إلى Aspose.Cells لتعديله.
### هل هناك نسخة تجريبية من Aspose.Slides؟
 نعم يمكنك الحصول على[تجربة مجانية](https://releases.aspose.com/) لاختبار ميزات Aspose.Slides.
### أين يمكنني العثور على الوثائق الخاصة بـ Aspose.Slides؟
 يمكنك العثور على وثائق مفصلة عن[صفحة وثائق Aspose.Slides](https://reference.aspose.com/slides/java/).