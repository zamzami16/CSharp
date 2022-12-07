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

