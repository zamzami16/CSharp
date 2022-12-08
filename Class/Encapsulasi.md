# <ins>Encapsulasi</ins>

## <ins>Access Modifier</ins>

### Public

`public` dapat diakses siapa saja.

### Private

`private` hanya dapat diakses didalam class tersebut.

> Jika tidak diberikan kata kunci, maka secara langsung akses dibuat ke `private`

### Protected

`protected` membatasi akses hanya dari class tersebut, dan class yang mewarisi sifat tidak punya akses.

### Internal

`internal` hanya dapat diakses dari program yang masih dalam 1 assembly.

## Property

Memberikan batasan akses / memberikan pintu akses untuk mendapatkan atau mengubah suatu value.

```
<acces_modifier> <return_type> <property_name>
{
    get
    {
        // untuk medapatkan nilai
    }
    set
    {
        // untuk menetapkan nilai
    }
}
```

dapat ditulis dengan

```Csharp
class SebuahClass
{
public int BilanganBulat { get; set; }
}
```

## Utility Class

Saat kita ingin mengakses method dari suatu class tanpa harus membuat object dari class tersebut.

### Static `class`

Sekumpulan method di dalam suatu class, tanpa membuat object class.

```CSharp
public static class Perhitungan
{
    public static int penjumlahan(int a, int b) => a + b;
    public static int pengurangan(int a, int b) => a - b;
    public static int perkalian(int a, int b) => a * b;
}

// Block main
Console.WriteLine(Perhitungan.pengurangan(10, 1));
Console.WriteLine(Perhitungan.perkalian(10, 1));
```

### Static Member

Apabila member dari sebuah class dibuat static, maka member tersebut akan dapat diakses tanpa membuat object dari class tersebut. Dalam artian member tersebut tidak menjadi bagian dari object, melainkan murni bagian class tersebut.

### Static Constructor

Digunakan dalam 2 kondisi:

- Untuk menginisiasi static member
- Untuk menjalankan sebuah operasi yang hanya perlu dijalankan sekali

Pemanggilannya dalam 2 kondisi:

- Sebelum object pertama dari class dibuat
- Sebelum sebuah static member digunakan sebagai referensi

> Note:
>
> - `static constructor` tidak dapat menerima access modifier
> - `static constructor` tidak dapat menerima input
> - `static constructor` tidak dapat dikontrol kapan pemanggilannya
> - `static constructor` tidak dapat dipanggil langsung

### Private constructor

Perilakunya sama dengan `static class`


[Home](../README.md)
