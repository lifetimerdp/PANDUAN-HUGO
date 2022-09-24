> "Halaman ini berisi beberapa Variabel dan Function bawaan dari HUGO. Ditulis dan dijelaskan sesuai pemahaman saya sendiri"

# Variabel

### Site.Params.nama-variabel  

**_nama variabel_** diambil dari file config.toml di Proyek HUGO kalian.  

File **config.toml**  
```
baseurl= "example.com"
title= "Doni Setiawan Website"
languagecode = "en-us"

[Params]
    author: "Doni"
    description: "Website ini dibuat oleh Doni Setiawan sebagai dokumentasi hasil belajar pribadi dan juga berisi artikel yang saya tulis"
```

#### Cara menggunakannya:

Misalnya saya mau menggunakannya di File **index.html**.  
Maka saya akan menuliskan ini:

**Akses variabel author**

```
{{ .Site.Params.author }}
```

**Akses variabel description**

```
{{ .Site.Params.description }}
```

Selain membuat variabel sendiri seperti sebelumnya. Kita juga dapat menggunakan **variabel bawaan HUGO**.  
Variabel bawaan itu contohnya seperti baseurl, title, languagecode yang terdapat di File **config.toml**.

### Variabel bawaan HUGO untuk file konfigurasi config.toml  

### archetypeDir

Default value: "archetypes"  
Ini digunakan untuk menentukan folder archetypes kustom (folder archetypes versi kita sendiri).

#### assetDir  

Default value: "assets"

Ini digunakan untuk menentukan folder assets kustom (folder assets tidak dibuat secara otomatis. Jadi kita perlu membuatnya terlebih dahulu jika memang membutuhkannya).  

> **Folder assets** digunakan untuk menyimpan file-file yang **_belum di kompilasi atau belum dikompres_**. Misalnya foto beresolusi tinggi dengan ukuran yang besar.  

> Hugo akan mengkompres file di folder assets dan mengirimkannya ke folder bernama **resources** untuk dikonsumsi publik atau pengunjung.  

> Biasanya kita perlu mengatur variabel tertentu di File **config.toml** agar file hasil kompres dapat kita gunakan.  

#### baseURL  

baseURL atau juga bisa ditulis baseurl adalah variabel untuk menentukan hostname atau url situs

#### build

Ini digunakan untuk mengkonfigurasi build global. Misalnya mengkompres gambar

Akan terlihat seperti ini:  

```
[build]
    useResourceCacheWhen = 'fallback'
    noJSConfigInAssets = false
```

**Selengkapnya: https://gohugo.io/getting-started/configuration/#configure-build**

#### buildDrafts

Default value: false

Sertakan draf saat build. Semua konten dalam draf akan ikut di masukkan ke folder /public saat melakukan build.  
Draf disini merujuk ke file didalam folder content kalian, yaitu postingankalian.md => frontmatternya ```draf: true```

#### buildExpired

Sertakan konten yang sudah kadaluarsa. konten kadaluarsa adalah konten yang memiliki waktu kadaluarsa.  
Kalian bisa mengatur waktu kadaluarsa konten menggunakan variabel expirydate: waktu-kadaluarsanya.  

**contoh postingan5.md:**  

```
title: "judul artikel"
languagecode: "en-us"
expirydate: 2023-09-19T15:25:14+07:00
```

#### buildFuture

Default value: false

Sertakan konten dimasa mendatang. Yaitu konten dengan front matter ```publishDate: waktu-posting-konten```

#### caches

Digunakan untuk mengatur ulang pen-cache-an di situs. Secara default, anda tidak perlu menggunakan ini, kecuali jika ingin mentaur ulang cache
(misalnya waktu kadaluarsa cache dari directory tertentu atau situs web keseluruhan)

**contoh file config.toml**

```
[caches]
    [caches.assets]
        dir = ':resourceDir/_gen'
        maxAge = -1
    [caches.images]
        dir = ':resourceDir/_gen'
        maxAge = -1
```

**Selengkapnya: https://gohugo.io/getting-started/configuration/#configure-file-caches**

### cascade

_Minimal version Hugo 0.86.0_

