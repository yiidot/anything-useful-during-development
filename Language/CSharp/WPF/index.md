1. WPF中DataGrid控件绑定了一个类A,如果需要把类A中的所有字段都绑定显示，则可以通过设置他的属性值 AutoGenerateColumns=”True”；
如果仅需要特定的Path来绑定特定需要展示的值，如Id这种不需要展示的就不显示的话，可以在DataGrid上设置为 AutoGenerateColumns=”False” ，这样就可以只显示有Path绑定的那个属性了

2. WPF使窗体弹出时在屏幕居中位置
```c#
 public partial class MainWindow : Window
{
    public MainWindow()
    {
        WindowStartupLocation = WindowStartupLocation.CenterScreen;
        InitializeComponent();
  }
}
```

3. 实现DataGrid控件宽充满布局 及 Header内容居中

3.1 充满布局
显式设置DataGridTextColumn的属性Width=“*” 实现DataGrid控件宽充满布局

3.2 设置Header居中
```xml
<!-- 设置Header居中 -->
 <DataGrid.ColumnHeaderStyle>
     <Style TargetType="DataGridColumnHeader">
         <Setter Property="HorizontalContentAlignment" Value="Center">
         </Setter>
     </Style>
 </DataGrid.ColumnHeaderStyle>
```
