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
```csharp

public class Car
{
    public DateTime ProductionDate {  get; set; }
    public string SerialKey { get; set; }
    public string Brand {  get; set; }  
    public string Model { get; set; }
    public string Color { get; set; }
    public int NumberOfDoors { get; set; }

}
```
Class.

```csharp
static void Main(string[] args)
{
    bool isContinue = true;  // Sonsuz Döngü kontrol için değişken
    List<Car> cars = new List<Car>();  // Oluşturulan araba nesnesini ekleyeceğimiz Liste

    //Sonsuz Döngü başlatıldı
    while (isContinue)
    {
        Console.ForegroundColor = ConsoleColor.Red; // Sorulan sorunun rengi Kırmızı ayarlandı
        Console.Write("Araba Üretmek İstiyor Musunuz ?(E- Evet / H- Hayır): ");
        Console.ResetColor();
        if (char.TryParse(Console.ReadLine().ToUpper(), out char choose)) // E veya H cevabı alınırsa İf Bloğuna giriyor. Büyük harf yapıyor otomatik
        {
            if (choose == 'E') // Eğer seçim e ise ;
            {

                Car car = new Car(); // Araba Class'ından araba nesnesini oluşturdu
                Console.Write("Arabanın Seri Numarası: ");  // seri numarası kullanıcıya soruldu
                car.SerialKey = Console.ReadLine(); // kullanıcının girdiği değer Araba nesnesinin SerialKey prop'una atandı

                Console.Write("Arabanın Markası: ");
                car.Brand = Console.ReadLine();  // marka atandı

                Console.Write("Arabanın Modeli: ");
                car.Model = Console.ReadLine(); // model atandı

                Console.Write("Arabanın Rengi: ");
                car.Color = Console.ReadLine(); // Renk atandı

            EnterNumberOfDoors:    // Goto için anahtar kelime tanımlandı. KapıNumarasıGir:
                Console.Write("Kapı Sayısı: ");
                if (!int.TryParse(Console.ReadLine(), out int doors) || doors < 2 || doors > 5) // Eğer Girilen değer 2'den küçük VEYA 5'den büyük VEYA Sayı değilse
                {
                    Console.ForegroundColor = ConsoleColor.Red;
                    Console.WriteLine("Geçersiz Giriş! Lütfen 2 ile 5 Arasında Bir Sayı Girin"); // Hata ver
                    Console.ResetColor();
                    goto EnterNumberOfDoors; // goto ile tekrardan soruyu soracak
                }
                car.NumberOfDoors = doors; // geçerli girişş yapılınca girilen değer properties'e atandı.

                car.ProductionDate = DateTime.Now; // Tarih alındı

                cars.Add(car);  // Oluşturulan nesne  cars listesine eklendi
            }
            else if (choose == 'H')  // eğer girilen değer H ise;
            {
                Console.ForegroundColor = ConsoleColor.Green;
                Console.WriteLine("Programdan Çıkılıyor\r\n");  // Mesaj göster
                Console.ResetColor();


                Console.ForegroundColor = ConsoleColor.Green;
                Console.WriteLine("\r\n----- ÜRETİLEN ARABA/ARABALAR -----");
                Console.ResetColor();

                foreach (var car in cars)
                {
                    Console.WriteLine($"" +
                    $"Seri Numarası: {car.SerialKey}, " +
                    $"Marka: {car.Brand}, " +
                    $"Model: {car.Model}, " +
                    $"Renk: {car.Color}, " +
                    $"Kapı Sayısı: {car.NumberOfDoors}, " +
                    $"Üretim Tarihi: {car.ProductionDate}");
                }
                Environment.Exit(0);
            }
        }
        else
        {
            Console.WriteLine("Hatalı Seçim yaptınız tekrar deneyin");
        }
    }

    Console.Read();
}
```





