---
title: เข้าถึงโหนดลูกในตำแหน่งเฉพาะใน SmartArt
linktitle: เข้าถึงโหนดลูกในตำแหน่งเฉพาะใน SmartArt
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีจัดการ SmartArt ใน Aspose.Slides สำหรับ Java ด้วยคำแนะนำโดยละเอียดนี้ คำแนะนำทีละขั้นตอน ตัวอย่าง และแนวทางปฏิบัติที่ดีที่สุดรวมอยู่ด้วย
weight: 11
url: /th/java/java-powerpoint-smartart-manipulation/access-child-node-specific-position-smartart-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## การแนะนำ
คุณกำลังมองหาที่จะยกระดับการนำเสนอของคุณไปอีกระดับด้วยกราฟิก SmartArt ที่ซับซ้อนหรือไม่? ไม่ต้องมองอีกต่อไป! Aspose.Slides สำหรับ Java มีชุดโปรแกรมอันทรงพลังสำหรับการสร้าง จัดการ และจัดการสไลด์การนำเสนอ รวมถึงความสามารถในการทำงานกับออบเจ็กต์ SmartArt ในบทช่วยสอนที่ครอบคลุมนี้ เราจะอธิบายให้คุณทราบถึงการเข้าถึงและการจัดการโหนดลูกที่ตำแหน่งเฉพาะภายในกราฟิก SmartArt โดยใช้ Aspose.Slides สำหรับไลบรารี Java

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม มีข้อกำหนดเบื้องต้นบางประการที่คุณต้องมี:
1.  Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK บนเครื่องของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก[หน้าออราเคิล JDK](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides สำหรับไลบรารี Java: ดาวน์โหลด Aspose.Slides สำหรับไลบรารี Java จากไฟล์[หน้าดาวน์โหลด](https://releases.aspose.com/slides/java/).
3. สภาพแวดล้อมการพัฒนาแบบรวม (IDE): ใช้ Java IDE ใดก็ได้ที่คุณเลือก IntelliJ IDEA, Eclipse หรือ NetBeans เป็นตัวเลือกยอดนิยม
4.  กำหนดใบอนุญาต: แม้ว่าคุณจะสามารถเริ่มต้นด้วยการทดลองใช้ฟรีได้ แต่หากต้องการความสามารถเต็มรูปแบบ ให้ลองพิจารณารับ[ใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/) หรือซื้อลิขสิทธิ์แบบเต็มจาก[ที่นี่](https://purchase.aspose.com/buy).
## แพ็คเกจนำเข้า
ขั้นแรก เรามานำเข้าแพ็คเกจที่จำเป็นในโปรเจ็กต์ Java ของคุณกันก่อน นี่เป็นสิ่งสำคัญสำหรับการใช้ฟังก์ชัน Aspose.Slides
```java
import com.aspose.slides.*;
import java.io.File;
```
ตอนนี้ เรามาแบ่งตัวอย่างออกเป็นขั้นตอนโดยละเอียด:
## ขั้นตอนที่ 1: สร้างไดเร็กทอรี
ขั้นตอนแรกคือการตั้งค่าไดเร็กทอรีที่จะจัดเก็บไฟล์งานนำเสนอของคุณ เพื่อให้แน่ใจว่าแอปพลิเคชันของคุณมีพื้นที่ที่กำหนดไว้สำหรับจัดการไฟล์
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างไดเร็กทอรีหากไม่มีอยู่
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
```
ที่นี่ เรากำลังตรวจสอบว่ามีไดเร็กทอรีอยู่หรือไม่ และหากไม่มี เรากำลังสร้างมันขึ้นมา นี่เป็นแนวทางปฏิบัติที่ดีที่สุดทั่วไปเพื่อหลีกเลี่ยงข้อผิดพลาดในการจัดการไฟล์
## ขั้นตอนที่ 2: สร้างอินสแตนซ์การนำเสนอ

ต่อไป เราจะสร้างอินสแตนซ์การนำเสนอใหม่ นี่คือแกนหลักของโครงการของเราที่จะเพิ่มสไลด์และรูปร่างทั้งหมด
```java
//ยกตัวอย่างการนำเสนอ
Presentation pres = new Presentation();
```
บรรทัดโค้ดนี้เริ่มต้นวัตถุการนำเสนอใหม่โดยใช้ Aspose.Slides
## ขั้นตอนที่ 3: เข้าถึงสไลด์แรก

ตอนนี้ เราต้องเข้าถึงสไลด์แรกในการนำเสนอ สไลด์คือที่ที่ใช้วางเนื้อหาทั้งหมดของงานนำเสนอ
```java
// การเข้าถึงสไลด์แรก
ISlide slide = pres.getSlides().get_Item(0);
```
ซึ่งจะเข้าถึงสไลด์แรกในงานนำเสนอ ทำให้เราสามารถเพิ่มเนื้อหาลงไปได้
## ขั้นตอนที่ 4: เพิ่มรูปร่าง SmartArt
### เพิ่มรูปร่าง SmartArt
ต่อไป เราจะเพิ่มรูปร่าง SmartArt ลงในสไลด์ SmartArt เป็นวิธีที่ยอดเยี่ยมในการแสดงข้อมูลด้วยภาพ
```java
// การเพิ่มรูปร่าง SmartArt ในสไลด์แรก
ISmartArt smart = slide.getShapes().addSmartArt(0, 0, 400, 400, SmartArtLayoutType.StackedList);
```
 ที่นี่ เราระบุตำแหน่งและขนาดของรูปร่าง SmartArt และเลือกประเภทเค้าโครง ในกรณีนี้`StackedList`.
## ขั้นตอนที่ 5: เข้าถึงโหนด SmartArt

ตอนนี้เราเข้าถึงโหนดเฉพาะภายในกราฟิก SmartArt โหนดคือองค์ประกอบแต่ละอย่างภายในรูปร่าง SmartArt
```java
// การเข้าถึงโหนด SmartArt ที่ดัชนี 0
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
ซึ่งจะดึงข้อมูลโหนดแรกในกราฟิก SmartArt ซึ่งเราจะจัดการเพิ่มเติม
## ขั้นตอนที่ 6: เข้าถึงโหนดลูก

ในขั้นตอนนี้ เราเข้าถึงโหนดลูกในตำแหน่งเฉพาะภายในโหนดหลัก
```java
// การเข้าถึงโหนดลูกที่ตำแหน่ง 1 ในโหนดหลัก
int position = 1;
SmartArtNode chNode = (SmartArtNode) node.getChildNodes().get_Item(position);
```
วิธีนี้จะดึงโหนดลูกในตำแหน่งที่ระบุ ซึ่งช่วยให้เราสามารถจัดการคุณสมบัติของมันได้
## ขั้นตอนที่ 7: พิมพ์พารามิเตอร์โหนดย่อย

สุดท้ายนี้ เรามาพิมพ์พารามิเตอร์ของโหนดลูกเพื่อตรวจสอบการเปลี่ยนแปลงของเรา
```java
// การพิมพ์พารามิเตอร์โหนดลูก SmartArt
String outString = String.format("j = {0},.Text{1},  Level = {2}, Position = {3}", position, chNode.getTextFrame().getText(), chNode.getLevel(), chNode.getPosition());
System.out.println(outString);
```
บรรทัดโค้ดนี้จะจัดรูปแบบและพิมพ์รายละเอียดของโหนดย่อย เช่น ข้อความ ระดับ และตำแหน่ง
## บทสรุป
ยินดีด้วย! คุณเข้าถึงและจัดการโหนดลูกภายในกราฟิก SmartArt ได้สำเร็จโดยใช้ Aspose.Slides สำหรับ Java คู่มือนี้จะอธิบายการตั้งค่าโปรเจ็กต์ของคุณ การเพิ่ม SmartArt และการจัดการโหนดทีละขั้นตอน ด้วยความรู้นี้ คุณสามารถสร้างงานนำเสนอที่มีพลังและดึงดูดสายตามากขึ้นได้แล้ว
 หากต้องการอ่านเพิ่มเติมและสำรวจคุณสมบัติขั้นสูงเพิ่มเติม โปรดดูที่[Aspose.Slides สำหรับเอกสาร Java](https://reference.aspose.com/slides/java/) หากคุณมีคำถามหรือต้องการความช่วยเหลือ[กำหนดฟอรั่มชุมชน](https://forum.aspose.com/c/slides/11) เป็นสถานที่ที่ดีเยี่ยมในการขอความช่วยเหลือ
## คำถามที่พบบ่อย
### ฉันจะติดตั้ง Aspose.Slides สำหรับ Java ได้อย่างไร
 คุณสามารถดาวน์โหลดได้จาก[หน้าดาวน์โหลด](https://releases.aspose.com/slides/java/) และปฏิบัติตามคำแนะนำในการติดตั้งที่ให้ไว้
### ฉันสามารถลองใช้ Aspose.Slides สำหรับ Java ก่อนซื้อได้หรือไม่
 ใช่ คุณจะได้รับ[ทดลองฟรี](https://releases.aspose.com/) หรือก[ใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/) เพื่อทดสอบคุณสมบัติต่างๆ
### เค้าโครง SmartArt ประเภทใดบ้างที่มีใน Aspose.Slides
 Aspose.Slides รองรับเค้าโครง SmartArt ต่างๆ เช่น รายการ กระบวนการ วงจร ลำดับชั้น และอื่นๆ คุณสามารถดูข้อมูลโดยละเอียดได้ใน[เอกสารประกอบ](https://reference.aspose.com/slides/java/).
### ฉันจะรับการสนับสนุนสำหรับ Aspose.Slides สำหรับ Java ได้อย่างไร
 คุณสามารถรับการสนับสนุนจาก[กำหนดฟอรั่มชุมชน](https://forum.aspose.com/c/slides/11) หรืออ้างถึงอย่างกว้างขวาง[เอกสารประกอบ](https://reference.aspose.com/slides/java/).
### ฉันสามารถซื้อใบอนุญาตแบบเต็มสำหรับ Aspose.Slides สำหรับ Java ได้หรือไม่
 ใช่ คุณสามารถซื้อใบอนุญาตฉบับสมบูรณ์ได้จาก[หน้าซื้อ](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
