# 🎮 Türkçe Video Oyunları Haber Hesabı için X Algoritma Kılavuzu

> Bu kılavuz, X (eski adıyla Twitter) algoritmasının nasıl çalıştığına dayanarak, IGN veya PCGamer gibi bir Türkçe video oyunları haber hesabının etkileşimini ve görünürlüğünü maksimize etmek için hazırlanmıştır.

---

## 📑 İçindekiler

- [Algoritma Nasıl Çalışır?](#algoritma-nasıl-çalışır)
- [Etkileşim Sinyalleri ve Ağırlıkları](#etkileşim-sinyalleri-ve-ağırlıkları)
- [En Etkili Paylaşım Tipleri](#en-etkili-paylaşım-tipleri)
- [Türkiye İçin Optimal Paylaşım Saatleri](#türkiye-için-optimal-paylaşım-saatleri)
- [İçerik Stratejileri](#içerik-stratejileri)
- [Kaçınılması Gerekenler](#kaçınılması-gerekenler)
- [Haftalık Paylaşım Planı](#haftalık-paylaşım-planı)
- [Teknik Optimizasyon İpuçları](#teknik-optimizasyon-ipuçları)

---

## 🧠 Algoritma Nasıl Çalışır?

X'in "Sana Özel" (For You) akışı, içerikleri iki kaynaktan çeker:

### 1. Ağ İçi (In-Network) - Thunder Sistemi
- **Takip edilen hesaplardan gelen paylaşımlar**
- Alt milisaniye hızında çalışır
- Son paylaşımlar gerçek zamanlı olarak işlenir

### 2. Ağ Dışı (Out-of-Network) - Phoenix Sistemi
- **Takip etmediğiniz hesaplardan keşif**
- ML tabanlı benzerlik araması
- Kullanıcının etkileşim geçmişine göre ilgili içerikler bulunur

### Puanlama Süreci
Her paylaşım, bir Grok tabanlı transformer modeli tarafından şu eylemlerin olasılıkları hesaplanarak puanlanır:

```
P(beğeni) + P(yanıt) + P(retweet) + P(alıntı) + P(tıklama) + 
P(profil tıklaması) + P(video görüntüleme) + P(fotoğraf genişletme) + 
P(paylaşım) + P(kalma süresi) + P(yazar takibi) - 
P(ilgilenmiyorum) - P(engelle) - P(sessize al) - P(raporla)
```

**Pozitif etkileşimler puanı artırır, negatif etkileşimler düşürür.**

---

## ⚖️ Etkileşim Sinyalleri ve Ağırlıkları

X algoritması aşağıdaki sinyalleri ağırlıklandırarak sıralama yapar:

### 🟢 Yüksek Pozitif Etki (En Değerli)

| Sinyal | Açıklama | Önem |
|--------|----------|------|
| **Retweet/Repost** | Paylaşımın yeniden paylaşılması | ⭐⭐⭐⭐⭐ |
| **Alıntı Tweetleme** | Yorumlu paylaşım | ⭐⭐⭐⭐⭐ |
| **Yanıt (Reply)** | Paylaşıma yorum yapılması | ⭐⭐⭐⭐ |
| **Beğeni (Like)** | Kalp butonu tıklaması | ⭐⭐⭐⭐ |
| **Yazar Takibi** | Paylaşım sonrası hesap takibi | ⭐⭐⭐⭐⭐ |

### 🔵 Orta Pozitif Etki

| Sinyal | Açıklama | Önem |
|--------|----------|------|
| **Video Görüntüleme (VQV)** | Kaliteli video izleme süresi | ⭐⭐⭐⭐ |
| **Link Paylaşımı** | Paylaşım butonuyla paylaşma | ⭐⭐⭐ |
| **DM ile Paylaşım** | Direkt mesaj ile gönderim | ⭐⭐⭐ |
| **Link Kopyalama** | Paylaşım linkinin kopyalanması | ⭐⭐⭐ |
| **Profil Tıklaması** | Hesap profilini ziyaret | ⭐⭐⭐ |

### 🟡 Düşük Pozitif Etki

| Sinyal | Açıklama | Önem |
|--------|----------|------|
| **Tıklama (Click)** | Paylaşıma tıklama | ⭐⭐ |
| **Fotoğraf Genişletme** | Görseli büyütme | ⭐⭐ |
| **Kalma Süresi (Dwell)** | Paylaşımda geçirilen süre | ⭐⭐ |
| **Alıntı Tıklaması** | Alıntılanan içeriğe tıklama | ⭐⭐ |

### 🔴 Negatif Etki (Kaçınılması Gerekenler)

| Sinyal | Açıklama | Etki |
|--------|----------|------|
| **İlgilenmiyorum** | "Not Interested" tıklaması | ❌❌❌ |
| **Yazar Engelleme** | Hesabın engellenmesi | ❌❌❌❌❌ |
| **Yazar Sessize Alma** | Hesabın sessize alınması | ❌❌❌❌ |
| **Raporlama** | Paylaşımın raporlanması | ❌❌❌❌❌ |

---

## 📱 En Etkili Paylaşım Tipleri

### 1. 🎬 Video İçerikler (EN YÜKSEK ÖNCELİK)

Video içerikler, VQV (Video Quality View) metriği sayesinde çok değerlidir.

**Optimal Video Özellikleri:**
- **Süre:** Minimum 30 saniye (algoritma 30 sn+ videoları ödüllendirir)
- **İdeal süre:** 45-90 saniye (oyun haberleri için)
- **Uzun içerik:** 2-5 dakika (detaylı analizler/incelemeler için)

**Video İçerik Türleri:**
| Tür | Açıklama | Örnek |
|-----|----------|-------|
| **Oyun Duyuruları** | Trailer ve teaser'lar | "GTA 6 Yeni Trailer!" |
| **Gameplay Klipler** | Kısa oyun içi anlar | "Elden Ring Boss Fight" |
| **Haber Özeti** | Günlük/haftalık özet | "Bu Hafta Oyun Dünyası" |
| **Quick Review** | Hızlı inceleme | "60 Saniyede Marvel's Spider-Man 2" |
| **Karşılaştırma** | A vs B formatı | "PS5 vs Xbox Series X Grafik Testi" |

### 2. 🖼️ Görsel İçerikler

**Fotoğraf Genişletme** sinyali önemli bir etkileşim metriğidir.

**Görsel Türleri:**
| Tür | Detay | İpucu |
|-----|-------|-------|
| **Screenshot Karşılaştırma** | Grafik kıyaslamaları | 4'lü carousel kullan |
| **Infografik** | Bilgi görselleri | Türkçe ve okunaklı |
| **Konsept Art** | Oyun sanatı | Kaynak belirt |
| **Meme** | Oyun mizahı | Güncel ve alakalı |
| **Çıkış Takvimi** | Aylık oyun listesi | Düzenli güncelle |

**Carousel (Çoklu Görsel) Stratejisi:**
- 2-4 görsel optimal
- Her görsel hikayeyi devam ettirmeli
- Son görselde CTA (call-to-action)

### 3. 💬 Metin Bazlı Paylaşımlar

**Yanıt ve Alıntı** sinyalleri için optimize edilmiş içerikler.

**Etkili Formatlar:**
```
🎮 HABER: [Başlık]

[2-3 satır özet]

💭 Ne düşünüyorsunuz?

[İlgili hashtag'ler]
```

**Thread (Konu) Formatı:**
```
🧵 [KONU BAŞLIĞI]

1/X [Giriş - dikkat çekici]

2/X [Detay 1]

3/X [Detay 2]

...

X/X [Sonuç + Tartışma sorusu]
```

### 4. 📊 Anket ve Soru İçerikleri

Anketler yüksek etkileşim sağlar:

**Anket Türleri:**
| Format | Örnek |
|--------|-------|
| **VS Anketi** | "Daha çok hangisini bekliyorsunuz? 🎮 GTA 6 vs Elder Scrolls 6" |
| **Tercih Anketi** | "Bu yılın en iyi oyunu hangisi?" |
| **Tahmin Anketi** | "Game Awards 2024 GOTY kim alacak?" |

### 5. 🔗 Link İçerikler

Link paylaşımları tıklama ve paylaşım metrikleri için önemlidir:

**Optimizasyon İpuçları:**
- Dikkat çekici başlık yazın
- Açıklama metninde merak uyandırın
- Native video varsa linksiz de paylaşın

---

## 🕐 Türkiye İçin Optimal Paylaşım Saatleri

Türkiye saat dilimi (UTC+3) için optimize edilmiş paylaşım stratejisi:

### 📅 Hafta İçi (Pazartesi - Cuma)

| Zaman Dilimi | Saat | Aktivite Seviyesi | Önerilen İçerik |
|--------------|------|-------------------|-----------------|
| **Sabah Erken** | 07:00 - 09:00 | ⭐⭐⭐ | Gece boyunca biriken haberler, özet |
| **Öğle Molası** | 12:00 - 14:00 | ⭐⭐⭐⭐⭐ | Ana haberler, hızlı içerikler |
| **İş Çıkışı** | 17:00 - 19:00 | ⭐⭐⭐⭐⭐ | Video içerikler, incelemeler |
| **Prime Time** | 20:00 - 23:00 | ⭐⭐⭐⭐⭐ | En önemli haberler, tartışmalar |
| **Gece** | 23:00 - 01:00 | ⭐⭐⭐⭐ | Hardcore oyuncu kitlesi |

### 📅 Hafta Sonu (Cumartesi - Pazar)

| Zaman Dilimi | Saat | Aktivite Seviyesi | Önerilen İçerik |
|--------------|------|-------------------|-----------------|
| **Sabah** | 10:00 - 12:00 | ⭐⭐⭐⭐ | Hafta özeti, büyük haberler |
| **Öğleden Sonra** | 14:00 - 17:00 | ⭐⭐⭐⭐⭐ | Detaylı içerikler, thread'ler |
| **Akşam** | 19:00 - 23:00 | ⭐⭐⭐⭐⭐ | Video içerikler, canlı etkinlikler |
| **Gece** | 23:00 - 02:00 | ⭐⭐⭐⭐ | Uluslararası etkinlik coverage |

### 🎯 Özel Zamanlamalar

| Etkinlik | Zamanlama | Strateji |
|----------|-----------|----------|
| **Nintendo Direct** | Genellikle 17:00-18:00 TR | Canlı tweet, anında özet |
| **PlayStation Showcase** | Genellikle 23:00-00:00 TR | Thread hazırla, canlı paylaş |
| **Xbox Showcase** | Genellikle 20:00-21:00 TR | Prime time, maksimum erişim |
| **Game Awards** | Aralık, gece saatleri | Gece boyunca coverage |
| **E3/Summer Game Fest** | Haziran, çeşitli saatler | Yoğun paylaşım programı |
| **Oyun Çıkışları** | Genellikle 00:00 veya 19:00 | Embargo kalktığında hemen |

### ⏰ Günlük Paylaşım Sıklığı

| Hesap Büyüklüğü | Minimum | Optimal | Maksimum |
|-----------------|---------|---------|----------|
| **Küçük (0-10K)** | 5 | 8-10 | 15 |
| **Orta (10K-50K)** | 8 | 12-15 | 20 |
| **Büyük (50K+)** | 10 | 15-20 | 25+ |

**Not:** Kalite > Miktar. Spam algısı algoritmayı olumsuz etkiler.

---

## 🎯 İçerik Stratejileri

### 1. Etkileşim Odaklı Taktikler

#### Yanıt (Reply) Artırma
```
✅ Soru ile bitirin: "Siz ne düşünüyorsunuz?"
✅ Tartışma başlatın: "Katılıyor musunuz?"
✅ Deneyim isteyin: "Siz de yaşadınız mı?"
✅ Tahmin sorun: "Sizce ne olacak?"
```

#### Retweet Artırma
```
✅ Değerli bilgi paylaşın
✅ Hızlı/özet içerik oluşturun
✅ İlk haber olun
✅ Özel/sızdırılmış bilgi paylaşın
```

#### Takip Artırma
```
✅ Tutarlı içerik kalitesi
✅ Niş uzmanlık gösterin
✅ Topluluğa değer katın
✅ Etkileşimde bulunun
```

### 2. İçerik Kategorileri Dağılımı

Optimal içerik mix'i:

```
📊 İçerik Dağılımı (Örnek)

🔴 HABER: %40
   ├── Son dakika: %15
   ├── Duyurular: %15
   └── Güncellemeler: %10

🎬 VİDEO: %25
   ├── Trailer/Teaser: %10
   ├── Gameplay: %10
   └── Özet/Analiz: %5

💬 ETKİLEŞİM: %20
   ├── Anket: %8
   ├── Soru: %7
   └── Tartışma: %5

📚 EVERGREEN: %15
   ├── Rehber/İpucu: %8
   └── Liste/Ranking: %7
```

### 3. Hashtag Stratejisi

**Türkçe Oyun Hashtag'leri:**
| Kategori | Hashtag'ler |
|----------|-------------|
| **Genel** | #oyun #gaming #türkçeoyun #oyunhaberleri |
| **Platform** | #PlayStation #Xbox #NintendoSwitch #PC #Steam |
| **Türler** | #FPS #RPG #MMORPG #Indie #BattleRoyale |
| **Özel** | #OyunInceleme #YeniOyun #OyunDünyası |

**Hashtag Kuralları:**
- Maksimum 3-5 hashtag kullanın
- İlk yoruma da hashtag ekleyebilirsiniz
- Trend hashtag'leri takip edin
- Spam görünümünden kaçının

### 4. Thread (Konu) Stratejisi

Thread'ler kalma süresi ve tıklama metriklerini artırır:

**Etkili Thread Formatı:**
```
🧵 [Sayı] + [Başlık] + [Emoji]

Örnek:
🧵 10 ADIMDA: Elden Ring Başlangıç Rehberi ⚔️
```

**Thread Yapısı:**
1. **Hook (Dikkat Çekici Giriş)** - İlk tweet en önemli
2. **Değer** - Her tweet tek bir bilgi
3. **Görsel** - Mümkünse her tweet'e görsel
4. **CTA** - Son tweet'te aksiyon çağrısı

### 5. Topluluk Yönetimi

Algoritma, etkileşim geçmişine önem verir:

**Aktif Topluluk Taktikleri:**
| Taktik | Uygulama |
|--------|----------|
| **Yanıt Verme** | Her yoruma cevap verin (ilk 1 saat kritik) |
| **RT/Quote** | Takipçi içeriklerini paylaşın |
| **Mention** | İlgili kişileri etiketleyin |
| **Collab** | Diğer oyun hesaplarıyla işbirliği |

---

## ❌ Kaçınılması Gerekenler

### Algoritma Cezaları

| Davranış | Sonuç | Önlem |
|----------|-------|-------|
| **Spam paylaşım** | Erişim düşüşü | Kaliteye odaklan |
| **Clickbait** | "İlgilenmiyorum" sinyali | Dürüst başlıklar |
| **Aşırı hashtag** | Spam algısı | Max 5 hashtag |
| **Kopya içerik** | Duplicate filtresi | Özgün ol |
| **Tartışmalı içerik** | Report sinyali | Dikkatli ol |
| **Takip/Takipten çık** | Spam algısı | Organik büyüme |

### İçerik Filtreleri

X algoritması şu içerikleri filtreler:
- Silinen paylaşımlar
- Spam işaretli içerikler
- Şiddet/Gore içerikler
- Raporlanmış paylaşımlar
- Çok eski paylaşımlar

### Dikkat Edilmesi Gerekenler

```
❌ Asla:
├── Sahte haber paylaşmayın
├── Telif haklı içeriği izinsiz kullanmayın
├── Aşırı negatif/toxic olmayın
├── Bot aktivitesi yapmayın
└── Diğer hesaplarla koordineli davranmayın

⚠️ Dikkatli:
├── Spoiler içeriklerinde uyarı verin
├── Hassas konularda dikkatli olun
├── Kaynak belirtin
└── Hata yaparsanız düzeltin
```

---

## 📆 Haftalık Paylaşım Planı

### Örnek Haftalık Takvim

| Gün | Sabah (08-09) | Öğle (12-13) | Akşam (19-20) | Gece (22-23) |
|-----|---------------|--------------|---------------|--------------|
| **Pzt** | Hafta özeti | Haber | Video | Anket |
| **Sal** | Haber | Meme/Eğlence | İnceleme | Thread |
| **Çar** | Haber | Haber | Video | Tartışma |
| **Per** | Haber | Rehber/İpucu | Video | Haber |
| **Cum** | Haber | Liste | Hafta sonu planı | Canlı event |
| **Cmt** | Rahat içerik | Detaylı thread | Video marathon | Topluluk |
| **Paz** | Rahat içerik | Önizleme | Hafta özeti | Sonraki hafta |

### Özel Gün Stratejileri

| Gün/Dönem | Strateji |
|-----------|----------|
| **Oyun Çıkış Günü** | Embargo kalkışında inceleme, sürekli güncelleme |
| **Büyük Etkinlik** | Canlı tweet, thread, hızlı özet |
| **Tatil Dönemleri** | Retrospektif, liste, evergreen içerik |
| **İndirim Dönemleri** | Steam Sale, PS/Xbox sale rehberleri |

---

## 🔧 Teknik Optimizasyon İpuçları

### 1. Profil Optimizasyonu

```
✅ Profil Checklist:
├── Profesyonel profil fotoğrafı
├── Tanımlayıcı banner
├── Açık bio (ne yaptığınız belli olsun)
├── Website linki
├── Konum (Türkiye)
└── Doğrulanmış hesap (mümkünse)
```

### 2. Paylaşım Teknik Detayları

**Video Teknik Özellikleri:**
| Özellik | Optimal |
|---------|---------|
| Format | MP4 (H.264) |
| Çözünürlük | 1920x1080 (16:9) veya 1080x1080 (1:1) |
| FPS | 30 veya 60 |
| Süre | 30 sn - 2 dk 20 sn |
| Altyazı | Türkçe altyazı ekleyin |

**Görsel Teknik Özellikleri:**
| Özellik | Optimal |
|---------|---------|
| Format | PNG veya JPG |
| Boyut | 1200x675 (16:9) veya 1080x1080 (1:1) |
| Dosya boyutu | Max 5MB |
| Renk | Canlı, dikkat çekici |

### 3. Analytics ve Takip

Düzenli olarak şunları takip edin:
- **Impression (Gösterim):** Kaç kişiye ulaştınız
- **Engagement Rate:** Etkileşim oranı
- **Profile Visits:** Profil ziyaretleri
- **Follower Growth:** Takipçi artışı
- **Top Posts:** En iyi performans gösteren paylaşımlar

### 4. Araç Önerileri

| Araç | Kullanım |
|------|----------|
| **X Analytics** | Native analitik |
| **TweetDeck** | Çoklu hesap yönetimi |
| **Canva** | Görsel tasarım |
| **CapCut/Premiere** | Video düzenleme |
| **Buffer/Hootsuite** | Zamanlama |

---

## 📈 Büyüme Metrikleri

### Hedef Belirleme

| Metrik | Başlangıç | 3 Ay | 6 Ay | 1 Yıl |
|--------|-----------|------|------|-------|
| **Takipçi** | 0 | 5K | 15K | 50K |
| **Avg. Impression** | 100 | 5K | 20K | 100K |
| **Engagement Rate** | %2 | %3 | %4 | %5 |
| **Günlük Post** | 5 | 10 | 15 | 15-20 |

### KPI'lar

**Haftalık Takip:**
- Takipçi değişimi
- Top 5 post performansı
- Engagement rate ortalaması
- Profile visit sayısı

**Aylık Analiz:**
- İçerik tipi performans karşılaştırması
- En iyi paylaşım saatleri analizi
- Rakip analizi
- Strateji güncellemesi

---

## 🎮 Oyun Türüne Göre İçerik Stratejileri

### AAA Oyunlar
- Duyuru anında paylaşım
- Detaylı thread'ler
- Karşılaştırma içerikleri
- Topluluk beklentileri

### Indie Oyunlar
- Keşif içerikleri
- Geliştirici röportajları
- Hidden gem listeleri
- Topluluk spotlight

### Esports
- Canlı turnuva coverage
- Takım/oyuncu haberleri
- Maç özeti ve highlight
- Tahmin anketleri

### Mobile Gaming
- Yeni çıkışlar
- Güncelleme haberleri
- Ücretsiz oyun önerileri
- Battle pass/event bilgileri

---

## 🤝 İşbirliği ve Networking

### Potansiyel İşbirlikleri

| Partner Tipi | Fayda |
|--------------|-------|
| **Oyun Geliştiricileri** | Erken erişim, özel içerik |
| **Diğer Haber Hesapları** | Cross-promotion |
| **Streamer/YouTuber** | Geniş erişim |
| **Oyun Toplulukları** | Niş kitle |

### Networking İpuçları
- Sektör profesyonellerini takip edin
- Etkinliklere katılın
- Discord toplulukları oluşturun
- Düzenli etkileşimde bulunun

---

## 📝 Sonuç ve Özet

### Algoritma Başarı Formülü

```
BAŞARI = (Kaliteli İçerik × Doğru Zamanlama × Etkileşim) 
         - (Spam + Negatif Sinyal)
```

### Kritik Hatırlatmalar

1. **Video öncelikli** içerik stratejisi (30sn+ videolar)
2. **Prime time** paylaşımları (12-14, 17-19, 20-23)
3. **Etkileşim** odaklı içerikler (soru, anket, tartışma)
4. **Tutarlılık** (günlük 10-15 kaliteli paylaşım)
5. **Topluluk** yönetimi (yanıt, RT, mention)
6. **Negatif sinyallerden** kaçınma

### Son Söz

X algoritması sürekli gelişir. Bu kılavuz, algoritmanın temel prensiplerini anlatır. Düzenli olarak:
- Kendi analytics verilerinizi analiz edin
- A/B testleri yapın
- Stratejinizi güncelleyin
- Topluluk geri bildirimlerini dinleyin

---

> **Not:** Bu kılavuz, X algoritmasının açık kaynak koduna dayanarak hazırlanmıştır. Algoritma değişikliklerine göre güncellenmelidir.

**Son Güncelleme:** [Algoritma değişikliklerine göre güncelleyin]
