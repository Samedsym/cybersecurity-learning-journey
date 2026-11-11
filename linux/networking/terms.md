# Network Terms Notes

## Network Topologies

| Topology      | Low cost | Easy setup | Speed | Reliability | Scalability |
|---------------|----------|------------|-------|-------------|-------------|
| Bus (Yol)     | +        | +          | -     | -           | -           |
| Star (Yıldız) | ~        | +          | +     | ~ (center)  | +           |
| Ring (Halka)  | -        | ~          | ~     | -           | ~           |
| Tree (Ağaç)   | ~        | -          | +     | ~           | +           |
| Mesh (Örgü)   | -        | -          | +     | +           | ~           |

+ good   ~ medium   - weak

- Bus: tüm cihazlar tek kabloyu paylaşır.
- Star: tüm cihazlar merkezdeki bir switch'e bağlanır, merkez bozulursa ağ durur.
- Ring: her cihaz iki komşusuna bağlanır, halka oluşur.
- Tree: yıldız yapılarının hiyerarşik birleşimi.
- Mesh: cihazlar birçok (ya da tüm) diğer cihazla bağlanır, yedek yol çoktur ama maliyet yüksektir.

## Standards (IEEE)

IEEE standartları yayımlayan bir kuruluştur (Wi-Fi için 802.11, Ethernet için 802.3).
Standartlar, farklı üreticilerin cihazlarının birbiriyle uyumlu çalışmasını sağlar.

## Wi-Fi (IEEE 802.11)

802.11, kablosuz yerel ağlar (WLAN) için standart ailesidir.

| Standard | Name   | Band        |
|----------|--------|-------------|
| b        | -      | 2.4 GHz     |
| g        | -      | 2.4 GHz     |
| n        | Wi-Fi 4| 2.4 / 5 GHz |
| ac       | Wi-Fi 5| 5 GHz       |
| ax       | Wi-Fi 6| 2.4 / 5 GHz |

- Yeni standart genelde daha hızlıdır.
- 2.4 GHz: menzil uzun, daha yavaş, kalabalık.
- 5 GHz: menzil kısa, daha hızlı.

## Wi-Fi security

- WEP: eski ve kırılabilir, kullanma.
- WPA: zayıf, eski.
- WPA2: hâlâ yaygın.
- WPA3: en yeni ve en güçlü.
- Open network: şifresiz ağda trafik sniff edilebilir (izlenebilir).

## ISP (İSS)
İnternet Servis Sağlayıcı. İnternet bağlantısını ve genelde bir public IP adresini sağlar.
Örnek: Türk Telekom, Turkcell Superonline.

## Wan Topology

Point to Point: İki konum arasında doğrudan bağlantı kurar.
+ Güvenilir ve hızlı.
- Yüksek maliyet ve yalnızca iki noktayı bağlar.
Örn: Banka atm'siyle merkez sunucu arasındaki bağlantı.

Hub and Spoke
Bir Hub router'ı tüm spoke routerlara tek arayüz üzerinden bağlanır.
Spoke'lar yalnızca hub aracılığıyla iletişim kurar.
+ Maliyet düşük.
- Hub router arızalanırsa tüm hata düşer.

Dual homed
Bir ağ iki farklı servis sağlayıcısına bağlanır
+ Kesintisiz hizmet, yüksek erişebilirlik
- Yüksek maliyet ve karışıklık

Fully Meshed
Tüm site'lar birbirine bağlanır.

Partially Meshed
Site'lar seçici olarak bağlanır. Hepsi birbirine bağlı değildir.

Carrier
Servis sağlayıcı ve müşteri arasındaki fiziksel bağlantıyı yapan şirket.
(Fiber hat,kablolar...)

Single-Carrier
Tek ISS ile çalışır. Yedeklilik yok.
Dual-Carrier
İki farklı ISS var. Yedeklilik var. Karmaşık yönetim, daha fazla maliyet.


## İletişimin Temelleri
1. Gönderen / Kaynak 'Source'
2. Ortam Transmission Media
3. Alıcı / Heded 'Receiver'

Ön İletişim = Handshake

### Protokol Yığını

HTTP: Hypertext Transfer Protocol
Web sunucusu ile istemcisi arasındaki etkileşimi yönetir.

TCP: Bireysel veri alışverişlerini yönetir.

IP: Mesajların göndericiden alıcıya ulaştırılmasında sorumludur.

Ethernet: Aynı yerel ağ 'LAN' üzerindeki iki ağ kartı arasında mesaj iletimini sağlar

