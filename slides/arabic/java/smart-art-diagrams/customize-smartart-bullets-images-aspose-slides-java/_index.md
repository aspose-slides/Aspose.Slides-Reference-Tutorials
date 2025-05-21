---
"date": "2025-04-18"
"description": "تعرّف على كيفية تحسين عروضك التقديمية بتخصيص نقاط SmartArt بالصور باستخدام Aspose.Slides لجافا. اتبع هذا الدليل خطوة بخطوة للحصول على مظهر احترافي."
"title": "كيفية تخصيص نقاط SmartArt بالصور باستخدام Aspose.Slides لجافا | دليل خطوة بخطوة"
"url": "/ar/java/smart-art-diagrams/customize-smartart-bullets-images-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية تخصيص نقاط SmartArt بالصور باستخدام Aspose.Slides لـ Java

## مقدمة

يُعد إنشاء عروض تقديمية جذابة بصريًا أمرًا بالغ الأهمية لجذب انتباه جمهورك وإيصال رسالتك بفعالية. ومن التحديات الشائعة في تصميم الشرائح تحسين النقاط في رسومات SmartArt باستخدام صور مخصصة. سيرشدك هذا البرنامج التعليمي إلى كيفية تعيين صورة كتنسيق ملء النقاط في عُقد SmartArt باستخدام Aspose.Slides لجافا، مما يُمكّنك من الارتقاء بعروضك التقديمية بشكل احترافي.

**ما سوف تتعلمه:**
- إعداد Aspose.Slides واستخدامه لـ Java
- تخصيص النقاط باستخدام الصور في رسومات SmartArt
- التطبيقات العملية لهذا التخصيص
- استكشاف الأخطاء وإصلاحها الشائعة

قبل أن نبدأ في التنفيذ، تأكد من أن كل شيء جاهز.

## المتطلبات الأساسية

لمتابعة هذا البرنامج التعليمي، تأكد من تلبية المتطلبات الأساسية التالية:

1. **المكتبات والتبعيات**:ستحتاج إلى Aspose.Slides لمكتبة Java الإصدار 25.4 أو أحدث.
2. **إعداد البيئة**:
   - بيئة تطوير متكاملة متوافقة مثل IntelliJ IDEA أو Eclipse
   - JDK 16 مثبت على جهازك
3. **متطلبات المعرفة**:المعرفة ببرمجة Java وبنية العرض التقديمي الأساسية في PowerPoint.

## إعداد Aspose.Slides لـ Java

للبدء، قم بتضمين مكتبة Aspose.Slides في مشروعك باستخدام إحدى الطرق التالية:

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

قم بتضمين هذا في `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### التحميل المباشر

بدلاً من ذلك، قم بتنزيل المكتبة مباشرة من [إصدارات Aspose.Slides لـ Java](https://releases.aspose.com/slides/java/).

**خطوات الحصول على الترخيص**يقدم Aspose ترخيصًا تجريبيًا مجانيًا مثاليًا لاختبار ميزاته. يمكنك طلب ترخيص مؤقت أو شراء ترخيص لإزالة قيود التقييم.

لتهيئة بيئتك وإعدادها، قم بإنشاء مثيل لـ `Presentation` الصف كما هو موضح:

```java
Presentation presentation = new Presentation();
```

## دليل التنفيذ

سيقوم هذا القسم بتقسيم العملية إلى خطوات قابلة للإدارة، ويشرح كيفية تحقيق الوظيفة المطلوبة.

### إضافة SmartArt مع تعبئة نقطية مخصصة

#### ملخص

سنبدأ بإضافة شكل SmartArt إلى الشريحة الخاصة بك وتخصيص نقاطه باستخدام تعبئة الصورة.

#### تعليمات خطوة بخطوة

**1. تهيئة كائن العرض التقديمي**

```java
Presentation presentation = new Presentation();
```

*غاية*:يقوم بتهيئة مثيل عرض تقديمي جديد حيث ستضيف رسومات SmartArt.

**2. إضافة شكل SmartArt**

```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 500, 400, SmartArtLayoutType.VerticalPictureList);
```

*توضيح*يضيف هذا الخط شكل SmartArt جديدًا إلى الشريحة الأولى في الموضع (x=10، y=10) بأبعاد 500×400 بكسل. `VerticalPictureList` يتم استخدام التخطيط للمحاذاة الرأسية.

**3. الوصول إلى تعبئة النقاط وتخصيصها**

```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);

if (node.getBulletFillFormat() != null) {
    IImage img = Images.fromFile("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg");
    IPPImage image = presentation.getImages().addImage(img);
    
    node.getBulletFillFormat().setFillType(FillType.Picture);
    node.getBulletFillFormat().getPictureFillFormat().getPicture().setImage(image);
    node.getBulletFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Stretch);
}
```

*غاية*:يتحقق مما إذا كانت العقدة تحتوي على `BulletFillFormat` إذا كان الأمر كذلك، فسيتم تحميل صورة وتعيينها كملء للنقاط.
*حدود*:
  - `"YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg"`:المسار إلى ملف صورتك.
  - `PictureFillMode.Stretch`:يضمن أن الصورة تملأ منطقة الرصاصة بالكامل.

**4. احفظ عرضك التقديمي**

```java
presentation.save("YOUR_OUTPUT_DIRECTORY/out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}