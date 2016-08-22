---
title: First Post
excerpt: "Testing the post functionality"
categories:
  - Test
tags:
  - general
  - sample
---
Testing the post functionality

#### code syntax highlight
```ruby
def show
  @widget = Widget(params[:id])
  respond_to do |format|
    format.html # show.html.erb
    format.json { render json: @widget }
  end
end
```

#### Youtube Embed
<iframe width="560" height="315" src="https://www.youtube.com/embed/mfI1S0PKJR8" frameborder="0" allowfullscreen></iframe>