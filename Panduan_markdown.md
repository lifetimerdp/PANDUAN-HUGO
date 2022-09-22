**format file markdown:   nama-file.md**

1.  Garis Miring  
    ’_Kucing adalah hewan yang paling banyak di pelihara_’
    
2.  Huruf tebal atau Bold  
    **Anjing adalah hewan yang setia**
    
3.  Tebal dan miring
    **_Saya tidak percaya ini!_**
    
4.  Heading
    # Header one        => h1
    ## Header two       => h2
    ### Header three    => h3
    #### Header four    => h4
    ##### Header five   => h5
    ###### Header six   => h6
    
5.  Membuat link
    [text](https://url.com)
    
6.  Menyiapkan link agar dapat digunakan berkali-kali
    Kucing adalah [hewan][refHewan] kategori mamalia. [Hewan][refHewan] mamalia adalah [hewan][refHewan] yang menyusui dan melahirkan.
    [refHewan]: https://id.wikipedia.org/wiki/Hewan
    
7.  Membuat Gambar
    ![Text alt](https://www.url.com/gambar1.png)
    
8.  Gambar yang dapat digunakan berkali-kali
    ![Kucing][cat] adalah hewan kategori mamalia. ![Kucing][cat] banyak dipelihara manusia karena tidak berbahaya.
    [cat]: https://id.wikipedia.org/wiki/Kucing
    
9.  Kutipan atau Blockquote ( Gunakan tanda > di paling awal kata )
    > "Kucingku bernama hebe.
       Dia sangat lucu :)"
       
    Note: Jika terdapat baris kosong, gunakan > lagi (baris kosong dan paragraf selanjutnya) maka blockquote akan menjadi 1
    
    
10. List tak-terurut
    * list1
    * list2
    * dst
    
11. List angka
    1. Daftar pertama
    2. Kedua
    3. Ketiga
    4. Dst
    
12. Sub daftar tak-terurut
    * Resep ikan bakar
        * kunyit
        * bawang
            * merah
            * putih
        * Jeruk nipis
        * Kecap bangau
        * Garam
        * Micin
    
13. Paragraf di antara list

    1. Harga sepatu
    
     Harga sepatu mulai dari 50 ribu sampai dengan 1 juta rupiah.
     Sesuaikan dengan kemampuan anda.
     
    2. Harga sandal

     Harga sandal relatif murah jika dibandingkan dengan harga sepatu.
     Anda dapat membelinya mulai dari 10 ribu sampai dengan 400 ribu rupiah.

    Note: setiap ingin membuat paragraf di dalam list. Harus membuat baris kosong 1 dan spasi sekali diawal paragraf.
    
14. Jarak lembut atau soft breaks (Gunakan spasi 2 kali di akhir paragraf)
    
    Paragraf pertama lorem ipsum sume te gake youon.  
    Paragraf kedua 
    
15. Membuat block kode
    
    contoh:
    ```
    <DOCTYPE html>
    <html>
        <head></head>
        <body></body>
    </html>
    ```
    
    Kode block dengan highlight. Tambahkan nama bahasanya atau ekstensi dibelakang backtick awal (mendukung bahasa apapun)
    ```html
    <DOCTYPE html>
    <html>
        <head></head>
        <body></body>
    </html>
    ```
    
    ```json
    {
      "firstName": "John",
      "lastName": "Smith",
      "age": 25
    }
    ```

16. Tabel
    | judul 1 | judul 2 | judul 3 |
    |---------|---------|---------|
    | isi 1   | isi 2   | isi 3   |
    | isi 1.1 | isi 2.1 | isi 3.1 |
    
    saran: tidak perlu rapi seperti diatas, seperti dibawah ini juga bisa
    
    |judul 1|judul 2|judul 3|
    |isi 1|isi 2|isi 3|
    |isi 1.1|isi 2.1|isi 3.1|
    
    Hasil akhirnya sama saja.
    
17. Membuat tabel rata kanan, tengah, atau kiri
    |  judul 1  |   judul 2   |   judul 3  |
    |   :---    |    :---:    |    ---:    |
    | rata kiri | rata tengah | rata kanan |
    |           |             |            |


18. Penanda untuk kata atau kalimat penting
    Saat ini, kucing[^1] adalah salah satu hewan peliharaan terpopuler di dunia. Kucing yang garis keturunannya tercatat secara resmi sebagai kucing         trah atau galur murni (pure breed), seperti persia, siam, manx, dan sphinx. Kucing seperti ini biasanya dibiakkan di tempat pemeliharaan hewan resmi.     Jumlah kucing ras hanyalah 1% dari seluruh kucing di dunia, sisanya adalah kucing dengan keturunan campuran[^2] seperti kucing liar atau kucing           kampung.

    [^1]: teks catatan pertama
    [^2]: teks catatan kedua
    
    Ket: antara [^1] dan [^1]: akan saling terhubung dan dapat diklik


19. Cara lain membuat penanda
    [catatan 1](#note1)
    
    Nantinya kalian dapat mengeklik link ini dan akan langsung menuju yang link yang ditandai (ini seperti internal link pada halaman).


20. Mencoret kata / kalimat
    ~~kata yang mau dicoret~~
    
    
21. Daftar Tugas (Keren)
    1. [x] Write the press release
    2. [ ] Update the website
    3. [ ] Contact the media
    
    
22. Video Youtube
    {{< youtube 11_kode_videonya >}}
    
    {{< youtube 2xkNJL4gJ9E >}}