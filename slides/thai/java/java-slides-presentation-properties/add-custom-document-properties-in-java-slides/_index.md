---
title: เพิ่มคุณสมบัติเอกสารที่กำหนดเองใน Java Slides
linktitle: เพิ่มคุณสมบัติเอกสารที่กำหนดเองใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีปรับปรุงงานนำเสนอ PowerPoint ด้วยคุณสมบัติเอกสารที่กำหนดเองใน Java Slides คำแนะนำทีละขั้นตอนพร้อมตัวอย่างโค้ดโดยใช้ Aspose.Slides สำหรับ Java
weight: 13
url: /th/java/presentation-properties/add-custom-document-properties-in-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## ข้อมูลเบื้องต้นเกี่ยวกับการเพิ่มคุณสมบัติเอกสารที่กำหนดเองใน Java Slides

ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการเพิ่มคุณสมบัติเอกสารแบบกำหนดเองให้กับงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java คุณสมบัติเอกสารแบบกำหนดเองช่วยให้คุณสามารถจัดเก็บข้อมูลเพิ่มเติมเกี่ยวกับการนำเสนอเพื่อใช้อ้างอิงหรือจัดหมวดหมู่

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งและตั้งค่าไลบรารี Aspose.Slides สำหรับ Java ในโปรเจ็กต์ Java ของคุณแล้ว

## ขั้นตอนที่ 1: นำเข้าแพ็คเกจที่จำเป็น

```java
import com.aspose.slides.*;
```

## ขั้นตอนที่ 2: สร้างงานนำเสนอใหม่

ขั้นแรก คุณต้องสร้างวัตถุการนำเสนอใหม่ คุณสามารถทำได้ดังนี้:

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";

// สร้างอินสแตนซ์ของคลาสการนำเสนอ
Presentation presentation = new Presentation();
```

## ขั้นตอนที่ 3: รับคุณสมบัติเอกสาร

ถัดไป คุณจะดึงคุณสมบัติเอกสารของงานนำเสนอ คุณสมบัติเหล่านี้มีคุณสมบัติที่มีอยู่แล้วภายใน เช่น ชื่อเรื่อง ผู้แต่ง และคุณสมบัติแบบกำหนดเองที่คุณสามารถเพิ่มได้

```java
// รับคุณสมบัติเอกสาร
IDocumentProperties documentProperties = presentation.getDocumentProperties();
```

## ขั้นตอนที่ 4: การเพิ่มคุณสมบัติที่กำหนดเอง

ตอนนี้ เรามาเพิ่มคุณสมบัติแบบกำหนดเองให้กับงานนำเสนอกันดีกว่า คุณสมบัติแบบกำหนดเองประกอบด้วยชื่อและค่า คุณสามารถใช้มันเพื่อจัดเก็บข้อมูลใด ๆ ที่คุณต้องการ

```java
documentProperties.set_Item("New Custom", 12);
documentProperties.set_Item("My Name", "Mudassir");
documentProperties.set_Item("Custom", 124);
```

## ขั้นตอนที่ 5: รับชื่อทรัพย์สินที่ดัชนีเฉพาะ

คุณยังสามารถดึงข้อมูลชื่อของคุณสมบัติแบบกำหนดเองได้ที่ดัชนีเฉพาะ สิ่งนี้มีประโยชน์หากคุณต้องการทำงานกับคุณสมบัติเฉพาะ

```java
// รับชื่อคุณสมบัติที่ดัชนีเฉพาะ
String getPropertyName = documentProperties.getCustomPropertyName(2);
```

## ขั้นตอนที่ 6: การลบคุณสมบัติที่เลือก

หากคุณต้องการลบคุณสมบัติแบบกำหนดเอง คุณสามารถทำได้โดยระบุชื่อคุณสมบัตินั้น ที่นี่ เรากำลังลบทรัพย์สินที่เราได้รับในขั้นตอนที่ 5

```java
// กำลังลบคุณสมบัติที่เลือก
documentProperties.removeCustomProperty(getPropertyName);
```

## ขั้นตอนที่ 7: บันทึกการนำเสนอ

สุดท้าย ให้บันทึกงานนำเสนอด้วยคุณสมบัติแบบกำหนดเองที่เพิ่มและลบลงในไฟล์

```java
// กำลังบันทึกการนำเสนอ
presentation.save(dataDir + "CustomDocumentProperties_out.pptx", SaveFormat.Pptx);
```

## กรอกซอร์สโค้ดเพื่อเพิ่มคุณสมบัติเอกสารที่กำหนดเองใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างอินสแตนซ์ของคลาสการนำเสนอ
Presentation presentation = new Presentation();
// รับคุณสมบัติเอกสาร
IDocumentProperties documentProperties = presentation.getDocumentProperties();
// การเพิ่มคุณสมบัติแบบกำหนดเอง
documentProperties.set_Item("New Custom", 12);
documentProperties.set_Item("My Name", "Mudassir");
documentProperties.set_Item("Custom", 124);
// รับชื่อคุณสมบัติที่ดัชนีเฉพาะ
String getPropertyName = documentProperties.getCustomPropertyName(2);
// กำลังลบคุณสมบัติที่เลือก
documentProperties.removeCustomProperty(getPropertyName);
// กำลังบันทึกการนำเสนอ
presentation.save(dataDir + "CustomDocumentProperties_out.pptx", SaveFormat.Pptx);
```

