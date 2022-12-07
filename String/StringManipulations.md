# <ins>Memanipulasi String</ins>

## Membuat string
```Csharp
String nama = "Ayam Goreng";
```
or
```Csharp
String nama;
nama = "Ayam Goreng";
```

Bisa juga dengan tanda **@**
```Csharp
deskripsi = @"
Lorem ipsum dolor sit amet consectetur adipisicing elit
Hic suscipit aperiam, vitae sequi in dolores eligendi
magnam ea dolor molestias?"
;
```

## Menggabungkan String

* Menggunakan **+**
  ```Csharp
    Console.WriteLine("Aku" + "kamu");
  ```
* Interpolations
  ```Csharp
  String[] hewani = {"ayam", "kambing"}
  Console.WriteLine($"nama hewan {hewani[0]} {hewani[1]");
  Console.WriteLine("nama hewan {0} dan {1}", hewani[0], hewani[1]);
  ```
* Menggunakan Concat
  ```Csharp
  String nama, alamat;
  nama = "Saya";
  alamat = "Plosokursi";
  Console.WriteLine(string.Concat(nama, alamat));
  ```


## Akses String
misal kita punya variabel alamat
```Csharp
String alamat = "Jalan Cakra Buwana";
```

* Akses element string
  ```Csharp
  Console.WriteLine("Huruf pertama dari alamat adalah `{0}`", alamat[0]);
  Console.WriteLine("Huruf 5 pertama dari alamat adalah `{0}`", alamat.Substring(0, 5));
  ```
* Akses index string
  ```Csharp
  Console.WriteLine("Index huruf a dari `alamat` adalah {0}", alamat.IndexOf("a"));
  ```


