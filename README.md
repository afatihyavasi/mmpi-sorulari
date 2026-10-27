# MMPI Soruları

Minnesota Çok Yönlü Kişilik Envanteri (MMPI) sorularını tarayıcıda tek tek cevaplamak, sonucu psikologla paylaşmak ve PDF olarak indirmek için hazırlanmış, kâr amacı gütmeyen bir web uygulaması.

Canlı adres: [mmpi.afatihyavasi.com](https://mmpi.afatihyavasi.com)

## Özellikler

- **566 soru, adım adım:** Her ifade Doğru ya da Yanlış olarak işaretlenir. Mobilde cevap düğmeleri başparmak hizasında, ekranın altında durur. Bilgisayarda `D`, `Y` ve ok tuşları kullanılabilir.
- **Otomatik kayıt:** Cevaplar yalnızca kullanıcının tarayıcısında (`localStorage`) saklanır, kaldığı yerden devam edilir. Hiçbir sunucuya gönderilmez.
- **Psikologla paylaşma:** Sonuç ekranından link, kısa kod ya da karekod ile paylaşılır. Psikolog linki açtığında cevapları salt okunur görür, değiştiremez. Karekod görsel olarak indirilebilir ya da paylaşılabilir.
- **Başka cihazda devam etme:** Aktarma linki, karekod ya da kod ile cevaplar başka bir cihaza taşınır.
- **PDF:** Cevaplar orijinal cevap anahtarı düzeninde PDF olarak indirilir.
- **Diğer:** İlk açılışta tanıtım, isteğe bağlı kişisel bilgi formu, tebrikler ekranı, açık/koyu tema.

## Nasıl çalışır

Uygulama tek bir `index.html` dosyasıdır; derleme ya da kurulum gerekmez.

- Soru metinleri `sorular.md` dosyasından okunur. Aynı sorular ana ekrandaki "MMPI soruları listesi" bölümünde sayfa metni olarak da bulunur. Sayfa doğrudan dosyadan (`file://`) açıldığında `sorular.md` okunamadığı için uygulama soruları bu listeden alır. `sorular.md` değiştirilirse `index.html` içindeki listenin de güncellenmesi gerekir.
- Paylaşım kodu, cevapları sıkıştırılmış biçimde taşır (`M1.` ile başlar). 566 cevap yaklaşık 150 karaktere sığar.
- Linkler kodu adresin `#` işaretinden sonraki kısmında taşır, bu kısım tarayıcı tarafından sunucuya gönderilmez:
  - `https://mmpi.afatihyavasi.com/#k=M1.…` psikolog için salt okunur görünüm açar.
  - `https://mmpi.afatihyavasi.com/#devam=M1.…` cevapları açıldığı cihaza aktarır.

## Arama motorları ve yapay zekâ araçları

- `index.html`: başlık, açıklama, `canonical`, Open Graph ve Twitter etiketleri, yapılandırılmış veri (`WebSite`, `WebApplication`, `FAQPage`). Sık sorulan sorular ve tam soru listesi sayfa metni olarak yer alır.
- `mmpi-nedir/`: MMPI'ın ne olduğu, kaç soru olduğu, ne kadar sürdüğü ve nasıl doldurulduğu hakkında rehber.
- `psikologlar-icin/`: psikologlar için aracın tanıtımı ve danışana gönderilecek hazır mesaj. Bu iki sayfa `assets/content.css` stilini paylaşır.
- `og-image.png` (1200x630): link paylaşıldığında görünen önizleme görseli.
- `favicon.svg`, `apple-touch-icon.png`: tarayıcı ve ana ekran simgeleri.
- `robots.txt`: tüm tarayıcılara, yapay zekâ tarayıcıları dahil, açıkça izin verir ve site haritasını gösterir.
- `sitemap.xml`: site haritası.
- `llms.txt`: yapay zekâ araçları için sitenin kısa açıklaması.

Yayına aldıktan sonra siteyi [Google Search Console](https://search.google.com/search-console) ve [Bing Webmaster Tools](https://www.bing.com/webmasters)'a ekleyip `sitemap.xml` adresini gönder.

## Yerelde çalıştırma

`index.html` dosyasını tarayıcıda açmak yeterlidir. Tüm özellikleri (ör. `sorular.md` okuma) denemek için basit bir sunucu kullanılabilir:

```bash
python3 -m http.server 8000
```

Ardından `http://localhost:8000` adresini aç.

## Önemli not

Bu araç yalnızca cevapları kaydeder ve paylaşır. Tanı koymaz ve puanlama yapmaz; değerlendirmeyi bir uzman yapar.

## İletişim

Öneri ve geri bildirim için: [hello@afatihyavasi.com](mailto:hello@afatihyavasi.com)
