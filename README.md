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
- Array / List
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

**List** adalah struktur data yang digunakan untuk menyimpan kumpulan objek/nilai atau disebut elemen list. Elemen pada list tersimpan menurut urutan tertentu. Isi sebuah list dapat dimanipulasi sehingga dapat berubah (mutable), baik ditambah maupun dikurangi.

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

**Dictionary** adalah struktur data yang menyimpan kumpulan nilai/data dalam format pencarian nilai kunci. **Dictionary** menyediakan kunci dan hashmap akan mengembalikan nilai terkait. 

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

        Dictionary<string, Enemy> enemyDict = new Dictionary<string, Enemy>
        {
            {"A", Abenk},
            {"B", Budi},
            {"C", Coki},
            {"D", Dipa},
        };

        // Mengakses data
        Console.WriteLine(enemyDict["C"].Name);

        // Menambah data
        enemyDict["E"] = Erlangga;
        Console.WriteLine(enemyDict["E"].Name);
 
        // Bool mengecek apakah dapat menambah data
        enemyDict.TryAdd("E", Erlangga);

        // Mengecek apakah ada data
        Console.WriteLine(enemyDict.ContainsValue(Erlangga));

        // Menghapus data
        enemyDict.Remove("D");
        
        // Membersihkan data
        enemyDict.Clear();
    }
}
```

Output:
<p align="center"><img width="100%" src="https://user-images.githubusercontent.com/113922230/192109048-3aaba400-1292-441e-825b-e11f6e687d80.png"> </p>

<h2>Queue</h2>

**Queue** adalah struktur data yang menyimpan kumpulan nilai/data dengan setiap penambahan kumpulan, data tersebut akan ditambahkan pada indeks terakhir dari data sebelumnya. **Queue** mendukung tipe data sejenis maupun berbeda jenis dan berkonsep FIFO (First in First Out). 

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

        List<Enemy> enemyList = new List<Enemy>
        {
            {Abenk},
            {Budi},
            {Coki},
            {Dipa},
        };

        Queue<Enemy> enemyQueue = new Queue<Enemy>(enemyList);

        // Mengakses data
        Console.WriteLine(enemyQueue.Peek().Name);

        // Menghapus data
        enemyQueue.Dequeue();
        Console.WriteLine(enemyQueue.Peek().Name);

        // Menambah data
        enemyQueue.Enqueue(Erlangga);

        // Membersihkan data
        enemyQueue.Clear();
    }
}
```

Output:
<p align="center"><img width="100%" src="https://user-images.githubusercontent.com/113922230/192109517-64971848-e011-4d44-b570-2718f27e2297.png"> </p>

<h2>Stack</h2>

**Stack** adalah struktur data yang menyimpan kumpulan nilai/data dengan setiap penambahan kumpulan, data tersebut akan ditumpuk di atas data sebelumnya. **Stack**  mendukung tipe data sejenis maupun berbeda jenis dan berkonsep LIFO (Last in First Out). 

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

        List<Enemy> enemyList = new List<Enemy>
        {
            {Abenk},
            {Budi},
            {Coki},
            {Dipa},
        };

        Stack<Enemy> enemyStack = new Stack<Enemy>(enemyList);

        
        // Menambah data
        enemyStack.Push(Erlangga);
        

        // Menghapus nama
        var pop = enemyStack.Pop();
        Console.WriteLine(pop.Name);

        // Mengakses data
        Console.WriteLine(enemyStack.Peek().Name);
        

        // Memeriksa data
        Console.WriteLine(enemyStack.Contains(Erlangga));

        // 
        Console.WriteLine(enemyStack.ElementAt(0).Name);

        // Membersihkan data
        enemyStack.Clear();
    }
}
```

Output:
<p align="center"><img width="100%" src="https://user-images.githubusercontent.com/113922230/192109767-be016eff-2839-49e6-95d4-044793e92d78.png"> </p>


<br/>
**Copyright by Felix Irwanto - 2022**
