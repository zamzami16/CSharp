# *USING FIREBIRD*

## Create Connection to DB

```csharp
static public FbConnection Connetc()
{
    FbConnection conn = new FbConnection(@"User ID=SYSDBA;Password=masterkey;Database=localhost:C:\Users\yusuf\OneDrive\Desktop\Axata\DB\TOKOBUKU.fdb");
    conn.Open();
    return conn;
}
```

## Load data from DB

```csharp
public static DataTable Barang(FbConnection conn)
{
    DataTable dt = new DataTable();
    FbDataAdapter da = new FbDataAdapter("select * from rak", conn);
    //da.SelectCommand.Parameters.Add("@id", 123);
    da.Fill(dt);
    da.Dispose();
    return dt;
}
```

## Insert Into

```csharp
var strSql = "INSERT INTO KATEGORI (NAMA, STATUS) VALUES (@nama, @status) returning Id;";
using (var cmd = new FbCommand(strSql, con))
{
    cmd.CommandType = CommandType.Text;
    cmd.Parameters.Add("@nama", namaInput);
    cmd.Parameters.Add("@status", "AKTIF");
    ids = (int)cmd.ExecuteScalar();
    cmd.Dispose();
}
```

## Delete row

```csharp
var strSql = "DELETE FROM KATEGORI WHERE id=@Id";
using (var cmd = new FbCommand(strSql, con))
{
    cmd.CommandType = CommandType.Text;
    cmd.Parameters.Add("@id", selectedId);
    cmd.ExecuteNonQuery();
    cmd.Dispose();
}
MessageBox.Show($"Data {selectedName} deleted.");
```

## Inner Join

```csharp
var query = "select "+
    "b.id_barang, k.nama, p.nama_penerbit, rak.nama, b.nama_barang, b.stock, " +
    "b.harga, b.isbn, b.penulis, b.diskon, b.status, b.barcode, b.keterangan " +
    "from barang b " +
    "INNER JOIN kategori k ON b.id_kategori = k.id " +
    "INNER JOIN penerbit p ON b.id_penerbit = p.id " +
    "INNER JOIN rak ON b.id_rak = rak.id;";
```
