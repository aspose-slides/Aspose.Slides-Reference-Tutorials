---
title: แอนิเมชั่นสไลด์ต้นแบบด้วย Aspose.Slides สำหรับ .NET
linktitle: การควบคุมภาพเคลื่อนไหวสไลด์ใน Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: ยกระดับการนำเสนอของคุณด้วย Aspose.Slides สำหรับ .NET! เรียนรู้การควบคุมภาพเคลื่อนไหวของสไลด์ได้อย่างง่ายดาย ดาวน์โหลดห้องสมุดทันที!
weight: 10
url: /th/net/slide-animation-control/slide-animation-control/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แอนิเมชั่นสไลด์ต้นแบบด้วย Aspose.Slides สำหรับ .NET

## การแนะนำ
การปรับปรุงการนำเสนอของคุณด้วยภาพเคลื่อนไหวที่น่าดึงดูดสามารถยกระดับผลกระทบโดยรวมต่อผู้ชมของคุณได้อย่างมาก ในบทช่วยสอนนี้ เราจะสำรวจวิธีการควบคุมภาพเคลื่อนไหวของสไลด์โดยใช้ Aspose.Slides สำหรับ .NET Aspose.Slides เป็นไลบรารีอันทรงพลังที่ช่วยให้การจัดการงานนำเสนอ PowerPoint ในสภาพแวดล้อม .NET เป็นไปอย่างราบรื่น
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1.  Aspose.Slides สำหรับ .NET Library: ดาวน์โหลดและติดตั้งไลบรารีจาก[หน้าดาวน์โหลด](https://releases.aspose.com/slides/net/).
2.  ไดเร็กทอรีเอกสาร: สร้างไดเร็กทอรีเพื่อจัดเก็บไฟล์งานนำเสนอของคุณ อัพเดต`dataDir` ตัวแปรในข้อมูลโค้ดพร้อมเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
## นำเข้าเนมสเปซ
ตรวจสอบให้แน่ใจว่าได้นำเข้าเนมสเปซที่จำเป็นที่จุดเริ่มต้นของไฟล์ .NET ของคุณ:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides.SlideShow;
```
ตอนนี้ เรามาแบ่งตัวอย่างที่ให้ไว้ออกเป็นหลายขั้นตอน:
## ขั้นตอนที่ 1: สร้างอินสแตนซ์การนำเสนอ
 ยกตัวอย่าง`Presentation` คลาสเพื่อแสดงไฟล์การนำเสนอของคุณ:
```csharp
using (Presentation pres = new Presentation(dataDir + "BetterSlideTransitions.pptx"))
{
    // รหัสสำหรับภาพเคลื่อนไหวสไลด์อยู่ที่นี่
}
```
## ขั้นตอนที่ 2: ใช้การเปลี่ยนประเภทวงกลม
ใช้การเปลี่ยนประเภทวงกลมกับสไลด์แรก:
```csharp
pres.Slides[0].SlideShowTransition.Type = TransitionType.Circle;
```
ตั้งเวลาการเปลี่ยนแปลงเป็น 3 วินาที:
```csharp
pres.Slides[0].SlideShowTransition.AdvanceOnClick = true;
pres.Slides[0].SlideShowTransition.AdvanceAfterTime = 3000;
```
## ขั้นตอนที่ 3: ใช้การเปลี่ยนประเภทหวี
ใช้การเปลี่ยนประเภทหวีกับสไลด์ที่สอง:
```csharp
pres.Slides[1].SlideShowTransition.Type = TransitionType.Comb;
```
ตั้งเวลาการเปลี่ยนแปลงเป็น 5 วินาที:
```csharp
pres.Slides[1].SlideShowTransition.AdvanceOnClick = true;
pres.Slides[1].SlideShowTransition.AdvanceAfterTime = 5000;
```
## ขั้นตอนที่ 4: ใช้การเปลี่ยนประเภทการซูม
ใช้การเปลี่ยนประเภทการซูมกับสไลด์ที่สาม:
```csharp
pres.Slides[2].SlideShowTransition.Type = TransitionType.Zoom;
```
ตั้งเวลาการเปลี่ยนแปลงเป็น 7 วินาที:
```csharp
pres.Slides[2].SlideShowTransition.AdvanceOnClick = true;
pres.Slides[2].SlideShowTransition.AdvanceAfterTime = 7000;
```
## ขั้นตอนที่ 5: บันทึกการนำเสนอ
เขียนงานนำเสนอที่แก้ไขแล้วกลับไปยังดิสก์:
```csharp
pres.Save(dataDir + "SampleTransition_out.pptx", SaveFormat.Pptx);
```
ตอนนี้คุณได้ควบคุมภาพเคลื่อนไหวของสไลด์โดยใช้ Aspose.Slides สำหรับ .NET เรียบร้อยแล้ว!
## บทสรุป
การทำให้สไลด์เคลื่อนไหวในงานนำเสนอของคุณช่วยเพิ่มสัมผัสแบบไดนามิก ทำให้เนื้อหาของคุณน่าสนใจยิ่งขึ้น ด้วย Aspose.Slides สำหรับ .NET กระบวนการจะตรงไปตรงมา ช่วยให้คุณสร้างงานนำเสนอที่ดึงดูดสายตาได้อย่างง่ายดาย
## คำถามที่พบบ่อย
### ฉันสามารถปรับแต่งเอฟเฟ็กต์การเปลี่ยนแปลงเพิ่มเติมได้หรือไม่
 ใช่ Aspose.Slides มีประเภทการเปลี่ยนภาพที่หลากหลายและคุณสมบัติเพิ่มเติมสำหรับการปรับแต่ง อ้างถึง[เอกสารประกอบ](https://reference.aspose.com/slides/net/) เพื่อดูรายละเอียด
### มีการทดลองใช้ฟรีหรือไม่?
 ใช่ คุณสามารถสำรวจ Aspose.Slides ได้ด้วย[ทดลองฟรี](https://releases.aspose.com/).
### ฉันจะรับการสนับสนุนสำหรับ Aspose.Slides ได้ที่ไหน
 เยี่ยมชม[ฟอรั่ม Aspose.Slides](https://forum.aspose.com/c/slides/11) สำหรับการสนับสนุนและการอภิปรายของชุมชน
### ฉันจะขอรับใบอนุญาตชั่วคราวได้อย่างไร
 คุณสามารถรับใบอนุญาตชั่วคราวได้จาก[ที่นี่](https://purchase.aspose.com/temporary-license/).
### ฉันจะซื้อ Aspose.Slides สำหรับ .NET ได้ที่ไหน
 ซื้อห้องสมุด[ที่นี่](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
