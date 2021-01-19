---
layout: post
title: Stacked Headers | WinUI | DataGrid | Syncfusion
description: Learn about stacked headers (multiple-column headers) support in Syncfusion WinUI DataGrid (SfDataGrid) control and more details.
platform: winui
control: DataGrid
documentation: ug
---

# Stacked Headers in WinUI DataGrid (SfDataGrid)

SfDataGrid supports additional unbound header rows known as `stacked header rows` that span across the DataGrid columns using [StackedHeaderRows](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Grids.SfGridBase.html#Syncfusion_UI_Xaml_Grids_SfGridBase_StackedHeaderRows). You can group one or more columns under each stacked header.

Each [StackedHeaderRow](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Grids.StackedHeaderRow.html) contains the [StackedColumns](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Grids.StackedColumns.html) where each [StackedColumn](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.Grids.StackedColumn.html) contains a number of child columns. `StackedColumn.ChildColumns` property returns the columns which are grouped under the stacked header row. The `StackedColumn.MappingName` is a unique name used for mapping a specific child columns grouped under the same stacked header row whereas, the `StackedColumn.HeaderText` returns the text that displays in stacked header row.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="sfDataGrid"
                        AllowSorting="True"
                        AutoGenerateColumns="True"
                        ColumnWidthMode="AutoLastColumnFill"
                        ItemsSource="{Binding OrdersDetails}">
            <syncfusion:SfDataGrid.StackedHeaderRows>
                <grids:StackedHeaderRow>
                    <grids:StackedHeaderRow.StackedColumns>
                        <grids:StackedColumn ChildColumns="OrderID,OrderDate,ProductID,Quantity,UnitPrice,ShipCity,ShipAddress" HeaderText="Sales Details" />                       
                    </grids:StackedHeaderRow.StackedColumns>
                </grids:StackedHeaderRow>
                <grids:StackedHeaderRow>
                    <grids:StackedHeaderRow.StackedColumns>
                        <grids:StackedColumn ChildColumns="OrderID,OrderDate" HeaderText="Order Details" />
                        <grids:StackedColumn ChildColumns="Quantity,UnitPrice" HeaderText="Product Details" />
                        <grids:StackedColumn ChildColumns="ShipCity,ShipAddress" HeaderText="Shipping Details" />
                    </grids:StackedHeaderRow.StackedColumns>
                </grids:StackedHeaderRow>
            </syncfusion:SfDataGrid.StackedHeaderRows>    
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
var stackedHeaderRow1 = new StackedHeaderRow();
stackedHeaderRow1.StackedColumns.Add(new StackedColumn() { ChildColumns = "OrderID,OrderDate,Quantity,UnitPrice,ShipCity,ShipAddress" , HeaderText = "Sales Details", MappingName = "SalesDetails" });
sfDataGrid.StackedHeaderRows.Add(stackedHeaderRow1);

var stackedHeaderRow2 = new StackedHeaderRow();
stackedHeaderRow2.StackedColumns.Add(new StackedColumn() { ChildColumns = "OrderID,OrderDate", HeaderText = "Order Details", MappingName = "OrderDetails" });
stackedHeaderRow2.StackedColumns.Add(new StackedColumn() { ChildColumns = "Quantity,UnitPrice", HeaderText = "Product Details", MappingName = "ProductrDetails" });
stackedHeaderRow2.StackedColumns.Add(new StackedColumn() { ChildColumns = "ShipCity,ShipAddress", HeaderText = "Shipping Details", MappingName = "ShippingDetails" });
sfDataGrid.StackedHeaderRows.Add(stackedHeaderRow2);
{% endhighlight %}
{% endtabs %}

![WinUI datagrid shown with stacked header rows](Stacked-Headers-images/Stacked-Headers-image1.png)

## Stacked Headers using Data Annotation

You can also add the stacked headers using `GroupName` property of [Data Annotations Display attributes](https://msdn.microsoft.com/en-us/library/system.componentmodel.dataannotations.displayattribute.aspx). 

{% tabs %}
{% highlight c# %}
public class OrderInfo : NotificationObject
{
    private int orderID;
    private double _unitPrice;
    private DateTime _orderDate;
    private string _shipcity;
    private int _quantity;
    private string _shipAddress;

    public OrderInfo()
    {

    }

    [Display(Name = "Order ID", GroupName = "Order Details")]
    public int OrderID
    {
        get
        {
            return orderID;
        }
        set
        {
            orderID = value;
            RaisePropertyChanged("OrderID");
        }
    }


    [Display(Name = "Order Date", GroupName = "Order Details")]
    public DateTime OrderDate
    {
        get
        {
            return _orderDate;
        }
        set
        {
            _orderDate = value;
            RaisePropertyChanged("OrderDate");
        }
    }


    [Display(Name = "Unit Price", GroupName = "Product Details")]
    public double UnitPrice
    {
        get
        {
            return _unitPrice;
        }
        set
        {
            _unitPrice = value;
            RaisePropertyChanged("UnitPrice");
        }
    }


    [Display(Name = "Quantity", GroupName = "Product Details")]
    public int Quantity
    {
        get
        {
            return _quantity;
        }
        set
        {
            _quantity = value;
            RaisePropertyChanged("Quantity");
        }
    }


    [Display(Name = "Ship Address", GroupName = "Shipping Details")]
    public string ShipAddress
    {
        get
        {
            return _shipAddress;
        }
        set
        {
            _shipAddress = value;
            RaisePropertyChanged("ShipAddress");
        }
    }
    
    [Display(Name = "Ship City", GroupName = "Shipping Details")]
    public string ShipCity
    {
        get
        {
            return _shipcity;
        }
        set
        {
            _shipcity = value;
            RaisePropertyChanged("ShipCity");
        }
    }
}

{% endhighlight %}
{% endtabs %}

## Adding child columns

You can add the child columns in particular stacked header directly.

{% tabs %}
{% highlight c# %}
var childColumn = this.sfDataGrid.StackedHeaderRows[1].StackedColumns[0].ChildColumns;
this.sfDataGrid.StackedHeaderRows[1].StackedColumns[0].ChildColumns = childColumn + ",OrderID";
{% endhighlight %}
{% endtabs %}

## Removing child columns

Similarly, you can remove the child columns from particular stacked header directly.

{% tabs %}
{% highlight c# %}
var removingColumns = this.sfDataGrid.StackedHeaderRows[1].StackedColumns[0].ChildColumns.Split(',').ToList<string>();
string childColumns = string.Empty;
foreach (var stackedColumnName in removingColumns.ToList())
{
    if (stackedColumnName.Equals("OrderID"))
    {
        removingColumns.Remove(stackedColumnName);
    }
    else
        childColumns = childColumns + stackedColumnName + ",";
    }
    this.sfDataGrid.StackedHeaderRows[1].StackedColumns[0].ChildColumns = childColumns;
}
this.sfDataGrid.StackedHeaderRows[1].StackedColumns[0].ChildColumns = childColumns;
{% endhighlight %}
{% endtabs %}

## Changing stacked header row height

You can change the height of stacked header rows using [SfDataGrid.QueryRowHeight](https://help.syncfusion.com/cr/winui/Syncfusion.UI.Xaml.DataGrid.SfDataGrid.html#Syncfusion_UI_Xaml_DataGrid_SfDataGrid_QueryRowHeight) event.

{% tabs %}
{% highlight c# %}
this.sfDataGrid.QueryRowHeight += sfDataGrid_QueryRowHeight;

void sfDataGrid_QueryRowHeight(object sender, QueryRowHeightEventArgs e)
{
    if (e.RowIndex < this.sfDataGrid.GetHeaderIndex())
    {
        e.Height = 50;
        e.Handled = true;
    }
}
{% endhighlight %}
{% endtabs %}