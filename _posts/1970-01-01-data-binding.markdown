---
layout: docs
categories: docs
title:  "Data Binding"
---

Data binding uses reflection and when using Monotouch (Xamarin.iOS) or Monodroid (Xamarin.Droid) their linker can sometimes be too aggressive in removing 'Unused' symbols. If you encounter NullReference exceptions when data binding then your going to need to add [fake references](https://raw.github.com/slodge/MvvmCross-Tutorials/master/Sample%20-%20TwitterSearch/TwitterSearch.UI.Touch/LinkerIncludePlease.cs):

<div class="section-container tabs" data-section="tabs" data-options="deep_linking: true">
  <div class="section">
    <p class="title"><a href="#LinkerIncludePlease.cs">LinkerIncludePlease.cs</a></p>
    <div class="content" data-slug="LinkerIncludePlease.cs">

{% highlight csharp %}
[Preserve]
private class LinkerInclude
{
    private void IncludeStuff()
    {
        UITextField textField = null;
        textField.Text = textField.Text + "";

        UIButton button = null;
        button.TouchUpInside += delegate(object sender, EventArgs e) {          
        };
    }
}
{% endhighlight %}

    </div>
  </div>
</div>

## One Way Binding

<div class="section-container tabs" data-section="tabs" data-options="deep_linking: false">
    <div class="section">
        <p class="title"><a href="#">Android</a></p>
        <div class="content" data-slug="">

{% highlight xml %}
<TextView
    android:layout_width="fill_parent"
    android:layout_height="wrap_content"
    local:MvxBind="Text FirstName" />
{% endhighlight %}

        </div>
    </div>
    <div class="section">
        <p class="title"><a href="#">iOS</a></p>
        <div class="content" data-slug="">

{% highlight csharp %}
var label = new UILabel();
Add(label);
this.CreateBinding(label)
    .To<FirstViewModel>(vm => vm.FirstName)
    .Apply();
{% endhighlight %}

        </div>
    </div>
    <div class="section">
        <p class="title"><a href="#">Windows</a></p>
        <div class="content" data-slug="">

{% highlight xml %}
<TextBlock
    Text="{Binding FirstName}"/>
{% endhighlight %}

        </div>
    </div>
</div>



## Two Way Binding

<div class="section-container tabs" data-section="tabs" data-options="deep_linking: false">
    <div class="section">
        <p class="title"><a href="#">Android</a></p>
        <div class="content" data-slug="">

{% highlight xml %}
<TextView
    android:layout_width="fill_parent"
    android:layout_height="wrap_content"
    local:MvxBind="Text FirstName" />
{% endhighlight %}

        </div>
    </div>
    <div class="section">
        <p class="title"><a href="#">iOS</a></p>
        <div class="content" data-slug="">

{% highlight csharp %}
var label = new UILabel();
Add(label);
this.CreateBinding(label)
    .To<FirstViewModel>(vm => vm.FirstName)
    .Apply();
{% endhighlight %}

        </div>
    </div>
    <div class="section">
        <p class="title"><a href="#">Windows</a></p>
        <div class="content" data-slug="">

{% highlight xml %}
<TextBlock
    Text="{Binding FirstName}, Mode=TwoWay"/>
{% endhighlight %}

        </div>
    </div>
</div>

## Value Convertors

-- See lotsofslides.pptx - slide 19 to 24

## Collections

-- See lotsofslides.pptx - slide 25 to 32


## SubObjects

-- See lotsofslides.pptx - slide 33

