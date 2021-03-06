It is possible to have RGBA (rgb color and an alpha channel) backgrounds in modern browsers -- as well as Internet Explorer 7 and 8. This less mixin makes that process a little less tedious.

Setting up
---------------
Simply include ie-rgbabg.less in your LESS project via:

    @import "path/to/ie-rgbabg.less";

Or just copy the contents out of ie-rgbabg.less and paste it right into your less file(s).

Usage
---------------
ie-rgbab.less gives you two new mixins:

    .mixin--rgbabg(@r, @g, @b, @a);
    .mixin--rgbabg-string(rgba(255,255,255.1));

The arguments are self explanatory. If you would normally set a background like so:

    .selector{
      background-color: rgba(255,138,0,.5);
    }

You would now instead set your background like so:

    .selector{
      .mixin--rgbabg(255,138,0,.5);
    }

or instead, like so:

    .selector{
    	.mixin--rgbabg-string(255,138,0,.5);
    }

Output
---------------
This mixin attempts to output the proper format for IE7 and 8, as well as regular old non-stupid rgba. The output of the above mixin would be:

    .selector{
      background-color: rgba(255, 138, 0, 0.5);
      -ms-filter: progid:DXImageTransform.Microsoft.gradient(startColorstr=#7FFF8A00,endColorstr=#7FFF8A00);
      filter: progid:DXImageTransform.Microsoft.gradient(startColorstr=#7FFF8A00,endColorstr=#7FFF8A00);
      zoom: 1;
    }

Credit
---------------
The brilliant hex conversion comes from the very talented Kilian Valkof at
http://kilianvalkhof.com/2010/css-xhtml/how-to-use-rgba-in-ie/