# Katkı Rehberi

## Dosya düzeni

- Her sayfa `NN-slug.mdx` biçiminde numaralı bir dosyadır (`07-denetim-olusturma.mdx`).
  Numara yalnızca dosya listesindeki sıralamayı belirler; site bunu atar ve sayfa
  `/denetim-olusturma/` adresinde yayınlanır. Numarayı değiştirmek URL'yi bozmaz,
  ama iki dosya aynı slug'a düşmemelidir.
- `README.mdx` ana sayfadır (`/`).
- Görseller `assets/` altında tutulur ve `](assets/dosya.png)` ile referanslanır.
  `assets/frames/` ara ürünler içindir, yayınlanmaz.

## Frontmatter

Her dosyanın başında şu iki alan zorunludur:

```mdx
---
title: "Sayfa başlığı"
description: "Arama ve önizleme için bir cümlelik özet."
---
```

Kenar çubuğu etiketi, ikonu ve sıralaması site yapılandırmasından gelir; dosyaya
eklemezsiniz. Bu yüzden **yeni sayfa** eklemek isterseniz PR'ınızda hangi konuma
gireceğini belirtin — site tarafındaki menü kaydını biz ekleriz. (Alternatif:
önce issue açıp öneriyi tartışmak.)

## Bileşenler

Metin düz Markdown'ın ötesinde MDX bileşenleri kullanılabilir. Bileşenler
dosyanın başında import edilir:

```mdx
import { Callout, Steps, Tabs, TabItem, Card, CardGrid, Accordions, AccordionItem, Badge, FileTree, Icon } from '@prosefly/astro-components';
import Kbd from '@/components/Kbd.astro';
```

Sık kullanılanlar:

- `<Callout type="info|warning|danger">` — vurgu kutusu
- `<Steps>` — numaralı işlem adımları (içine düz Markdown numaralı liste yazılır)
- `<Tabs>` / `<TabItem>` — sekme
- `<Card>` / `<CardGrid>` — bağlantı kartları
- `<Accordions>` / `<AccordionItem>` — açılır bölümler
- `<Kbd>` — klavye kısayolu (`<Kbd>Ctrl</Kbd>+<Kbd>K</Kbd>`)
- `<Badge>` — durum etiketi

## Linkler

- Başka bir rehber sayfasına: `[metin](diger-dosya.mdx)` veya
  `[metin](diger-dosya.mdx#bolum-basligi)` — site derlerken route'a çevrilir.
- Dış bağlantılar normal URL'dir.
- Dosya yeniden adlandırılırsa ona link veren tüm sayfalar güncellenmelidir.

## MDX notları

- Düz metinde çıplak `<` kullanmayın — MDX onu JSX sanır. `&lt;` yazın.
- Import satırları frontmatter'dan hemen sonra gelir.

## PR'lar

- Bir PR tek konuya odaklansın; yazım düzeltmeleri toplu da gönderilebilir.
- Görsel ekliyorsanız dosyayı `assets/` altına koymayı unutmayın.
- Türkçe yazım ve üslup mevcut sayfalarla tutarlı olsun: sakin, görev odaklı,
  ikinci tekil şahıs ("siz") yerine yalın anlatım tercih edilir.
