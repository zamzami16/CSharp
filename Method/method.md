# <ins>Method</ins>

## Deklarasi method

```CSharp
private static void NamaMethod()
{
    // block code
}
```

penjelasan:

> private: akses identifier
> static: method hanya ikut class, tidak ikut di object
> void: tidak memiliki nilai return

## Meringkas method

kita bisa meringkas penulisan method dengan:

```CSharp
private static int NamaMethod(int x = 10, int y = 12) => x + y;
```

## Parameter & Argument

```CSharp
private static int NamaMethod(int x, int y)
{
    return x + y;
}

// Block main
Console.WriteLine($"Hasil penjumlahan 10 dan 12 adalah {NamaMethod(10, 12)}");

// Output: Hasil penjumlahan 10 dan 12 adalah 22
```

> Note:
>
> - int --> Type data hasil
> - x & y --> Parameter
> - 10 & 12 --> Argumen

## Method with default argument

```CSharp
private static int NamaMethod(int x = 10, int y = 12)
{
    return x + y;
}

// Block main
Console.WriteLine($"Hasil NamaMethod {NamaMethod()}");
Console.WriteLine($"Hasil penjumlahan 11 dan 12 adalah {NamaMethod(11, 12)}");

// Output:
// Hasil NamaMethod 22
// Hasil penjumlahan 11 dan 12 adalah 23
```

## Argumen bernama

kita bisa mengakses method tanpa memperhatikan urutan parameternya dengan memberikan nama argumen pada method tersebut

```Csharp
// Sebuah method
private static int NamaMethod(int x = 10, int y = 12, int z = 10) => x + y + z;

// Block main
int a = NamaMethod(y: 3, x: 10);
Console.WriteLine(a);

// Output: 23
```

## Method Overloading

Dengan method overloading, kita bisa membuat beberapa method dengan nama yang sama, namun dapat menerima parameter yang berbeda.
contoh:

```CSharp
// Method pertama
private static int NamaMethod(int x = 10, int y = 12, int z = 10) => x + y + z;
// Method kedua
private static double NamaMethod(double x = 10.0, double y = 12.0, double z = 10.0) => x + y + z;
// Method ke tiga
private static string NamaMethod(string a = "alamat", string b = "Jalan") => a + b;

// Block main
// Method 1
int hasilMethod1 = NamaMethod(x: 10, y: 11, z: 12);
Console.WriteLine($"Hasil Method1 {hasilMethod1}");
// Method 2
double hasilMethod2 = NamaMethod(y: 10.2, x: 1.1, z: 12.0);
Console.WriteLine($"Hasil Method2 {hasilMethod2}");
// Method 3
string hasilMethod3 = NamaMethod(a: "Alamat anda", b: " Jalan Kenari");
Console.WriteLine($"Hasil Method3 {hasilMethod3}");

// Output:
// Hasil Method1 33
// Hasil Method2 23,3
// Hasil Method3 Alamat anda Jalan Kenari
```


[Home](../README.md)