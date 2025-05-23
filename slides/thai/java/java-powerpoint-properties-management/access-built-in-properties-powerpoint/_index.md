---
"description": "เรียนรู้วิธีการเข้าถึงคุณสมบัติในตัวใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java บทช่วยสอนนี้จะแนะนำคุณเกี่ยวกับการดึงข้อมูลชื่อผู้เขียน วันที่สร้าง และอื่นๆ"
"linktitle": "เข้าถึงคุณสมบัติในตัวของ PowerPoint"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "เข้าถึงคุณสมบัติในตัวของ PowerPoint"
"url": "/th/java/java-powerpoint-properties-management/access-built-in-properties-powerpoint/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# เข้าถึงคุณสมบัติในตัวของ PowerPoint

## การแนะนำ
ในบทช่วยสอนนี้ เราจะมาเรียนรู้วิธีการเข้าถึงคุณสมบัติในตัวของงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java Aspose.Slides เป็นไลบรารีอันทรงพลังที่ช่วยให้ผู้พัฒนา Java สามารถทำงานกับงานนำเสนอ PowerPoint ได้ด้วยโปรแกรม ซึ่งช่วยให้สามารถทำงานต่างๆ เช่น การอ่านและแก้ไขคุณสมบัติได้อย่างราบรื่น
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม โปรดตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1. Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK ไว้ในระบบของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://www-oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Slides สำหรับ Java: ดาวน์โหลดและติดตั้ง Aspose.Slides สำหรับ Java จาก [ลิงค์นี้](https://releases-aspose.com/slides/java/).

## แพ็คเกจนำเข้า
ขั้นแรก คุณต้องนำเข้าแพ็กเกจที่จำเป็นไปยังโปรเจ็กต์ Java ของคุณ เพิ่มคำสั่งนำเข้าต่อไปนี้ที่จุดเริ่มต้นของไฟล์ Java ของคุณ:
```java
import com.aspose.slides.IDocumentProperties;
import com.aspose.slides.Presentation;

```
## ขั้นตอนที่ 1: ตั้งค่าวัตถุการนำเสนอ
เริ่มต้นด้วยการตั้งค่าวัตถุการนำเสนอเพื่อแสดงการนำเสนอ PowerPoint ที่คุณต้องการใช้งาน นี่คือวิธีที่คุณสามารถทำได้:
```java
// เส้นทางไปยังไดเรกทอรีที่มีไฟล์นำเสนอ
String dataDir = "path_to_your_presentation_directory/";
// สร้างอินสแตนซ์คลาสการนำเสนอ
Presentation pres = new Presentation(dataDir + "your_presentation_file.pptx");
```
## ขั้นตอนที่ 2: เข้าถึงคุณสมบัติของเอกสาร
หลังจากตั้งค่าวัตถุการนำเสนอแล้ว คุณสามารถเข้าถึงคุณสมบัติในตัวของการนำเสนอได้โดยใช้อินเทอร์เฟซ IDocumentProperties นี่คือวิธีที่คุณสามารถดึงคุณสมบัติต่างๆ ได้:
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
### คำสำคัญ
```java
System.out.println("KeyWords : " + documentProperties.getKeywords());
```
### ปรับปรุงล่าสุดโดย
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
### วันที่พิมพ์ล่าสุด
```java
System.out.println("Last Print Date : " + documentProperties.getLastPrinted());
```
### ร่วมกันระหว่างผู้ผลิต
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
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีการเข้าถึงคุณสมบัติในตัวในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java เมื่อทำตามขั้นตอนที่ระบุไว้ข้างต้นแล้ว คุณจะสามารถเรียกค้นคุณสมบัติต่างๆ เช่น ผู้เขียน วันที่สร้าง และชื่อเรื่องได้อย่างง่ายดายด้วยโปรแกรม
## คำถามที่พบบ่อย
### ฉันสามารถปรับเปลี่ยนคุณสมบัติในตัวเหล่านี้โดยใช้ Aspose.Slides สำหรับ Java ได้หรือไม่
ใช่ คุณสามารถปรับเปลี่ยนคุณสมบัติเหล่านี้ได้โดยใช้ Aspose.Slides เพียงใช้เมธอดตัวตั้งค่าที่เหมาะสมที่จัดเตรียมไว้โดยอินเทอร์เฟซ IDocumentProperties
### Aspose.Slides เข้ากันได้กับ PowerPoint เวอร์ชันต่างๆ ได้หรือไม่
Aspose.Slides รองรับ PowerPoint เวอร์ชันต่างๆ มากมาย เพื่อให้แน่ใจว่าสามารถใช้งานร่วมกับแพลตฟอร์มต่างๆ ได้
### ฉันสามารถดึงคุณสมบัติที่กำหนดเองได้หรือไม่
ใช่ นอกเหนือจากคุณสมบัติในตัวแล้ว คุณยังสามารถดึงข้อมูลและปรับเปลี่ยนคุณสมบัติแบบกำหนดเองได้โดยใช้ Aspose.Slides สำหรับ Java
### Aspose.Slides มีเอกสารประกอบและการสนับสนุนหรือไม่
ใช่ คุณสามารถค้นหาเอกสารประกอบที่ครอบคลุมและเข้าถึงฟอรัมสนับสนุนได้ที่ [เว็บไซต์อาโพส](https://reference-aspose.com/slides/java/).
### มีเวอร์ชันทดลองใช้สำหรับ Aspose.Slides สำหรับ Java หรือไม่
ใช่ คุณสามารถดาวน์โหลดเวอร์ชันทดลองใช้งานฟรีได้จาก [ที่นี่](https://releases-aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}