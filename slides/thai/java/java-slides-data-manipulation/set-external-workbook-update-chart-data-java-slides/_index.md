---
"description": "เรียนรู้วิธีตั้งค่าเวิร์กบุ๊กภายนอกและอัปเดตข้อมูลแผนภูมิใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java พัฒนาทักษะการทำงานอัตโนมัติใน PowerPoint ของคุณ"
"linktitle": "ตั้งค่าเวิร์กบุ๊กภายนอกด้วยการอัปเดตข้อมูลแผนภูมิใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "ตั้งค่าเวิร์กบุ๊กภายนอกด้วยการอัปเดตข้อมูลแผนภูมิใน Java Slides"
"url": "/th/java/data-manipulation/set-external-workbook-update-chart-data-java-slides/"
"weight": 20
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# ตั้งค่าเวิร์กบุ๊กภายนอกด้วยการอัปเดตข้อมูลแผนภูมิใน Java Slides


## บทนำสู่การตั้งค่าเวิร์กบุ๊กภายนอกด้วยการอัปเดตข้อมูลแผนภูมิใน Java Slides

ในคู่มือฉบับสมบูรณ์นี้ เราจะแนะนำคุณเกี่ยวกับขั้นตอนการตั้งค่าเวิร์กบุ๊กภายนอกด้วยข้อมูลแผนภูมิที่อัปเดตใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java API ไลบรารีอันทรงพลังนี้ช่วยให้คุณสามารถจัดการการนำเสนอ PowerPoint ได้ด้วยโปรแกรม ทำให้การทำงานอัตโนมัติ เช่น การอัปเดตข้อมูลแผนภูมิจากแหล่งภายนอกเป็นเรื่องง่าย เมื่ออ่านบทช่วยสอนนี้จบ คุณจะเข้าใจอย่างชัดเจนว่าต้องทำอย่างไรจึงจะทำงานนี้ได้สำเร็จ โดยมีคำแนะนำทีละขั้นตอนและโค้ด Java ประกอบ

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเจาะลึกการใช้งานจริง ให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

1. Aspose.Slides สำหรับ Java: คุณควรติดตั้งไลบรารี Aspose.Slides สำหรับ Java คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases-aspose.com/slides/java/).

2. สภาพแวดล้อมการพัฒนา Java: ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนา Java บนระบบของคุณแล้ว

## ขั้นตอนที่ 1: สร้างงานนำเสนอใหม่

ในการเริ่มต้น ให้สร้างงานนำเสนอ PowerPoint ใหม่โดยใช้ Aspose.Slides สำหรับ Java นี่คือโค้ด Java ที่ใช้ในการดำเนินการดังกล่าว:

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## ขั้นตอนที่ 2: เพิ่มแผนภูมิ

ตอนนี้เรามาเพิ่มแผนภูมิลงในงานนำเสนอของเรากัน เราจะสร้างแผนภูมิวงกลมในตัวอย่างนี้:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
```

## ขั้นตอนที่ 3: ตั้งค่าสมุดงานภายนอก

นี่คือจุดที่เราตั้งค่าเวิร์กบุ๊กภายนอกเป็นแหล่งข้อมูลสำหรับแผนภูมิของเรา คุณต้องระบุ URL ไปยังเวิร์กบุ๊กภายนอก แม้ว่าเวิร์กบุ๊กภายนอกนั้นจะไม่มีอยู่แล้วก็ตาม:

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook("http://เส้นทาง/ไม่ได้/มีอยู่", false);
```

## ขั้นตอนที่ 4: บันทึกการนำเสนอ

สุดท้าย ให้บันทึกการนำเสนอด้วยข้อมูลแผนภูมิที่อัปเดต:

```java
pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
```

## โค้ดต้นฉบับสมบูรณ์สำหรับการตั้งค่าเวิร์กบุ๊กภายนอกพร้อมอัปเดตข้อมูลแผนภูมิใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
	IChartData chartData = chart.getChartData();
	chartData.setExternalWorkbook("http://เส้นทาง/ไม่ได้/มีอยู่", false);
	pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## บทสรุป

ขอแสดงความยินดี! คุณได้เรียนรู้วิธีตั้งค่าเวิร์กบุ๊กภายนอกด้วยข้อมูลแผนภูมิที่อัปเดตใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java แล้ว วิธีนี้มีประโยชน์อย่างยิ่งในการอัปเดตแผนภูมิแบบไดนามิกในงานนำเสนอ PowerPoint ของคุณจากแหล่งข้อมูลภายนอก

## คำถามที่พบบ่อย

### ฉันจะอัปเดตข้อมูลเวิร์กบุ๊กภายนอกสำหรับแผนภูมิได้อย่างไร

หากต้องการอัปเดตข้อมูลเวิร์กบุ๊กภายนอกสำหรับแผนภูมิ คุณเพียงแค่ต้องแก้ไขข้อมูลในเวิร์กบุ๊กภายนอกที่ URL ที่ระบุ ในครั้งถัดไปที่คุณเปิดการนำเสนอ Aspose.Slides สำหรับ Java จะดึงข้อมูลที่อัปเดตจากเวิร์กบุ๊กภายนอกและอัปเดตแผนภูมิตามนั้น

### ฉันสามารถใช้ไฟล์ภายในเครื่องเป็นเวิร์กบุ๊กภายนอกได้หรือไม่

ใช่ คุณสามารถใช้ไฟล์ภายในเครื่องเป็นเวิร์กบุ๊กภายนอกได้โดยระบุเส้นทางของไฟล์แทน URL เพียงตรวจสอบให้แน่ใจว่าเส้นทางของไฟล์ถูกต้องและสามารถเข้าถึงได้จากแอปพลิเคชัน Java ของคุณ

### มีข้อจำกัดใด ๆ ในการใช้เวิร์กบุ๊กภายนอกกับ Aspose.Slides สำหรับ Java หรือไม่

แม้ว่าการใช้เวิร์กบุ๊กภายนอกจะเป็นฟีเจอร์ที่มีประสิทธิภาพ แต่โปรดจำไว้ว่าความพร้อมใช้งานของข้อมูลในเวิร์กบุ๊กภายนอกนั้นขึ้นอยู่กับการเข้าถึงได้ที่ URL หรือเส้นทางไฟล์ที่ให้มา ตรวจสอบให้แน่ใจว่าแหล่งข้อมูลภายนอกพร้อมใช้งานเมื่อคุณเปิดงานนำเสนอเพื่อหลีกเลี่ยงปัญหาการดึงข้อมูล

### ฉันสามารถปรับแต่งลักษณะที่ปรากฏของแผนภูมิหลังจากตั้งค่าเวิร์กบุ๊กภายนอกได้หรือไม่

ใช่ คุณสามารถปรับแต่งลักษณะของแผนภูมิได้ รวมถึงชื่อ ป้ายกำกับ สี และอื่นๆ แม้จะตั้งค่าเวิร์กบุ๊กภายนอกแล้วก็ตาม Aspose.Slides สำหรับ Java มีตัวเลือกการจัดรูปแบบแผนภูมิมากมายเพื่อตอบสนองความต้องการของคุณ

### ฉันสามารถหาเอกสารและแหล่งข้อมูลเพิ่มเติมสำหรับ Aspose.Slides สำหรับ Java ได้ที่ไหน

สำหรับเอกสารโดยละเอียดและแหล่งข้อมูลเพิ่มเติม โปรดไปที่เอกสาร Aspose.Slides สำหรับ Java ได้ที่ [ที่นี่](https://reference-aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}