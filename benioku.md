# WatcherS Partner Botu Dökümantasyonu

### Botun Amacı

[WatcherS](http://discord.gg/watchers) Partner Botu, WatcherS sunucusunda partnerlik işlerini kolaylaştırmayı amaçlayan ve WatcherS sunucuna özel olan bir Discord botudur. Genel amaçları olarak; Paylaşılan partner metinlerini kontrol eder, sunucunun yasaklanma durumunu inceler, varsa davet linklerini kontrol eder ve de ayrıca ayarlanmışsa partnerlik sürelerini takip eder. Böylece sunucudaki partnerlik işlemlerini daha düzenli hale getirmeyi amaçlar.

### Komutlar ve Kullanımları

> ```
> Kısa Bilgilendirme:
> Komutlar tamamen eğik çizgi komutlarıyla yapılmıştır.
> EVERYONE: Bu komutu herkes kullanabilir.
> ADMIN: Bu komutu sadece izin verilen kişiler kullanabilir.
> OWNER: Bu komutu sadece sunucu sahibi kullanabilir.
> ```

- _Botun bilgilerini gösterir_

```
EVERYONE /bot-info
```

- _Günlük yaptığınız partner miktarını, tarihi, kullanıcı avatarınıız ve ID'nizi içeren bir resim gösterir_

```
EVERYONE /raporum
```

- _Günlük partner yapan kişilerin, yaptığı partner miktarının çoktan aza doğru sıralamasını yapar_

```
EVERYONE /sıralama
```

- _ID'si verilen sunucu kara listede bulunuyorsa bilgilerini gösterir_

```
EVERYONE /kara-liste-getir <sunucu-id>
```

| Parametre   | Tip    | Gerekli  | Varsayılan | Açıklama                                  |
| ----------- | ------ | -------- | ---------- | ----------------------------------------- |
| `sunucu-id` | `sayı` | **Evet** | -          | Yasaklanma bilgileri istenen sunucu ID'si |

- **Kara listeye alınmış sunucuları sizin için listeler**

```
EVERYONE /kara-liste-görüntüle
```

- **Davet linki verilen sunucunun basit bilgilerini gösterir**

```
EVERYONE /sunucu-sorgula
```

| Parametre     | Tip    | Gerekli  | Varsayılan | Açıklama                           |
| ------------- | ------ | -------- | ---------- | ---------------------------------- |
| `davet-linki` | `yazı` | **Evet** | -          | Sorgulanacak sunucunun davet linki |

- _ID'si verilen sunucuyu (yoksa) kara listeye ekler_

```
ADMIN /kara-liste-ekle <sunucu-id> <sebep>
```

| Parametre   | Tip    | Gerekli   | Varsayılan          | Açıklama                             |
| ----------- | ------ | --------- | ------------------- | ------------------------------------ |
| `sunucu-id` | `sayı` | **Evet**  | -                   | Yasaklanacak sunucunun ID'si         |
| `sebep`     | `yazı` | **Hayır** | Sebep Belirtilmedi! | Sununucunun yasaklanma nedeni/sebebi |

- _ID'si verilen sunucuyu (varsa) kara listeden çıkarır_

```
ADMIN /kara-liste-çıkar <sunucu-id> <sebep>
```

| Parametre   | Tip    | Gerekli   | Varsayılan          | Açıklama                                             |
| ----------- | ------ | --------- | ------------------- | ---------------------------------------------------- |
| `sunucu-id` | `sayı` | **Evet**  | -                   | Yasaklanması kaldırılacak sunucunun ID'si            |
| `sebep`     | `yazı` | **Hayır** | Sebep Belirtilmedi! | Sununucunun yasaklanmasının kaldırılma nedeni/sebebi |

- _Partner ayarlarının hepsini tek seferde ayarlamanıza olanak tanır_

```
OWNER /ayarla <partner-kanalı> <bildirim-kanalı> <süre> <süre-türü>
```

| Parametre         | Tip       | Gerekli   | Varsayılan | Açıklama                                                           |
| ----------------- | --------- | --------- | ---------- | ------------------------------------------------------------------ |
| `partner-kanalı`  | `kanal`   | **Evet**  | -          | Partner mesajlarının kontrol edileceği kanal                       |
| `bildirim-kanalı` | `kanal`   | **Hayır** | -          | Partnerlik ayarlarında yapılan değişikliklerin paylaşılacağı kanal |
| `süre`            | `sayı`    | **Hayır** | -          | Partnerlik süresinin miktarı                                       |
| `süre-türü`       | `seçenek` | **Hayır** | -          | Partnerlik süresinin türü                                          |

> **Not:** `süre` belirtilmişse `süre-türü`nü belirtmek zorunludur.

- _Partner kanalını yeniden ayaralamanıza olanak sağlar_

```
OWNER /ayarla-partner-kanalı <kanal> <sebep>
```

| Parametre | Tip     | Gerekli   | Varsayılan          | Açıklama                                     |
| --------- | ------- | --------- | ------------------- | -------------------------------------------- |
| `kanal`   | `kanal` | **Evet**  | Eski Kanal          | Partner mesajlarının kontrol edileceği kanal |
| `sebep`   | `yazı`  | **Hayır** | Sebep Belirtilmedi! | Partner kanalının değiştirilme nedeni/sebebi |

- _Bildirim kanalını yeniden ayaralamanıza olanak sağlar_

```
OWNER /ayarla-bildirim-kanalı <kanal> <sebep>
```

| Parametre | Tip     | Gerekli   | Varsayılan          | Açıklama                                                           |
| --------- | ------- | --------- | ------------------- | ------------------------------------------------------------------ |
| `kanal`   | `kanal` | **Evet**  | Eski Kanal          | Partnerlik ayarlarında yapılan değişikliklerin paylaşılacağı kanal |
| `sebep`   | `yazı`  | **Hayır** | Sebep Belirtilmedi! | Partner kanalının değiştirilme nedeni/sebebi                       |

- _Partner süresini yeniden ayaralamanıza olanak sağlar_

```
OWNER /ayarla-partner-süre <süre> <süre-türü>
```

| Parametre   | Tip       | Gerekli  | Varsayılan | Açıklama                     |
| ----------- | --------- | -------- | ---------- | ---------------------------- |
| `süre`      | `sayı`    | **Evet** | Eski Süre  | Partnerlik süresinin miktarı |
| `süre-türü` | `seçenek` | **Evet** | Eski Süre  | Partnerlik süresinin türü    |

- _Partnerlik ayarlarını sıfırlar ve bütün verileri siler_

```
OWNER /partnerlik-kapat
```

## Gerekli İzinler

| Ad                        | komut(lar)         | Kanallar   |
| ------------------------- | ------------------ | ---------- |
| Kanalları Görüntüle       | `Genel`            | `Genel`    |
| Mesaj Gönder              | `Genel`            | `Genel`    |
| Mesaj Geçmişini Görüntüle | `Genel`            | `Genel`    |
| Attach Files              | `Genel`            | `Genel`    |
| Embed Link                | `Genel`            | `Genel`    |
| Mesajları Yönet           | `Partner Kontrolü` | `Partner`  |
| Yönetici                  | `Önerilen`         | `Önerilen` |

## Hata İletme ve Destek

Destek almak için [WatcherS](http://discord.gg/watchers) discord sunucuna gelip `<@1224363326335881317> | exion.hub` discord hesabıyla iletişime geçebilirsiniz. Boş yazmanız durumunda engellenebilirsiniz.


## Bot Hakkında Diğer Bilgiler

- **Geliştirici:** exionhub | exion.hub
- **Discord.js Versiyonu:** v14.15.2
- **Node.js Versiyonu:** v20.13.1
- **Bot Versiyonu:** v1.0.0
- **Yazılan Program:** VS Code
