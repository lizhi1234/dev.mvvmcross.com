---
layout: docs
categories: docs
title:  "Application Startup"
---

MvvmCross applications generally use the `IMvxAppStart` interface as a starting mechanism. A implementation of this interface which always loads the `FirstViewModel` upon application startup would look like this:

<div class="section-container tabs" data-section="tabs" data-options="deep_linking: true">
  <div class="section">
    <p class="title"><a href="#App.cs">App.cs</a></p>
    <div class="content" data-slug="App.cs">

{% highlight csharp %}
Mvx.RegisterAppStart<FirstViewModel>();
{% endhighlight %}

    </div>
  </div>
</div>

Conditional application startup beaviour can be customized by extending from `MvxNavigatingObject`:

<div class="section-container tabs" data-section="tabs" data-options="deep_linking: true">
  <div class="section">
    <p class="title"><a href="#CustomAppStart.cs">CustomAppStart.cs</a></p>
    <div class="content" data-slug="CustomAppStart.cs">

{% highlight csharp %}
public class CustomAppStart : MvxNavigatingObject, IMvxAppStart
{
    private readonly ILoginService _service;

    public CustomAppStart(ILoginService service)
    {
        _service = service;
    }

    public void Start(object hint = null)
    {
        if (!_service.IsLoggedIn)
        {
            ShowViewModel<LoginViewModel>();
        }
        else
        {
            ShowViewModel<FirstViewModel>();
        }
    }
}
{% endhighlight %}

    </div>
  </div>
</div>

`IMvxAppStart.Start(object hint)` can be used to pass paramaters into your core application from your platform operating system/platform-specific code. i.e. processing a photo which has been sent to you from a different application.