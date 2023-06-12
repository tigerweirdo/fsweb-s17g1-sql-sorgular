# SQL Sorgu Alıştırmaları

Bu hafta SQL sorguları üzerine çalışıyorsunuz. Bugünkü alıştırmada sizin için hazırladığımız veritabanında aşağıda istediğimiz sonuçları elde etmenize yarayan SQL sorgularını oluşturacaksınız.

# Proje Kurulumu
Projeyi forklayın ve clonlayın. Tamamladığınızda da pushlayın.

## Kütüphane Bilgi Sistemi

Bu veritabanı, bir okulun kütüphanesinden öğrencilerin aldıkları kitapların bilgisini barındırmaktadır.

#Tablolar 
`ogrenci` tablosu öğrencilerin listesini tutar.
`islem` tablosu öğrencilerin kütüphaneden aldıkları kitapların bilgilerini tutar
`kitap` tablosu kütüphanedeki kitapların bilgisini tutar
`yazar` tablosu kitapların yazarları bilgisini tutar
`tur` tablosu kitapların türlerini tutar.

Tablo ilişiklerini görmek için [ktphn.png] dosyasına göz atın.

Yazdığınız sorguları buradan test edebilirsiniz: [https://ergineer.com/assets/materials/fkg36so5-kutuphanebilgisistemi-sql/] (update, delete, drop sorguları iptal edilmiştir).

### Görevler

Aşağıda istenilen sonuçlara ulaşabilmek için gerekli SQL sorgularını altlarına yazın. 


	1) ÖRNEK SORU: Öğrenci tablosundaki tüm kayıtları listeleyin.
	
		CEVAP: select * from ogrenci

	
	2) Öğrenci tablosundaki öğrencinin adını ve soyadını ve sınıfını listeleyin.	select ograd, ogrsoyad, sinif  from ogrenci 

	
	3) Öğrenci tablosundaki kız öğrencileri listeleyin. select  * from ogrenci where cinsiyet ="k"


	4) Öğrenci tablosunda kaydı bulunan sınıfların adını her sınıf bir kez görüntülenecek şekilde listeleyiniz 		select distinct sinif from ogrenci *****
	
	
	5) Öğrenci tablosunda, 10A sınıfında olan kız öğrencileri listeleyiniz. select * from ogrenci where sinif = "10A" and cinsiyet = "K" order by ogrno

	
	6) Öğrenci tablosundaki 10A veya 10B sınıfındaki öğrencilerin adını, soyadını ve sınıfını listeleyiniz. select ograd,ogrsoyad,sinif from ogrenci where sinif in ("10A","10B") order by sinif *****
	
	
	7) Öğrenci tablosundaki öğrencinin adını, soyadını ve numarasını okul numarası olarak listeleyiniz. (as kullanım örneği) select ograd, ogrsoyad, ogrno as ogrno from ogrenci 
	
	
	8) Öğrenci tablosundaki öğrencinin adını ve soyadını birleştirip, adsoyad olarak listeleyiniz. (concat, as kullanım örneği) select concat (ograd," ",ogrsoyad) as adsoyad from ogrenci 

	
	
	9) Öğrenci tablosundaki Adı ‘A’ harfi ile başlayan öğrencileri listeleyiniz. SELECT * FROM ogrenci WHERE ograd LIKE 'A%'

	
	
	10) Kitaplar tablosundaki sayfa sayısı 50 ile 200 arasında olan kitapların adını ve sayfa sayısını listeleyiniz. SELECT * FROM kitap WHERE sayfasayisi BETWEEN 50 AND 200;



	11) Öğrenci tablosunda adı Fidan, İsmail ve Leyla olan öğrencileri listeleyiniz. SELECT * FROM ogrenci WHERE ograd IN ('Fidan', 'İsmail', 'Leyla');

	
	
	12) Öğrenci tablosundaki öğrencilerden adı A, D ve K ile başlayan öğrencileri listeleyiniz. SELECT * FROM ogrenci WHERE ograd LIKE 'A%' OR ograd LIKE 'D%' OR ograd LIKE 'K%';
	
	
	13) Öğrenci tablosundaki sınıfı 9A olan Erkekleri veya sınıfı 9B olan kızların adını, soyadını, sınıfını ve cinsiyetini listeleyiniz. SELECT * FROM ogrenci WHERE (sinif = '9A' AND cinsiyet = 'E') OR (sinif = '9B' AND cinsiyet = 'K');

	
	
	14) Sınıfı 10A veya 10B olan erkekleri listeleyiniz. SELECT * FROM ogrenci WHERE (sinif IN ('10A', '10B')) AND cinsiyet = 'E';

	
	
	15) Öğrenci tablosunda doğum yılı 1989 olan öğrencileri listeleyiniz. SELECT * FROM ogrenci WHERE dtarih = 1989

	
	
	16) Öğrenci numarası 30 ile 50 arasında olan Kız öğrencileri listeleyiniz. SELECT * FROM ogrenci WHERE ogrno BETWEEN 30 AND 50 AND cinsiyet = 'K';

	
	
	17) Öğrencileri adına göre sıralayınız (alfabetik).	SELECT * FROM ogrenci ORDER BY ograd
	
	
	18) Öğrencileri adına, adı aynı olanlarıda soyadlarına göre sıralayınız. SELECT * FROM ogrenci ORDER BY ograd, ogrsoyad
	 
	
	19) 10A sınıfındaki öğrencileri okul numarasına göre azalan olarak sıralayınız.	SELECT * FROM ogrenci WHERE sinif = '10A' ORDER BY ogrno DESC
	
	
	20) Öğrenciler tablosundaki ilk 10 kaydı listeleyiniz.
	[İPUCU: `Select top tüm mysql versiyonlarında düzgün çalışmaz. LİMİT kullanmak daha faydalıdır`]	SELECT * FROM ogrenci LIMIT 10
	
	21) Öğrenciler tablosundaki ilk 10 kaydın ad, soyad ve doğum tarihi bilgilerini listeleyiniz. SELECT ograd, ogrsoyad, dtarih FROM ogrenci LIMIT 10
	
	
	22) Sayfa sayısı en fazla olan kitabı listeleyiniz. SELECT * FROM kitap ORDER BY sayfasayisi Desc LIMIT 1
	
	
	23) Öğrenciler tablosundaki en genç öğrenciyi listeleyiniz. SELECT * FROM ogrenci ORDER BY dtarih DESC LIMIT 1
	
	
	24) 10A sınıfındaki en yaşlı öğrenciyi listeyin. SELECT * FROM ogrenci WHERE sinif="10A" AND dtarih IS NOT NULL ORDER BY dtarih

	
	
	25) İkinci harfi N olan kitapları listeleyiniz.	 SELECT * FROM kitap WHERE kitapadi LIKE '_N%'
	
	
	26) Öğrencileri sınıflarına göre gruplayarak listeleyin.	SELECT sinif, COUNT(*) as ogrenci_sayisi  FROM ogrenci  GROUP BY sinif;

	
	
	27) Öğrencileri her sorgulamada sıralaması farklı olacak şekilde rastgele listeleyin. SELECT * FROM ogrenci ORDER BY RAND();

	[İPUCU: rand() fonksiyonu]
	
	
	28) Öğrenci tablosundan Rastgele bir öğrenci seçiniz.	SELECT * FROM ogrenci ORDER BY RAND() LIMIT 1

	
	
	29) 10A sınıfından rastgele bir öğrencinin adını, soyadını, numarasını ve sınıfını getirin. SELECT ograd,ogrsoyad,sinif FROM ogrenci  WHERE sinif="10A" ORDER BY RAND() LIMIT 1

	
	
	# Esnek
	30) Öğrenci tablosunda aynı isimde kaçar öğrenci olduğunu bulmak istiyoruz. 
	Öğrenci isimlerinin sayısını "adet" olarak öğrencilerin isimleri "isim" olarak listeleyin. 		SELECT ograd as isim, COUNT(*) as adet FROM ogrenci GROUP BY ograd;

	[İPUCU: count() ve group by]

