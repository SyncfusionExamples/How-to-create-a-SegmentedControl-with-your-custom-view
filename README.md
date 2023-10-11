# Creating a project
Create a new BlankApp (Xamarin.Forms.Portable) application in Visual Studio for Xamarin.Forms.

## Adding SfSegmentedControl in Xamarin.Forms
Add the required assembly references to the PCL and renderer projects as discussed in the Assembly deployment  section.

Import the control namespace as shown in the following code.
[XAML]
```
xmlns:buttons="clr-namespace:Syncfusion.XForms.Buttons;assembly=Syncfusion.Buttons.XForms"
```
[C#]
```
using Syncfusion.XForms.Buttons;
```
Set the control to content in ContentPage.

[XAML]
```
 <ContentPage.Content>
            <buttons:SfSegmentedControl  />
 </ContentPage.Content>
```
[C#]
```
public partial class MainPage : ContentPage
{
    private SfSegmentedControl segmentedControl;
    public MainPage()
    {
        InitializeComponent();
        segmentedControl = new SfSegmentedControl();
        this.Content = segmentedControl;
    }
}
```
# How to create a SegmentedControl with your custom view

SegmentedControl provides support to add any custom view as their segment by populating collections of custom views as ItemsSource.

The code below shows how to add image view collection as segmented items

**[ViewModel]**
    
    public class ViewModel
    {
        public ObservableCollection<View> CustomViews { get; set; }
        string fontfamily = "FontAwesome5Pro-Regular";
        public ViewModel()
        {
            CustomViews = new ObservableCollection<View>();
            Image photo = new Image();
            Image video = new Image();
            Image music = new Image();

            FontImageSource  photo.Source = new FontImageSource() { FontFamily = fontfamily, Glyph = "\uf1c5",  Size = 24, Color = Color.Black, };
            FontImageSource  video.Source = new FontImageSource() { FontFamily = fontfamily, Glyph = "\uf1c8", Size = 24, Color = Color.Black, };
            FontImageSource  music.Source = new FontImageSource() { FontFamily = fontfamily, Glyph = "\uf1c3", Size = 24, Color = Color.Black, };

            CustomViews.Add(photo);
            CustomViews.Add(video);
            CustomViews.Add(music);
        }
    }

**[XAML]**
    
    <sfbutoon:SfSegmentedControl
    HeightRequest="40"
    HorizontalOptions="Center"
    VerticalOptions="Center"
    x:Name="segmentedControl"
    VisibleSegmentsCount="3"
    Color="Transparent"
    CornerRadius="10"
    SelectedIndex="1”
    ItemsSource="{Binding CustomViews}">    
    </sfbutoon:SfSegmentedControl>

 

## How to run this application?

To run this application, you need to first clone the How-to-create-a-SegmentedControl-with-your-custom-view repository and then open it in Visual Studio 2022. Now, simply build and run your project to view the output.

## <a name="troubleshooting"></a>Troubleshooting ##
### Path too long exception
If you are facing path too long exception when building this example project, close Visual Studio and rename the repository to short and build the project.

## License

Syncfusion has no liability for any damage or consequence that may arise by using or viewing the samples. The samples are for demonstrative purposes, and if you choose to use or access the samples, you agree to not hold Syncfusion liable, in any form, for any damage that is related to use, for accessing, or viewing the samples. By accessing, viewing, or seeing the samples, you acknowledge and agree Syncfusion’s samples will not allow you seek injunctive relief in any form for any claim related to the sample. If you do not agree to this, do not view, access, utilize, or otherwise do anything with Syncfusion’s samples.
