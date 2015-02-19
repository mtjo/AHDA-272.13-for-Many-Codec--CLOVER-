#AHDA-272.4-for-Many-Codec--CLOVER- [Especially OS X Yosemite 10.10.2]

##===== Main Link======
https://github.com/andreszerocross/AHDA-272.4-for-Many-Codec--CLOVER-/
##===================

##Platform, Layout dan HDA Config Default from Mirone post:
http://www.insanelymac.com/forum/topic/298663-applehda-for-yosemite/

##Cara penggunaan :
###1 LayoutID
- Khusus untuk Kext AppleHDA for Notebook yang disediakan di Repository ini adalah menggunakan "Sound Layout 3" atau "HDEF=3" silahkan inject LayoutID anda via Clover atau DSDT agar menjadi LayoutID = 3. 

- Khusus untuk Kext AppleHDA  for Desktop yang disediakan di Repository ini adalah menggunakan "Sound Layout 5, 7 dan 9".
Dengan pengertian :

| Layout_ID 5 = 3 ports supported (Pink, Green, Blue) 
| Layout_ID 7 = 5/6 ports supported (Grey, Black, Laranja, Pink, Green, Blue) 
| Layout_ID 9 = 5/6 ports supported (Grey, Black, Laranja, Pink, Green, Blue, CodecAddress: 2)

Verifikasi status LayoutID Audio anda dengan membuka IOREG dan ketik "HDEF" dipencarian. Lihat posisi layoutID anda, untuk layout3 seharusnya tertulis "layout-id Data <03 00 00 00> di IOREG. Pastikan Codec Audio terbaca di DPCI Manager, lakukan semua ini sebelum melangkah pada penginstallan kext pada file yang disediakan di REPOSITORY.

Inject Audio ID bisa melalui Inject  Clover di config.plist, HDAEnabler, DSDT atau edit org.chameleon.plist
-----------------
2. Di dalam folder yang bernama "NAMA CODEC AUDIO ANDA" terdapat 3 File yaitu "NamaCodec.kext", "AppleHDA.kextx" dan "Patch OTF.rtf". Letakkan file "NamaCodec.kext" ke /EFI/Clover/Kexts/10.10 dan install file "AppleHDA.kext" menggunakan Kext Utility.
-------------------
3. Adapun file AppleHDA yang digunakan masih berstatus NATIVE, belum dipatch dan akan diusahakan seperti itu dan sebagai pengganti patch yang biasa digunakan via script bcc9 digantikan dengan Patch Binary via OTF / Kernel and Kext Patch Clover. Untuk itu di dalam file "Patch OTF.rtf" sudah terdapat script atau value yang diimplementasikan ke CLOVER Configurator yang akan tertulis di "config.plist" atau bila config.plist dibuka via textedit maka value value ini dipastekan sesuai gambar berikut, klik 
<a>http://oi57.tinypic.com/1zflhye.jpg"></a>
<a>--------------------</a>
--------------------
4. File Platform.xml.zlib dan Layout3.xml.zlib yang terdapat di dalam Native AppleHDA.kext/Contents/Resources/ sama sekali tidak di overwrite, lantas bagaimana menggantikannya dengan value value sesuai codec masing masing? Jawabanya adalah sekali lagi kita membuat value value itu tertulis dalam file yang berbeda extension yaitu file "Platform.zml.zlib" dan "Layout3.zml.zlib". Perhatikan ada perbedaan "xml.zlib vs zml.zlib", agar system membaca file zml.zlib ini maka kita melakukan Patch OTF sekali lagi dengan memasukkan value yang kembali sudah ditulis di file "Patch OTF.rtf". Silahkan diperhatikan, dipelajari dan diimplementasikan.
--------------------
5. Apabila terdapat masalah internal microphone yang tidak berfungsi atau lain sebagainya mungkin dikarenakan path map dan lain lain yang belum sempurna dan bila ingin memodifikasi silahkan ikuti post ini http://www.insanelymac.com/forum/topic/295001-guide-to-patch-applehda-for-your-codec/, sekali lagi file platform.zml.zlib dan layout3.zml.zlib adalah hasil dari "MASAKAN" Mirone yang link post telah dijelaskan di bagian teratas.
---------------------
6. File akan terus diusahakan ditambah,, tapi secara pelan pelan karena yang namanya manusia juga banyak kegiatan :D
---------------------
7. Untuk yang tidak berfungsi silahkan berkomentar di bawah dengan sopan dan jelas, coz yang namanya memodifikasi tidak ada yang "JOSH" 100% :D
---------------------
8. No PM just KOMENTAR di kolom komentar
-------------------
9. Seharusnya, bila nanti ada update AppleHDA Official maka otomatis AppleHDA system tidak akan kembali error. Karena apa?? Karena file layout3 dan platform tidak ter "overwrite" dikarenakan Apple biasanya melakukan update pada file yang sama sehingga yang di "overwrite" adalah file "layout3.xml.zlib dan platform.xml.zlib" bukan "layout3.zml.zlib dan platform.zml.zlib"




Salam Hackintosh Indonesia 


= Filsafat Musafir Hati =
