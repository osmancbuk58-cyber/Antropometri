# Antropometri · Cep

Pediatrik antropometri ve büyüme değerlendirme aracı. Polikliniğin omurgası.

## Yapı

**Üst bar (sticky):** cinsiyet + yaş (yıl) + boy (cm) + kilo (kg) → **BMI ve BSA (Mosteller)** anında hesaplanır.

## Sekmeler

### 1. Büyüme
- **WHO/CDC toggle:** Otomatik default (0–5 yaş WHO, &gt; 5 yaş CDC) veya manuel seçim.
- Ağırlık, boy, BMI, baş çevresi (0–5 yaş için) → **z-skor + persentil**.
- Her parametre için kategorik yorum:
  - Ağırlık/boy: ağır düşük / düşük / normal / yüksek
  - BMI: zayıf / normal / kilolu / obez / ağır obez
  - Baş çevresi: mikrosefali / normal / makrosefali

### 2. Boy Hedefi
- **Mid-parental boy:** Anne + baba boyundan hedef + ± 8.5 cm hedef aralık.
- **Büyüme hızı:** İki tarih + iki boy ölçümü → cm/yıl. Yaşa göre beklenen aralık ile kıyasla, patolojik (&lt; 4 cm/yıl 3–10 yaşta) uyarısı.
- Yaşa göre beklenen büyüme hızı referans tablosu.

### 3. Düzeltilmiş Yaş
- Gestasyon haftası + kronolojik yaş (hafta) → düzeltilmiş yaş.
- Ne zaman kullanılır rehberi (büyüme &lt; 3 yaş, nörogelişim &lt; 2 yaş, aşı düzeltme YOK).

### 4. Tanner
- Cinsiyete göre dinamik içerik (E: G + P, K: B + P + menarş).
- Her evre için tarif + yaş normalleri.
- **Prekoks puberte:** kız &lt; 8 yaş, erkek &lt; 9 yaş eşikleri.
- **Geç puberte:** kız 13 yaş B1, erkek 14 yaş G1.
- Adrenarş bilgisi.

## Hesap mantığı

**Persentil:** Yaşa göre çevreleyen iki ay arasında lineer interpolasyon. Kullanıcı değeri persentil tablosundaki hangi aralığa düşüyor, yine lineer interpolasyon ile tahmini persentil.

**Z-skor:** Abramowitz-Stegun yaklaşımı ile persentilden hesaplanır. %0.0001 hata payı.

**BSA:** Mosteller formülü `√(boy × kilo / 3600)`.

**Mid-parental:** `[(anne + baba) / 2] ± 6.5 cm` (erkek +, kız −).

## Veri kaynakları

WHO Child Growth Standards (0–60 ay) + WHO Growth Reference (5–19 yaş) + CDC 2000 Growth Charts (2–20 yaş). 

**⚠ Uyarı:** Veri tabloları eğitim verisindeki referans noktalarından üretilmiştir, ±1–2% hata payı olabilir. Kritik klinik kararda WHO Anthro / WHO Growth Reference Tool / CDC Growth Charts resmi grafiklerini kullan.

## Sorumluluk

Karar destek aracı. Bireysel hasta için kritik kararlarda resmi grafik + uzman onayı esastır.