## OSI (Open System Interconnection)
### SENDER
7-Application/Uygulama: İşlemden işleme iletişim için kullanılan protokolleri içerir.
6-Presentation/Sunum: Uygulama katmanı servisleri arasında aktarılan verilerin ortak temsilini sağlar.
5-Session/Oturum: Sunum katmanına iletişim diyaloğunu organize etme ve veri değişimini yöentme servislerini sunar.
4-Transport/Taşıma: Uç cihazlar arasındaki bireysel iletişimler için veriyi segmentlere ayırma, aktarma ve yeniden birleştirme servislerini tanımlar.
3-Network/Ağ: Tanımlanmış uç cihazlar arasında veri parçalarının ağ üzerinden değişimini sunar
2-Data Link/Veri Bağı: Ortak bir medya üzerinden cihazlar arasında veri çerçevelerini değişim yöntemlerini tanımlar
1-Physical: Mekanik, elektriksel, işlevsel ve prosedürel yöntemlerle bit iletimini başlatma, sürdürme ve sondanlardırma için fiziksel bağlantıları tanımlar.

### RECEIVER
1-2-3-4-5-6-7


Üst katmanlar 7-6-5
Alt katmanlar 4-3-2-1

## OSI & TCP/IP Reference Models

| OSI Layer | OSI Name     | TCP/IP Layer        |
|-----------|--------------|---------------------|
| 7         | Application  |                     |
| 6         | Presentation | Application         |
| 5         | Session      |_____________________|
| 4         | Transport    | Transport __________|
| 3         | Network      | Internet  __________|
| 2         | Data Link    |                     |
| 1         | Physical     | Network Access      |

- OSI 7 katmanlı, TCP/IP 4 katmanlı bir modeldir.
- TCP/IP'de Application, OSI'nin üst 3 katmanını (7, 6, 5) tek başına karşılar.
- TCP/IP'de Network Access, OSI'nin alt 2 katmanını (2, 1) birlikte karşılar.
- OSI teorik referans modeldir, TCP/IP internetin gerçekte kullandığı modeldir.

## Ağ Medyası
Veri iletişimini sağlayan kablolu veya kablosuz ortam.

Bakır Kablolar: En sık kullanılan alan yerel ağlar(LAN).
Fiber Optik Kablolar: Işık hızına yakın bi hızda iletişim sağlar.
Kablosuz İletim:Verinin elektromanyetik dalgalar aracılığıyla iletilmesini sağlar.

### Terms Note 
Elektromanyetik Parazit = EMI

## Cat Cable Standards

| Category | Max speed               | Bandwidth | Max distance | Shielding       |
|----------|-------------------------|-----------|--------------|-----------------|
| Cat 3    | 10 Mbps                 | 16 MHz    | 100 m        | None (UTP)      |
| Cat 5    | 100 Mbps                | 100 MHz   | 100 m        | Mostly UTP      |
| Cat 5e   | 1 Gbps                  | 100 MHz   | 100 m        | UTP / STP       |
| Cat 6    | 1G (100 m) / 10G (55 m) | 250 MHz   | 100 m / 55 m | UTP or STP      |
| Cat 6a   | 10 Gbps                 | 500 MHz   | 100 m        | Mostly STP      |
| Cat 7    | 10 Gbps                 | 600 MHz   | 100 m        | Full (S/FTP)    |
| Cat 7a   | 10 Gbps (up to 40)      | 1000 MHz  | 100 m        | S/FTP           |
| Cat 8    | 25-40 Gbps              | 2000 MHz  | 30 m         | S/FTP           |

## Where each is used

- Cat 3: eski telefon ve 10Base-T ağları.
- Cat 5: eski Ethernet ağları (100Base-T).
- Cat 5e: günümüzde yaygın (Gigabit Ethernet).
- Cat 6: ofisler ve modern ağlar.
- Cat 6a: yoğun veri trafiği olan yapılar.
- Cat 7: veri merkezleri, endüstriyel ağlar.
- Cat 7a: yüksek hızlı profesyonel ortamlar.
- Cat 8: veri merkezleri, kısa mesafede yüksek hız.

## Key terms
- UTP (Unshielded Twisted Pair): ekransız bükümlü çift kablo.
- STP (Shielded Twisted Pair): ekranlı, parazite daha dayanıklı.
- S/FTP: hem çiftler hem tüm kablo ekranlı.
- Ekranlama, elektriksel parazite (girişim) karşı korur.

## Cabling (T568A / T568B)

