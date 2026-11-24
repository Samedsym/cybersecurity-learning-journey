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

<<<<<<< HEAD
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
=======
### Uç Cihaz Adreslemesi
IP Adresi: Cihazın ağ üzerindeki kimliğidir.Hostu tanımlar.
Alt Ağ Maskesi (Subnet Mask): Cihazın bağlı olduğu ağı tanımlar.
Varsayılan Ağ Geçidi (Default Gateway): Cihazın internete veya başka uzak ağlara erişmek için kullandığı yönlendirici cihazı tanımlar.
DNS: Domain Name System. Alan adlarını IP adreslerine çeviren sistemdir.

## Ethernet
### Kablolu Ağ Teknolojisi

Kablolu ağlar üzerinden veri alışverişi yapmasını sağlayan teknolojidir. 
OSI modelinin iki katmanında çalışır:
Fiziksel Katman(Layer 1): Elektrik sinyallerinin, kabloların, bağlantı uçlarının standartını belirler.
Veri Bağlantı Katmanı(Layer 2): Verinin frame halinde nasıl paketleneceğini ve hedef cihaza nasıl gönderileceğini tanımlar.

### Ethernet MAC Adresi
Cihazın fiziksel adresidir. 48 Bitlik adrestir. 16lık sayı sisteminde yazılmıştır. Ağ birim kartının üzerinde yazılıdır.

### MAC Address Format
48 bit = 12 hex digit (örnek: 00:60:2F:3D:32:1A).
- İlk yarı (24 bit): OUI, üretici firmayı gösterir (Cisco, Intel gibi).
- İkinci yarı (24 bit): üreticinin cihaza verdiği benzersiz numara.
- first half = vendor, second half = device.

## Unicast / Multicast / Broadcast
- Unicast: tek bir cihaza gönderilen mesaj (bire bir).
- Multicast: belirli bir gruba gönderilen mesaj (bire birkaç).
- Broadcast: aynı ağdaki herkese gönderilen mesaj (bire hepsi).
  MAC adresi: FF:FF:FF:FF:FF:FF
- Bir cihaz, bir grup ya da herkes.

## DHCP
Ağa bağlanan cihaza IP adresini otomatik verir (IP, subnet mask, gateway, DNS).
Kısacası: otomatik IP dağıtımı.

## ARP
IP adresinin MAC adresini bulur. Soru broadcast ile gider, cevap unicast ile döner.
Kısacası: "Bu IP kimde?" sorusu.

# IP
## OSI Referans Modeli

7 katmanlı modeldir. Her katmanın görevi, veri birimi (PDU) ve cihazı vardır.
### Katmanlar

- **7. Uygulama:** Kullanıcı uygulamalarına servis sağlar. PDU: Veri. Cihaz: Ağ Geçidi.
- **6. Sunum:** Veriyi dönüştürür, yeniden düzenler. PDU: Veri. Cihaz: Ağ Geçidi.
- **5. Oturum:** Oturum oluşturur, yönetir, durdurur. PDU: Veri. Cihaz: Ağ Geçidi.
- **4. Taşıma:** Veriyi paket boyutunda parçalara böler. PDU: Segment / Datagram. Cihaz: Ağ Geçidi.
- **3. Ağ:** Mantıksal adresleme (IP) ve yönlendirme. PDU: Paket. Cihaz: Router, L3 Switch.
- **2. Veri Bağı:** Çerçeveleme, fiziksel adresleme (MAC), hata tespiti. PDU: Çerçeve. Cihaz: Bridge, L2 Switch, NIC.
- **1. Fiziksel:** Veriyi bit olarak iletir (kablo/medya). PDU: Bit. Cihaz: Repeater, Hub.

## Notlar

