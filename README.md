# How to set StackedHeaders when AutoGenerateColumn as true in WPF DataGrid(SfDataGrid)?
# About the sample

How to set StackedHeaders when AutoGenerateColumn as true in WPF DataGrid(SfDataGrid)?

By default, SfDataGrid does not provide support for setting the stacked header when auto generate column as true. You can achieve this by add stackedHeaderRows in AutoGeneratingColumn event

```c#
private void Sfgrid_AutoGeneratingColumn(object sender, Syncfusion.UI.Xaml.Grid.AutoGeneratingColumnArgs e)
{
  if (sfgrid.StackedHeaderRows.Count == 0)
  {
    var gridSHRow = new Syncfusion.UI.Xaml.Grid.StackedHeaderRow();
    gridSHRow.StackedColumns.Add(new Syncfusion.UI.Xaml.Grid.StackedColumn { ChildColumns = "OrderID,CustomerID", HeaderText = "ID's" });
    sfgrid.StackedHeaderRows.Add(gridSHRow);
  }
}   
```
## Requirements to run the demo
 Visual Studio 2015 and above versions
