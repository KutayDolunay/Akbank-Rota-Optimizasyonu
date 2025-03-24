# Sürücüsüz Metro Simülasyonu (Rota Optimizasyonu)

Bu proje, bir metro ağında iki istasyon arasındaki en hızlı ve en az aktarmalı rotayı bulan bir simülasyon geliştirmek için hazırlanmıştır.

## 📌 Proje Amacı
Bu projede aşağıdaki hedeflere ulaşmanız beklenmektedir:
1. Graf veri yapısını kullanarak metro ağını modelleme
2. BFS (Breadth-First Search) algoritması ile en az aktarmalı rotayı bulma
3. A* algoritması ile en hızlı rotayı bulma
4. Gerçek dünya problemlerini algoritmik düşünce ile çözme

## 🚀 Kullanılan Teknolojiler ve Kütüphaneler
- **Python** (Ana programlama dili)
- **collections** (BFS için deque veri yapısı)
- **heapq** (A* algoritması için öncelik kuyruğu)
- **typing** (Tip ipuçları için)

## 🔍 Algoritmaların Çalışma Mantığı
### BFS Algoritması (en_az_aktarma_bul)
BFS (Breadth-First Search) algoritması, en az aktarma yapan rotayı bulmak için kullanılır:
1. Başlangıç istasyonundan itibaren genişlik öncelikli olarak istasyonlar ziyaret edilir.
2. Kuyruk yapısı (deque) kullanılarak komşu istasyonlar eklenir.
3. Daha önce ziyaret edilen istasyonlar tekrar ziyaret edilmez.
4. Hedef istasyona ulaşıldığında, en az aktarma yapılan rota döndürülür.

### A* Algoritması (en_hizli_rota_bul)
A* algoritması, en hızlı rotayı bulmak için kullanılır:
1. Öncelik kuyruğu (heapq) ile her istasyon için en kısa sürede ulaşılabilecek komşular hesaplanır.
2. Her istasyon için en düşük maliyetli yol saklanır.
3. Daha önce bulunan süreden daha kısa bir sürede ulaşılan istasyonlar tekrar değerlendirilir.
4. Hedef istasyona ulaşıldığında en hızlı rota ve toplam süre döndürülür.

## 🎯 Örnek Kullanım
```python
metro = MetroAgi()
metro.istasyon_ekle("K1", "Kızılay", "Kırmızı Hat")
metro.istasyon_ekle("K2", "Ulus", "Kırmızı Hat")
metro.baglanti_ekle("K1", "K2", 4)

rota = metro.en_az_aktarma_bul("K1", "K2")
print("En az aktarmalı rota:", " -> ".join(i.ad for i in rota))
```

## 🛠️ Projeyi Geliştirme Fikirleri
- Daha büyük bir metro ağı ekleyerek simülasyonu genişletme
- Harita veya grafik tabanlı görselleştirme ekleme
- Kullanıcıdan başlangıç ve hedef istasyonları alarak interaktif bir terminal uygulaması yapma

