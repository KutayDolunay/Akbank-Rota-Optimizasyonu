# Metro Ağı Simülasyonu

Bu proje, bir şehirdeki metro ağını modelleyerek en kısa ve en az aktarmalı rotaları bulmayı sağlayan bir Python uygulamasıdır.

## Özellikler
- **İstasyon Yönetimi**: Yeni istasyonlar ekleyebilir ve istasyonları belirli hatlara bağlayabilirsiniz.
- **Bağlantı Yönetimi**: İstasyonlar arasında seyahat süresi bazında bağlantılar oluşturabilirsiniz.
- **En Az Aktarmalı Rota**: BFS algoritması ile aktarma sayısı en az olan rotayı hesaplar.
- **En Hızlı Rota**: A* algoritması ile toplam süreyi minimize eden en hızlı rotayı hesaplar.

## Kullanılan Algoritmalar
- **BFS (Breadth-First Search)**: En az aktarma ile bir istasyondan diğerine ulaşmak için kullanılır.
- **A* Algoritması**: İstasyonlar arasındaki bağlantı sürelerini dikkate alarak en hızlı rotayı bulur.

## Kurulum
Bu projeyi çalıştırmak için aşağıdaki adımları takip edebilirsiniz:

1. **Depoyu Kopyalayın**
   ```bash
   git clone https://github.com/kullaniciadi/metro-agi.git
   cd metro-agi
   ```

2. **Python Gereksinimlerini Karşılayın**
   Python 3.x yüklü olmalıdır. Eğer sisteminizde Python yoksa [Python'un resmi web sitesinden](https://www.python.org/) yükleyebilirsiniz.
   
3. **Dosyayı Çalıştırın**
   ```bash
   python metro.py
   ```

## Kullanım

Örnek bir metro ağı oluşturmak için aşağıdaki adımları takip edebilirsiniz:

```python
from metro import MetroAgi

metro = MetroAgi()

# İstasyon ekleme
metro.istasyon_ekle("K1", "Kızılay", "Kırmızı Hat")
metro.istasyon_ekle("K2", "Ulus", "Kırmızı Hat")
metro.istasyon_ekle("M1", "AŞTİ", "Mavi Hat")
metro.istasyon_ekle("M2", "Kızılay", "Mavi Hat")

# Bağlantı ekleme
metro.baglanti_ekle("K1", "K2", 4)
metro.baglanti_ekle("M1", "M2", 5)
metro.baglanti_ekle("K1", "M2", 2)  # Aktarma noktası

# En az aktarmalı rota
rota = metro.en_az_aktarma_bul("M1", "K2")
print("En az aktarmalı rota:", " -> ".join(i.ad for i in rota))

# En hızlı rota
sonuc = metro.en_hizli_rota_bul("M1", "K2")
if sonuc:
    rota, sure = sonuc
    print(f"En hızlı rota ({sure} dakika):", " -> ".join(i.ad for i in rota))
```

## Örnek Çıktılar
```
=== Test Senaryoları ===

1. AŞTİ'den OSB'ye:
En az aktarmalı rota: AŞTİ -> Kızılay -> Ulus -> Demetevler -> OSB
En hızlı rota (15 dakika): AŞTİ -> Kızılay -> Ulus -> Demetevler -> OSB

2. Batıkent'ten Keçiören'e:
En az aktarmalı rota: Batıkent -> Demetevler -> Gar -> Keçiören
En hızlı rota (21 dakika): Batıkent -> Demetevler -> Gar -> Keçiören
```

## Katkıda Bulunma
Eğer projeye katkıda bulunmak isterseniz:
1. **Bu repoyu fork edin**
2. **Yeni bir branch oluşturun**: `git checkout -b yeni-ozellik`
3. **Değişiklikleri yapın ve commit atın**: `git commit -m 'Yeni özellik eklendi'`
4. **Push yapın**: `git push origin yeni-ozellik`
5. **Pull request açın**

## Lisans
Bu proje MIT lisansı ile sunulmaktadır. Daha fazla bilgi için `LICENSE` dosyasına bakabilirsiniz.

