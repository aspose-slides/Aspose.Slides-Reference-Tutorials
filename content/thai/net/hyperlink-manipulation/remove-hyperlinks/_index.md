---
title: วิธีลบไฮเปอร์ลิงก์ออกจากสไลด์ด้วย Aspose.Slides .NET
linktitle: ลบไฮเปอร์ลิงก์ออกจากสไลด์
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: เรียนรู้วิธีลบไฮเปอร์ลิงก์ออกจากสไลด์ PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET สร้างงานนำเสนอที่สะอาดตาและเป็นมืออาชีพ
type: docs
weight: 11
url: /th/net/hyperlink-manipulation/remove-hyperlinks/
---

ในโลกของการนำเสนอแบบมืออาชีพ การทำให้แน่ใจว่าสไลด์ของคุณดูเรียบร้อยและเป็นระเบียบถือเป็นสิ่งสำคัญ องค์ประกอบทั่วไปประการหนึ่งที่มักทำให้สไลด์เกะกะคือไฮเปอร์ลิงก์ ไม่ว่าคุณจะจัดการกับไฮเปอร์ลิงก์ไปยังเว็บไซต์ เอกสาร หรือสไลด์อื่นๆ ภายในงานนำเสนอของคุณ คุณอาจต้องการลบไฮเปอร์ลิงก์ออกเพื่อให้ดูสะอาดตาและเน้นมากขึ้น ด้วย Aspose.Slides สำหรับ .NET คุณสามารถทำงานนี้ให้สำเร็จได้อย่างง่ายดาย ในคำแนะนำทีละขั้นตอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการลบไฮเปอร์ลิงก์ออกจากสไลด์โดยใช้ Aspose.Slides สำหรับ .NET

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

