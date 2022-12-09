#<ins>DATA TABLE</ins>

## Create Data Table

```csharp
DataTable sourceDataGrid = new DataTable();
```

Add Column to `Data Table`

```csharp
this.sourceDataGrid.Clear(); // opsional
this.sourceDataGrid.Columns.Add("NO", typeof(int));
this.sourceDataGrid.Columns.Add("KODE", typeof(string));
this.sourceDataGrid.Columns.Add("NAMA BARANG", typeof(string));
this.sourceDataGrid.Columns.Add("HARGA BELI", typeof(double));
this.sourceDataGrid.Columns.Add("HARGA JUAL", typeof(double));
```

Add Row to `DataTble`

```csharp
DataRow drow = this.sourceDataGrid.NewRow();
drow["NO"] = idx_ + 1;
drow["KODE"] = kode_;
drow["NAMA BARANG"] = nama_barang_;
drow["HARGA BELI"] = hargaBarang_;
drow["HARGA JUAL"] = hargaJual_;
this.sourceDataGrid.Rows.Add(drow);
```

## Find data in `DataTable` and show it in `DataGridView`
Contoh Project dapat dilihat di [Aplikasi Toko Sederhana](https://github.com/zamzami16/TokoSederhana)
- Filter data yang mau di tampilkan / dicari

  ```csharp
  private DataTable SelectSearchData(string keyWord, DataTable dt)
  {
      DataView dataView = new DataView(dt);
      //dataView.RowFilter = $"'NAMA BARANG' Like '%{keyWord}%' or KODE Like '%{keyWord}%' or 'HARGA BELI' Like '%{keyWord}%' or 'HARGA JUAL' Like '%{keyWord}%'";
      dataView.RowFilter = "[NAMA BARANG] LIKE '%" + keyWord + "%'";
      return dataView.ToTable();
  }
  ```

  lalu tampilkan de `DataGridView`

- Beri warna text kata kunci pencarian di `DataGridView`
  ```csharp
  private void dataGridView1_CellPainting(object sender, DataGridViewCellPaintingEventArgs e)
  {
      // High light and searching apply over selective fields of grid.
      if (e.RowIndex > -1 && e.ColumnIndex > -1 && this.sourceDataGrid.Columns[e.ColumnIndex].ColumnName != "NO")
      {
          // Check data for search
          if (!String.IsNullOrWhiteSpace(textBoxSearch.Text.Trim()))
          {
              String gridCellValue = e.FormattedValue.ToString();
              // check the index of search text into grid cell.
              int startIndexInCellValue = gridCellValue.ToLower().IndexOf(textBoxSearch.Text.Trim().ToLower());
              // IF search text is exists inside grid cell then startIndexInCellValue value will be greater then 0 or equal to 0
              if (startIndexInCellValue >= 0)
              {
                  e.Handled = true;
                  e.PaintBackground(e.CellBounds, true);
                  //the highlite rectangle
                  Rectangle hl_rect = new Rectangle();
                  hl_rect.Y = e.CellBounds.Y + 2;
                  hl_rect.Height = e.CellBounds.Height - 5;
                  //find the size of the text before the search word in grid cell data.
                  String sBeforeSearchword = gridCellValue.Substring(0, startIndexInCellValue);
                  //size of the search word in the grid cell data
                  String sSearchWord = gridCellValue.Substring(startIndexInCellValue, textBoxSearch.Text.Trim().Length);
                  Size s1 = TextRenderer.MeasureText(e.Graphics, sBeforeSearchword, e.CellStyle.Font, e.CellBounds.Size);
                  Size s2 = TextRenderer.MeasureText(e.Graphics, sSearchWord, e.CellStyle.Font, e.CellBounds.Size);
                  if (s1.Width > 5)
                  {
                      hl_rect.X = e.CellBounds.X + s1.Width - 5;
                      hl_rect.Width = s2.Width - 6;
                  }
                  else
                  {
                      hl_rect.X = e.CellBounds.X + 2;
                      hl_rect.Width = s2.Width - 6;
                  }
                  //color for showing highlighted text in grid cell
                  SolidBrush hl_brush;
                  hl_brush = new SolidBrush(Color.Yellow);
                  //paint the background behind the search word
                  e.Graphics.FillRectangle(hl_brush, hl_rect);
                  hl_brush.Dispose();
                  e.PaintContent(e.CellBounds);
              }
          }
      }
  }
  ```
