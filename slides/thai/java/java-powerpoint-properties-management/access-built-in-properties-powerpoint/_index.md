---
title: เข้าถึงคุณสมบัติในตัวใน PowerPoint
linktitle: เข้าถึงคุณสมบัติในตัวใน PowerPoint
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีการเข้าถึงคุณสมบัติในตัวใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java บทช่วยสอนนี้จะแนะนำคุณในการเรียกข้อมูลผู้เขียน วันที่สร้าง และอื่นๆ
weight: 10
url: /th/java/java-powerpoint-properties-management/access-built-in-properties-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เข้าถึงคุณสมบัติในตัวใน PowerPoint

## การแนะนำ
ในบทช่วยสอนนี้ เราจะสำรวจวิธีการเข้าถึงคุณสมบัติในตัวในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java Aspose.Slides เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนา Java สามารถทำงานกับงานนำเสนอ PowerPoint โดยทางโปรแกรม ช่วยให้งานต่างๆ เช่น การอ่านและการแก้ไขคุณสมบัติเป็นไปอย่างราบรื่น
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1.  Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK บนระบบของคุณ คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides สำหรับ Java: ดาวน์โหลดและติดตั้ง Aspose.Slides สำหรับ Java จาก[ลิงค์นี้](https://releases.aspose.com/slides/java/).

## แพ็คเกจนำเข้า
ขั้นแรก คุณต้องนำเข้าแพ็คเกจที่จำเป็นไปยังโปรเจ็กต์ Java ของคุณ เพิ่มคำสั่งนำเข้าต่อไปนี้ที่จุดเริ่มต้นของไฟล์ Java ของคุณ:
```java
import com.aspose.slides.IDocumentProperties;
import com.aspose.slides.Presentation;

```
## ขั้นตอนที่ 1: ตั้งค่าวัตถุการนำเสนอ
เริ่มต้นด้วยการตั้งค่าวัตถุการนำเสนอเพื่อแสดงงานนำเสนอ PowerPoint ที่คุณต้องการใช้งาน ต่อไปนี้คือวิธีที่คุณสามารถทำได้:
```java
// พาธไปยังไดเร็กทอรีที่มีไฟล์การนำเสนอ
String dataDir = "path_to_your_presentation_directory/";
// สร้างอินสแตนซ์ของคลาสการนำเสนอ
Presentation pres = new Presentation(dataDir + "your_presentation_file.pptx");
```
## ขั้นตอนที่ 2: เข้าถึงคุณสมบัติเอกสาร
หลังจากตั้งค่าออบเจ็กต์การนำเสนอ คุณสามารถเข้าถึงคุณสมบัติในตัวของงานนำเสนอได้โดยใช้อินเทอร์เฟซ IDocumentProperties ต่อไปนี้คือวิธีที่คุณสามารถเรียกข้อมูลคุณสมบัติต่างๆ:
### หมวดหมู่
```java
System.out.println("Category : " + documentProperties.getCategory());
```
### สถานะปัจจุบัน
```java
System.out.println("Current Status : " + documentProperties.getContentStatus());
```
### วันที่สร้าง
```java
System.out.println("Creation Date : " + documentProperties.getCreatedTime());
```
### ผู้เขียน
```java
System.out.println("Author : " + documentProperties.getAuthor());
```
### คำอธิบาย
```java
System.out.println("Description : " + documentProperties.getComments());
```
### คำหลัก
```java
System.out.println("KeyWords : " + documentProperties.getKeywords());
```
### แก้ไขล่าสุดโดย
```java
System.out.println("Last Modified By : " + documentProperties.getLastSavedBy());
```
### หัวหน้างาน
```java
System.out.println("Supervisor : " + documentProperties.getManager());
```
### วันที่แก้ไข
```java
System.out.println("Modified Date : " + documentProperties.getLastSavedTime());
```
#### รูปแบบการนำเสนอ
```java
System.out.println("Presentation Format : " + documentProperties.getPresentationFormat());
```
### วันที่พิมพ์ครั้งล่าสุด
```java
System.out.println("Last Print Date : " + documentProperties.getLastPrinted());
```
### แบ่งปันระหว่างผู้ผลิต
```java
System.out.println("Is Shared between producers : " + documentProperties.getSharedDoc());
```
### เรื่อง
```java
System.out.println("Subject : " + documentProperties.getSubject());
```
### ชื่อ
```java
System.out.println("Title : " + documentProperties.getTitle());
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีการเข้าถึงคุณสมบัติในตัวในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ด้วยการทำตามขั้นตอนที่สรุปไว้ข้างต้น คุณสามารถดึงข้อมูลคุณสมบัติต่างๆ เช่น ผู้แต่ง วันที่สร้าง และชื่อโดยทางโปรแกรมได้อย่างง่ายดาย
## คำถามที่พบบ่อย
### ฉันสามารถแก้ไขคุณสมบัติในตัวเหล่านี้โดยใช้ Aspose.Slides สำหรับ Java ได้หรือไม่
ใช่ คุณสามารถแก้ไขคุณสมบัติเหล่านี้ได้โดยใช้ Aspose.Slides เพียงใช้วิธีการตั้งค่าที่เหมาะสมที่ได้รับจากอินเทอร์เฟซ IDocumentProperties
### Aspose.Slides เข้ากันได้กับ PowerPoint เวอร์ชันต่างๆ หรือไม่
Aspose.Slides รองรับ PowerPoint เวอร์ชันต่างๆ มากมาย ทำให้มั่นใจได้ถึงความเข้ากันได้บนแพลตฟอร์มต่างๆ
### ฉันสามารถดึงข้อมูลคุณสมบัติแบบกำหนดเองได้หรือไม่
ใช่ นอกจากคุณสมบัติในตัวแล้ว คุณยังสามารถดึงข้อมูลและแก้ไขคุณสมบัติแบบกำหนดเองโดยใช้ Aspose.Slides สำหรับ Java ได้อีกด้วย
### Aspose.Slides มีเอกสารและการสนับสนุนหรือไม่
 ใช่ คุณสามารถค้นหาเอกสารที่ครอบคลุมและเข้าถึงฟอรัมสนับสนุนได้ที่[เว็บไซต์กำหนด](https://reference.aspose.com/slides/java/).
### มีรุ่นทดลองใช้งานสำหรับ Aspose.Slides สำหรับ Java หรือไม่
 ใช่ คุณสามารถดาวน์โหลดเวอร์ชันทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