1.  Aspose.Slides สำหรับ .NET: คุณควรติดตั้ง Aspose.Slides สำหรับ .NET และตั้งค่าในสภาพแวดล้อมการพัฒนาของคุณ หากยังไม่มีสามารถขอรับได้จาก[Aspose.Slides สำหรับเอกสาร .NET](https://reference.aspose.com/slides/net/).

2. งานนำเสนอ PowerPoint: คุณจะต้องมีงานนำเสนอ PowerPoint (ไฟล์ PPTX) ที่คุณต้องการลบไฮเปอร์ลิงก์

เมื่อเป็นไปตามข้อกำหนดเบื้องต้นเหล่านี้ คุณก็พร้อมที่จะเริ่มต้นแล้ว มาดูกระบวนการลบไฮเปอร์ลิงก์ออกจากสไลด์ทีละขั้นตอนกัน

## ขั้นตอนที่ 1: นำเข้าเนมสเปซ

ในการเริ่มต้น คุณจะต้องนำเข้าเนมสเปซที่จำเป็นในโค้ด C# ของคุณ เนมสเปซเหล่านี้ให้การเข้าถึงไลบรารี Aspose.Slides สำหรับ .NET เพิ่มบรรทัดต่อไปนี้ลงในโค้ดของคุณ:

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
```

## ขั้นตอนที่ 2: โหลดงานนำเสนอ

ตอนนี้ คุณต้องโหลดงานนำเสนอ PowerPoint ที่มีไฮเปอร์ลิงก์ที่คุณต้องการลบ ตรวจสอบให้แน่ใจว่าคุณได้ระบุเส้นทางที่ถูกต้องไปยังไฟล์งานนำเสนอของคุณ ต่อไปนี้คือวิธีที่คุณสามารถทำได้:

```csharp
string dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "Hyperlink.pptx");
```

 ในโค้ดด้านบน ให้แทนที่`"Your Document Directory"`ด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณและ`"Hyperlink.pptx"` ด้วยชื่อไฟล์งานนำเสนอ PowerPoint ของคุณ

## ขั้นตอนที่ 3: ลบไฮเปอร์ลิงก์

เมื่อโหลดงานนำเสนอของคุณแล้ว คุณสามารถดำเนินการลบไฮเปอร์ลิงก์ได้ Aspose.Slides สำหรับ .NET มีวิธีการที่ตรงไปตรงมาสำหรับจุดประสงค์นี้:

```csharp
presentation.HyperlinkQueries.RemoveAllHyperlinks();
```

 ที่`RemoveAllHyperlinks()` วิธีการลบไฮเปอร์ลิงก์ทั้งหมดออกจากการนำเสนอ

## ขั้นตอนที่ 4: บันทึกงานนำเสนอที่แก้ไข

หลังจากลบไฮเปอร์ลิงก์แล้ว คุณควรบันทึกงานนำเสนอที่แก้ไขลงในไฟล์ใหม่ คุณสามารถเลือกที่จะบันทึกในรูปแบบเดียวกัน (PPTX) หรือรูปแบบอื่นได้หากต้องการ ต่อไปนี้เป็นวิธีบันทึกเป็นไฟล์ PPTX:

```csharp
presentation.Save(dataDir + "RemovedHyperlink_out.pptx", SaveFormat.Pptx);
```

 อีกครั้งแทนที่`"RemovedHyperlink_out.pptx"` ด้วยชื่อไฟล์เอาต์พุตและเส้นทางที่คุณต้องการ

ยินดีด้วย! คุณได้ลบไฮเปอร์ลิงก์ออกจากงานนำเสนอ PowerPoint ของคุณโดยใช้ Aspose.Slides สำหรับ .NET เรียบร้อยแล้ว ตอนนี้สไลด์ของคุณปราศจากสิ่งรบกวน มอบประสบการณ์การรับชมที่สะอาดตาและมีสมาธิมากขึ้น

## บทสรุป

ในบทช่วยสอนนี้ เราได้อธิบายขั้นตอนการลบไฮเปอร์ลิงก์ออกจากงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET ด้วยขั้นตอนง่ายๆ เพียงไม่กี่ขั้นตอน คุณก็สามารถมั่นใจได้ว่าสไลด์ของคุณดูเป็นมืออาชีพและไม่เกะกะ Aspose.Slides สำหรับ .NET ช่วยลดความยุ่งยากในการทำงานกับงานนำเสนอ PowerPoint โดยมอบเครื่องมือที่คุณต้องการสำหรับการจัดการที่มีประสิทธิภาพและแม่นยำ

หากคุณพบว่าคู่มือนี้มีประโยชน์ คุณสามารถสำรวจคุณสมบัติและความสามารถเพิ่มเติมของ Aspose.Slides สำหรับ .NET ได้ในเอกสารประกอบ[ที่นี่](https://reference.aspose.com/slides/net/) . คุณยังสามารถดาวน์โหลดห้องสมุดได้จาก[ลิงค์นี้](https://releases.aspose.com/slides/net/) และซื้อใบอนุญาต[ที่นี่](https://purchase.aspose.com/buy) ถ้าคุณยังไม่ได้ สำหรับผู้ที่ต้องการทดลองใช้ก่อนสามารถทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/) และสามารถขอรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).

## คำถามที่พบบ่อย (FAQ)

### ฉันสามารถลบไฮเปอร์ลิงก์แบบเลือกจากสไลด์เฉพาะในงานนำเสนอของฉันได้หรือไม่
ใช่คุณสามารถ. Aspose.Slides สำหรับ .NET จัดเตรียมวิธีการกำหนดเป้าหมายสไลด์หรือรูปร่างเฉพาะ และลบไฮเปอร์ลิงก์ออกจากสไลด์หรือรูปร่างเหล่านั้น

### Aspose.Slides สำหรับ .NET เข้ากันได้กับรูปแบบไฟล์ PowerPoint ล่าสุดหรือไม่
ใช่ Aspose.Slides สำหรับ .NET รองรับรูปแบบไฟล์ PowerPoint ล่าสุด รวมถึง PPTX

### ฉันสามารถทำให้กระบวนการนี้เป็นอัตโนมัติสำหรับการนำเสนอหลายรายการพร้อมกันได้หรือไม่
อย่างแน่นอน. Aspose.Slides สำหรับ .NET ช่วยให้คุณสามารถทำงานอัตโนมัติในการนำเสนอหลายรายการ ทำให้เหมาะสำหรับการประมวลผลเป็นชุด

### มีคุณสมบัติอื่นๆ ที่ Aspose.Slides สำหรับ .NET นำเสนอสำหรับการนำเสนอ PowerPoint หรือไม่
ใช่ Aspose.Slides สำหรับ .NET นำเสนอคุณสมบัติที่หลากหลาย รวมถึงการสร้างสไลด์ การแก้ไข และการแปลงเป็นรูปแบบต่างๆ

### มีการสนับสนุนด้านเทคนิคสำหรับ Aspose.Slides สำหรับ .NET หรือไม่
 ใช่ คุณสามารถขอรับการสนับสนุนด้านเทคนิคและมีส่วนร่วมกับชุมชน Aspose ได้ที่[ฟอรั่ม Aspose](https://forum.aspose.com/).