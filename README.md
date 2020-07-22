# How to set StackedHeaders when AutoGenerateColumn as true in WPF DataGrid(SfDataGrid)?
# About the sample

How to set StackedHeaders when AutoGenerateColumn as true in WPF DataGrid(SfDataGrid)?

By default, you can’t add the StackedHeaderRows in SfDataGrid when generate the column automatically. But you can achieve this by using AutoGeneratingColumn event

```c#
private void Sfgrid_AutoGeneratingColumn(object sender, Syncfusion.UI.Xaml.Grid.AutoGeneratingColumnArgs e)
{
    if (sfgrid.StackedHeaderRows.Count == 0)
    {
        var gridSHRow = new Syncfusion.UI.Xaml.Grid.StackedHeaderRow();
        gridSHRow.StackedColumns.Add(new Syncfusion.UI.Xaml.Grid.StackedColumn { ChildColumns = "OrderID,CustomerID", HeaderText = "ID" });
        gridSHRow.StackedColumns.Add(new Syncfusion.UI.Xaml.Grid.StackedColumn { ChildColumns = "ProductName,OrderDate,Quantity,UnitPrice", HeaderText = "Order Details" });
        gridSHRow.StackedColumns.Add(new Syncfusion.UI.Xaml.Grid.StackedColumn { ChildColumns = "DeliveryDelay,ShipAddress,ContactNumber", HeaderText = "Delivery Details" });
        sfgrid.StackedHeaderRows.Add(gridSHRow);
    }
}   
```
## Requirements to run the demo
 Visual Studio 2015 and above versions
