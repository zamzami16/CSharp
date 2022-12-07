# <ins>Enum</ins>

Sekumpulan konstanta / tidak dapat diganti, dan dapat diakses langsung nama konstantanya.
contoh:
```Csharp
public enum namaHari
{
    Senin,
    Selasa,
    Rabu,
    Kamis,
    Jumat,
    Sabtu,
    Minggu,
    AkhirPekan = Sabtu|Minggu
}

// Block code in main

namaHari akhirPekan = namaHari.AkhirPekan;
Console.WriteLine(akhirPekan);
Console.WriteLine($"Apakah minggu adalah akhir pekan? {(namaHari.AkhirPekan & namaHari.Minggu) == namaHari.Minggu}");

// output: Apakah minggu adalah akhir pekan? True
```

kita juga bisa mengakses indexnya dengan
```Csharp
int indexSenin = (int)namaHari.Senin;
Console.WriteLine($"Index hari senin adalah {indexSenin}");

// Output: Index hari senin adalah 0
```

Kita juga bisa menginisiasi index pada enum
```Csharp
public enum namaHari
{
    Senin = 1,
    Selasa,     // akan berindex 2
    Rabu,       // akan berindex 3
    Kamis = 10,
    Jumat,      // akan berindex 11
    Sabtu,
    Minggu,
    AkhirPekan = Sabtu|Minggu
}

// Kode pada min
int indexSenin = (int)namaHari.Senin;
Console.WriteLine($"Index hari senin adalah {indexSenin}");
int indexSelasa = (int)namaHari.Selasa;
Console.WriteLine($"Index hari kamis adalah {indexSelasa}");
int indexKamis = (int)namaHari.Kamis;
Console.WriteLine($"Index hari kamis adalah {indexKamis}");
int indexJumat = (int)namaHari.Jumat;
Console.WriteLine($"Index hari kamis adalah {indexJumat}");

// Output:
// Index hari senin adalah 1
// Index hari kamis adalah 2
// Index hari kamis adalah 10
// Index hari kamis adalah 11
```

**Contoh dari w3schools**
```Csharp
enum Level 
{
  Low,
  Medium,
  High
}

static void Main(string[] args) 
{
  Level myVar = Level.Medium;
  switch(myVar) 
  {
    case Level.Low:
      Console.WriteLine("Low level");
      break;
    case Level.Medium:
       Console.WriteLine("Medium level");
      break;
    case Level.High:
      Console.WriteLine("High level");
      break;
  }
}

// Output: Medium level
```
[Home](../README.md)