> "Halaman ini berisi beberapa Variabel dan Function bawaan dari HUGO. Ditulis dan dijelaskan sesuai pemahaman saya sendiri"

# Variabel

### Site.Params.nama-variabel  

**_nama variabel_** diambil dari file config.toml di Proyek HUGO kalian.  

File **config.toml**  
```
baseurl= "example.com"
title= "Doni Setiawan Website"
languagecode = "en-us"

[params]
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

# Function