- **Ana Bilgisayar katmanları:** 5-7
- **Ortam katmanları:** 1-4 (slayttaki gruplama; bazı kaynaklar Taşıma'yı ana bilgisayar katmanına dahil eder)
- **Veri birimi sırası (1 → 7):** Bit → Çerçeve → Paket → Segment/Datagram → Veri

## Network Layer 3
IP bilgisayar ağlarında verilen iletimini sağlayan temel protokollerden biridir.

-IP verileri küçük paketlere ayırır
-Her paketin header'ında kaynak ve hedefin IP adresi bulunur.
-Paketler ağlar arasında router aracılığıyla iletilir.

## Protokol
IPv4: Taşıma katmanından gelen ileti parçalarını alır, bu iletiler paketler haline getirilir, paketleri adresler ve ağ üzerinde uçtan uca teslimat için yönlendirir. 32 bitlik adres yapısı kullanır

IPv6: IPv4'e benzer ama 128 bitlik adres yapısına sahiptir.IPsec desteği, Multicast desteği.
Genişletilmiş Adres Alanı: 128 Bit adresler
Dahili Güvenlik: IPsec
Daha İyi Çoklu Yayın: Multicast

NAT(Ağ adresi çevirici): private bir ağdaki IPv4 adreslerini global olarak benzersiz olan public IPv4 adreslerine çevirir.

## IP Özellikleri
Düşük ek yükle tasarlanmış bir protokoldür.

Connectionless: Veri paketlerini göndermeden önce hedefle bağlantı kurulmaz.
Best Effort: IP doğası gereği güvenilmezdir çünkü paket teslimi garanti edilmez. TCP gibi üst katmanlara bırakır.
Media Independent: Veriyi taşıyan ortamdan bağımsızdır. Esnek ve uyumludur.

MTU(Maximum Transmission Unit): Bir ağ bağlantısından tek seferde gönderilebilecek en büyük paket boyutudur, bayt cinsinden ölçülür.Ethernette standard MTU 1500 bayttır. IP paketinin header dahil alabileceği en büyük boyuttur.

MTU: IP paketinin en büyük boyutu (Layer3).
MSS: TCP'nin tek segmentte taşıyabileceği veri boyutu. Yaklaşık olarak MTU -40bayt (20 bayt IP+20 bayt TCP başlığı), yani ethernette 1460 bayt.

CIDR: Classes Inter Domain Routing

# IP Adres Sınıfları

> Kaynak: BTK Akademi, Bilgisayar Ağlarına Giriş

## Oktet
- IPv4 adresi 32 bittir, 4 oktete bölünür. Oktet = 8 bit.
- Her oktet 0-255 arasındadır (2^8 = 256 değer).
- Örnek: `192.168.1.25` → 1. oktet 192, 4. oktet 25.

## Sınıflar
Sınıfı IP'nin **ilk sayısı (ilk oktet)** belirler. CIDR belirlemez.

- **A:** 1-126, varsayılan /8, 16.777.214 cihaz, çok büyük ağlar
- **B:** 128-191, varsayılan /16, 65.534 cihaz, orta büyük ağlar
- **C:** 192-223, varsayılan /24, 254 cihaz, küçük ağlar
- **D:** 224-239, multicast (grup yayını)
- **E:** 240-255, deneysel, kullanılmaz
- **127.x.x.x:** loopback (cihazın kendisi), örn. 127.0.0.1

## Sabit bit deseni
İlk 0'a kadar kaç tane 1 varsa sınıf odur:
- A: `0xxxxxxx`
- B: `10xxxxxx`
- C: `110xxxxx`
- D: `1110xxxx`

## Özel (private) aralıklar
İç ağlarda kullanılır, internete doğrudan çıkmaz. Sınıftan bağımsız bir konudur.
- `10.0.0.0/8` (A)
- `172.16.0.0/12` (B)
- `192.168.0.0/16` (C)

Bunların dışındaki adresler genel (public) adrestir.

## Not
- Sınıf sistemi artık kullanılmıyor, yerini CIDR aldı. Sınavlarda ve terimlerde hâlâ geçiyor.
- Sınıf = IP'nin ilk sayısı. Özel/genel = ayrı bir konu.

# CIDR ve Subnetting

## CIDR nedir?
- IP adresi ve ağ büyüklüğünü birlikte yazma yöntemi: `192.168.1.0/24`
- `/24` = ilk 24 bit ağ kısmı, kalan bitler cihaz (host) kısmı.
- `/24` ile `255.255.255.0` (subnet mask) aynı şeydir.
- CIDR 0-32 arası her değer olabilir, 8'in katları zorunlu değil.

## Cihaz sayısı
- Host biti = 32 - CIDR
- Cihaz sayısı = 2^(host biti) - 2
- 2 adres ayrılmıştır: ağ adresi (ilk) ve broadcast (son).
- IP'nin değeri cihaz sayısını etkilemez, sadece CIDR belirler.
- Örnek: `/8` → 24 bit → 2^24 - 2 = 16.777.214

## Sık kullanılan CIDR'lar
- /24: mask 255.255.255.0, 254 cihaz
- /25: mask 255.255.255.128, 126 cihaz
- /26: mask 255.255.255.192, 62 cihaz
- /27: mask 255.255.255.224, 30 cihaz
- /28: mask 255.255.255.240, 14 cihaz
- /29: mask 255.255.255.248, 6 cihaz
- /30: mask 255.255.255.252, 2 cihaz

## Mask nasıl bulunur?
Son oktette soldan her ağ biti şunu ekler: 128, 64, 32, 16, 8, 4, 2, 1
- /26 → 128 + 64 = 192
- /27 → 128 + 64 + 32 = 224
## Mask mantığı
- Mask: ağ bitleri 1, cihaz bitleri 0 olarak yazılır.
- /26 → 11111111.11111111.11111111.11000000 → 255.255.255.192

## Blok boyutu (atlama miktarı)
- Blok boyutu = 256 - mask
- /26 → 256 - 192 = 64 → bloklar: 0, 64, 128, 192
- /27 → 256 - 224 = 32 → bloklar: 0, 32, 64, 96...

## Hangi oktette bölünür?
- /1-/8: 1. oktet
- /9-/16: 2. oktet
- /17-/24: 3. oktet

- /25-/32: 4. oktet
- Cihaz biti 8'den fazlaysa cihaz kısmı bir önceki oktete de taşar.

## Örnek: 192.168.1.72/26
- 72, .64-.127 bloğunda
- Ağ adresi: 192.168.1.64
- Kullanılabilir: 192.168.1.65 - 192.168.1.126
- Broadcast: 192.168.1.127
- Cihaz sayısı: 62

## Neden CIDR?
Sınıf sistemi çok israfa yol açıyordu (300 cihaz için C yetmiyor, B çok fazla). CIDR ile ağ ihtiyaca göre boyutlandırılır.

## Alt Ağ Maskesi(Subnet Mask)
IP adresi , network, host kısımlardan oluşmaktadır.
Network adresi, belirli bir ağa ait olan tüm cihazların grup adresidir.
Host adresi ise o ağdaki belirli bir cihaza ait benzersiz adrestir.

### Not: 
/30 iki network'ün birbiri ile point to point konuştuğu (özellikle WAN servislerinde) aynı networke sadece 2 tane IP adresine ihtiyaç duyulur.

P2P için kullanılabilecek en verimli IP maskesi CIDR gösterimi = /30

## Private IP - Public IP
IANA (Internet Assign Numbers Authority) Dünyayı 5 bölgeye ayırarak Regional Internet Registry (RIR) firmaları aracılığı ile IP adreslerini dağıtmıştır. RIR olarak bilinen kuruluşlar:
ARIN: Kuzey Amerika
LACNIC: Latin Amerika
RIPE: Avrupa
AFRINIC: Afrika
APNIC: Asya Pasifik

### 127.0.0.1 - Loopback Adress
Cihazın kendi ağ arabirim kartı üzerinden döner. TCP/IP protokolleri üzeirnden iç yolun çalıştığını doğrulamak için test amacıyla kullanılır.

### APIPA - Automatic Private IP Addressing
169.254.x.y
255.255.0.0 subnet mask
Yönlendirelemez
Link Localde kalmayı sağlar.

# Özel (Private) ve Genel (Public) IP

## Özel IP (LAN, iç arayüz)
- Yerel ağın içinde kullanılır, örnek: 192.168.1.1
- Aralıklar: `10.0.0.0/8`, `172.16.0.0/12`, `192.168.0.0/16`
- Benzersiz olmak zorunda değil, farklı ağlarda aynı olabilir.
- İnternette doğrudan kullanılamaz.

## Genel IP (WAN, dış arayüz)
- İnternette kullanılır, örnek: 84.15.186.115
- ISP verir.
- Dünyada benzersizdir.
- İnternetten ulaşılabilir.

## Diyagram
- Üç ağın da iç adresi aynı (192.168.1.1), ama WAN tarafında farklı genel IP'leri var.
- Özel IP'ler çakışmaz, çünkü her biri kendi ağının içinde kalır.

## Interface (Arayüz)
- Router'ın ağa bağlandığı bağlantı noktası. Her arayüzün kendi IP'si olur.
- **Internal interface (iç arayüz):** Router'ın LAN'a bakan tarafı, özel IP taşır.
- **External interface (dış arayüz):** Router'ın internete (WAN) bakan tarafı, genel IP taşır.

## LAN ve WAN
- LAN (Local Area Network): Yerel ağ, evin ya da iş yerinin iç ağı.
- WAN (Wide Area Network): Geniş ağ, internet tarafı.

## Note
- Özel IP: farklı ağlarda aynı olabilir (herkesin kendi ağı var).
- Genel IP: dünyada benzersiz, her ağın (evin) bir tane, o ağdaki tüm cihazlar internete bu IP ile çıkar.
