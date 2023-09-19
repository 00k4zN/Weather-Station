ÖZET

Hava istasyonu, arduino ve raspberry  pi kullanarak lokal hava durumunu tek bir arayüzde sıcaklığı, yağışı , rüzgar hızını ve basıncı sayısal verilerle görmemizi sağlıyor. Proto Shield’ın üzerine yerleştirdiğimiz DHT22 sensörüyle sıcaklık ve nemi, BMP180 basınç sensörüyle sıcaklık ve basıncı ölçebiliyoruz. Arduino ve raspberry pi arasında iletişimi sağlamak için NRF24L01 wireless modülünü tercih ettim. Bu şekilde dış mekan sistemini yani arduinoyu balkonumuza kurduğumuzda raspberry arayüzünü başka bir odada rahatlıkla kullanabiliyoruz. NRF24L01 modülünün menzili 100 metre civarı olduğundan 3+1’lik bir evin bütün odalarından rahatlıkla sinyal alabiliyoruz.  Arduinoya bağladığımız 12 cm’lik bir kasa fanını rüzgar ölçüm cihazı olarak kullanıyoruz. Meteorolojinin kullandığı kilometre, saat gibi verileri kullanmadığımız için kasa fanından  elde ettiğimiz veriler ham ve bilimsel olmaktan uzak. Yine de projeye işlevsellik katması açısından kullanmayı tercih ettim. Kasa fanına monte ettiğimiz plastik kaşıklar rüzgarda döndükçe fan içindeki mıknatıs bir miktar elektrik üretecek ve bu voltaj değişimini 10 bitlik bir çözünürlükte yani 0 ile  1023 arasında bir sayısal değere tekabül edecek şekilde  göreceğiz. Örneğin, 0 ile 100 bit arasındaysa sakin, 100 ile 250 bit arasındaysa rüzgarlı olarak  karşımıza çıkacaktır. 














GİRİŞ – Neyi, Nerde, Nasıl Kullandım?

 Arduino Proto Shield üzerine yerleştirdiğim DHT22 sensörüyle havadaki sıcaklığı elde ettik.  


Proto Shield’ın üstüne yerleştirdiğimiz diğer sensörümüz BMP180 basınç sensörü yardımıyla hava basıncını Pascal cinsinden yazdırdık.
 


Kasa fanına bağladığımız plastik kaşıklar döndükçe yarattığı voltaj değişimini 10 bitlik bir çözünürlükte yani 0-1023 aralığında bir sayıya tekabül edecek şekilde görmekteyiz. Plastik kaşıkları kasa fanına monte etmek için bir adet kapak ve silikon tabanca kullandım. 	
 



Sensörlerin ve kasa fanının Arduino uno ile bağlantısını Arduino Proto Shield yardımıyla yapıyoruz.
 
	







Sensörlerin kütüphanelerini ve gerekli kodları Arduino uno r3 modeline yükledim. Proto Shield’ı arduino unoya taktıktan sonra cihazı çalıştırmak için 9 voltluk bir adaptör kullandım.
 


Proto Shield’a yerleştirdiğim NRF24L01 wireless modülü de arduinodan aldığım verileri raspberry pi’ya kablosuz olarak iletmektedir.
 








Raspberry pi’ye de bir adet NRF24L01 wireless modülü taktım. Böylece arduinodan rahat bir şekilde veri alabilmekte, bu verileri github’dan bulduğum kodlarla işleyip bir hava durumu arayüzü olarak göstermektedir.
 



Daha sonra NRF24L01 wireless modülünün raspberry pi ile bağlantısı aşağıdaki şekilde yapıldı.
 



Wireless modülündeki pinleri raspberry pi’deki ilgili pinlere bağlamak için aşağıdaki görselden yararlandım.
 



Kurulum için gerekli olan tüm şemaların ve kodların  olduğu github linkini de aşağıya ekliyorum:

[https://github.com/meraklimaymun/minihavaistasyonu_v2]



Arduino'da kullandığım nrf24l01 kütüphanesi linki:

[https://github.com/nRF24/RF24]



Arduino'da kullandığım BMP180 kütüphanesi linki:

[https://github.com/sparkfun/BMP180_Breakout]

















SONUÇ

Arduino verileri sorunsuz  bir şekilde raspberry pi’ya iletti. BMP180 basınç sensörünü lehimleyemediğim için basınç verilerini şimdilik alamadım. Buna rağmen proje sorunsuz bir şekilde çalıştı. Raspberry pi arayüzünde hava sıcaklığı, yağış durumu ve rüzgar hızını görebiliyoruz. Projeyi yaparken karşılaştığım sorunlardan biri de raspberry pi için kullandığım python kodlarının büyük ölçüde hata içermesiydi. Bu yüzden arduinodan gelen verileri işlemede zaman zaman zorluk yaşadım. Malzeme listesinde opsiyonel olarak sunduğum raspberry pi’nin orijinal dokunmatik ekran  ve kasasını proje maliyeti açısından çıkarmak zorunda kaldım. Bunun yerine raspberry pi çalışır durumdayken VNC Viewer  yardımıyla  raspberry pi masaüstüne uzaktan erişimle bağlanıyorum. Böylece istediğim zaman bilgisayardan da hava istasyonu verilerini kontrol edebiliyorum. Sonuç olarak proje hala geliştirilebilir bir durumda  fakat şu anki haliyle de sorunsuz bir şekilde çalışmakta. 


  
