# <ins>PEWARISAN SIFAT / INHERITANCE</ins>

## Inheritance
di C#, dapat menggunakan
```CSharp
class MyClass2: MyClass
{

}
```
contohnya:
```CSharp
class KendaraanBermotor
{
    public int jumlahRoda { get; set; }
    public string bahanBakar { get; set; }
    public string NoPol { get; set; }
    public string Transmisi { get; set; }

    public void HidupkanMesin() => Console.WriteLine("Mesin kendaraan dihidupkan");
    public void MatikanMesin() => Console.WriteLine("Mesin kendaraan dimatikan");
    public void Jalan() => Console.WriteLine("Kendaraan Berjalan");

}

class Mobil : KendaraanBermotor
{
    public Mobil()
    {
        this.jumlahRoda = 4;
        this.bahanBakar = "Pertamax";
        this.Transmisi = "Manual";
    }
}

class Motor: KendaraanBermotor
{
    public Motor()
    {
        this.jumlahRoda = 2;
        this.bahanBakar = "Pertalite";
        this.Transmisi = "Otomatis";
    }
}

// Block main
Mobil kijang = new Mobil();
kijang.NoPol = "AG 2209 XX";

Motor vario = new Motor();
vario.NoPol = "AG 2210 XX";
```

