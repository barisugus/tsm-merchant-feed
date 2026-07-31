# tsm-merchant-feed

Türkiye Solar Market ürün beslemesi (Google Merchant Center / RSS 2.0 + g: namespace).

- **Tek içerik:** `merchant-feed.xml` — https://www.turkiyesolarmarket.com.tr/merchant-feed.xml adresinden zaten herkese açık servis edilen veri.
- **Üretim:** özel bir depodaki `generate_feed.py` her gün 04:00 TR'de üretir ve buraya iter.
- **Yayın:** Cloudflare Worker `tsm-edge-cache` bu deponun raw içeriğini proxy'ler.

Bu depo **bilerek public**: içeriği zaten kamuya açık ürün verisi (başlık, fiyat, link, görsel).
Alış fiyatı, kimlik bilgisi veya iç veri **içermez** — o veriler ayrı ve private olan üretim deposunda kalır.
Elle düzenlemeyin; her gün otomatik üzerine yazılır.
