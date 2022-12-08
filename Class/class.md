# <ins>Class</ins>

## Membuat dan menggunakan class

```CSharp
public class MyClass
{
    int no = 10; // field, dapat diakses di semua method

    // Methode
    public void getNo()
    {
        Console.WriteLine(no);
    }

    // Method yang tidak berhubungan dengan object
    public static int gettingNo(MyClass myClass)
    {
        return myClass.no;
    }
}

// Block main
MyClass namaKelas = new MyClass();
```

atau secara simple

```CSharp
public class MyClass
{
    // tambahkan Class member disini
}
```

> Note:
> Class member terdiri dari:
>
> - Field
> - Method
> - Property
> - Event

### Field

Merupakan variabel yang dapat diakses oleh member class yang lain.

```Csharp
class Mobil
{
// Mendeklarasikan variabel sebagai field dari class Mobil
public string pabrikan;
public string tipe;
public int thnPembuatan;
public const double pi = 3.14;
}
```

### Method

```Csharp
class Mobil
{
    // field
    public bool statusMesin;
    // method
    public bool MenghidupkanMesin()
    {
        // instruksi untuk proses menghidupkan mesin mobil
        Console.WriteLine("Menghidupkan mesin mobil");
        // true = ON
        statusMesin = true;
        return statusMesin;
    }
    // method
    public bool MematikanMesin()
    {
        // instruksi untuk proses menghidupkan mesin mobil
        Console.WriteLine("Mematikan mesin mobil");
        // false = OFF
        statusMesin = false;
        return statusMesin;
    }
}
```

### Constructor

Method khusus yang mempunyai nama sama dengan nama `class` dan digunakan untuk menginisiasi suatu `object`.
ada 5 jenis `Constructor`

1. Default constructor
2. Parameterized constructor
3. Copy constructor
4. [Static constructor](Encapsulasi.md#static-constructor)
5. [Private constructor](Encapsulasi.md#private-constructor)

#### Default Constructor

meskipun tidak dibuat, compiler akan otomatis menambahkannya.

```CSharp
public class Mobil
 {
     public Mobil() { }
 }
```

#### Parametrize Constructor

```CSharp
class Mobil
 {
     public string pabrikan;
     public string model;
     int tahunPembuatan;
     // Default Constructor
     public Mobil(string pabrikans="toyota", string models="Hatchback")
     {
         pabrikan = pabrikans;
         model = models;
     }
 }

// Block main
Mobil mobil = new Mobil(models: "Mazda", pabrikans: "Toyota");
Console.WriteLine(mobil.pabrikan);

// Output: Toyota
```

#### Copy constructor

dengan memberikan sebuah object dari class untuk membuat class baru.

```CSharp
class Mobil
 {
     public string pabrikan;
     public string model;
     int tahunPembuatan;
     // Default Constructor
     public Mobil(string pabrikans="toyota", string models="Hatchback", int tahun=1900)
     {
         pabrikan = pabrikans;
         model = models;
         tahunPembuatan = tahun;
     }

     public Mobil(Mobil mobil)
     {
         pabrikan = mobil.pabrikan;
         model = mobil.model;
         tahunPembuatan = mobil.tahunPembuatan;
     }
 }

// Block main
Mobil mobil = new Mobil(models: "Mazda", pabrikans: "Toyota");

Mobil mobil2 = new Mobil(mobil);
Console.WriteLine($"mobil 2: pabrikan {mobil2.pabrikan}, model {mobil2.model}, tahun buat {mobil2.tahunPembuatan}");

// Output: mobil 2: pabrikan Toyota, model Mazda, tahun buat 1900
```

#### Key `this`

Merupakan entitas dari sebuah object itu sendiri. kalau di python `self`.
Sangat berguna jika nama parameter sama dengan nama variabel.

```CSharp
class Mobil
 {
     public string pabrikan;
     public string model;
     public int tahunPembuatan;
     // Default Constructor
     public Mobil(string pabrikan="toyota", string model="Hatchback", int tahunPembuatan=1900)
     {
         this.pabrikan = pabrikan;
         this.model = model;
         this.tahunPembuatan = tahunPembuatan;
     }
 }
```

#### Constructor Chaining

Berguna apabila kita ingin membuat `constructor` yang dapat menerima beberapa variasi dan atau nilai tetap.

```CSharp
class ParkirMobil
{
   string model;
   int harga;

   ParkirMobil() : this("sedan")
   {

   }
   ParkirMobil(string tipe) : this(tipe, 10000)
   {

   }
   ParkirMobil(string model, int harga)
   {
      this.model = model;
      this.harga = harga;
   }
}

```

[Home](../README.md)
