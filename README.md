# Gelişmiş Online Bilimsel Grafik Platformu

Bu paket, CSV, Excel ve NetCDF dosyalarından online grafik, harita, CTD profili, istatistik ve rapor çıktısı üretmek için hazırlanmıştır.

## Ana özellikler

- X/Y/Z eksen seçimi
- Çizgi, saçılım, 3B saçılım, sütun, yatay sütun, kutu, violin, histogram
- Yoğunluk ısı haritası, yoğunluk kontur, pivot ısı haritası
- Radar grafiği, korelasyon matrisi
- CTD derinlik profili, çoklu profil, T-S diyagramı
- Hovmöller ve transekt/kesit grafikleri
- Oksijen eşik çizgileri: 5 mg/L ve 2 mg/L
- Harita ve uydu/grid görselleştirme
- 1 m derinlik ortalaması
- Veri kalite kontrol özeti
- Tanımlayıcı istatistik, korelasyon, PCA biplot, Mann-Kendall trend
- HTML, PNG, SVG, PDF, CSV, Word ve PowerPoint çıktı seçenekleri

## Örnek veri setleri

`sample_data` klasöründe deneme için sentetik örnek veri setleri vardır:

- `ornek_ctd_profilleri.csv`
- `ornek_secchi_optik_su_kalitesi.csv`
- `ornek_uydu_grid_karadeniz.csv`
- `ornek_istasyon_koordinatlari.csv`
- `ornek_veri_setleri.xlsx`

Bu veriler gerçek ölçüm değildir; programı test etmek için üretilmiş sentetik verilerdir.

## Yerelde çalıştırma

```bash
pip install -r requirements.txt
streamlit run app.py
```

## Online yayınlama

1. GitHub'da yeni bir repository oluşturun.
2. Bu klasördeki dosyaları GitHub'a yükleyin.
3. Streamlit Community Cloud'a girin.
4. GitHub repository'yi seçin.
5. Main file path olarak `app.py` yazın.
6. Deploy düğmesine basın.

## Önerilen kullanım

### CTD verisi

- Sekme: CTD / profil
- Grafik: Derinlik profili, T-S diyagramı, Hovmöller veya transekt/kesit
- Derinlik: Depth_m
- Parametre: Temperature_C, Salinity_PSU, Oxygen_mgL, pH, Chl_a_ugL
- Grup: Station, Cast_ID, Month veya Season

### Secchi-optik veri

- Sekme: Genel grafik veya İstatistik
- Scatter: Secchi_m vs Chl_a_ugL
- Trend: Year vs Secchi_m
- Boxplot: Season vs Secchi_m
- Korelasyon: Secchi_m, Chl_a_ugL, TSS_mgL, Turbidity_NTU

### Uydu grid veri

- Sekme: Harita / uydu
- Harita türü: Uydu grid ısı haritası
- Enlem: Latitude
- Boylam: Longitude
- Renk/Z: chlor_a_mg_m3, spm_mg_L veya turbidity_FNU


## Yeni eklenen özellikler
- Haritada istasyon adlarını gösterme
- Haritada kesit/transekt çizgisini istasyonları birleştirerek gösterme
- Hovmöller ve kesit grafiklerinde kontur/kesit çizgilerini gösterme
- Örnek veri setlerine Transect, Section_Name ve Station_Order sütunları eklenmiştir
- Streamlit tekrar grafik kimliği hatasını önlemek için grafik anahtarları güncellenmiştir
