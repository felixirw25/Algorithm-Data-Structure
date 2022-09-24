<h1> Algorithm & Data Structure </h1>
<p> oleh Felix Irwanto (GameDev Kelompok 3) </p>
<br>

## Algorithm

***Algorithm*** berasal dari kata bahasa inggris yang memiliki arti permainan. Contoh: Menebak angka. Cara membuat sebuah algoritma:
- Permasalahan pernyataan harus jelas
- Informasi (input) yang didapat dan hasil (output) yang diharapkan harus jelas.
- Membuat instruksi dan mengeksekusi sesuai urutan.
- Diujicoba (testing) agar memeriksa apakah algoritma sudah menghasilkan hasil (output) yang sesuai.

## Data Structure

***Data Structure*** berasal dari kata bahasa inggris yang memiliki arti struktur data. Struktur data adalah cara dan teknik yang berbeda untuk menyimpan dan mengoperasikan data dalam komputer. Data struktur hidup sementara di RAM laptop yang artinya bersifat sementara. Data struktur memiliki posisi karena adanya relasi atau hubungan antara data yang satu dengan yang lainnya.

Operasi dasar pada struktur data:
- Mengakses dan membaca data
- Mencari data
- Menambah data
- Menghapus data

Bentuk umum struktur data:
- Array / list
- Hashmap / Hashtable / Dictionary (pada C#): Pengimplementasiannya cukup kompleks
- Queue
- Stack 
- Linked List, Tree, dan Heap.

<h2>Array</h2>

**Array** adalah struktur data yang dimulai dari indeks 0, 1, 2, dst. dan harus bertipe data sejenis. Pada beberapa bahasa pemrograman dapat berbeda jenis, yaitu disebut array generik. Array di C# bersifat fix, jika ingin menggunakan dynamic array di C# dapat menggunakan list.

Contoh Pengimplementasian:
```
class Enemy
{
    public string Name;
    public int Health;

    public Enemy(string name, int health)
    {
        this.Name = name;
        this.Health = health;
    }
}

class Program
{
    static void Main()
    {
        Enemy Abenk = new Enemy("Abenk", 10);
        Enemy Budi = new Enemy("Budi", 20);
        Enemy Coki = new Enemy("Coki", 30);
        Enemy Dipa = new Enemy("Dipa", 40);
        Enemy Erlangga = new Enemy("Erlangga", 50);

        Enemy[] enemyArray = { Abenk, Budi, Coki, Dipa, };

        // mengetahui nama tipe data yang dipakai dari satu objek
        Console.WriteLine(nameof(Coki));

        // Mengetahui nama tipe data dari semua objek
        Console.WriteLine(string.Join<Enemy>(",", enemyArray));
        
        // Access Array
        Console.WriteLine(enemyArray[2].Name);
        
        // mengubah isi array (hrs diinisialisasi dulu)
        enemyArray[2] = Erlangga;
        Console.WriteLine(enemyArray[2].Name);

        // tidak ada fungsi add di array, hanya bisa membuat objek enemy baru 
        Enemy[] newEnemyArray = new Enemy[enemyArray.Length+1];
        for (int i = 0; i < enemyArray.Length; i++)
        {
            newEnemyArray[i] = enemyArray[i];
        }
        newEnemyArray[4] = Erlangga;
        Console.WriteLine(newEnemyArray[4].Name);
        }
}
```
Output:
<p align="center"><img width="100%" src="https://user-images.githubusercontent.com/113922230/192108098-9e802256-2e5e-433a-a447-4ebdcba8b678.png"> </p>

<h2>List</h2>

**List** adalah .

Contoh Pengimplementasian:
```
class Enemy
{
    public string Name;
    public int Health;

    public Enemy(string name, int health)
    {
        this.Name = name;
        this.Health = health;
    }
}

class Program
{
    static void Main()
    {
        Enemy Abenk = new Enemy("Abenk", 10);
        Enemy Budi = new Enemy("Budi", 20);
        Enemy Coki = new Enemy("Coki", 30);
        Enemy Dipa = new Enemy("Dipa", 40);
        Enemy Erlangga = new Enemy("Erlangga", 50);

        List<Enemy> enemyList = new List<Enemy>{
            Abenk, 
            Budi,
            Coki,
            Dipa,
            new Enemy("Coki", 30),
        };

        Console.Clear();
        // NB: list tidak memiliki length, jadi pakai count
        Console.WriteLine(enemyList.Count);

        // Mengakses data
        Console.WriteLine(enemyList[2].Name);

        // Menambah data di list
        enemyList.Add(Erlangga);

        // Menghapus data di list
        // enemyList.Remove(Erlangga);

        // Mencari data di list (-1 = tidak ditemukan)
        Console.WriteLine(enemyList.Contains(Erlangga));
        Console.WriteLine(enemyList.IndexOf(Erlangga));

        // NB: jika ada dua objek dengan nama yang sama, ketika diserang akan mengurangi nyawa sebanyak dua kali

        // Reference type, berbeda karena perbedaan hashcode
        Console.WriteLine(enemyList[2].GetType==enemyList[4].GetHashCode);
        }
}
```
Output:
<p align="center"><img width="100%" src="https://user-images.githubusercontent.com/113922230/192108201-36c06ebe-ba7c-47da-b588-f3c2a744bd48.png"> </p>

<h2>Dictionary</h2>

**Dictionary** adalah struktur data yang menyimpan kumpulan nilai/data dalam format pencarian nilai kunci. **Dictionary** menyediakan kunci dan hashmap akan mengembalikan nilai terkait. Contoh Pengimplementasian:

```

```

Output:
<p align="center"><img width="100%" src="https://user-images.githubusercontent.com/113922230/192108201-36c06ebe-ba7c-47da-b588-f3c2a744bd48.png"> </p>




Menurut [Chris Crawford](https://en.wikipedia.org/wiki/Chris_Crawford_(game_designer)), ( [Atari](https://en.wikipedia.org/wiki/Atari) Game Designer ), terdapat 5 tahapan untuk mendefinisikan sebuah game: 
<p align="center"><img width="80%" src="https://user-images.githubusercontent.com/113922230/191320508-99d16ea0-d184-4601-9942-f846585c1a51.gif">

- Game disebut **seni** jika diperuntukkan untuk **kesenangan**, namun disebut **hiburan** jika diperuntukkan untuk **uang**.
- Sebuah hiburan disebut **game** apabila bersifat **interaktif**.
- Jika tidak terdapat **tujuan akhir** dari sebuah hiburan, maka disebut **mainan**.
- Jika game **tidak memiliki** lawan, maka disebut **puzzle** dan disebut **conflict**, jika **memiliki** lawan.
- Jika conflict **tidak boleh** mengganggu lawan, maka disebut **kompetisi** dan disebut **GAME**, jika **boleh mengganggu** lawan.


Keterampilan / Skills yang dibutuhkan dalam Game Development:
- Game Design: Konsep dan dokumentasi game, aturan game (kalah-menang), statistik game yang bersifat tahap utama. Kemampuan yang dituntuk yaitu analisa, visi, penulisan cerita, keseimbangan statistik, desain, tren, komunikasi, dan ilmu umum.
- Programming: Pengimplementasian game design menjadi produk melalui fase ngoding yang bersifat tahap kedua. Kemampuan yang dituntuk yaitu pemrograman, logika, peralatan yang terkait, pemodelan data, pemecahan masalah, analisa, sains, dan matematika.
- Arts: Estetika (suara, musik, narasi, dsb.) yang ada di dalam game yang bersifat tahap tersier. Kemampuan yang dituntuk yaitu rasa seni, peralatan yang terkait, photoshop, blender, FL Studio, tren, dan fleksibel.

Catatan Penting:
<p align="center"><img width="80%" src="https://sp-ao.shortpixel.ai/client/to_webp,q_glossy,ret_img,w_1200/https://nikopartners.com/wp-content/uploads/2022/07/220623-NIKO-Infographic-Esports-Market-Asia_V6_high-1200x675.png"> </p>
<p align="center">Sumber: <a href="https://hybrid.co.id/post/pasar-esports-asia-2021">hybrid.co.id</a> (2021)</p>

- Negara China menjadi pasar E-sports terbesar di Asia dengan pendapatan sebesar $403,1juta atau sekitar 6 Triliun Rupiah.
- Negara Indonesia memiliki pendapatan sebesar $14,9juta atau sekitar 223 Miliar Rupiah yang tidak jauh dengan negara-negara di Asia Tenggara lainnya, meski memiliki penduduk ke-4 terbesar di dunia.

## Introduction-to-Programming

Menurut Atmoko & Arizona (2016), **Programming / Pemrograman** adalah aktivitas membuat program. **Program** adalah sederetan instruksi atau ***statement*** dalam bahasa yang dimengerti oleh komputer yang bersangkutan, Yulikuspartono (2009:29). Bahasa yang dimengerti dari kalimat sebelumnya juga dikenal sebagai ***Programming Language*** / Bahasa Pemrograman. **Programming Language** bertujuan untuk mengajarkan komputer apa yang harus dilakukan secara jelas, sehingga komputer dapat menghasilkan output sesuai keinginan pengguna. Berikut contoh bahasa pemrograman yang dimengerti oleh komputer dan cukup populer, seperti: C, C#, PHP, Python, Javascript, Pascal, dll.
<p align="center"><img width="60%" src="https://www.watelectronics.com/wp-content/uploads/different-programming-languages.png"> </p>


Bahasa Pemrograman terbagi menjadi beberapa jenis, yaitu Procedural Programming Language, Functional Programming Language, Object-oriented Programming Language, Scripting Programming Language, dan Logic Programming Language: 
- Procedural Programming Language : Bahasa pemrograman yang mengeksekusi urutan pernyataan yang mengarah pada hasil, menggunakan banyak variabel, loop berat, dan elemen lainnya.
- Functional Programming Language : Bahasa pemrograman yang menggunakan data yang tersimpan, fungsi rekursif, dan nilai kembali fungsi. 
- Object-oriented Programming Language : Bahasa pemrograman yang menggunakan sistem enkapsulasi, pewarisan, dan polimorfisme. 
- Scripting Programming Language : Bahasa pemrograman yang bersifat prosedural, dapat terdiri dari elemen bahasa berorientasi objek, namun tidak cocok untuk pengembangan sistem besar. 
- Logic Programming Language : Bahasa pemrograman yang memuat pernyataan deklaratif dan memungkinkan mesin untuk mempertimbangkan konsekuensi dari pernyataan tersebut.


Dikutip dari [dosenIT](https://dosenit.com/kuliah-it/pemrograman/tingkatan-bahasa-pemrograman), Bahasa Pemrograman terbagi menjadi beberapa tingkatan:
- Bahasa pemrograman tingkat rendah (Bahasa Mesin): Bahasa yang bisa diolah komputer secara langsung tanpa kompilasi. 
Contoh: Bahasa biner.
- Bahasa pemrograman tingkat menengah (Bahasa Assembly): Bahasa yang memberikan satu tingkat abstraksi di atas kode mesin dan sedikit semantik / simbol. Contoh: Bahasa Assembler.
- Bahasa pemrograman tingkat tinggi: Bahasa yang memiliki sifat lebih mudah digunakan, mudah diadaptasikan antar-platform, dan lebih abstrak. Contoh: Bahasa C++, Visual Basic, Delphi, dan Pascal.
- Bahasa pemrograman tingkat sangat tinggi: Bahasa pemrograman dengan tingkat abstraksi yang sangat tinggi, yang di gunakan terutama sebagai alat produktivitas programmer profesional. Contoh: Bahasa VB.Net, Java, dan PHP.


<h2>Statement Vs Syntax</h2>

<p align="center"><img width="60%" alt="Statement" src="https://user-images.githubusercontent.com/113922230/192080238-2e4aff55-0952-4beb-8d11-536e71511a25.png"></p>

**Statement** berfungsi memerintah komputer dengan instruksi yang jelas dan terperinci.
**Syntax** adalah aturan yang mendefinisikan kombinasi simbol yang dianggap sebagai statement / pernyataan terstruktur dengan benar dalam suatu bahasa pemrograman.

<h2>Variabel</h2>

**Variabel** adalah lokasi penyimpanan yang dipasangkan dengan nama simbolis terkait (pengidentifikasi) yang berisi nilai.
Contoh: 
``` int x = 80; ``` 

<h2>Data & Data Types</h2>

**Data** adalah suatu kumpulan yang terdiri dari fakta-fakta untuk memberikan gambaran yang luas terkait dengan suatu keadaan.
**Data Types** atau tipe data adalah cara yang digunakan untuk menentukan jenis dari suatu data. Contoh: char, string, integer, float, dan boolean. Contoh: 
``` int x = 80; ``` 

<h2>Conditional</h2>

**Conditional** atau pengkondisian adalah pernyataan untuk menangani keputusan yang ada ketika membuat sebuah program untuk melakukan tindakan yang berbeda tergantung pada suatu kondisi benar atau salah. Pengkondisian yang sering dipakai dalam program yaitu if-else dan switch.

Contoh pengkondisian if digabung dengan switch (kondisi benar dan salah):
```
int gold = 10000;

Console.Write("Gold yang Dimiliki: " + gold);
Console.Write("\nItem Yang Ingin Dibeli : ");
string item = Console.ReadLine();

switch(item){
    case "Sword" : 
        if(gold >= 5000)
        {
            gold -= 5000;
            Console.WriteLine("Item Sword Terbeli");
            Console.WriteLine("Sisa Gold : " + gold);
        }
        else{
            Console.WriteLine("Gold Kurang");
        }
        break;
    case "Shield" :
        if(gold >= 3000)
        {
            gold -= 3000;
            Console.WriteLine("Item Shield Terbelih");
            Console.WriteLine("Sisa Gold : " + gold);
        }
        else{
            Console.WriteLine("Gold Kurang");
        }
        break;
    case "Gun" :
        if(gold >= 12000)
        {
            gold -= 12000;
            Console.WriteLine("Item Gun Terbelih");
            Console.WriteLine("Sisa Gold : " + gold);
        }
        else{
            Console.WriteLine("Gold Kurang");
        }
        break;
    default:
        Console.WriteLine("Item tidak tersedia");
        break;
}
```
Output:
<p align="center"><img width="40%" src="https://user-images.githubusercontent.com/113922230/192082070-b24ed7fc-d2f7-40e6-8048-e6a2b1e3f142.png">  &nbsp; &nbsp;  <img width="40%" src="https://user-images.githubusercontent.com/113922230/192082147-2ffc0520-adf1-4c24-8543-a9c4d6a557f2.png"> </p>

<h2>Loops</h2>

**Loops** atau perulangan berfungsi mengulangi tugas tertentu sampai mencapai titik henti. Titik henti dapat berupa pernyataan yang telah ditentukan sebelumnya atau kondisional. Perulangan yang sering dipakai dalam program yaitu for dan while. For dipakai ketika suatu perulangan sudah secara jelas diketahui titik hentinya. Contoh:
```
using System;
namespace Perulangan{
    class perulanganFor{
        static void Main (string[] args) {
            // Program Felix Irwanto - Game 3
            Console.Clear();
            int[,] duaDimensi = new int[3,4]{ {1,2,3,4}, {5,6,7,8}, {9,10,11,12}};
            for (int i = 0; i < duaDimensi.GetLength(0); i++)
            {
                for (int j = 0; j < duaDimensi.GetLength(1); j++)
                {
                    Console.Write(duaDimensi[i,j] + " ");
                }
                Console.WriteLine();
            }
        }
    }
}
```
Output:
<p align="center"><img width="100%" src="https://user-images.githubusercontent.com/113922230/192082686-5c62136d-da60-4cd9-9a03-59fb5520c598.png"> </p>

While dipakai ketika suatu perulangan belum diketahui titik hentinya. Contoh:
```
using System;
namespace Perulangan{
    class perulanganWhile{
        static void Main (string[] args) {
            // Program Felix Irwanto - Game 3
            Console.Clear();
            int angka;
            int jumlahDigit;

            angka = 10;
            jumlahDigit = 0;

            Console.WriteLine("Angka: " + angka);
            while (angka > 0)
            {
                jumlahDigit++;
                angka = angka / 10;
            }

            Console.WriteLine("Jumlah Digit: " + jumlahDigit);
        }
    }
}
```
Output: 
<p align="center"><img width="100%" src="https://user-images.githubusercontent.com/113922230/192083066-c92f6af4-76d8-4762-a1b7-1d7e361495dc.png"> </p>


<h2>Function / Method</h2>

**Function / Method** adalah bagian dari kode yang ditulis sekali tetapi dapat digunakan di banyak tempat dalam program. **Function / Method** dalam program terbagi dua, yaitu method void dan method bertipe data. Method void dipakai ketika suatu method tidak memiliki nilai balikan. Contoh: 
```
using System;
namespace FungsiMethod {
    class MethodVoid
    {
        static void Main(string[] args)
        {
            Console.Clear();
            HitungTampilkanHasil();
            HitungTampilkanHasil();
            HitungTampilkanHasil();
        }

        static void HitungTampilkanHasil()
        {
            Console.WriteLine(45 + 55);
        }
    }
}
```
Output: 
<p align="center"><img width="100%" src="https://user-images.githubusercontent.com/113922230/192084090-dae2bc7a-b8ad-42b0-8709-761c9f670a0b.png"> </p>

Method bertipe data dipakai ketika suatu method memiliki nilai balikan. Method juga dapat disederhanakan dengan mendefinisikan Expression-Embodied Member. Contoh:
```
using System;
namespace Penjumlahan {
    class Angka {
        static int PenjumlahanTigaAngka(int angka1, int angka2, int angka3) => angka1 + angka2 + angka3;
        static void Main(String[] args) {
            Console.Clear();
            Console.WriteLine(PenjumlahanTigaAngka(33,33,34));
        }
    }
}
```
Output: 
<p align="center"><img width="100%" src="https://user-images.githubusercontent.com/113922230/192084325-d983a8d3-5d52-40f5-9713-0f71f3726d64.png"> </p>

<h2>Array</h2>

**Array** adalah struktur data yang menyimpan data yang serupa. Array terbagi menjadi array satu dan multi dimensi. 

Contoh Array Satu Dimensi: 
```
object[] arrayObjek = { 20.33, "Lorem ipsum", true, 'D' };
Console.WriteLine($"{arrayObjek[2]}");
```
Output: 
<p align="center"><img width="100%" src="https://user-images.githubusercontent.com/113922230/192084656-36ea5146-4ff1-4763-a80f-baf8c1a2c82b.png"> </p>

Contoh Array Dua Dimensi: 
```
char[,] arrayXO   = new char [3, 3];

for (int i = 0; i < arrayXO.GetLength(0); i++)
{
    for (int j = 0; j < arrayXO.GetLength(1); j++)
    {
        if(i % 2 == 0)
        {
            if(j % 2 == 0) {
                arrayXO[i,j] = 'x';
            }
            else{
                arrayXO[i,j] = 'o';
            }
        }
        else
        {
            if(j % 2 == 0) {
                arrayXO[i,j] = 'o';
            }
            else {
                arrayXO[i,j] = 'x';
            }
        }
    }
}

for (int i = 0; i < arrayXO.GetLength(0); i++)
{
    for (int j = 0; j < arrayXO.GetLength(1); j++)
    {
        Console.Write(arrayXO[i,j] + " ");
    }
    Console.WriteLine();
}
```
Output:
<p> <img width="100%" src="https://user-images.githubusercontent.com/113922230/192084781-ab1ecd40-2f71-4d15-9df9-8050845b1495.png"> </p>

<br/>
**Copyright by Felix Irwanto - 2022**
