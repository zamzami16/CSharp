# <ins>While statement</ins>

## Penggunaan while
```Csharp
while (true)
{
    // Block code
}
```
contoh:
```Csharp
int i = 0;
while (i < 5) 
{
  Console.WriteLine(i);
  i++;
}
```

## Penggunaan do/while
mengeksekusi code block, baru mengcek kondisi
```Csharp
do 
{
  // Block code
}
while (condition);
```
contoh:
```Csharp
int i = 1;
do
{
    Console.WriteLine(i);
    i++;
}
while (i < 5);
```
