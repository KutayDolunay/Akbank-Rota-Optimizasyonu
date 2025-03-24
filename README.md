# Sürücüsüz Metro Simülasyonu (Rota Optimizasyonu)

Bu proje, bir metro ağında iki istasyon arasındaki en hızlı ve en az aktarmalı rotayı bulan bir simülasyon geliştirmek için hazırlanmıştır.

## 📌 Proje Amacı
Bu projede aşağıdaki hedeflere ulaşmanız beklenmektedir:
1. Graf veri yapısını kullanarak metro ağını modelleme
2. BFS (Breadth-First Search) algoritması ile en az aktarmalı rotayı bulma
3. A* algoritması ile en hızlı rotayı bulma
4. Gerçek dünya problemlerini algoritmik düşünce ile çözme

## 🚀 Kullanılan Teknolojiler ve Kütüphaneler
- **Python**
- **collections** 
- **heapq** 

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

## 🎯 Test Senaryoları
=== Test Senaryoları ===

1. AŞTİ'den OSB'ye:
En az aktarmalı rota: AŞTİ -> Kızılay -> Kızılay -> Ulus -> Demetevler -> OSB
En hızlı rota (25 dakika): AŞTİ -> Kızılay -> Kızılay -> Ulus -> Demetevler -> OSB

2. Batıkent'ten Keçiören'e:
En az aktarmalı rota: Batıkent -> Demetevler -> Gar -> Keçiören
En hızlı rota (21 dakika): Batıkent -> Demetevler -> Gar -> Keçiören

3. Keçiören'den AŞTİ'ye:
En az aktarmalı rota: Keçiören -> Gar -> Gar -> Sıhhiye -> Kızılay -> AŞTİ
En hızlı rota (19 dakika): Keçiören -> Gar -> Gar -> Sıhhiye -> Kızılay -> AŞTİ

## 🛠️ Projeyi Geliştirme Fikirleri
- Daha büyük bir metro ağı ekleyerek simülasyonu genişletme
- Harita veya grafik tabanlı görselleştirme ekleme
- Kullanıcıdan başlangıç ve hedef istasyonları alarak interaktif bir terminal uygulaması yapma

## Not! 
Ek olarak heuristikli bir dosya mevcut büyük networklerde daha hızlı çalışıyor!
