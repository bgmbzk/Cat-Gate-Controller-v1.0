# Cat-Gate Controller v1.0 🐱🚪

Bu proje, kedilerin sesli komutlarına (veya belirli miyavlama frekanslarına) duyarlı bir şekilde çalışan, otomatik bir kedi kapısı kontrol sistemidir. Donanım tasarımı tamamen **KiCad** kullanılarak gerçekleştirilmiştir.

## 🎯 Projenin Amacı
Projenin temel amacı, evcil hayvanların eve giriş ve çıkış süreçlerini otomatize ederek hem konforu hem de güvenliği artırmaktır. Sistem, bir mikrofon sensöründen gelen verileri işleyerek **DRV8833** motor sürücüsü üzerinden kapı mekanizmasını harekete geçirir.

## 🛠 Teknik Özellikler ve Tasarım Süreci
Bu tasarımda **ATmega328P** mikrodenetleyici kullanılmıştır. Tasarım süreci boyunca sadece bir devre kurmayı değil, aynı zamanda yüksek akım çeken bileşenlerin bir sistem üzerindeki etkilerini yönetmeyi öğrendik.

### 🚀 Kritik Tasarım Noktaları & Kazanımlar
Projede özellikle motorun elektriksel gerekliliklerini yerine getirmek adına şu teknik detaylara odaklanılmıştır:

* **Yüksek Akım ve Kalın Yollar:** Motorun çalışma anında çektiği yüksek akım (inrush current) nedeniyle, güç hatlarını (VCC ve GND) standart sinyal yollarından çok daha **kalın** tutarak voltaj düşümlerini ve ısınmayı engelledik.
* **Gürültü Yönetimi:** Motorların devreye girerken oluşturduğu elektriksel gürültünün (noise) hassas mikrodenetleyici sinyallerini bozmaması için **Ground Plane (Toprak Düzlemi)** stratejisi uygulanmıştır.
* **Katman Yönetimi:** Kartın her iki yüzünde de (F.Cu ve B.Cu) geniş bakır alanlar oluşturularak hem gürültü kalkanı sağlanmış hem de termal rahatlama (soğutma) elde edilmiştir.

## 📸 Proje Görselleri

### 1. Devre Şematiği (Schematic)
Sistemin mantıksal bağlantılarını ve bileşenler arası iletişimi temsil eder.
![Schematic](Cat-Gate%20Controller%20v1.0_sch.png)

### 2. PCB Tasarımı (Layout)
Güç yollarının kalınlığına ve gürültü kalkanına dikkat edilen baskı devre yerleşimi.
![PCB Layout](Cat-Gate%20Controller%20v1.0_pcb.png)

### 3. 3D Model Önizlemesi
Donanımın fiziksel olarak bitmiş halinin 3D render görüntüsü.
![3D View](Cat-Gate%20Controller%20v1.0.png)

## 📁 Dosya Yapısı
* `/Production`: Fabrika üretimi için gerekli olan Gerber ve Drill (.drl) dosyaları.
* `/Source`: KiCad proje dosyaları (.kicad_pro, .kicad_sch, .kicad_pcb).

---
*Bu proje, gömülü sistemler ve donanım tasarımı konusundaki öğrenim sürecinin bir parçası olarak geliştirilmiştir.*