## บทสรุป

คุณได้เรียนรู้วิธีเพิ่มคุณสมบัติเอกสารที่กำหนดเองลงในงานนำเสนอ PowerPoint ใน Java โดยใช้ Aspose.Slides คุณสมบัติแบบกำหนดเองอาจมีประโยชน์ในการจัดเก็บข้อมูลเพิ่มเติมที่เกี่ยวข้องกับการนำเสนอของคุณ คุณสามารถขยายความรู้นี้เพื่อรวมคุณสมบัติที่กำหนดเองเพิ่มเติมได้ตามความต้องการสำหรับกรณีการใช้งานเฉพาะของคุณ

## คำถามที่พบบ่อย

### ฉันจะดึงค่าของคุณสมบัติที่กำหนดเองได้อย่างไร

 หากต้องการดึงค่าของคุณสมบัติที่กำหนดเอง คุณสามารถใช้`get_Item` วิธีการบน`documentProperties` วัตถุ. ตัวอย่างเช่น:

```java
Object customPropertyValue = documentProperties.get_Item("New Custom");
```

### ฉันสามารถเพิ่มคุณสมบัติที่กำหนดเองของข้อมูลประเภทต่างๆ ได้หรือไม่

ได้ คุณสามารถเพิ่มคุณสมบัติแบบกำหนดเองของข้อมูลประเภทต่างๆ รวมถึงตัวเลข สตริง วันที่ และอื่นๆ ดังที่แสดงในตัวอย่าง Aspose.Slides สำหรับ Java จัดการข้อมูลประเภทต่างๆ ได้อย่างราบรื่น

### มีการจำกัดจำนวนคุณสมบัติแบบกำหนดเองที่ฉันสามารถเพิ่มได้หรือไม่?

ไม่มีการจำกัดจำนวนคุณสมบัติแบบกำหนดเองที่คุณสามารถเพิ่มได้ อย่างไรก็ตาม โปรดทราบว่าการเพิ่มคุณสมบัติมากเกินไปอาจส่งผลต่อประสิทธิภาพและขนาดของไฟล์งานนำเสนอของคุณ

### ฉันจะแสดงรายการคุณสมบัติแบบกำหนดเองทั้งหมดในงานนำเสนอได้อย่างไร

คุณสามารถวนซ้ำคุณสมบัติแบบกำหนดเองทั้งหมดเพื่อแสดงรายการได้ นี่คือตัวอย่างวิธีการดำเนินการนี้:

```java
for (int i = 0; i < documentProperties.getCustomCount(); i++) {
    String propertyName = documentProperties.getCustomPropertyName(i);
    Object propertyValue = documentProperties.get_Item(propertyName);
    System.out.println("Property Name: " + propertyName);
    System.out.println("Property Value: " + propertyValue);
}
```

รหัสนี้จะแสดงชื่อและค่าของคุณสมบัติที่กำหนดเองทั้งหมดในงานนำเสนอ
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
