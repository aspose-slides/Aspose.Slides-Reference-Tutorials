---
"date": "2025-04-16"
"description": "เรียนรู้วิธีฝังวัตถุ OLE ในสไลด์ PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET คู่มือนี้ครอบคลุมถึงการผสานรวม การบันทึกรูปแบบ และการใช้งานจริง"
"title": "วิธีการฝังวัตถุ OLE ใน PowerPoint โดยใช้ Aspose.Slides .NET&#58; คู่มือสำหรับนักพัฒนา"
"url": "/th/net/ole-objects-embedding/add-ole-object-powerpoint-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# วิธีการฝังวัตถุ OLE ใน PowerPoint โดยใช้ Aspose.Slides .NET: คู่มือสำหรับนักพัฒนา

## การแนะนำ

เพิ่มประสิทธิภาพการนำเสนอ PowerPoint ของคุณด้วยการฝังวัตถุ OLE (Object Linking and Embedding) เช่น สเปรดชีต เอกสาร หรือไฟล์อื่นๆ ได้อย่างราบรื่น คู่มือนี้จะแนะนำคุณเกี่ยวกับการใช้ Aspose.Slides สำหรับ .NET เพื่อเพิ่มวัตถุ OLE ลงในสไลด์ PowerPoint อย่างมีประสิทธิภาพ

**สิ่งที่คุณจะได้เรียนรู้:**
- วิธีการรวมวัตถุ OLE ลงในสไลด์ PowerPoint
- ขั้นตอนการบันทึกการนำเสนอของคุณในรูปแบบต่างๆ
- คุณสมบัติหลักและประโยชน์จากการใช้ Aspose.Slides สำหรับ .NET

ก่อนที่จะเจาะลึกถึงการนำไปใช้งาน เรามาทบทวนข้อกำหนดเบื้องต้นกันก่อนดีกว่า!

## ข้อกำหนดเบื้องต้น

วิธีปฏิบัติตามบทช่วยสอนนี้อย่างมีประสิทธิภาพ:

### ไลบรารี เวอร์ชัน และการอ้างอิงที่จำเป็น:
- **Aspose.Slides สำหรับ .NET** ไลบรารีสำหรับทำงานกับไฟล์ PowerPoint
- เวอร์ชันที่เข้ากันได้ของ .NET framework หรือ .NET Core ในสภาพแวดล้อมการพัฒนาของคุณ

### ข้อกำหนดการตั้งค่าสภาพแวดล้อม:
- โปรแกรมแก้ไขโค้ด เช่น Visual Studio หรือ VS Code
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม C# และแนวคิดของ .NET framework

## การตั้งค่า Aspose.Slides สำหรับ .NET

ในการเริ่มต้นด้วย Aspose.Slides ให้ติดตั้งไลบรารีผ่านตัวจัดการแพ็กเกจที่คุณต้องการ:

**.NET CLI:**
```bash
dotnet add package Aspose.Slides
```

**คอนโซลตัวจัดการแพ็คเกจ:**
```bash
Install-Package Aspose.Slides
```

**UI ตัวจัดการแพ็กเกจ NuGet:**
- ค้นหา "Aspose.Slides" และติดตั้งเวอร์ชันล่าสุด

### ขั้นตอนการรับใบอนุญาต:
1. **ทดลองใช้งานฟรี:** เริ่มต้นด้วยการทดลองใช้ฟรีเพื่อสำรวจคุณสมบัติต่างๆ
2. **ใบอนุญาตชั่วคราว:** สมัครใบอนุญาตชั่วคราวหากคุณต้องการมากกว่าที่ข้อเสนอทดลองใช้งาน
3. **ซื้อ:** ควรพิจารณาซื้อใบอนุญาตเพื่อใช้งาน Aspose.Slides ต่อไปโดยไม่มีข้อจำกัด

**การเริ่มต้นและการตั้งค่าเบื้องต้น:**
เมื่อติดตั้งแล้ว ให้เริ่มต้นโครงการของคุณด้วย `using` คำสั่งให้รวมเนมสเปซที่จำเป็น เช่น `Aspose.Slides` และ `System-IO`.

## คู่มือการใช้งาน

### คุณลักษณะที่ 1: ฝังวัตถุ OLE ในงานนำเสนอ

#### ภาพรวม
ฟีเจอร์นี้จะแนะนำคุณเกี่ยวกับการฝังไฟล์ฝังตัวเป็นวัตถุ OLE ภายในสไลด์ PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET

#### ขั้นตอน:

**ขั้นตอนที่ 1: เริ่มต้นการนำเสนอ**
```csharp
using (Presentation pres = new Presentation())
{
    // รหัสของคุณที่นี่...
}
```
- **คำอธิบาย:** เราเริ่มต้นด้วยการสร้างอินสแตนซ์ของ `Presentation` เพื่อจัดการสไลด์

**ขั้นตอนที่ 2: กำหนดไดเรกทอรีเอกสารและอ่านไบต์ไฟล์**
```csharp
string dataDir = \@"YOUR_DOCUMENT_DIRECTORY";
byte[] fileBytes = File.ReadAllBytes(dataDir + "test.zip");
```
- **พารามิเตอร์:** `dataDir` เป็นเส้นทางที่จัดเก็บไฟล์ของคุณ
- **ค่าส่งคืน:** `fileBytes` เก็บเนื้อหาไบนารีของไฟล์ของคุณ ซึ่งจำเป็นสำหรับการฝัง

**ขั้นตอนที่ 3: สร้างวัตถุ OleEmbeddedDataInfo**
```csharp
IOleEmbeddedDataInfo dataInfo = new OleEmbeddedDataInfo(fileBytes, "zip");
```
- **วัตถุประสงค์:** วัตถุนี้จะรวมข้อมูลที่ฝังไว้และระบุประเภทไฟล์ (เช่น zip)

**ขั้นตอนที่ 4: เพิ่ม OLE Object Frame ลงในสไลด์**
```csharp
IOleObjectFrame oleFrame = pres.Slides[0].Shapes.AddOleObjectFrame(150, 20, 50, 50, dataInfo);
oleFrame.IsObjectIcon = true;
```
- **คำอธิบาย:** เพิ่มวัตถุ OLE ลงในสไลด์แรก ที่นี่ `IsObjectIcon` จะถูกตั้งค่าเป็นจริงเพื่อแสดงไอคอนแทนวัตถุทั้งหมด

**เคล็ดลับการแก้ไขปัญหา:**
- ตรวจสอบให้แน่ใจว่าเส้นทางไฟล์ถูกต้องและสามารถเข้าถึงได้
- ตรวจสอบว่าชนิดไฟล์เป็นไปตามที่ระบุไว้ใน `OleEmbeddedDataInfo` ตรงกับรูปแบบไฟล์จริงของคุณ

### คุณสมบัติ 2: บันทึกการนำเสนอ

#### ภาพรวม
เรียนรู้วิธีบันทึกงานนำเสนอที่ปรับเปลี่ยนแล้วของคุณไปยังรูปแบบที่ต้องการโดยใช้ Aspose.Slides สำหรับ .NET

#### ขั้นตอน:

**ขั้นตอนที่ 1: กำหนดไดเรกทอรีผลลัพธ์และบันทึก**
```csharp
string outputDir = \@"YOUR_OUTPUT_DIRECTORY";
pres.Save(outputDir + "SetFileTypeForAnEmbeddingObject.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}