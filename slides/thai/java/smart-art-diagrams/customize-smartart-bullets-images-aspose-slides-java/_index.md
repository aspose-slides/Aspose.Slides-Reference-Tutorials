---
"date": "2025-04-18"
"description": "เรียนรู้วิธีปรับปรุงการนำเสนอของคุณโดยปรับแต่งจุดแสดงหัวข้อย่อย SmartArt ด้วยรูปภาพโดยใช้ Aspose.Slides สำหรับ Java ทำตามคำแนะนำทีละขั้นตอนนี้เพื่อให้ดูเป็นมืออาชีพ"
"title": "วิธีปรับแต่ง SmartArt Bullets ด้วยรูปภาพโดยใช้ Aspose.Slides สำหรับ Java | คำแนะนำทีละขั้นตอน"
"url": "/th/java/smart-art-diagrams/customize-smartart-bullets-images-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# วิธีปรับแต่งจุดแสดง SmartArt ด้วยรูปภาพโดยใช้ Aspose.Slides สำหรับ Java

## การแนะนำ

การสร้างงานนำเสนอที่ดึงดูดสายตาเป็นสิ่งสำคัญสำหรับการดึงดูดความสนใจของผู้ชมและสื่อสารข้อความของคุณได้อย่างมีประสิทธิภาพ ความท้าทายทั่วไปอย่างหนึ่งในการออกแบบสไลด์คือการปรับปรุงจุดหัวข้อย่อยในกราฟิก SmartArt โดยใช้รูปภาพที่กำหนดเอง บทช่วยสอนนี้จะแนะนำคุณเกี่ยวกับการตั้งค่ารูปภาพเป็นรูปแบบการเติมจุดหัวข้อย่อยในโหนด SmartArt ด้วย Aspose.Slides สำหรับ Java ช่วยให้คุณยกระดับงานนำเสนอของคุณอย่างมืออาชีพ

**สิ่งที่คุณจะได้เรียนรู้:**
- การตั้งค่าและการใช้งาน Aspose.Slides สำหรับ Java
- การปรับแต่งจุดหัวข้อด้วยรูปภาพในกราฟิก SmartArt
- การประยุกต์ใช้งานจริงของการปรับแต่งนี้
- การแก้ไขปัญหาทั่วไป

ก่อนที่จะเริ่มใช้งาน ให้แน่ใจว่าคุณมีทุกอย่างพร้อมแล้ว

## ข้อกำหนดเบื้องต้น

หากต้องการทำตามบทช่วยสอนนี้ โปรดแน่ใจว่าคุณปฏิบัติตามข้อกำหนดเบื้องต้นต่อไปนี้:

1. **ห้องสมุดและสิ่งที่ต้องพึ่งพา**คุณจะต้องมีไลบรารี Aspose.Slides สำหรับ Java เวอร์ชัน 25.4 ขึ้นไป
2. **การตั้งค่าสภาพแวดล้อม**-
   - IDE ที่เข้ากันได้ เช่น IntelliJ IDEA หรือ Eclipse
   - JDK 16 ติดตั้งบนเครื่องของคุณแล้ว
3. **ข้อกำหนดเบื้องต้นของความรู้**: ความคุ้นเคยกับการเขียนโปรแกรม Java และโครงสร้างการนำเสนอ PowerPoint ขั้นพื้นฐาน

## การตั้งค่า Aspose.Slides สำหรับ Java

ในการเริ่มต้น ให้รวมไลบรารี Aspose.Slides ไว้ในโปรเจ็กต์ของคุณโดยใช้หนึ่งในวิธีต่อไปนี้:

### เมเวน

เพิ่มการอ้างอิงนี้ให้กับคุณ `pom.xml` ไฟล์:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### แกรเดิล

รวมสิ่งนี้ไว้ในของคุณ `build.gradle`-

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### ดาวน์โหลดโดยตรง

หรืออีกวิธีหนึ่งคือดาวน์โหลดไลบรารีโดยตรงจาก [Aspose.Slides สำหรับการเปิดตัว Java](https://releases-aspose.com/slides/java/).

**ขั้นตอนการรับใบอนุญาต**:Aspose นำเสนอใบอนุญาตทดลองใช้งานฟรีซึ่งเหมาะสำหรับการทดสอบฟีเจอร์ต่างๆ คุณสามารถขอใบอนุญาตชั่วคราวหรือซื้อใบอนุญาตเพื่อลบข้อจำกัดในการประเมินได้

หากต้องการเริ่มต้นและตั้งค่าสภาพแวดล้อมของคุณ ให้สร้างอินสแตนซ์ของ `Presentation` ชั้นเรียนดังแสดง:

```java
Presentation presentation = new Presentation();
```

## คู่มือการใช้งาน

ในส่วนนี้จะแบ่งกระบวนการออกเป็นขั้นตอนที่สามารถจัดการได้ โดยอธิบายถึงวิธีการบรรลุฟังก์ชันการทำงานตามต้องการ

### การเพิ่ม SmartArt ด้วยการเติมหัวข้อแบบกำหนดเอง

#### ภาพรวม

เราจะเริ่มต้นด้วยการเพิ่มรูปร่าง SmartArt ลงในสไลด์ของคุณและปรับแต่งจุดหัวข้อโดยใช้การเติมรูปภาพ

#### คำแนะนำทีละขั้นตอน

**1. เริ่มต้นวัตถุการนำเสนอ**

```java
Presentation presentation = new Presentation();
```

*วัตถุประสงค์*:เริ่มต้นอินสแตนซ์การนำเสนอใหม่ที่คุณจะเพิ่มกราฟิก SmartArt

**2. เพิ่มรูปทรง SmartArt**

```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 500, 400, SmartArtLayoutType.VerticalPictureList);
```

*คำอธิบาย*:บรรทัดนี้จะเพิ่มรูปร่าง SmartArt ใหม่ลงในสไลด์แรกที่ตำแหน่ง (x=10, y=10) โดยมีขนาด 500x400 พิกเซล `VerticalPictureList` เค้าโครงใช้สำหรับการจัดแนวตั้ง

**3. เข้าถึงและปรับแต่งการเติมหัวข้อย่อย**

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

*วัตถุประสงค์*: ตรวจสอบว่าโหนดมี `BulletFillFormat` คุณสมบัติ หากเป็นเช่นนั้น ระบบจะโหลดรูปภาพและตั้งค่าให้เติมเป็นหัวข้อย่อย
*พารามิเตอร์*-
  - `"YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg"`: เส้นทางไปยังไฟล์รูปภาพของคุณ
  - `PictureFillMode.Stretch`:ช่วยให้แน่ใจว่าภาพจะเติมเต็มพื้นที่หัวข้ออย่างสมบูรณ์

**4. บันทึกการนำเสนอของคุณ**

```java
presentation.save("YOUR_OUTPUT_DIRECTORY/out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}