# AHDA-272.4-for-Many-Codec--CLOVER- [Especially OS X Yosemite 10.10.2]
Platform, Layout dan HDA Config Default from Mirone Thread : http://www.insanelymac.com/forum/topic/298663-applehda-for-yosemite/

Cara penggunaan :

1. Di dalam folder yang bernama "NAMA CODEC AUDIO ANDA" terdapat 3 File yaitu "NamaCodec.kext", "AppleHDA.kext" dan "Patch OTF.rtf".  Letakkan file "NamaCodec.kext" ke /EFI/Clover/Kexts/10.10 dan install file "AppleHDA.kext" menggunakan Kext Utility.
2. Adapun file AppleHDA yang digunakan masih berstatus NATIVE, belum dipatch dan akan diusahakan seperti itu dan sebagai pengganti patch yang biasa digunakan via script bcc9 digantikan dengan Patch Binary via OTF / Kernel and Kext Patch Clover. Untuk itu di dalam file "Patch OTF.rtf" sudah terdapat script atau value yang diimplementasikan ke CLOVER Configurator yang akan tertulis di "config.plist" atau bila config.plist dibuka via textedit maka value value ini dipaste diantara
<p/>/---------------------------------------/
<p/><a><</a>key>KextsToPatch<<a>/</a>key>
<p/><a><</a>array>
<p/>............<------- Paste Value yang tertulis di "Patch OTF.rtf"
<p/><<a>/</a>array>
<p/>/---------------------------------------/
3. Khusus untuk Kext AppleHDA yang disediakan di Repository ini adalah menggunakan "Sound Layout 3" atau "HDEF=3" silahkan inject LayoutID anda via Clover atau DSDT agar menjadi LayoutID = 3.
4. File Platform.xml.zlib dan Layout3.xml.zlib yang terdapat di dalam Native AppleHDA.kext/Contents/Resources/ sama sekali tidak di overwrite, lantas bagaimana menggantikannya dengan value value sesuai codec masing masing? Jawabanya adalah sekali lagi kita membuat value value itu tertulis dalam file yang berbeda extension yaitu file "Platform.zml.zlib" dan "Layout3.zml.zlib". Perhatikan ada perbedaan "xml.zlib vs zml.zlib", agar system membaca file zml.zlib ini maka kita melakukan Patch OTF sekali lagi dengan memasukkan value yang kembali sudah ditulis di file "Patch OTF.rtf". Silahkan diperhatikan, dipelajari dan diimplementasikan.
5. Apabila terdapat masalah internal microphone yang tidak berfungsi atau lain sebagainya mungkin dikarenakan path map dan lain lain yang belum sempurna dan bila ingin memodifikasi silahkan ikuti post di sini http://www.insanelymac.com/forum/topic/295001-guide-to-patch-applehda-for-your-codec/, sekali lagi file platform.zml.zlib dan layout3.zml.zlib adalah hasil dari "MASAKAN" Mirone yang link post telah dijelaskan di bagian teratas.

<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
Salam Hackintosh Indonesia 
<br/>
<br/>
<br/>
= Filsafat Musafir Hati = 
