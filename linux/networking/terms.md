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

