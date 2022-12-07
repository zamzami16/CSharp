# <ins>Memanipulasi String</ins>

## Membuat string
```
String nama = "Ayam Goreng";
```
or
```
String nama;
nama = "Ayam Goreng";
```

Bisa juga dengan tanda **@**
```
deskripsi = @"
Lorem ipsum dolor sit amet consectetur adipisicing elit
Hic suscipit aperiam, vitae sequi in dolores eligendi
magnam ea dolor molestias?"
;
```

## Menggabungkan String

* Menggunakan **+**
  ```
    Console.WriteLine("Aku" + "kamu");
  ```
* Interpolations
  ```
  String[] hewani = {"ayam", "kambing"}
  Console.WriteLine($"nama hewan {hewani[0]} {hewani[1]");
  Console.WriteLine("nama hewan {0} dan {1}", hewani[0], hewani[1]);
  ```
* Menggunakan Concat
  ```
  String nama, alamat;
  nama = "Saya";
  alamat = "Plosokursi";
  Console.WriteLine(string.Concat(nama, alamat));
  ```


## Akses String
misal kita punya variabel alamat
```
String alamat = "Jalan Cakra Buwana";
```

* Akses element string
  ```
  Console.WriteLine("Huruf pertama dari alamat adalah `{0}`", alamat[0]);
  Console.WriteLine("Huruf 5 pertama dari alamat adalah `{0}`", alamat.Substring(0, 5));
  ```
* Akses index string
  ```
  Console.WriteLine("Index huruf a dari `alamat` adalah {0}", alamat.IndexOf("a"));
  ```


