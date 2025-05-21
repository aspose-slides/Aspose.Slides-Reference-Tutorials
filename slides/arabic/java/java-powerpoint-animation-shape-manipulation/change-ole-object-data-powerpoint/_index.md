---
"description": "تعرّف على كيفية تغيير بيانات كائنات OLE في PowerPoint باستخدام Aspose.Slides لـ Java. دليل خطوة بخطوة لتحديثات فعّالة وسهلة."
"linktitle": "تغيير بيانات كائن OLE في PowerPoint"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "تغيير بيانات كائن OLE في PowerPoint"
"url": "/ar/java/java-powerpoint-animation-shape-manipulation/change-ole-object-data-powerpoint/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تغيير بيانات كائن OLE في PowerPoint

## مقدمة
يُعد تغيير بيانات كائنات OLE في عروض PowerPoint التقديمية أمرًا بالغ الأهمية عند الحاجة إلى تحديث المحتوى المضمّن دون الحاجة إلى تحرير كل شريحة يدويًا. سيرشدك هذا الدليل الشامل خلال العملية باستخدام Aspose.Slides for Java، وهي مكتبة فعّالة مُصممة للتعامل مع عروض PowerPoint التقديمية. سواء كنت مطورًا محترفًا أو مبتدئًا، ستجد هذا البرنامج التعليمي مفيدًا وسهل المتابعة.
## المتطلبات الأساسية
قبل أن نتعمق في الكود، دعنا نتأكد من أن لديك كل ما تحتاجه للبدء.
1. مجموعة تطوير جافا (JDK): تأكد من تثبيت JDK على نظامك. يمكنك تنزيله من [موقع أوراكل](https://www.oracle.com/java/technologies/javase-downloads.html).
2. Aspose.Slides لـ Java: قم بتنزيل أحدث إصدار من [صفحة تنزيل Aspose.Slides](https://releases.aspose.com/slides/java/).
3. بيئة التطوير المتكاملة (IDE): يمكنك استخدام أي بيئة تطوير متكاملة لـ Java مثل IntelliJ IDEA، أو Eclipse، أو NetBeans.
4. Aspose.Cells لجافا: هذا مطلوب لتعديل البيانات المضمنة في كائن OLE. نزّله من [صفحة تنزيل Aspose.Cells](https://releases.aspose.com/cells/java/).
5. ملف العرض التقديمي: جهّز ملف PowerPoint مع كائن OLE مُضمّن. في هذا البرنامج التعليمي، دعنا نسميه `ChangeOLEObjectData.pptx`.
## استيراد الحزم
أولاً، دعنا نستورد الحزم الضرورية في مشروع Java الخاص بك.
```java
import com.aspose.cells.OoxmlSaveOptions;
import com.aspose.cells.Workbook;
import com.aspose.slides.*;

import java.io.ByteArrayInputStream;
import java.io.ByteArrayOutputStream;
```

الآن، دعونا نقسم العملية إلى خطوات بسيطة وقابلة للإدارة.
## الخطوة 1: تحميل عرض PowerPoint
للبدء، تحتاج إلى تحميل عرض PowerPoint الذي يحتوي على كائن OLE.
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
قم بالتكرار خلال الأشكال الموجودة في الشريحة لتحديد موقع كائن OLE.
```java
OleObjectFrame ole = null;
// عبور جميع الأشكال لإطار Ole
for (IShape shape : slide.getShapes()) {
    if (shape instanceof OleObjectFrame) {
        ole = (OleObjectFrame) shape;
        break;
    }
}
```
## الخطوة 4: استخراج البيانات المضمنة من كائن OLE
إذا تم العثور على كائن OLE، فاستخرج البيانات المضمنة فيه.
```java
if (ole != null) {
    ByteArrayInputStream msln = new ByteArrayInputStream(ole.getEmbeddedData().getEmbeddedFileData());
```
## الخطوة 5: تعديل البيانات المضمنة باستخدام Aspose.Cells
الآن، استخدم Aspose.Cells لقراءة البيانات المضمنة وتعديلها، والتي في هذه الحالة من المرجح أن تكون مصنف Excel.
```java
    Workbook wb = new Workbook(msln);
    // تعديل بيانات المصنف
    wb.getWorksheets().get(0).getCells().get(0, 4).putValue("E");
    wb.getWorksheets().get(0).getCells().get(1, 4).putValue(12);
    wb.getWorksheets().get(0).getCells().get(2, 4).putValue(14);
    wb.getWorksheets().get(0).getCells().get(3, 4).putValue(15);
```
## الخطوة 6: حفظ البيانات المعدلة مرة أخرى في كائن OLE
بعد إجراء التغييرات اللازمة، احفظ المصنف المعدل مرة أخرى في كائن OLE.
```java
    ByteArrayOutputStream msout = new ByteArrayOutputStream();
    OoxmlSaveOptions so1 = new OoxmlSaveOptions(SaveFormat.XLSX);
    wb.save(msout, so1);
    IOleEmbeddedDataInfo newData = new OleEmbeddedDataInfo(msout.toByteArray(), ole.getEmbeddedData().getEmbeddedFileExtension());
    ole.setEmbeddedData(newData);
```
## الخطوة 7: حفظ العرض التقديمي المحدث
أخيرًا، احفظ عرض PowerPoint المحدث.
```java
    pres.save(dataDir + "OleEdit_out.pptx", SaveFormat.Pptx);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## خاتمة
تحديث بيانات كائنات OLE في عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ Java عملية سهلة بمجرد تقسيمها إلى خطوات بسيطة. شرح هذا الدليل خطوات تحميل العرض التقديمي، والوصول إلى بيانات OLE المضمنة وتعديلها، وحفظ العرض التقديمي المُحدّث. بهذه الخطوات، يمكنك إدارة المحتوى المضمن في شرائح PowerPoint وتحديثه برمجيًا بكفاءة.
## الأسئلة الشائعة
### ما هو كائن OLE في PowerPoint؟
يسمح كائن OLE (ربط الكائنات وتضمينها) بتضمين المحتوى من تطبيقات أخرى، مثل جداول بيانات Excel، في شرائح PowerPoint.
### هل يمكنني استخدام Aspose.Slides مع لغات برمجة أخرى؟
نعم، يدعم Aspose.Slides العديد من اللغات بما في ذلك .NET، وPython، وC++.
### هل أحتاج إلى Aspose.Cells لتعديل كائنات OLE في PowerPoint؟
نعم، إذا كان كائن OLE عبارة عن جدول بيانات Excel، فستحتاج إلى Aspose.Cells لتعديله.
### هل هناك نسخة تجريبية من Aspose.Slides؟
نعم يمكنك الحصول على [نسخة تجريبية مجانية](https://releases.aspose.com/) لاختبار ميزات Aspose.Slides.
### أين يمكنني العثور على الوثائق الخاصة بـ Aspose.Slides؟
يمكنك العثور على وثائق مفصلة على [صفحة توثيق Aspose.Slides](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}