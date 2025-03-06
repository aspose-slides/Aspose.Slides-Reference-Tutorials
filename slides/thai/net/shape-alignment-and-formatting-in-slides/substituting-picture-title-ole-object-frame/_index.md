---
title: การฝังคู่มือวัตถุ OLE ด้วย Aspose.Slides สำหรับ .NET
linktitle: การทดแทนชื่อรูปภาพของ OLE Object Frame ในสไลด์การนำเสนอ
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: เรียนรู้วิธีปรับปรุงสไลด์การนำเสนอของคุณด้วยวัตถุ OLE แบบไดนามิกโดยใช้ Aspose.Slides สำหรับ .NET ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อการบูรณาการที่ราบรื่น
type: docs
weight: 15
url: /th/net/shape-alignment-and-formatting-in-slides/substituting-picture-title-ole-object-frame/
---
## การแนะนำ
การสร้างสไลด์การนำเสนอแบบไดนามิกและน่าสนใจมักเกี่ยวข้องกับการรวมเอาองค์ประกอบมัลติมีเดียต่างๆ เข้าด้วยกัน ในบทช่วยสอนนี้ เราจะสำรวจวิธีการแทนที่ชื่อรูปภาพของ OLE (การเชื่อมโยงวัตถุและการฝัง) กรอบวัตถุในสไลด์การนำเสนอโดยใช้ไลบรารี Aspose.Slides สำหรับ .NET อันทรงพลัง Aspose.Slides ทำให้กระบวนการจัดการวัตถุ OLE ง่ายขึ้น ช่วยให้นักพัฒนามีเครื่องมือในการปรับปรุงการนำเสนอได้อย่างง่ายดาย
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกคำแนะนำทีละขั้นตอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
-  Aspose.Slides สำหรับ .NET Library: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Aspose.Slides สำหรับ .NET Library แล้ว คุณสามารถดาวน์โหลดได้จาก[เอกสาร Aspose.Slides .NET](https://reference.aspose.com/slides/net/).
- ข้อมูลตัวอย่าง: เตรียมไฟล์ Excel ตัวอย่าง (เช่น "ExcelObject.xlsx") ที่คุณต้องการฝังเป็นวัตถุ OLE ในงานนำเสนอ นอกจากนี้ มีไฟล์รูปภาพ (เช่น "Image.png") ที่จะทำหน้าที่เป็นไอคอนสำหรับวัตถุ OLE
- สภาพแวดล้อมการพัฒนา: ตั้งค่าสภาพแวดล้อมการพัฒนาด้วยเครื่องมือที่จำเป็น เช่น Visual Studio หรือ IDE ที่ต้องการอื่นๆ สำหรับการพัฒนา .NET
## นำเข้าเนมสเปซ
ในโปรเจ็กต์ .NET ของคุณ ตรวจสอบให้แน่ใจว่าได้นำเข้าเนมสเปซที่จำเป็นสำหรับการทำงานกับ Aspose.Slides:
```csharp
using Aspose.Slides;
using Aspose.Slides.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Drawing;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Slides.DOM.Ole;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสาร
```csharp
string dataDir = "Your Document Directory";
```
ตรวจสอบให้แน่ใจว่าได้แทนที่ "Your Document Directory" ด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ
## ขั้นตอนที่ 2: กำหนดเส้นทางไฟล์ต้นฉบับ OLE และเส้นทางไฟล์ไอคอน
```csharp
string oleSourceFile = dataDir + "ExcelObject.xlsx";
string oleIconFile = dataDir + "Image.png";
```
อัปเดตเส้นทางเหล่านี้ด้วยเส้นทางจริงไปยังไฟล์ Excel ตัวอย่างและไฟล์รูปภาพของคุณ
## ขั้นตอนที่ 3: สร้างอินสแตนซ์การนำเสนอ
```csharp
using (Presentation pres = new Presentation())
{
    // รหัสสำหรับขั้นตอนต่อไปจะอยู่ที่นี่
}
```
 เริ่มต้นอินสแตนซ์ใหม่ของ`Presentation` ระดับ.
## ขั้นตอนที่ 4: เพิ่ม OLE Object Frame
```csharp
ISlide slide = pres.Slides[0];
byte[] allbytes = File.ReadAllBytes(oleSourceFile);
IOleEmbeddedDataInfo dataInfo = new OleEmbeddedDataInfo(allbytes, "xlsx");
IOleObjectFrame oof = slide.Shapes.AddOleObjectFrame(20, 20, 50, 50, dataInfo);
oof.IsObjectIcon = true;
```
เพิ่มกรอบวัตถุ OLE ลงในสไลด์ โดยระบุตำแหน่งและขนาด
## ขั้นตอนที่ 5: เพิ่มวัตถุรูปภาพ
```csharp
byte[] imgBuf = File.ReadAllBytes(oleIconFile);
using (MemoryStream ms = new MemoryStream(imgBuf))
{
    IPPImage image = pres.Images.AddImage(new Bitmap(ms));
}
```
อ่านไฟล์รูปภาพและเพิ่มลงในงานนำเสนอเป็นออบเจ็กต์รูปภาพ
## ขั้นตอนที่ 6: ตั้งค่าคำอธิบายภาพเป็นไอคอน OLE
```csharp
oof.SubstitutePictureTitle = "Caption example";
```
ตั้งค่าคำอธิบายภาพที่ต้องการสำหรับไอคอน OLE
## บทสรุป
การรวมวัตถุ OLE ลงในสไลด์การนำเสนอของคุณโดยใช้ Aspose.Slides สำหรับ .NET เป็นกระบวนการที่ไม่ซับซ้อน บทช่วยสอนนี้ได้แนะนำคุณตลอดขั้นตอนที่จำเป็น ตั้งแต่การตั้งค่าไดเร็กทอรีเอกสารไปจนถึงการเพิ่มและกำหนดออบเจ็กต์ OLE ทดลองใช้ไฟล์ประเภทต่างๆ และคำอธิบายภาพเพื่อเพิ่มความสวยงามให้กับงานนำเสนอของคุณ
## คำถามที่พบบ่อย
### ฉันสามารถฝังไฟล์ประเภทอื่นเป็นวัตถุ OLE โดยใช้ Aspose.Slides ได้หรือไม่
ใช่ Aspose.Slides รองรับการฝังไฟล์ประเภทต่างๆ เช่น สเปรดชีต Excel, เอกสาร Word และอื่นๆ
### ไอคอนวัตถุ OLE สามารถปรับแต่งได้หรือไม่
อย่างแน่นอน. คุณสามารถแทนที่ไอคอนเริ่มต้นด้วยรูปภาพที่คุณเลือกเพื่อให้เหมาะกับธีมงานนำเสนอของคุณมากขึ้น
### Aspose.Slides ให้การสนับสนุนภาพเคลื่อนไหวด้วยวัตถุ OLE หรือไม่
ในเวอร์ชันล่าสุด Aspose.Slides มุ่งเน้นไปที่การฝังและการแสดงผลวัตถุ OLE และไม่จัดการภาพเคลื่อนไหวภายในวัตถุ OLE โดยตรง
### ฉันสามารถจัดการวัตถุ OLE โดยทางโปรแกรมหลังจากเพิ่มวัตถุเหล่านั้นลงในสไลด์ได้หรือไม่
แน่นอน. คุณมีการควบคุมออบเจ็กต์ OLE ทางโปรแกรมเต็มรูปแบบ ซึ่งช่วยให้คุณสามารถปรับเปลี่ยนคุณสมบัติและลักษณะที่ปรากฏได้ตามต้องการ
### มีข้อจำกัดใดๆ เกี่ยวกับขนาดของวัตถุ OLE ที่ฝังอยู่หรือไม่
แม้ว่าจะมีข้อจำกัดเรื่องขนาด แต่โดยทั่วไปแล้วพวกเขาก็ใจกว้าง ขอแนะนำให้ทดสอบกับกรณีการใช้งานเฉพาะของคุณเพื่อให้แน่ใจว่ามีประสิทธิภาพสูงสุด