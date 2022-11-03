# SIG_Working-with-Terrain-Data

*Tutorial Working with Terrain Data

1. Download terlebih dahulu file GMTED2010N10E60_300.zip

2. Buka QGIS setelah itu klik Layer lalu pilih Add Layer lalu pilih Add Raster Layer (*Gambar 1*)

3. Pada jendela Data Source Manager pilih Raster setelah itu klik pada ... di bawah sumber, cari dan pilih file 10n060e_20101117_gmted_mea300.tif (*Gambar 2*)

4. Kita akan melihat data medan di kanvas QGIS. Setiap pixel dalam raster medan mewakili ketinggian rata-rata dalam meter di lokasi tersebut. Pixel gelap mewakili area dengan ketinggian rendah dan pixel yang lebih terang mewakili area dengan ketinggian tinggi (*Gambar 3*)

5. Pada wikipedia untuk emnemukan koordinat untuk area Gunung Everest terletak pada koordinat 27.9881 derjat LU, 86.9253 derjat BT. Perhatikan pada QGIS menggunakan koordinat dalam format (X,Y) jadi kita harus menggunakan koordinat sebagai (Bujur, Lintang). Untuk memperbesar , masukkan 1:1000000 di bidang Skala dan tekan enter. Kita akan melihat viewport zoom ke area sekitar himalaya (*Gambar 4*)

6. Kita akan memotong raster ke area yang diminati. Cari klip pada Proceesing Toolbox pilih Clip Raster by extent di bawah algoritma GDAL (*Gambar 5*)

7. Pada jendela Clip Raster by Extent, pilih 10n060e_20101117_gmted_mea300 sebagai Input Layer, klik ... di Clipping extent dan pilih Use Map canvas extent, klik ... di Clipped (extent) dan masukkan nama sebagai mt_everest.tif, lalu klik Run (*Gambar 6*)

8. Layer baru mt_everest akan muncul di kanvas. Cari Hill pada Processing Toolbox. Pilih algoritma Hillshade di bawah algoritma GDAL (*Gambar 7*)

9. Pada jendela Hillshade pilih mt_everest sebagai Elevation Layer, masukkan 315.000 di Azimuth (sudut horizontal), masukkan 45.000 di sudut vertikal. Klik ... di Hillshade dan masukkan namanya sebagai mt_everest_hillshade.tif, klik Run (*Gambar 8*)

10. Layer baru mt_everest_hillshade akan muncul pada kanvas (*Gambar 9*)

11. Cari Contour di Processing Toolbox. Pilih algoritma contour di bawah algoritma GDAL (*Gambar 10*)

12. Pada jendel Contour pilih mt_everest sebagai input Layer, masukkan 250 di Interval antara garis contour. Klik ... di contours dan masukkan namanya sebagai mt_everest_contour.gpkg, lalu klik Run (*Gambar 11*)

13. Layer baru mt_everest_contour akan muncul pada kanvas. Klik kanan pada layer dan klik Open Attribute Table (*Gambar 12*)

14. Kita akan melihat bahwa setiap fitur baris memiliki atribut bernama ELEV. Ini adalah ketinggian dalam meter yang diwakili oleh setiap garis. Klik pada tajuk kolom beberapa kali untuk mengurutkan nilai dalam urutan menurun. Di sini kita akn menemukan garis yang mewakili elevasi tertinggi dalam data yaitu Gunung Everest (*Gambar 13*)

15. Pilih top row lalu klik zoom map to the selected rows (*Gambar 14*)

16. Beralih pada QGIS utama. Kita akan melihat garis contour yang dipilih. Ini adalah area elevasi tertinggi dalam dataset (*Gambar 15*)

17. Cari Smooth pada Processing Toolbox. Pilih Smooth dibawah geometri vektor *Gambar 16*)

18. Pada jendela Smooth pilih mt_everest_contour sebagai Input Layer, masukkan 5 di Iterasi klik Run (*Gambar 17*)

19. Sebuah layer baru Smoothed akan muncul pada kanvas. Lapisan ini akan memiliki tepi yang halus dibandingkan dengan lapisan mt_everest_contour (*Gambar 18*)

20. Kita juga dapat memvisualisasikan lapisan contour dan memverifikasi analisi dengan mengekspor layer contour sebagai KML dan melihatnya di Google Earth, Klik kanan pada layer, pili Export Save Feature As... (*Gambar 19*)

21. Pilih bahasa Keyhole Markup Language (KML) sebagai format. klik ... di file name dan masukkan namanya sebagai contour_smoothed.kml, lalu klik OK (*Gambar 20*)

22. Jelajahi file keluaran pada disk dan klik dua kali untuk membuka Google Earth Pro, jika belum ada apliksinya dapat di download terlebih dahulu (*Gambar 21*)
