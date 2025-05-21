---
"date": "2025-04-18"
"description": "تعرّف على كيفية إضافة وتكوين وحدات ماكرو VBA في عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ Java. بسّط مهام عملك مع إنشاء الشرائح تلقائيًا."
"title": "تضمين وحدات الماكرو VBA في PowerPoint باستخدام Aspose.Slides لـ Java"
"url": "/ar/java/vba-macros-automation/embed-vba-macros-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# تضمين وحدات الماكرو VBA في PowerPoint باستخدام Aspose.Slides لـ Java

في بيئة الأعمال المتسارعة اليوم، يُمكن لأتمتة المهام المتكررة أن تُحسّن الإنتاجية بشكل كبير وتوفر الوقت. إحدى الطرق الفعّالة لتحقيق ذلك هي تضمين وحدات ماكرو Visual Basic for Applications (VBA) في شرائح PowerPoint باستخدام Aspose.Slides لـ Java. سيرشدك هذا البرنامج التعليمي خلال عملية إنشاء كائن عرض تقديمي، وإضافة مشاريع VBA، وتكوينها بالمراجع اللازمة، وحفظ العرض التقديمي النهائي المُفعّل بوحدات الماكرو بتنسيق PPTM.

## ما سوف تتعلمه
- **إنشاء مثيل وبدء التشغيل** عرض تقديمي باستخدام Aspose.Slides لـ Java
- إنشاء وتكوين **مشروع VBA** ضمن العرض التقديمي الخاص بك
- أضف ما يلزم **مراجع** لضمان تشغيل وحدات الماكرو VBA بسلاسة
- احفظ العرض التقديمي الخاص بك كملف **ملف PPTM الممكّن للماكرو**

قبل أن نبدأ، دعونا نغطي المتطلبات الأساسية.

## المتطلبات الأساسية

تأكد من أن لديك:
- **Aspose.Slides لمكتبة Java**:الإصدار 25.4 أو أحدث.
- **بيئة تطوير جافا**:يوصى باستخدام JDK 16.
- **المعرفة الأساسية بلغة جافا**:المعرفة بقواعد اللغة Java ومفاهيم البرمجة.

## إعداد Aspose.Slides لـ Java

لاستخدام Aspose.Slides في مشروعك، اتبع تعليمات التثبيت التالية:

### مافن
أضف هذه التبعية إلى `pom.xml` ملف:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
### جرادل
قم بتضمين هذا في `build.gradle` ملف:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
### التحميل المباشر
بدلاً من ذلك، قم بتنزيل الإصدار الأحدث مباشرةً من [إصدارات Aspose.Slides لـ Java](https://releases.aspose.com/slides/java/).

#### الحصول على الترخيص
للاستفادة الكاملة من إمكانيات Aspose.Slides:
- **نسخة تجريبية مجانية**:استكشف الميزات من خلال الإصدار التجريبي المجاني.
- **رخصة مؤقتة**:الحصول على ترخيص مؤقت للاختبار الموسع.
- **شراء**:شراء ترخيص كامل للاستخدام الإنتاجي.

#### التهيئة الأساسية
قم بتهيئة Aspose.Slides في تطبيق Java الخاص بك على النحو التالي:
```java
import com.aspose.slides.Presentation;

Presentation presentation = new Presentation();
try {
    // الكود الخاص بك هنا
} finally {
    if (presentation != null) presentation.dispose();
}
```

## دليل التنفيذ

دعونا نقوم بتقسيم عملية إضافة وحدات الماكرو VBA إلى خطوات قابلة للإدارة.

### الميزة 1: إنشاء العرض التقديمي وتهيئته
إنشاء `Presentation` الكائن كأساس لعمليات الشريحة أو الماكرو:
```java
import com.aspose.slides.Presentation;

// إنشاء مثيل عرض تقديمي جديد
Presentation presentation = new Presentation();
try {
    // العمليات على العرض التقديمي تذهب هنا
} finally {
    if (presentation != null) presentation.dispose();  // ضمان تحرير الموارد
}
```
### الميزة 2: إنشاء مشروع VBA وتكوينه
إعداد مشروع VBA داخل `Presentation` هدف:
```java
import com.aspose.slides.*;

// قم بتهيئة مشروع VBA\presentation.setVbaProject(new VbaProject());
IVbaModule module = presentation.getVbaProject().getModules().addEmptyModule("Module");

// إضافة كود المصدر للماكرو
module.setSourceCode("Sub Test(oShape As Shape) MsgBox \"Test\" End Sub");
```
### الميزة 3: إضافة مراجع إلى مشروع VBA
إن إضافة المراجع تضمن وصول وحدات الماكرو إلى المكتبات الضرورية:
```java
import com.aspose.slides.*;

// تعريف وإضافة مرجع مكتبة نوع OLE القياسي
VbaReferenceOleTypeLib stdoleReference = new VbaReferenceOleTypeLib(
        "stdole\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}