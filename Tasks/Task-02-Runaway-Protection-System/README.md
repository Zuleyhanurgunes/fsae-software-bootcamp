Görev 2 : Çift Sensörlü Gaz Pedalı Güvenliği (APPS Logic)
🎯 Amaç: "Mühendis Gibi Düşünmek"
Bir yarış aracında gaz pedalına güvenemezsiniz. Kablo kopabilir, sensör bozulabilir. Bu yüzden araçlarda 2 farklı sensör bulunur.

Problem: Ya sensörün biri "%100 Gaz" derken, diğeri "%0 Gaz" derse? Araba ne yapmalı? Gaza mı basmalı? Durmalı mı?

Görev: FSAE T11.8 kuralını uygulayan, hatalı sensör verilerini yakalayıp aracı güvenli moda alan bir Karar Algoritması yazmak.

⚙️ Senaryo ve Kurallar (The Logic Puzzle)
Elinizde PedalSistemi adında bir struct var. İçinde sensor_1 ve sensor_2 verileri var.

Kurallar (Algoritma):

Fark Kontrolü: İki sensör arasındaki fark %10'dan fazlaysa bu bir HATADIR. (Örn: Biri 50, diğeri 65 ise fark 15 -> HATA).

Karar:

Eğer hata yoksa: İki sensörün ortalamasını al ve motoru çalıştır.

Eğer hata varsa: Motor gücünü DERHAL 0 yap ve ekrana "IMPLAUSIBILITY ERROR" yaz.

Matematiksel Zorluk: Fark negatif de çıkabilir (40 - 50 = -10). Mutlak değer mantığını (abs fonksiyonu veya if ile) kendiniz kurmalısınız.

🛠️ Teknik Gereksinimler
Struct Zorunluluğu: Tüm veriler (Sensör 1, Sensör 2, Hata Durumu, Sonuç Torku) tek bir struct içinde olmalı.

Kullanıcı Girişi: Program kullanıcıdan 2 sayı girmesini isteyecek: Sensor 1 ve Sensor 2.

Problem Çözme: Hazır abs() fonksiyonu kullanmadan, iki sayı arasındaki farkı pozitif olarak hesaplayan mantığı if-else ile kurun.
