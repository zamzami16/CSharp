# <ins>Abstract Class</ins>

Mencegah pembuatan object dari `class` induk yang diwariskan ke class anaknya.

```Csharp
abstract class KendaraanBermotor
{
    // block code here
}
```

# <ins>Menyediakan Method Overriding</ins>

Memberikan sebuah method dengan nama yang sama, namun dapat diimplementasikan berbeda pada masing-masing `class` turunannya.

## `abstract method`

dengan menambahkan kata `abstract` pada method `base`.

```Csharp
public abstract void JalanMaju();
```

> Limitations:
>
> - `abstract method` hanya dapat dibuat di `abstract class` saja.
> - Tidak boleh punya implementasi apapun.
> - harus diakhiri `;`.
> - Harus diimplementasikan pada class turunannya.

## `virtual method`

dengan menambahkan kata `virtual`. dapat digunakan atau tidak dalam class turunannya, dan dapat digunakan di `class` biasa.

```CSharp
public virtual void JalanMaju(){ }
```

# <ins>Menggantikan Method pada Base</ins>

## Method Hiding

Menggunakan `new` pada method turunannya.

```csharp
abstract class KendaraanBermotor
{
    public int jumlahRoda { get; set; }
    public string bahanBakar { get; set; }
    public string NoPol { get; set; }
    public string Transmisi { get; set; }

    public void HidupkanMesin() => Console.WriteLine("Mesin kendaraan dihidupkan");
    public void MatikanMesin() => Console.WriteLine("Mesin kendaraan dimatikan");
    public virtual void Jalan() => Console.WriteLine("Kendaraan Berjalan");

}

class Mobil : KendaraanBermotor
{
    public new void Jalan()
    {
        // block code here
    }
    public Mobil()
    {
        this.jumlahRoda = 4;
        this.bahanBakar = "Pertamax";
        this.Transmisi = "Manual";
    }
}
```

## Method Overriding
dengan menggunakan `override` pada methode turunannya.
```csharp
abstract class KendaraanBermotor
{
    public int jumlahRoda { get; set; }
    public string bahanBakar { get; set; }
    public string NoPol { get; set; }
    public string Transmisi { get; set; }

    public void HidupkanMesin() => Console.WriteLine("Mesin kendaraan dihidupkan");
    public void MatikanMesin() => Console.WriteLine("Mesin kendaraan dimatikan");
    public virtual void Jalan() => Console.WriteLine("Kendaraan Berjalan");

}

class Motor: KendaraanBermotor
{
    public override void Jalan()
    {
        // block code here
    }
    public Motor()
    {
        this.jumlahRoda = 2;
        this.bahanBakar = "Pertalite";
        this.Transmisi = "Otomatis";
    }
}
```
