# <ins>Array in C#</ins>
## Array 1D
contoh penggunaan.
```Csharp
int[] aa = new int[4];
aa[0] = 11;
aa[1] = 115;
aa[3] = 11100;
Console.WriteLine($"Panjang array aa adalah {aa.Length}, bilangan pertama adalah {aa[0]}, bilangan terakhir {aa[aa.Length-1]}");
```
bisa juga dengan langsung menginisiasi nya.
```Csharp
int[] aa = { 11, 115, 0, 11100 };
```

## Array 2D
```Csharp
int[,] aa = new int[2, 2];
aa[0, 0] = 0;
aa[0, 1] = 1;
aa[1, 0] = 10;
aa[1, 1] = 11;
foreach (var item in aa)
{
    Console.WriteLine(item);
}
```
bisa juga dengan langsung menginisiasi nya.
```Csharp
int[,] aa = {
    {0, 1},
    {10, 11}
};
```

## Array 3D
```Csharp
int[,,] aa = new int[2, 3, 3];
aa[0, 0, 0] = 0;
aa[0, 0, 1] = 1;
aa[0, 0, 2] = 2;
aa[1, 1, 1] = 50;

foreach (var item in aa)
{
    Console.WriteLine(item);
}
```
atau bisa dengan langsung menginisiasinya
```Csharp
int[,,] aa = {
    {
        {11,12,13 }, {21,23,24}
    },
    {
        {31,32,33 }, {41,42,43}
    }
};
```

## Mengakses Array
```Csharp
int[,] aa = {
    {0, 1},
    {10, 11}
};
int dump = aa[0, 0];
```

## Sortir array
```Csharp
int[] aa = { 1, 4, 6, 87, 3, 6, 8, 32 };
Array.Sort(aa);
foreach (var item in aa)
{
    Console.WriteLine(item);
}
```

## Operasi sederhana dengan array
> Operasi **Min**, **Max**, **Sum**
```Csharp
int[] aa = { 1, 4, 6, 87, 3, 6, 8, 32 };
Console.WriteLine($"Nilai terkecil dari array `aa` adalah {aa.Min()}");
Console.WriteLine($"Nilai terbesar dari array `aa` adalah {aa.Max()}");
Console.WriteLine($"Total nilai dari array `aa` adalah {aa.Sum()}");
```
