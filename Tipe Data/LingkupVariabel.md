# <ins>LINGKUP VARIABEL</INS>

## Lingkup Class

dengan menggunakan `public` keyword, kita bisa mengakses sebuah variabel dalam suatu class.

```CSharp
public class SomeValue
    {
        public string someValue = "value";

        public string getValue()
        {
            return someValue;
        }
    }
```

## Lingkup Method

hanya bisa diakses didalam method tersebut.

```CSharp
public class SomeValue
    {
        public string someValue = "value";

        public string getValue()
        {
            int newValue = 10;
            return someValue;
        }

        newValue = 11; // Akan membuat error, karena tidak bisa diakses di luar method nya.
    }
```

## Lingkup Block

Variabel hanya aktif dalam suatu block tertentu, misal Looping

```Csharp
for (int i = 0; i < 10; i++)
{
    Console.WriteLine(i);
}

Console.WriteLine(i); // akan membuat error
```

## Hal-hal yang perlu diperhatikan

Hindari penamaan variabel yang sama pada lingkup yang berbeda. Misal kita punya variabel `a` pada lingkup `class` dan kita membuat variabel baru dengan nama `a` pada lingkup method, maka akan menggantikan variabel yang sudah ada di `class`.
