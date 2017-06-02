---
title: Using Slick with Angularjs does not working properly when update ng-repeat
layout: default
comments: true
---

I was using slick to create a carousel in angular module, it's okay if the variable in ng-repeat will not updated. However problems hapends when I push or splice the array.   
Angularjs: 1.4.8
Slick: 1.6.0
<!--more-->

Html is like this, $scope.array is a list of dictionary.

```
<div class="carousel">
   <img ng-src="{{ i.url }}" ng-repeat="i in array" ng-click="submit($index)"/>
</div>
<script type="text/javascript">
    $(document).ready(function(){
      $('.carousel').slick({
        setting-name: setting-value
      });
    });
</script>
```

When pushing new element into array, the layout of carousel is totally changed. If you inspect, you will find initially slick move everything inside the parent div to another div like the following,

```
<div class="carousel">
  <div aria-live="polite" class="slick-list draggable">
    <div class="slick-track" role="listbox" style="opacity: 1; width: 15000px; transform: translate3d(-10px, 0px, 0px);">
      <img/>
      <img/>
      <img/>
    </div>
  </div>
</div>
```

But after you update the variable in ng-repeat, div.slick-list now is empty, images goes right under carousel that's why the layout is not the way you expected.  
I was try to use the ones which wrap slick as a angular directive, but problem was not sloved, they didn't fix this.  
So I just use the lazy way which is unslick and initial slick again, or you can use 'slickAdd' which is already provided, and $compile to compile the html.   

A huge problem encounters when I try to splice the array. If I splice the element in the front, the click event of elements after this is not working!  
I couldn't find the reason, the array is spliced correctly, index is right, but somehow the click function was not been triggered.

```
var obj = angular.copy($scope.array);
obj.splice(index, 1);
$scope.array = angular.copy(obj);
```

After copy the array to a temp variable and then copy back, everything is working fine. = =  
Too tired to find out the reason, if you know why, please let me know.
