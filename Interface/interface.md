#<ins>INTERFACE</ins>

Dengan menggunakan abstract class sebagai antarmuka polimorfik memungkinkan Anda untuk memperluas fungsionalitas atau fitur dari aplikasi Anda. Hanya saja kekurangannya adalah, setiap class yang Anda definisikan harus berada dalam sebuah hirarki pewarisan agar dapat diakses melalui abstract classnya.

## Interface dan Abstraksi

### Mendefinisikan Interface

Konsensusnya penamaanya `I` dan diikuti NamaInterface.

```Csharp
interface INamaInterface
{
    void NamaMethod();
}
```

> Note:
>
> - Kita dapat membuat object dengan `Interface`
> - `Interface` tidak menerima implementasi `method`
> - `Interface` tidak menerima `field`
> - `Interface` mendukung property.

```csharp
interface INamaInterface
{
    // Error
    int Number = 10;
    void NamaMethod();
    {
        // Implementasi method
    }

    // Tidak Error
    int ReadWriteProperty { get; set; }
    int ReadOnlyProperty { get; }
    int WriteOnlyProperty { set; }
}
```

### Interface sebagai kontrak

Saat suatu `class` menggunakan `interface`, maka class tersebut harus diimplementasikan.

```csharp
public interface IKendaraan
{
    // setiap class dengan IKendaraan sebagai antar muka
    // harus mengimplementasikan method Jalankan()
    void Jalankan();
}

public class Mobil: IKendaraan
{
    public void Jalankan()
    {
        Console.WriteLine();
    }
}
```

## Aantarmuka Polimorfik dengan Interface

```csharp
public interface IBisaDichargeListrik
{
    string ChargeBaterai();
}

abstract class KendaraanBermotor
{
    public abstract string Jalankan();
}

abstract class PerangkatMobile
{
    public abstract string Operasikan();
}

class Mobil : KendaraanBermotor, IBisaDichargeListrik
{
    public string ChargeBaterai()
    {
        return "Mengisi Baterai Mobil Listrik";
    }
    public override string Jalankan()
    {
        return "Menjalankan Mobil";
    }
}

class Smartphone : PerangkatMobile, IBisaDichargeListrik
{
    public string ChargeBaterai()
    {
        return "Mengisi Baterai Smartphone";
    }
    public override string Operasikan()
    {
        return "Mengoperasikan Smartphone";
    }
}

// Block main
IBisaDichargeListrik mobil = new Mobil();
IBisaDichargeListrik smartphone = new Smartphone();
Console.WriteLine(Charger(mobil));
Console.WriteLine(Charger(smartphone));
Console.ReadLine();

//
private static string Charger(IBisaDichargeListrik ch)
{
    return ch.ChargeBaterai();
}


// Output:
// Mengisi Baterai Mobil Listrik
// Mengisi Baterai Smartphone
```

## Mengimplementasikan lebih dari 1 `interface`

Sebuah `class` tidak dapat mewarisi `interface`, namun dapat menerima lebih dari 1 `interface`

```csharp
public interface IBisaDichargeListrik
{
    string ChargeBaterai();
}

public interface IBisaDiisiBahanBakar
{
    string IsiBahanBakar();
}

class MobilHybrid : IBisaDiisiBahanBakar, IBisaDichargeListrik
{
    public string ChargeBaterai()
    {
        return "Mengisi Baterai";
    }

    public string IsiBahanBakar()
    {
        return "Mengisi Bahan Bakar";
    }
}

// block main
MobilHybrid toyotaPrius = new MobilHybrid();
Console.WriteLine(toyotaPrius.ChargeBaterai());
Console.WriteLine(toyotaPrius.IsiBahanBakar());
Console.ReadLine();

// Output:
// Mengisi Baterai
// Mengisi Bahan Bakar
```

[Home](../README.md)
