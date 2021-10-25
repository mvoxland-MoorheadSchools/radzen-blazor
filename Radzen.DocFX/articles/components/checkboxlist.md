# CheckBoxList component
This article demonstrates how to use the CheckBoxList component.

## Statically declared items
```
<RadzenCheckBoxList @bind-Value=@values TValue="int" Change=@OnChange>
    <Items>
        <RadzenCheckBoxListItem Text="Orders" Value="1" />
        <RadzenCheckBoxListItem Text="Employees" Value="2" />
        <RadzenCheckBoxListItem Text="Customers" Value="3" />
    </Items>
</RadzenCheckBoxList>
@code {
    IEnumerable<int> values = new int[] { 1 };

    void OnChange(IEnumerable<int> value)
    {
        Console.WriteLine($"Value changed to {string.Join(", ", value)}");
    }
}
```

## Items populated from data
```
<RadzenCheckBoxList Data="@data" TextProperty="Name" ValueProperty="Id" @bind-Value=@values TValue="int" Change=@OnChange />
@code {
    IEnumerable<int> values = new int[] { 1 };
    IEnumerable<MyObject> data = new MyObject[] {
        new MyObject(){ Id = 1 , Name = "Orders"}, new MyObject() { Id = 2 , Name = "Employees"}, new MyObject() { Id = 3 , Name = "Customers" } };

    void OnChange(IEnumerable<int> value)
    {
        Console.WriteLine($"Value changed to {string.Join(", ", value)}");
    }
}
```

## Statically declared and populated from data items
```
<RadzenCheckBoxList Data="@data" TextProperty="Name" ValueProperty="Id" @bind-Value=@values TValue="int" Change=@OnChange>
    <Items>
        <RadzenCheckBoxListItem Text="Static item" Value="0" />
    </Items>
</RadzenCheckBoxList>
@code {
    IEnumerable<int> values = new int[] { 1 };
    
    IEnumerable<MyObject> data = new MyObject[] {
        new MyObject(){ Id = 1 , Name = "Orders"}, new MyObject() { Id = 2 , Name = "Employees"}, new MyObject() { Id = 3 , Name = "Customers" } };

    void OnChange(IEnumerable<int> value)
    {
        Console.WriteLine($"Value changed to {string.Join(", ", value)}");
    }
}
```