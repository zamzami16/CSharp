#<ins>EXCEPTIONS</ins>

```csharp // adopt from microsoft.com
try
{
    using (StreamReader sr = File.OpenText("data.txt"))
    {
        Console.WriteLine($"The first line of this file is {sr.ReadLine()}");
    }
}
catch (FileNotFoundException e)
{
    Console.WriteLine($"The file was not found: '{e}'");
}
catch (DirectoryNotFoundException e)
{
    Console.WriteLine($"The directory was not found: '{e}'");
}
catch (IOException e)
{
    Console.WriteLine($"The file could not be opened: '{e}'");
}
```