Digunakan untuk memberikan front matter dengan nilai yang sama ke folder content, folder dibawah content, dan semua file markdown dibawahnya. Jika ingin mengubah nilai dari variabel yang diatur di cascade, Ubah nilai variabel yang sama dengan variabel di cascade sebelumnya secara manual. Misalnya saya ingin mengubah variabel keyword untuk postingan4.md

**content/_index.md**

```
---
title: "Halaman Blog"
summary: "Anda menemukan artikel menarik disini"
cascade:
    keywords: "Halaman blog adalah halaman yang berisi artikel-artikel menarik yang saya tulis sendiri."
---
```

**cara mengubah variabel terkait cascade. Misalnya mengubah variabel keywords untuk postingan4.md**

```
---
title: "Postingan 4"
cascade:
    keywords: "Postingan keempat berisi artikel tentang kucing."
---
```

**cara memanggil dan menggunakan variabel di cascade. Sebagai contoh, saya menggunakannya di file head.html**

```html
<meta name="keywords" content="{{range $.Params.keywords}}{{.}} {{end}}">
```

> Selengkapnya:
> - https://gohugo.io/content-management/front-matter#front-matter-cascade  
> - https://gohugo.io/content-management/front-matter#target-specific-pages
> 
> Tidak semua variabel di front matter dapat digunakan di bawah cascade. Silahkan uji coba sendiri.

### canonifyURLs

Default value: false

Digunakan untuk mengubah URL relatif menjadi URL absout.

### contentDir

Default value: "content"

Ubah sumber folder content ke folder lainnya.

### copyright

Default value: ""

Atur kata-kata untuk hak cipta. Umumnya hak cipta diletakkan di bagian footer situs.

### dataDir

Default value: "data"

Digunakan untuk menentukan folder alternatif selain folder data

### defaultContentLanguage

Default value: “en”

Digunakan untuk mengatur bahasa dari artikel yang kita buat. Jika artikel yang anda terbitkan tidak menyetel bahasa. Maka bahasa yang di setel di defaultContentLanguage akan digunakan.

### defaultContentLanguageInSubdir

Default value: false

Ini untuk memberikan url situs url tambahan dari bahasa saat ini. Sebagai contoh ```https://url.com/en/```

### disableAliases

Default value: false

Digunakan untuk mematikan pengalihan alias.  Meskipun disableAliases disetel ke true, alias masih ada di halaman. Misalnya redirect 301 pada halaman.

### disableHugoGeneratorInject

Default value: false

Jika disetel ke ```true```, maka meta generator Hugo akan tidak di ikut sertakan. Saya menyarankan untuk tidak mengaktifkan ini, sebagai rasa terima kasih dan support untuk tim Hugo.

meta generator Hugo kira-kira akan terlihat seperti ini:  
```html
<meta name="generator" content="Hugo 0.93.3">
```

### disableKinds

Default value: []

Digunakan untuk menonaktifkan halaman yang ditentukan. Misalnya halaman "page", "home", "section", "taxonomy", "term", "RSS", "sitemap", "robotsTXT", "404".

**contoh penggunaan:**

```
disableKinds: ["home"]
```

### disableLiveReload

Default value: false

Digunakan untuk _mematikan refresh otomastis_ di browser saat sedang melakukan perubahan di situs.

### disablePathToLower

Default value: false

Jika disetel true, maka url dengan huruf kapital tidak akan di konversi ke huruf kecil (Biasanya url selalu dikonversi ke huruf kecil).

### enableEmoji

Default value: false

Digunakan untuk mengaktifkan fitur emoji di situs anda (Disarankan untuk mengaktifkannya dengan cara menyetel ke ```true``` agar situs anda dapat menggunakan emoji).

**List emoji: https://www.webfx.com/tools/emoji-cheat-sheet**

### enableGitInfo

Default value: false

Set ke true, jika kalian membutuhkan git saat sedang melakukan pembangunan situs. Dengan mengaktifkan ini, kalian akan mendapatkan info commit terbaru dan kalian tidak perlu mengatur tanggal postingan (kecuali jika anda ingin menerbitkan artikel tersebut di waktu mendatang) karena .Lastmod akan otomatis disetel.

**contoh penggunaan:**


