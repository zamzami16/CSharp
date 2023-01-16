# <ins>Data Grid View</ins>

## Update Row Number

```csharp
 private void dataGridView1_RowPostPaint(object sender, DataGridViewRowPostPaintEventArgs e)
{
    var grid = sender as DataGridView;
    var rowIdx = (e.RowIndex + 1).ToString();

    var centerFormat = new StringFormat()
    {
        // right alignment might actually make more sense for numbers
        Alignment = StringAlignment.Center,
        LineAlignment = StringAlignment.Center
    };

    var headerBounds = new Rectangle(e.RowBounds.Left, e.RowBounds.Top, grid.RowHeadersWidth, e.RowBounds.Height);
    e.Graphics.DrawString(rowIdx, this.Font, SystemBrushes.ControlText, headerBounds, centerFormat);
}
```
