# <ins>Switch statement</ins>
Apabila terlalu banyak pilihan, maka statement IF dapat diganti dengan switch agar lebih efektif.
## Penggunaan
```Csharp
int data = 0;
switch (data)
{
    case 0:
        // Code block
        break;
    case 1:
        // code block
        break;
    default:
        break;
}
```
> Penggunaan switch lebih enak dengan type enum
> contoh:
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

// Main block

int data = 0;
switch (data)
{
    case (int)namaHari.Senin:
        // Code block
        break;
    case (int)namaHari.Selasa:
        // code block
        break;
    default:
        break;
}

```

[Home](../README.md)