| Pin | Signal | T568A          | T568B          |
|-----|--------|----------------|----------------|
| 1   | TX+    | White/Green    | White/Orange   |
| 2   | TX-    | Green          | Orange         |
| 3   | RX+    | White/Orange   | White/Green    |
| 4   |        | Blue           | Blue           |
| 5   |        | White/Blue     | White/Blue     |
| 6   | RX-    | Orange         | Green          |
| 7   |        | White/Brown    | White/Brown    |
| 8   |        | Brown          | Brown          |

Fark: yeşil ve turuncu çiftler yer değiştirir.

- Straight-through (düz): iki uç aynı standart (A-A veya B-B). Farklı cihazları bağlar (PC - switch).
- Crossover (çapraz): bir uç A, diğer uç B. Aynı cihazları bağlar (PC - PC, switch - switch).
- Auto-MDIX: modern cihazlar kablo türünü otomatik algılar.

## TX / RX
TX = Transmit (gönder), RX = Receive (al).
+ ve - : bir sinyali taşıyan çiftin iki teli (biri sinyal, biri ters sinyal).
Amaç: parazite (noise) karşı koruma. Bükümlü çift (twisted pair) de bunun için.

Throughput(Verim): Ağ tıkanıklığı, yönlendirme gecikemeleri veya donanım sınırlandırmaları nedeniyle gerçekleşen tüm olayları'da hesaplayarak gerçekte ağ üzerinden geçen veri miktarını gösterir.
Goodput(Net Veri Verimi): Throughput'dan TCP başlıkları gibi ek verileri çıkararak geriye kalan net veriyi gösterir.

## Ağ Bileşenleri
Cihazlar(Devices)
İletim Ortamı (Networking Media)
Services

### Üç Katmanlı Ağ Mimarisi (Three-Tier Architecture)
Acces Layer: Cihazların ağa fiziksel olarak bağlandığı ilk noktadır."Access switch"
Görevleri:
VLAN erişimis ağlamak. 
Son kullanıcıyı ağa bağlamak.
Port Güvenliği, MAC filtreleme vb. temel güvenlik kontrolleri

Distribution Layer:Access switch’leri toplar, aralarındaki trafiği yönlendirir, kuralları uygular. "Router, Layer 3 Switch"

Core Layer:	Ağın omurgası, en yüksek hızda ve kesintisiz taşır "Güçlü Core Switch, Router"

## OSI Reference Model

| No | Layer        | Görevi                                   | PDU                | Cihaz                  |
|----|--------------|------------------------------------------|--------------------|------------------------|
| 7  | Application  | Uygulamalara ağ servisi sağlar           | Data               | Default Gateway        |
| 6  | Presentation | Veri dönüşümü, şifreleme, sıkıştırma     | Data               | Default Gateway        |
| 5  | Session      | Oturum açar, yönetir, kapatır            | Data               | Default Gateway        |
| 4  | Transport    | Veriyi parçalar, uçtan uca taşır         | Segment / Datagram | Default Gateway        |
| 3  | Network      | IP adresleme ve yönlendirme              | Packet             | Router, L3 Switch      |
| 2  | Data Link    | MAC ile komşuya teslim, hata tespiti     | Frame              | Bridge, L2 Switch, NIC |
| 1  | Physical     | Bitleri sinyal olarak iletir             | Bit                | Repeater, Hub          |

- 7-5: host layers (ana bilgisayar katmanları), 4-1: media layers (ortam katmanları).
- PDU (Protocol Data Unit): verinin bir katmanda aldığı biçim ve ona verilen isim.
- Encapsulation: veri yukarıdan aşağıya inerken her katman kendi header'ını ekler.
- Decapsulation: alıcı tarafta her katman kendi header'ını çıkarır.
- Sıra: Data -> Segment -> Packet -> Frame -> Bit.
- Cihazlar: Router = Layer 3, Switch = Layer 2, Hub = Layer 1.
- Hafıza cümlesi (7 -> 1): All People Seem To Need Data Processing.

Kısacası: üstte uygulama, ortada taşıma ve adresleme, altta fiziksel iletim. Aynı veri her katmanda farklı bir PDU adıyla sarılır.

## PDU (Protocol Data Unit)
Verinin bir katmanda aldığı biçim ve ona verilen isimdir.
Encapsulation: yukarıdan aşağıya her katman kendi header'ını ekler.
Decapsulation: alıcı tarafta her katman kendi header'ını çıkarır.

Data (7-5) -> Segment/Datagram (4) -> Packet (3) -> Frame (2) -> Bit (1)

Kısacası: aynı veri, her katmanda farklı bir isimle sarılır.

