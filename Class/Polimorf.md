#<ins>POLIMORF dan Ekstensibilitas Program</ins>

## Polimorf

Sifat keturunan yang dimiliki oleh induk. Base `class` akan memiliki sifat yang dimiliki oleh `class` turunannya.

Misalkan base class ialah `KendaaraanBermotor` dan class keturunannya adalah `Mobil` dan `Motor`, maka saat kita membuat object `KendaraanBermotor` dengan instance object `Mobil` atau `Motor`, kita dapat melihat `Mobil` atau `Motor` merupakan `KendaraanBermotor`.

```csharp
KendaraanBermotor mobil = new Mobil();
KendaraanBermotor motor = new Motor();
```

Penerapan ini hanya dapat diperoleh dengan `method overriding`.

> Note: `method hiding` hanya akan menyembunyikan `method base` nya saja saat membuat object. Jika object tersebut dibuat berdasarkan `base` nya, maka masih dapat menggunakan `method yang ada di base`.

## Interaksi antar Object

Katakanlah kita punya class `Pengemudi` yang dapat mengendarai `Motor` atau `Mobil`.

```csharp
abstract class KendaraanBermotor
{
    protected virtual void Jalankan()
    {
        Console.WriteLine("Berjalan maju");
    }
}

class Mobil : KendaraanBermotor
{
    protected override void Jalankan()
    {
        Console.WriteLine("Menjalankan sebuah mobil:");
        Console.WriteLine("1.Memindah tuas transmisi dari N ke D");
        Console.WriteLine("2.Injak pedal gas");
    }
}

class Motor : KendaraanBermotor
{
    protected override void Jalankan()
    {
        Console.WriteLine("Menjalankan sebuah motor:");
        Console.WriteLine("1.Putar handle gas");
    }
}
class Pengemudi
{
    public void Mengemudi(Mobil mobil)
    {
        mobil.Jalankan();
    }
}

// Block main
Mobil mobil = new Mobil();
Motor motor = new Motor();
Pengemudi pengemudi = new Pengemudi();
pengemudi.Mengemudi(mobil);

// baris kode program berikut ini menghasilkan eror
// pengemudi hanya mengerti tipe Mobil saja
pengemudi.Mengemudi(motor); // muncul error
```

hal ini dikarenakan class `Pengemudi` hanya mengerti atau menerima class `Mobil` saja. Solusinya adalah dengan `Antarmuka Polimorfik`

> Note:
> C# tidak mau menerima inheritance 2 class.

## Antarmuka Polimorfik

dengan mengganti class `Pengemudi` pada code diatas dengan

```csharp
class Pengemudi
{
    public void Mengemudi(KendaraanBermotor kb)
    {
        kb.Jalankan();
    }
}
```

maka kita `Pengemudi` akan dapat menjalankan kendaraan bermotor (`Motor` dan `Mobil`)

```Csharp
// Block main
Mobil mobil = new Mobil();
Motor motor = new Motor();
Pengemudi pengemudi = new Pengemudi();
pengemudi.Mengemudi(mobil);
pengemudi.Mengemudi(motor);
```

## Ekstensibilitas

Code yang baik akan mengikuti prinsip **`OCP`** **_Open Closed Priciple_**. Dapat dikembangkan, namun tanpa harus menambahkan atau menulis ulang code.

dengan antarmuka polimorf, kedepannya, object `Pengemudi` akan dapat menjalankan segala jenis kendaraan bermotor tanpa harus menyentuh class `Pengemudi`.

Misal kita membuat class baru `Bus` dari jenis `KendaraanBermotor`, maka pengemudi nantinya akan dapat menjalankan `Bus` tersebut.
```csharp
class Bus : KendaraanBermotor
{
    public override void Jalankan()
    {
        Console.WriteLine("Menjalankan sebuah bus:");
        Console.WriteLine("1.Memindah tuas transmisi");
        Console.WriteLine("2.Injak kopling");
        Console.WriteLine("3.Injak pedal gas,lepas pedal kopling pelan-pelan");
    }
}

// Block main
KendaraanBermotor mobil = new Mobil();
KendaraanBermotor motor = new Motor();
KendaraanBermotor bus = new Bus();
Pengemudi pengemudi = new Pengemudi();
pengemudi.Mengemudi(mobil);
Console.WriteLine("");
pengemudi.Mengemudi(motor);
Console.WriteLine("");
pengemudi.Mengemudi(bus);
```

## Keterbatasan Abstract Class
Abstract memiliki keterbatasan karena semua method yang disediakan di `Base` harus digunakan pada class `Child` nya. Dengan demikian, katakanlah kita mempunyai `MobilListrik` dan `Mobil` yang mengikuti base `KendaraanBermotor` yang mana memiliki method `pengisianBBM`, maka akan terjadi kesulitan dengan `MobilListrik`. solusinya dengan [interface](Interface/interface.md)

[Home](../README.md)
