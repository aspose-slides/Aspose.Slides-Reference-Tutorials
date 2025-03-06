---
title: ลบเค้าโครงหลักที่ไม่ได้ใช้ใน Java Slides
linktitle: ลบเค้าโครงหลักที่ไม่ได้ใช้ใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: ลบเค้าโครงต้นแบบที่ไม่ได้ใช้ด้วย Aspose.Slides คำแนะนำและรหัสทีละขั้นตอน เพิ่มประสิทธิภาพการนำเสนอ
weight: 10
url: /th/java/additional-utilities/remove-unused-layout-master-in-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## ข้อมูลเบื้องต้นเกี่ยวกับการลบเค้าโครงหลักที่ไม่ได้ใช้ใน Java Slides

หากคุณกำลังทำงานกับ Java Slides คุณอาจพบสถานการณ์ที่งานนำเสนอของคุณมีต้นแบบเค้าโครงที่ไม่ได้ใช้ องค์ประกอบที่ไม่ได้ใช้เหล่านี้อาจทำให้การนำเสนอของคุณขยายใหญ่ขึ้นและทำให้มีประสิทธิภาพน้อยลง ในบทความนี้ เราจะแนะนำคุณเกี่ยวกับวิธีลบเค้าโครงต้นแบบที่ไม่ได้ใช้เหล่านี้โดยใช้ Aspose.Slides สำหรับ Java เราจะให้คำแนะนำทีละขั้นตอนและตัวอย่างโค้ดเพื่อให้คุณบรรลุงานนี้ได้อย่างราบรื่น

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกกระบวนการลบต้นแบบเค้าโครงที่ไม่ได้ใช้ ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- [Aspose.Slides สำหรับ Java](https://downloads.aspose.com/slides/java) ติดตั้งห้องสมุดแล้ว
- โครงการ Java ตั้งค่าและพร้อมที่จะทำงานกับ Aspose.Slides

## ขั้นตอนที่ 1: โหลดงานนำเสนอของคุณ

ขั้นแรก คุณต้องโหลดงานนำเสนอของคุณโดยใช้ Aspose.Slides นี่คือข้อมูลโค้ดสำหรับดำเนินการดังกล่าว:

```java
String pptxFileName = "YourPresentation.pptx";
Presentation pres = new Presentation(pptxFileName);
```

 แทนที่`"YourPresentation.pptx"` พร้อมเส้นทางไปยังไฟล์ PowerPoint ของคุณ

## ขั้นตอนที่ 2: ระบุผู้เชี่ยวชาญที่ไม่ได้ใช้

ก่อนที่จะลบต้นแบบเค้าโครงที่ไม่ได้ใช้ จำเป็นต้องระบุก่อน คุณสามารถทำได้โดยการตรวจสอบจำนวนสไลด์ต้นแบบในงานนำเสนอของคุณ ใช้รหัสต่อไปนี้เพื่อกำหนดจำนวนสไลด์หลัก:

```java
System.out.println("Master slides number in source presentation = " + pres.getMasters().size());
```

รหัสนี้จะพิมพ์จำนวนสไลด์หลักในงานนำเสนอของคุณ

## ขั้นตอนที่ 3: ลบ Masters ที่ไม่ได้ใช้

ตอนนี้ เรามาเอาสไลด์ต้นแบบที่ไม่ได้ใช้ออกจากงานนำเสนอของคุณกัน Aspose.Slides มีวิธีการที่ตรงไปตรงมาเพื่อให้บรรลุเป้าหมายนี้ ต่อไปนี้คือวิธีที่คุณสามารถทำได้:

```java
Compress.removeUnusedMasterSlides(pres);
```

ข้อมูลโค้ดนี้จะลบสไลด์ต้นแบบที่ไม่ได้ใช้ออกจากงานนำเสนอของคุณ

## ขั้นตอนที่ 4: ระบุสไลด์เค้าโครงที่ไม่ได้ใช้

ในทำนองเดียวกัน คุณควรตรวจสอบจำนวนสไลด์เค้าโครงในงานนำเสนอของคุณเพื่อระบุสไลด์ที่ไม่ได้ใช้:

```java
System.out.println("Layout slides number in source presentation = " + pres.getLayoutSlides().size());
```

รหัสนี้จะพิมพ์จำนวนสไลด์เค้าโครงในงานนำเสนอของคุณ

## ขั้นตอนที่ 5: ลบสไลด์เค้าโครงที่ไม่ได้ใช้

ลบสไลด์เค้าโครงที่ไม่ได้ใช้โดยใช้รหัสต่อไปนี้:

```java
Compress.removeUnusedLayoutSlides(pres);
```

รหัสนี้จะลบสไลด์เค้าโครงที่ไม่ได้ใช้ออกจากงานนำเสนอของคุณ

## ขั้นตอนที่ 6: ตรวจสอบผลลัพธ์

หลังจากลบต้นแบบและสไลด์เค้าโครงที่ไม่ได้ใช้ออกแล้ว คุณสามารถตรวจสอบการนับอีกครั้งเพื่อให้แน่ใจว่าได้ลบออกเรียบร้อยแล้ว:

```java
System.out.println("Master slides number in result presentation = " + pres.getMasters().size());
System.out.println("Layout slides number in result presentation = " + pres.getLayoutSlides().size());
```

รหัสนี้จะพิมพ์จำนวนที่อัปเดตในงานนำเสนอของคุณ ซึ่งแสดงว่าองค์ประกอบที่ไม่ได้ใช้ถูกลบออกไปแล้ว

## กรอกซอร์สโค้ดเพื่อลบเค้าโครงหลักที่ไม่ได้ใช้ใน Java Slides

```java
        String pptxFileName = "Your Document Directory";
        Presentation pres = new Presentation(pptxFileName);
        try {
            System.out.println("Master slides number in source presentation = " + pres.getMasters().size());
            System.out.println("Layout slides number in source presentation = " + pres.getLayoutSlides().size());
            Compress.removeUnusedMasterSlides(pres);
            Compress.removeUnusedLayoutSlides(pres);
            System.out.println("Master slides number in result presentation = " + pres.getMasters().size());
            System.out.println("Layout slides number in result presentation = " + pres.getLayoutSlides().size());
        } finally {
            if (pres != null) pres.dispose();
        }
```

## บทสรุป

ในบทความนี้ เราได้แนะนำคุณตลอดขั้นตอนการลบต้นแบบเค้าโครงและสไลด์เค้าโครงที่ไม่ได้ใช้ใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java นี่เป็นขั้นตอนสำคัญในการเพิ่มประสิทธิภาพการนำเสนอ ลดขนาดไฟล์ และปรับปรุงประสิทธิภาพ ด้วยการทำตามขั้นตอนง่ายๆ เหล่านี้และการใช้ตัวอย่างโค้ดที่ให้มา คุณสามารถล้างข้อมูลการนำเสนอของคุณได้อย่างมีประสิทธิภาพ

## คำถามที่พบบ่อย

### ฉันจะติดตั้ง Aspose.Slides สำหรับ Java ได้อย่างไร

 Aspose.Slides สำหรับ Java สามารถติดตั้งได้โดยการดาวน์โหลดไลบรารีจาก[เว็บไซต์กำหนด](https://downloads.aspose.com/slides/java)- ปฏิบัติตามคำแนะนำในการติดตั้งที่ให้ไว้เพื่อตั้งค่าไลบรารีในโปรเจ็กต์ Java ของคุณ

### มีข้อกำหนดสิทธิ์การใช้งานสำหรับการใช้ Aspose.Slides สำหรับ Java หรือไม่

ใช่ Aspose.Slides สำหรับ Java เป็นไลบรารีเชิงพาณิชย์ และคุณต้องได้รับใบอนุญาตที่ถูกต้องเพื่อใช้ในโปรเจ็กต์ของคุณ คุณสามารถรับข้อมูลเพิ่มเติมเกี่ยวกับการออกใบอนุญาตได้จากเว็บไซต์ Aspose

### ฉันสามารถลบเค้าโครงต้นแบบโดยทางโปรแกรมเพื่อเพิ่มประสิทธิภาพการนำเสนอของฉันได้หรือไม่

ได้ คุณสามารถลบเค้าโครงต้นแบบโดยทางโปรแกรมได้โดยใช้ Aspose.Slides สำหรับ Java ดังแสดงในบทความนี้ เป็นเทคนิคที่มีประโยชน์ในการเพิ่มประสิทธิภาพการนำเสนอและลดขนาดไฟล์

### การลบต้นแบบเค้าโครงที่ไม่ได้ใช้จะส่งผลต่อการจัดรูปแบบของสไลด์ของฉันหรือไม่

ไม่ การลบต้นแบบเค้าโครงที่ไม่ได้ใช้ออกจะไม่ส่งผลต่อการจัดรูปแบบของสไลด์ของคุณ โดยจะลบเฉพาะองค์ประกอบที่ไม่ได้ใช้ เพื่อให้มั่นใจว่างานนำเสนอของคุณยังคงสภาพเดิมและคงรูปแบบดั้งเดิมไว้

### ฉันจะเข้าถึงซอร์สโค้ดที่ใช้ในบทความนี้ได้ที่ไหน

คุณสามารถค้นหาซอร์สโค้ดที่ใช้ในบทความนี้ได้ภายในข้อมูลโค้ดที่ให้ไว้ในแต่ละขั้นตอน เพียงคัดลอกและวางโค้ดลงในโปรเจ็กต์ Java ของคุณเพื่อดำเนินการลบเค้าโครงหลักที่ไม่ได้ใช้ในงานนำเสนอของคุณ
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
