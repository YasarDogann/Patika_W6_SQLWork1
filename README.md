# Patika+ Week6 SQL ile İlk Ödev Uygulaması
Merhaba,
Bu proje SQL ile Patika+ 6.hafta SQL komutları pratik için yapılmış bir uygulamadır.

## 📚 Proje Hakkında
Bu proje, aşağıdaki konuları öğrenmeye yardımcı olmak için tasarlanmıştır:
- Temel SQL komutları
- WHERE kullanımı
- AND ve OR kullanımı


## İstenilen Görev
Aşağıdaki sorgu senaryolarını dvdrental örnek veri tabanı üzerinden gerçekleştiriniz.
   - film tablosunda bulunan title ve description sütunlarındaki verileri sıralayınız.
   - film tablosunda bulunan tüm sütunlardaki verileri film uzunluğu (length) 60 dan büyük VE 75 ten küçük olma koşullarıyla sıralayınız.
   - film tablosunda bulunan tüm sütunlardaki verileri rental_rate 0.99 VE replacement_cost 12.99 VEYA 28.99 olma koşullarıyla sıralayınız.
   - customer tablosunda bulunan first_name sütunundaki değeri 'Mary' olan müşterinin last_name sütunundaki değeri nedir?
   - film tablosundaki uzunluğu(length) 50 ten büyük OLMAYIP aynı zamanda rental_rate değeri 2.99 veya 4.99 OLMAYAN verileri sıralayınız.

## Kod 
```sql

/*Aşağıdaki sorgu senaryolarını dvdrental örnek veri tabanı üzerinden gerçekleştiriniz.

 1. film tablosunda bulunan title ve description sütunlarındaki verileri sıralayınız.
 2. film tablosunda bulunan tüm sütunlardaki verileri film uzunluğu (length) 60 dan büyük VE 75 ten küçük olma koşullarıyla sıralayınız.
 3. film tablosunda bulunan tüm sütunlardaki verileri rental_rate 0.99 VE replacement_cost 12.99 VEYA 28.99 olma koşullarıyla sıralayınız.
 4. customer tablosunda bulunan first_name sütunundaki değeri 'Mary' olan müşterinin last_name sütunundaki değeri nedir?
 5. film tablosundaki uzunluğu(length) 50 ten büyük OLMAYIP aynı zamanda rental_rate değeri 2.99 veya 4.99 OLMAYAN verileri sıralayınız.
	*/

-- 1.SORU
SELECT title, description FROM film;

-- 2.SORU
SELECT * FROM film
WHERE length > 60 AND length < 75;

-- 3.SORU
SELECT * FROM film
WHERE rental_rate = 0.99 AND (replacement_cost = 12.99 OR replacement_cost = 28.99);

-- 4.SORU
SELECT first_name, last_name FROM customer
WHERE first_name = 'Mary';	

-- 5.SORU
SELECT * FROM film
WHERE length < 50 AND NOT(rental_rate = 2.99 OR rental_rate = 4.99);


```





