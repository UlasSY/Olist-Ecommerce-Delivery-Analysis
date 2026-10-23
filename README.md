# Olist E-Ticaret: Bölgesel Sipariş ve Lojistik Performans Analizi

Bu repository, **VBO AI & Data Summer Camp 2026** kapsamında gerçekleştirilen Olist e-ticaret veri analizi çalışmasının, GitHub portföyü için yeniden düzenlenmiş versiyonunu içermektedir.

Projede Python ve Pandas kullanılarak sipariş hacmi, eyalet bazlı ortalama sipariş değeri ve teslimat performansı analiz edilmiştir. Analiz sonuçlarının ilişkisel bir veritabanında saklanabilmesi amacıyla PostgreSQL ve SQLAlchemy entegrasyonu da hazırlanmıştır.

## Proje Amacı

E-ticaret sipariş verileri üzerinden:

- Eyalet bazında sipariş yoğunluğunu,
- Ortalama sipariş değerlerini,
- Teslimat sürelerini,
- Bölgesel lojistik performans farklılıklarını

incelemek ve elde edilen sonuçları iş perspektifinden değerlendirmek amaçlanmıştır.

Çalışma, eğitim kapsamında verilen analiz sorularının tamamlanmasının ardından, daha düzenli ve portföy odaklı bir notebook yapısına dönüştürülmüştür.

## Repository İçeriği

- olist_delivery_analysis.ipynb — Veri hazırlama, keşifsel veri analizi, görselleştirmeler, bölgesel teslimat performansı değerlendirmeleri ve PostgreSQL entegrasyonunu içeren ana notebook.

- README.md — Türkçe proje dokümantasyonu.

- README_Eng.md — İngilizce proje dokümantasyonu.

- olist_customers_dataset.csv — Müşteri kimlikleri ve coğrafi konum bilgileri.

- olist_order_items_dataset.csv — Sipariş kalemleri, satıcı bilgileri, ürün fiyatları ve kargo ücretleri.

- olist_orders_dataset.csv — Sipariş durumları, satın alma zamanları ve teslimat tarihleri.

## Veri Seti

Projede Olist e-ticaret platformuna ait halka açık sipariş verileri kullanılmıştır.

Notebook içerisinde kullanılan temel tablolar:

- `olist_orders_dataset.csv` — Sipariş durumu, satın alma ve teslimat zaman bilgileri
- `olist_order_items_dataset.csv` — Sipariş ürünleri, fiyat ve kargo bilgileri
- `olist_customers_dataset.csv` — Müşteri ve eyalet bilgileri

Veriler, VBO Summer Camp 2026 kapsamında kullanılan halka açık GitHub veri kaynağından çalışma sırasında yüklenmektedir.

## Analiz Kapsamı

Notebook içerisinde aşağıdaki analizler gerçekleştirilmiştir:

- Eyalet bazında sipariş hacmi analizi
- Eyalet bazında ortalama sipariş değeri (AOV) analizi
- Genel teslimat süresi ve SLA analizi
- Eyalet bazında ortalama teslimat süresi karşılaştırması
- Ortalama teslimat süresi en uzun ilk 5 eyalet
- En hızlı ve en yavaş eyalet arasındaki teslimat süresi farkı
- Temel metriklerin görselleştirilmesi
- Analiz sonuçlarının iş perspektifinden değerlendirilmesi
- Analiz çıktılarının PostgreSQL'e aktarılması için veritabanı entegrasyonu

## Kullanılan Teknolojiler

- Python
- Pandas
- NumPy
- Matplotlib
- PostgreSQL
- SQLAlchemy
- Jupyter Notebook
- Google Colab

## Öne Çıkan Bulgular

- Analiz kapsamında 99.441 sipariş ve 112.650 sipariş kalemi incelenmiştir.
- Müşteri kayıtları 27 farklı Brezilya eyaletini kapsamaktadır.
- São Paulo (SP), 41.746 siparişle en yüksek sipariş hacmine sahip eyalettir.
- Teslim edilmiş siparişlerde medyan teslimat süresi 10 gün, P90 teslimat süresi 23 gündür.
- Eyaletlerin ortalama teslimat süreleri arasında yaklaşık 20,68 günlük fark bulunmaktadır.
- Sipariş hacmi, teslimat süresi, P90 ve ortalama sipariş değerinin birlikte değerlendirilmesi, bölgesel performans farklılıklarını daha kapsamlı incelemeyi sağlar.

**İş perspektifi:** Yüksek sipariş hacmine sahip bölgeler ile uzun teslimat sürelerinin görüldüğü bölgeler ayrı ayrı değerlendirilmelidir. Gecikmelerin olası nedenlerini doğrulamak için coğrafi mesafe, kargo maliyetleri ve lojistik ağ yapısı gibi ek değişkenlerle ileri analiz yapılabilir.

*Not: Bulgular mevcut veri setinin betimleyici analizine dayanır; gözlemlenen bölgesel farklılıklar tek başına neden-sonuç ilişkisi göstermez.*

## Gereksinimler ve Çalıştırma

Projeyi Jupyter Notebook, JupyterLab, VS Code veya Google Colab üzerinde çalıştırabilirsiniz.

Gerekli temel kütüphaneler:

```bash
pip install pandas numpy matplotlib sqlalchemy psycopg2-binary
```

Notebook içerisindeki veri yükleme işlemi GitHub üzerindeki kaynak üzerinden gerçekleştirildiği için veri setlerinin ayrıca indirilmesi gerekmemektedir.

PostgreSQL entegrasyonunu çalıştırmak için `DATABASE_URL` ortam değişkeninin tanımlanması gerekir. Bağlantı bilgileri repository içerisinde açık şekilde tutulmamalıdır.

## Proje Notu

Bu çalışma eğitim kapsamında oluşturulan bir veri analizi projesinin, GitHub üzerinde daha okunabilir ve portföy odaklı bir şekilde sunulması amacıyla yeniden düzenlenmiş versiyonudur.

Notebook içerisinde analiz adımları, görselleştirmeler ve iş perspektifinden değerlendirmeler birlikte sunulmaktadır.
