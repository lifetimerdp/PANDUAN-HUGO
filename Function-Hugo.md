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

### Variabel bawaan HUGO untuk file konfigurasi seperti config.toml  

#### archetypeDir

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

Lihat semua variabel bawaan HUGO di dokumentasi web hugo atau dengan mengeklik link ini https://gohugo.io/getting-started/configuration/#all-configuration-settings  

### Site Variabel 

> Site variabel adalah cara untuk mengakses variabel bawaan HUGO dari file.html (misalnya, index.html, single.html, dll).  

> Variabel bawaan hugo seperti baseURL, title, copyright, googleAnalytics, dan masih banyak lagi. Dokumentasi lengkapnya https://gohugo.io/getting-started/configuration/#all-configuration-settings



# Function