```html
<p>
	<strong>{{ .PublishDate.Format "January 2, 2006" }}</strong><br />
	{{- if ne (.PublishDate.Format "January 2, 2006") (.Lastmod.Format "January 2, 2006") }}
		Last modified {{ .Lastmod.Format "January 2, 2006" }}
	{{- else -}}
		&nbsp;
	{{- end -}}
</p>
```

### enableInlineShortcodes

Default value: false

Digunakan untuk mengaktifkan **ShortCode** Hugo.

> **Selengkapnya:**  
> - https://gohugo.io/variables/shortcodes/#readout  
> - https://gohugo.io/content-management/shortcodes/#readout

### enableMissingTranslationPlaceholders

Default value: false

Aktifkan jika anda membutuhkan fitur translate atau multi bahasa di situs anda. Anda perlu mengatur variabel lainnya juga seperti language.

**Baca sumber lainnya: https://phrase.com/blog/posts/i18n-tutorial-how-to-go-multilingual-with-hugo/#Adding_and_Using_Translations**

### enableRobotsTXT

Default value: false

jika disetel ke true, HUGO akan membuat file ```robots.txt``` di layouts/robots.txt

### frontmatter

Digunakan untuk mengatur elemen front matter. Misalnya mengatur cara front matter menampilkan waktu posting konten, dan lain-lain.

**Selengkapnya: https://gohugo.io/getting-started/configuration/#configure-front-matter**

### googleAnalytics

Default value: ""

Isi dengan tracking ID dari Google Analytics.

### hasCJKLanguage

Default value: false

Jika disetel true, akan mendeteksi otomatis Bahasa Cina/Jepang/Korea di konten.  
Ini akan membuat .Summary dan .WordCount berperilaku dengan benar untuk bahasa Cina/Jepang/Korea.

### imaging

Digunakan untuk mengatur cara gambar ditampilkan di situs, kompress gambar, dimensi, format gambar, dan lain-lain yang terkait dengan gambar.

**contoh:**

```
[imaging]
    anchor = 'Smart'
```

> **Selengkapnya:**  
> - https://gohugo.io/content-management/image-processing/
> - https://gohugo.io/content-management/image-processing/#imaging-configuration

### languageCode

Default value: ""

Untuk mengatur bahasa di situs anda. Sebagai contoh, ini akan digunakan di [RSS template](https://github.com/gohugoio/hugo/blob/master/tpl/tplimpl/embedded/templates/_default/rss.xml) dan [alias template](https://github.com/gohugoio/hugo/blob/master/tpl/tplimpl/embedded/templates/alias.html).

### language

Ini digunakan untuk mengatur bahasa, lebih tepatnya adalah untuk menerapkan multi bahasa di situs anda.

**contoh:**

```
copyright = 'Everything is mine'
defaultContentLanguage = 'en'
[languages]
  [languages.ar]
    languagedirection = 'rtl'
    title = 'مدونتي'
    weight = 2
  [languages.en]
    title = 'My blog'
    weight = 1
    [languages.en.params]
      linkedin = 'https://linkedin.com/whoever'
  [languages.fr]
    title = 'Mon blogue'
    weight = 2
    [languages.fr.params]
      linkedin = 'https://linkedin.com/fr/whoever'
      [languages.fr.params.navigation]
        help = 'Aide'
  [languages.pt-pt]
    title = 'O meu blog'
    weight = 3
```

**Selengkapnya: https://gohugo.io/content-management/multilingual/#configure-languages**

### disableLanguages  

Ini digunakan untuk mematikan bahasa di situs anda. Ini biasanya digunakan untuk situs multibahasa yang perlu pengaturan tertentu.

```

```

**Selengkapnya: https://gohugo.io/content-management/multilingual/#disable-a-language**

### 



### Site Variabel 

> Site variabel adalah cara untuk mengakses variabel bawaan HUGO dari file.html (misalnya, index.html, single.html, dll).  

> Variabel bawaan hugo seperti baseURL, title, copyright, googleAnalytics, dan masih banyak lagi. Dokumentasi lengkapnya https://gohugo.io/getting-started/configuration/#all-configuration-settings



# Function

### Param

Digunakan
