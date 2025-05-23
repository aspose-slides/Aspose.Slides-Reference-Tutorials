---
"description": "Java ile Aspose.Slides kullanarak SmartArt'ta grafik düzeni türlerini düzenlemede ustalaşın ve sunum görsellerinizi zahmetsizce geliştirin."
"linktitle": "Java kullanarak SmartArt'ta Grafik Düzeni Türünü Organize Etme"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java kullanarak SmartArt'ta Grafik Düzeni Türünü Organize Etme"
"url": "/tr/java/java-powerpoint-smartart-manipulation/organize-chart-layout-type-smartart-java/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java kullanarak SmartArt'ta Grafik Düzeni Türünü Organize Etme

## giriiş
Bu eğitimde, Java kullanarak SmartArt'ta grafik düzeni türünü düzenleme sürecini ele alacağız, özellikle Aspose.Slides kütüphanesinden yararlanacağız. Sunumlardaki SmartArt, verilerinizin görsel çekiciliğini ve netliğini büyük ölçüde artırabilir, bu da manipülasyonunda ustalaşmayı gerekli kılar.
## Ön koşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1. Sisteminizde Java Development Kit (JDK) yüklü.
2. Aspose.Slides kütüphanesi indirildi ve kuruldu. Henüz yapmadıysanız, şuradan indirin: [Burada](https://releases.aspose.com/slides/java/).
3. Java programlamanın temel bilgisi.

## Paketleri İçe Aktar
Öncelikle gerekli paketleri import edelim:
```java
import com.aspose.slides.*;
```
Verilen örneği birden fazla adıma bölelim:
## Adım 1: Sunum Nesnesini Başlat
```java
Presentation presentation = new Presentation();
```
Yeni bir sunum nesnesi oluşturun.
## Adım 2: Slayda SmartArt Ekleme
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.OrganizationChart);
```
İstediğiniz slayda belirtilen boyutlar ve düzen türüyle SmartArt ekleyin.
## Adım 3: Organizasyon Şeması Düzenini Ayarlayın
```java
smart.getNodes().get_Item(0).setOrganizationChartLayout(OrganizationChartLayoutType.LeftHanging);
```
Organizasyon şeması düzen türünü ayarlayın. Bu örnekte, Sol Asılı düzenini kullanıyoruz.
## Adım 4: Sunumu Kaydedin
```java
presentation.save(dataDir + "OrganizeChartLayoutType_out.pptx", SaveFormat.Pptx);
```
Sunuyu düzenli grafik düzeniyle kaydedin.

## Çözüm
SmartArt'ta Java kullanarak grafik düzeni türlerinin organizasyonunda ustalaşmak, görsel olarak ilgi çekici sunumları kolaylıkla oluşturmanızı sağlar. Aspose.Slides ile süreç kolaylaştırılır ve verimli hale gelir ve etkili içerik oluşturmaya odaklanmanızı sağlar.
## SSS
### Aspose.Slides farklı Java geliştirme ortamlarıyla uyumlu mudur?
Evet, Aspose.Slides çeşitli Java geliştirme ortamlarıyla uyumludur ve geliştiricilere esneklik sağlar.
### Aspose.Slides'ı kullanarak SmartArt öğelerinin görünümünü özelleştirebilir miyim?
Kesinlikle, Aspose.Slides SmartArt öğeleri için kapsamlı özelleştirme seçenekleri sunarak bunları özel gereksinimlerinize göre uyarlamanıza olanak tanır.
### Aspose.Slides geliştiriciler için kapsamlı dokümantasyon sunuyor mu?
Evet, geliştiriciler Java için Aspose.Slides tarafından sağlanan ayrıntılı belgelere başvurarak işlevselliği ve kullanımı hakkında bilgi edinebilirler.
### Aspose.Slides için deneme sürümü mevcut mu?
Evet, satın alma kararı vermeden önce özelliklerini keşfetmek için Aspose.Slides'ın ücretsiz deneme sürümüne erişebilirsiniz.
### Aspose.Slides ile ilgili sorularım için nereden destek alabilirim?
Aspose.Slides ile ilgili herhangi bir yardım veya sorunuz varsa destek forumunu ziyaret edebilirsiniz [Burada](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}