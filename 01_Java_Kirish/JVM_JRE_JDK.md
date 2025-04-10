### JVM, JRE va JDK Haqida

Java’ni o‘rganishda uchta asosiy tushuncha bilan tanishish juda muhim: **JVM**, **JRE** va **JDK**. Bu atamalar Java’ning qanday ishlashini tushunish uchun asos bo‘ladi.

#### 1. JVM (Java Virtual Machine)
- **JVM nima?**  
  JVM — bu Java Virtual Machine, ya’ni Java Virtual Mashinasi. Bu virtual kompyuter deb tasavvur qilishingiz mumkin, u siz yozgan Java kodini (`.class` fayllarni) ishga tushiradi. Java’ning eng katta afzalligi shundaki, u “bir marta yoz, hamma joyda ishlat” (Write Once, Run Anywhere) tamoyiliga asoslanadi. Bunga JVM sabab bo‘ladi.
- **Qanday ishlaydi?**  
  Siz Java kodini yozganingizda (masalan, `HelloWorld.java`), uni avval kompilyator (`javac`) `.class` faylga aylantiradi. Bu `.class` fayl mashina tili emas, balki baytkod (bytecode) deb ataladi. JVM esa bu baytkodni o‘qib, sizning operatsion tizimingiz (Windows, Mac, Linux) tushunadigan mashina tiliga aylantiradi va ishga tushiradi.
- **Python bilan farqi:**  
  Python’da kod to‘g‘ridan-to‘g‘ri interpretator orqali ishlaydi va har bir OS uchun alohida Python o‘rnatilishi kerak. Java’da esa JVM tufayli bir xil `.class` fayl hamma joyda ishlaydi.

#### 2. JRE (Java Runtime Environment)
- **JRE nima?**  
  JRE — Java Runtime Environment, ya’ni Java Ishga Tushirish Muhiti. Bu JVM’ni va Java dasturlarini ishga tushirish uchun zarur bo‘lgan kutubxonalarni (masalan, `System.out.println` uchun kerakli kodlarni) o‘z ichiga oladi.
- **Nimalardan iborat?**  
  - JVM (yuqorida aytib o‘tildi).
  - Standart Java kutubxonalari (Java Class Library).
- **Qachon kerak?**  
  Agar siz faqat Java dasturlarini *ishga tushirmoqchi* bo‘lsangiz (lekin yozmoqchi bo‘lmasangiz), JRE yetarli. Masalan, Java bilan yozilgan o‘yin yoki ilovani ishlatish uchun JRE o‘rnatiladi.
- **Python bilan solishtirish:**  
  Python’da `python3` o‘rnatganingizda, u ham interpretator va standart kutubxonalarni o‘z ichiga oladi. JRE shunga o‘xshaydi, lekin u faqat ishga tushirish uchun.

#### 3. JDK (Java Development Kit)
- **JDK nima?**  
  JDK — Java Development Kit, ya’ni Java Dastur Tashkillashtirish To‘plami. Bu dasturchilar uchun to‘liq vosita bo‘lib, Java kodini yozish, kompilyatsiya qilish va ishga tushirish uchun kerak bo‘lgan hamma narsani o‘z ichiga oladi.
- **Nimalardan iborat?**  
  - JRE (JVM + kutubxonalar).
  - Kompilyator (`javac`).
  - Qo‘shimcha vositalar (masalan, `javadoc` hujjat yaratish uchun, `jar` arxivlash uchun).
- **Qachon kerak?**  
  Siz Java’da dastur yozmoqchi bo‘lsangiz, JDK o‘rnatishingiz kerak. Masalan, biz `brew install openjdk@17` bilan JDK o‘rnatdik.
- **Python bilan solishtirish:**  
  Python’da `python3` o‘rnatish yetarli bo‘lsa, Java’da JDK o‘rnatish kerak, chunki kod avval kompilyatsiya qilinadi.

#### Qisqacha farq:
- **JVM:** Kodni ishga tushiradigan virtual mashina.
- **JRE:** JVM + kutubxonalar, faqat dasturni ishlatish uchun.
- **JDK:** JRE + kompilyator va vositalar, dastur yozish uchun.

#### Misol bilan tushuntirish:
1. Siz `HelloWorld.java` yozdingiz:
   ```java
   public class HelloWorld {
       public static void main(String[] args) {
           System.out.println("Salom!");
       }
   }
   ```
2. `javac HelloWorld.java` bilan JDK’dagi kompilyator `.class` fayl yaratadi.
3. `java HelloWorld` bilan JRE’dagi JVM bu faylni ishga tushiradi.

#### Python bilan taqqoslash:
- Python’da `print("Salom!")` deb yozsangiz, `python3 script.py` bilan to‘g‘ridan-to‘g‘ri ishlaydi. Java’da esa kompilyatsiya bosqichi qo‘shiladi.

---

### Qo‘shimcha ma’lumot: JIT va Baytkod
- **Baytkod (Bytecode):** Java kodi mashina tiliga emas, balki baytkodga kompilyatsiya qilinadi. Bu baytkod JVM tomonidan har bir platformada ishlaydi.
- **JIT (Just-In-Time Compiler):** JVM ichidagi maxsus kompilyator bo‘lib, baytkodni ishga tushirish paytida mashina tiliga aylantiradi va tezlashtiradi. Python’da bunday tushuncha yo‘q, chunki u interpretator bilan ishlaydi.

---

### Amaliy Misol (Kun 1 bilan bog‘liq):
`01_Java_Kirish_Ozgaruvchilar` papkasida `JVMTest.java` yarating:
```java
public class JVMTest {
    public static void main(String[] args) {
        System.out.println("JVM ishlayapti!");
        System.out.println("Java versiyasi: " + System.getProperty("java.version"));
        System.out.println("OS nomi: " + System.getProperty("os.name"));
    }
}
```
- Kompilyatsiya va ishga tushirish:
  ```
  javac JVMTest.java
  java JVMTest
  ```
- Natija: JVM haqida ma’lumot chiqadi (versiya, OS va hokazo).

---

### Vazifa:
1. `JVMTest.java` ni yarating va ishga tushiring.
2. Natijani `01_Java_Kirish_Ozgaruvchilar/output.txt` fayliga saqlang (masalan, `echo "Natija:" > output.txt && java JVMTest >> output.txt`).
3. “JVM nima qiladi?” degan savolga o‘z so‘zlaringiz bilan qisqa javob yozib, `notes.md` ga qo‘shing.

---

Agar qo‘shimcha savolingiz bo‘lsa, so‘rang. Aks holda, “Davom etamizmi?” deb yozsangiz, Kun 2 ga o‘tamiz!