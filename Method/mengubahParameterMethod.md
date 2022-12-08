Lihat [Method](method.md)

# Mengubah Parameter Pada Method

## Mengubah Parameter dengan `ref`

misal kita ingin menukar 2 buah variabel dengan suatu method, maka yang terjadi:

```CSharp
private static void TukarVariabel(string nama1, string nama2)
{
    string temp = nama1;
    nama1 = nama2;
    nama2 = nama1;
}

// Block main
string nama1 = "Dani";
string nama2 = "Alfan";
TukarVariabel(nama1, nama2);
Console.WriteLine($"Nama 1: {nama1}, nama 2: {nama2}");

// Output: Nama 1: Dani, nama 2: Alfan
```

dari block code diatas, variabel nama1 dan nama2 memiliki nilai tetap. berarti Method TukarVariabel tidak bekerja secara semestinya.

Agar sebuah method dapat mengubah variabel, maka dapat kita berikan kata kunci `ref` pada parameter method.

```CSharp
private static void TukarVariabel(ref string nama1, ref string nama2)
{
    string temp = nama1;
    nama1 = nama2;
    nama2 = nama1;
}

// Block main
string nama1 = "Dani";
string nama2 = "Alfan";
TukarVariabel(ref nama1, ref nama2);
Console.WriteLine($"Nama 1: {nama1}, nama 2: {nama2}");

// Output: Nama 1: Alfan, nama 2: Dani
```

sekarang variabel sudah tertukar. Untuk mempelajari lebih lanjut, bisa lihat [disini](https://mahirkoding.id/pengubah-parameter-pada-method-di-c/#Pengubah-Parameter-ref)

## Mengubah parameter dengan `out`

misal setelah menggunakan suatu method, kita mengharapkan ada nilai dari suatu variabel yang berubah, maka kita dapat menggunakan `out`

```CSharp
private static void DapatkanHasil(int x, int y, out int hasil) => hasil = x + y;

// Block main
int hasil;
int angka1 = 10, angka2 = 11;
DapatkanHasil(angka1, angka2, out hasil);
Console.WriteLine($"Hasil dari {angka1} dan {angka2} adalah {hasil}");

// Output: Hasil dari 10 dan 11 adalah 21
```

dengan menggunakan pengubah variabel `out`, kita bisa mendapatkan lebih dari satu nilai keluaran

```Csharp
private static void DapatkanHasil(int x, int y, out int hasilTambah, out int hasilKali)
{
    hasilTambah = x + y;
    hasilKali = x * y;
}

// Block main
int hasilTambah, hasilKali;
int angka1 = 10, angka2 = 11;
DapatkanHasil(angka1, angka2, out hasilTambah, out hasilKali);
Console.WriteLine($"Hasil dari {angka1} dan {angka2} adalah: hasil Tambah: {hasilTambah} dan hasil kali: {hasilKali}");

// Output: Hasil dari 10 dan 11 adalah: hasil Tambah: 21 dan hasil kali: 110
```

