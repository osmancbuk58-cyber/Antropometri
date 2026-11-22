# Antropometri · Cep

Pediatrik antropometri ve büyüme aracı. Tek dosya, çevrimdışı çalışır (PWA).

## v0.2 — neler değişti

- **Resmi LMS verisi.** Yaklaşık persentil tabloları kaldırıldı. Hesap resmi LMS parametreleriyle yapılıyor:
  - WHO Child Growth Standards 2006 (0–5 yaş): yaşa göre kilo, boy, BMI, baş çevresi; boya göre kilo
  - WHO Growth Reference 2007 (5–19 yaş; kilo 10 yaşa kadar)
  - CDC 2000 (2–20 yaş): kilo, boy, BMI; p95 üstünde CDC 2022 genişletilmiş BMI
- **Formül:** z = ((X/M)^L − 1) / (L·S). WHO'da |z| > 3 için WHO Anthro düzeltmesi (restricted application).
- **Bu yaş için referans:** yaş girilince kilo, boy, baş çevresi ve BMI için −2 SD / medyan / +2 SD.
- **Boya göre kilo** (WHO, 0–5 yaş) ve bu boy için beklenen kilo (%).
- **Kategoriler referansa göre:** 5 yaş altı WHO z-skor kesimleri, CDC'de BMI p85/p95 ve p95'in %120 / %140'ı (sınıf 2/3 obezite).
- **Yaş girişi:** yıl + ay ya da doğum tarihi + ölçüm tarihi.
- **Prematürite:** doğumdaki GH < 37 hf ise 24 aya kadar persentiller düzeltilmiş yaşla.
- **Hedef boy SDS:** çocuğun boy SDS'i hedef boy SDS'iyle karşılaştırılır (fark < −1,5 SD uyarı).
- Ondalık virgül, çevrimdışı önbellek (sw.js).

## Referans seçimi

- Otomatik: 5 yaş altı WHO 2006, 5 yaş ve üstü CDC 2000
- WHO: 0–5 yaş WHO 2006, 5–19 yaş WHO 2007
- CDC: 2–20 yaş CDC 2000 (24 ay altında WHO 2006 kullanılır)

## Veri kaynağı

LMS tabloları WHO ve CDC'nin yayımladığı dosyalardan alındı; WHO verisi iki bağımsız kaynakla, CDC verisi yayımlanmış medyanlarla karşılaştırıldı. WHO 0–5 yaş tablosu ilk 13 hafta haftalık, sonra aylık örneklenip doğrusal interpolasyonla hesaplanır.

Klinik karar desteği içindir; sonuçları klinik değerlendirmeyle birlikte yorumla.
