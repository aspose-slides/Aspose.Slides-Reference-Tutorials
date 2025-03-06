---
title: ตั้งค่ามุมของเส้นเชื่อมต่อใน PowerPoint
linktitle: ตั้งค่ามุมของเส้นเชื่อมต่อใน PowerPoint
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีการตั้งค่ามุมของเส้นเชื่อมต่อในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ปรับแต่งสไลด์ของคุณอย่างแม่นยำ
type: docs
weight: 17
url: /th/java/java-powerpoint-animation-shape-manipulation/set-connector-line-angle-powerpoint/
---
## การแนะนำ
ในบทช่วยสอนนี้ เราจะสำรวจวิธีตั้งค่ามุมของเส้นเชื่อมต่อในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java เส้นเชื่อมต่อเป็นสิ่งจำเป็นสำหรับการแสดงความสัมพันธ์และการไหลเวียนระหว่างรูปร่างในสไลด์ของคุณ ด้วยการปรับมุม คุณสามารถมั่นใจได้ว่าการนำเสนอของคุณจะถ่ายทอดข้อความของคุณอย่างชัดเจนและมีประสิทธิภาพ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม Java
- ติดตั้ง JDK (Java Development Kit) บนระบบของคุณ
-  Aspose.Slides สำหรับไลบรารี Java ที่ดาวน์โหลดและเพิ่มในโครงการของคุณ คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).

## แพ็คเกจนำเข้า
ในการเริ่มต้น ให้นำเข้าแพ็คเกจที่จำเป็นไปยังโปรเจ็กต์ Java ของคุณ ตรวจสอบให้แน่ใจว่าคุณรวมไลบรารี Aspose.Slides สำหรับการเข้าถึงฟังก์ชันการทำงานของ PowerPoint
```java
import com.aspose.slides.*;

```
## ขั้นตอนที่ 1: เริ่มต้นวัตถุการนำเสนอ
เริ่มต้นด้วยการเริ่มต้นวัตถุการนำเสนอเพื่อโหลดไฟล์ PowerPoint ของคุณ
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "ConnectorLineAngle.pptx");
```
## ขั้นตอนที่ 2: เข้าถึงสไลด์และรูปร่าง
เข้าถึงสไลด์และรูปร่างเพื่อระบุเส้นเชื่อมต่อ
```java
Slide slide = (Slide) pres.getSlides().get_Item(0);
Shape shape;
```
## ขั้นตอนที่ 3: วนซ้ำผ่านรูปร่าง
วนซ้ำแต่ละรูปร่างบนสไลด์เพื่อระบุเส้นเชื่อมต่อและคุณสมบัติต่างๆ
```java
for (int i = 0; i < slide.getShapes().size(); i++) {
    double dir = 0.0;
    shape = (Shape) slide.getShapes().get_Item(i);
    if (shape instanceof AutoShape) {
        AutoShape ashp = (AutoShape) shape;
        if (ashp.getShapeType() == ShapeType.Line) {
            // รูปทรงแฮนด์ไลน์
            dir = getDirection(ashp.getWidth(), ashp.getHeight(), ashp.getFrame().getFlipH() != 0, ashp.getFrame().getFlipV() != 0);
        }
    } else if (shape instanceof Connector) {
        // รูปทรง คอนเนคเตอร์ ด้ามจับ
        Connector ashp = (Connector) shape;
        dir = getDirection(ashp.getWidth(), ashp.getHeight(), ashp.getFrame().getFlipH() != 0, ashp.getFrame().getFlipV() != 0);
    }
    System.out.println(dir);
}
```
## ขั้นตอนที่ 4: คำนวณมุม
ใช้เมธอด getDirection เพื่อคำนวณมุมของเส้นเชื่อมต่อ
```java
public static double getDirection(float w, float h, boolean flipH, boolean flipV) {
    float endLineX = w * (flipH ? -1 : 1);
    float endLineY = h * (flipV ? -1 : 1);
    float endYAxisX = 0;
    float endYAxisY = h;
    double angle = (Math.atan2(endYAxisY, endYAxisX) - Math.atan2(endLineY, endLineX));
    if (angle < 0) angle += 2 * Math.PI;
    return angle * 180.0 / Math.PI;
}
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีจัดการมุมของเส้นเชื่อมต่อในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java เมื่อทำตามขั้นตอนเหล่านี้ คุณจะสามารถปรับแต่งสไลด์ของคุณได้อย่างมีประสิทธิภาพเพื่อแสดงข้อมูลและแนวคิดของคุณด้วยภาพที่แม่นยำ
## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Slides สำหรับ Java กับไลบรารี Java อื่นได้หรือไม่
อย่างแน่นอน! Aspose.Slides สำหรับ Java ผสานรวมกับไลบรารี Java อื่นๆ ได้อย่างราบรื่น เพื่อปรับปรุงประสบการณ์การสร้างและการจัดการงานนำเสนอของคุณ
### Aspose.Slides เหมาะสำหรับงาน PowerPoint ทั้งแบบง่ายและซับซ้อนหรือไม่
ใช่ Aspose.Slides มีฟังก์ชันการทำงานที่หลากหลายซึ่งตอบสนองความต้องการ PowerPoint ต่างๆ ตั้งแต่การจัดการสไลด์ขั้นพื้นฐานไปจนถึงการจัดรูปแบบขั้นสูงและงานแอนิเมชัน
### Aspose.Slides รองรับฟีเจอร์ PowerPoint ทั้งหมดหรือไม่
Aspose.Slides มุ่งมั่นที่จะสนับสนุนฟีเจอร์ PowerPoint ส่วนใหญ่ อย่างไรก็ตาม สำหรับฟังก์ชันเฉพาะหรือขั้นสูง ขอแนะนำให้อ่านเอกสารประกอบหรือติดต่อฝ่ายสนับสนุนของ Aspose
### ฉันสามารถปรับแต่งสไตล์เส้นตัวเชื่อมต่อด้วย Aspose.Slides ได้หรือไม่
แน่นอน! Aspose.Slides มีตัวเลือกมากมายสำหรับการปรับแต่งเส้นเชื่อมต่อ รวมถึงสไตล์ ความหนา และจุดสิ้นสุด ซึ่งช่วยให้คุณสร้างงานนำเสนอที่ดึงดูดสายตาได้
### ฉันจะรับการสนับสนุนสำหรับคำค้นหาที่เกี่ยวข้องกับ Aspose.Slides ได้ที่ไหน
 ท่านสามารถเยี่ยมชมได้ที่[ฟอรั่ม Aspose.Slides](https://forum.aspose.com/c/slides/11) เพื่อขอความช่วยเหลือเกี่ยวกับข้อสงสัยหรือปัญหาใดๆ ที่คุณพบในระหว่างกระบวนการพัฒนา