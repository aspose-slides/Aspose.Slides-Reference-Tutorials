---
title: ClsId الدليل الجذر في شرائح جافا
linktitle: ClsId الدليل الجذر في شرائح جافا
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية تعيين Root Directory ClsId في Aspose.Slides لعروض Java التقديمية. تخصيص سلوك الارتباط التشعبي باستخدام CLSID.
type: docs
weight: 10
url: /ar/java/media-controls/root-directory-clsid-in-java-slides/
---

## مقدمة لإعداد ClsId للدليل الجذري في Aspose.Slides لـ Java

في Aspose.Slides for Java، يمكنك تعيين Root Directory ClsId، وهو CLSID (معرف الفئة) المستخدم لتحديد التطبيق الذي سيتم استخدامه كدليل جذر عند تنشيط ارتباط تشعبي في العرض التقديمي الخاص بك. في هذا الدليل، سنرشدك إلى كيفية القيام بذلك خطوة بخطوة.

## المتطلبات الأساسية

قبل البدء، تأكد من توفر المتطلبات الأساسية التالية:

- تم تثبيت Java Development Kit (JDK) على نظامك.
-  تمت إضافة مكتبة Aspose.Slides لـ Java إلى مشروعك. يمكنك تنزيله من[Aspose.Slides لتوثيق جافا](https://reference.aspose.com/slides/java/).
- تم إعداد محرر التعليمات البرمجية أو بيئة التطوير المتكاملة (IDE) لتطوير Java.

## الخطوة 1: إنشاء عرض تقديمي جديد

أولاً، لنقم بإنشاء عرض تقديمي جديد باستخدام Aspose.Slides لـ Java. في هذا المثال، سنقوم بإنشاء عرض تقديمي فارغ.

```java
// ضع اسم الملف
String resultPath = "your_output_path/pres.ppt"; // استبدل "your_output_path" بدليل الإخراج المطلوب.
Presentation pres = new Presentation();
```

في الكود أعلاه، نحدد المسار لملف العرض التقديمي الناتج وننشئ ملفًا جديدًا`Presentation` هدف.

## الخطوة 2: قم بتعيين ClsId للدليل الجذر

 لتعيين معرف الجذر ClsId، تحتاج إلى إنشاء مثيل لـ`PptOptions` وقم بتعيين CLSID المطلوب. يمثل CLSID التطبيق الذي سيتم استخدامه كدليل جذر عند تنشيط الارتباط التشعبي.

```java
PptOptions pptOptions = new PptOptions();
// اضبط CLSID على "Microsoft Powerpoint.Show.8"
pptOptions.setRootDirectoryClsid(UUID.fromString("64818D10-4F9B-11CF-86EA-00AA00B929E8"));
```

 في الكود أعلاه، نقوم بإنشاء`PptOptions` الكائن وقم بتعيين CLSID على "Microsoft Powerpoint.Show.8". يمكنك استبداله بـ CLSID الخاص بالتطبيق الذي تريد استخدامه كدليل جذر.

## الخطوة 3: احفظ العرض التقديمي

الآن، لنحفظ العرض التقديمي باستخدام مجموعة Root Directory ClsId.

```java
// حفظ العرض التقديمي
pres.save(resultPath, SaveFormat.Ppt, pptOptions);
```

 في هذه الخطوة نقوم بحفظ العرض التقديمي في المكان المحدد`resultPath` مع ال`PptOptions` أنشأنا في وقت سابق.

## الخطوة 4: التنظيف

 لا تنسى التخلص من`Presentation` الاعتراض على تحرير أي موارد مخصصة.

```java
if (pres != null) {
    pres.dispose();
}
```

## أكمل كود المصدر لدليل الجذر ClsId في شرائح Java

```java
// ضع اسم الملف
String resultPath = "Your Output Directory" + "pres.ppt";
Presentation pres = new Presentation();
try {
	PptOptions pptOptions = new PptOptions();
	//اضبط CLSID على "Microsoft Powerpoint.Show.8"
	pptOptions.setRootDirectoryClsid(UUID.fromString("64818D10-4F9B-11CF-86EA-00AA00B929E8"));
	// حفظ العرض التقديمي
	pres.save(resultPath, SaveFormat.Ppt, pptOptions);
} finally {
	if (pres != null) pres.dispose();
}
```

## خاتمة

لقد قمت بتعيين Root Directory ClsId بنجاح في Aspose.Slides لـ Java. يتيح لك هذا تحديد التطبيق الذي سيتم استخدامه كدليل جذر عند تنشيط الارتباطات التشعبية في العرض التقديمي الخاص بك. يمكنك تخصيص CLSID وفقًا لمتطلباتك المحددة.

## الأسئلة الشائعة

### كيف يمكنني العثور على CLSID لتطبيق معين؟

للعثور على CLSID لتطبيق معين، يمكنك الرجوع إلى الوثائق أو الموارد التي يوفرها مطور التطبيق. معرفات CLSID هي معرفات فريدة يتم تعيينها لكائنات COM وتكون عادةً خاصة بكل تطبيق.

### هل يمكنني تعيين CLSID مخصص للدليل الجذر؟

 نعم، يمكنك تعيين CLSID مخصص للدليل الجذر عن طريق تحديد قيمة CLSID المطلوبة باستخدام`setRootDirectoryClsid` الطريقة كما هو موضح في مثال الكود يتيح لك هذا استخدام تطبيق معين كدليل جذر عند تنشيط الارتباطات التشعبية في العرض التقديمي الخاص بك.

### ماذا يحدث إذا لم أقم بتعيين معرف الجذر ClsId؟

إذا لم تقم بتعيين Root Directory ClsId، فسيعتمد السلوك الافتراضي على العارض أو التطبيق المستخدم لفتح العرض التقديمي. وقد يستخدم التطبيق الافتراضي الخاص به كدليل جذر عند تنشيط الارتباطات التشعبية.

### هل يمكنني تغيير Root Directory ClsId للارتباطات التشعبية الفردية؟

لا، عادةً ما يتم تعيين Root Directory ClsId على مستوى العرض التقديمي وينطبق على كافة الارتباطات التشعبية داخل العرض التقديمي. إذا كنت بحاجة إلى تحديد تطبيقات مختلفة للارتباطات التشعبية الفردية، فقد تحتاج إلى التعامل مع هذه الارتباطات التشعبية بشكل منفصل في التعليمات البرمجية الخاصة بك.

### هل هناك أي قيود على معرفات CLSID التي يمكنني استخدامها؟

عادةً ما يتم تحديد معرفات CLSID التي يمكنك استخدامها من خلال التطبيقات المثبتة على النظام. يجب عليك استخدام معرفات CLSID التي تتوافق مع التطبيقات الصالحة القادرة على التعامل مع الارتباطات التشعبية. انتبه إلى أن استخدام CLSID غير صالح قد يؤدي إلى سلوك غير متوقع.