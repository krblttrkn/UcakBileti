# ÖDEV :
* Java ile mesafeye ve şartlara göre uçak bileti fiyatı hesaplayan programı yapın. Kullanıcıdan Mesafe (KM), yaşı ve yolculuk tipi (Tek Yön , Gidiş-Dönüş) bilgilerini alın. Mesafe başına ücret 0,10 TL / km olarak alın. İlk olarak uçuşun toplam fiyatını hesaplayın ve sonrasında ki koşullara göre müşteriye aşağıdaki indirimleri uygulayın.;
* Kullanıcıdan alınan değerler geçerli (mesafe ve yaş değerleri pozitif sayı, yolculuk tipi ise 1 veya 2) olmalıdır. Aksi takdirde kullanıcıya "Hatalı Veri Girdiniz !" şeklinde bir uyarı verilmelidir.
* Kişi 12 yaşından küçükse bilet fiyatı üzerinden %50 indirim uygulanır.
* Kişi 12-24 yaşları arasında ise bilet fiyatı üzerinden %10 indirim uygulanır.
* Kişi 65 yaşından büyükse bilet fiyatı üzerinden %30 indirim uygulanır.
* Kişi "Yolculuk Tipini" gidiş-dönüş seçmişse bilet fiyatı üzerinden %20 indirim uygulanır.

```
import java.util.Scanner;

public class UcakBileti {
    public static void main(String[] args) {
        int km, age, type;
        double price = 0.1, total;
        Scanner input = new Scanner(System.in);


        System.out.print("Mesafeyi KM Türündem Giriniz : ");
        km = input.nextInt();
        System.out.print("Yaşınızı Giriniz : ");
        age = input.nextInt();
        System.out.print("Yolculuk Tipini Giriniz (1 =>Tek Yön , 2 => Gidiş-Dönüş) : ");
        type = input.nextInt();
        total = km * price;


        if ((age >= 0) && (km > 0) && ((type == 1) || (type == 2))) {
            System.out.println("İndirimsiz Toplam Fiyat : " + total + "TL");
            if (age < 12) {
                System.out.println("0-12 Yaş indirimi : " + (total *= 0.5) + "TL");
            } else if (age >= 12 && age <= 24) {
                System.out.println("12-24 Yaş İndirimi : " + (total *= 0.9) + "TL");
            } else if (age >= 65) {
                System.out.println("65 Yaş Üstü İndirimi : " + (total *= 0.7) + "TL");
            } else {
                System.out.println("Yetişkin : " + (total) + "TL");
            }
            if (type == 1) {
                System.out.println("Tek Yön İndirimi : " + (total = total) + "TL");
                System.out.println("Toplam Tutar : " + total + "TL");
            } else {
                System.out.println("Gidiş-Dönüş İndirimi : " + (total *=1.6) + "TL");
                System.out.println("Toplam Tutar : " + total + "TL");
            }
        } else {
            System.out.print("Hatalı Veri Girdiniz ! ");
        }
    }
}
```
# Patika Profilim
<a href='https://academy.patika.dev/profile'><u>Patika Profilim</u></a> 