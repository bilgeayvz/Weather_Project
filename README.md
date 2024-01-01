# Weather_Project
Projenin amacı hava durumu sitelerinden (havadurumux, weather.com, metoffice) Türkiye’nin 81 ili için 1 haftalık  hava durumunu kazımak. Kazınan veriyi MongoDB veritabanına aşağıda belirtilen formatta kaydetmektir. 

provincial_plate: "01" 

date:2023-11-07T00:00.000+00:00 

weather:Object 

weather_com:Object 

up:22.5 

low:15.5 

havadurumux:Object 

up:25 

low:18.3 

# Gereksinimler

Proje python dilinde yazılmıştır. Gerekli kütüphaneler “requirements.txt” dosyasının içinde mevcuttur. Veriyi kazımak için requests ve BeautifulSoup kütüphanelerini kullandım.

 

# Kodun Açıklaması

Gerekli kütüphaneleri import ettim. Havadurumux sitesinden veriyi çekmek için ‘extract_data_from_havadurumux’ fonksiyonunu kullandım. Url parametresi ile urlini aldım. Çektiğim verileri liste içerisinde tuttum. Date, up ve low üzerinde düzenlemeler yaparak istenilen formatta dictionary oluşturdum. Aynı işlemi weather.com sitesi içinde fonksiyon kullanarak yaptım. ‘Combine_data ‘ fonksiyonunu kullanarak iki farklı siteden alınan hava durumu verilerini birleştirdim. Parametreleri ‘weather_com_data’ weather’dan elde edilen verileri içeren liste ve ‘havadurumux_data’ havadurumux’dan elde edilen verileri içeren listedir. Zip fonksiyonunu kullanarak birleştirdiğim listelerin elemanlarını eşleştirdim. İstenilen formatta dictonaryi oluşturarak MongoDb’ye ekleme işlemini yaptım. 
