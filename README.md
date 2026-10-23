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

- Soru metinleri `sorular.md` dosyasından okunur. Sayfa doğrudan dosyadan (`file://`) açıldığında bu dosya okunamadığı için soruların bir kopyası `index.html` içine de gömülüdür. `sorular.md` değiştirilirse gömülü kopyanın da güncellenmesi gerekir.
- Paylaşım kodu, cevapları sıkıştırılmış biçimde taşır (`M1.` ile başlar). 566 cevap yaklaşık 150 karaktere sığar.
- Linkler kodu adresin `#` işaretinden sonraki kısmında taşır, bu kısım tarayıcı tarafından sunucuya gönderilmez:
  - `https://mmpi.afatihyavasi.com/#k=M1.…` psikolog için salt okunur görünüm açar.
  - `https://mmpi.afatihyavasi.com/#devam=M1.…` cevapları açıldığı cihaza aktarır.

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
