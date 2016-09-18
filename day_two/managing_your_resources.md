
### Managing Your Resources - Denys Shabalin

Apparently Denys Shabalin has grown tired of talking about his much-hyped work on 
[scala-native](https://github.com/scala-native/scala-native), unfortunately for me I was quite looking forward to 
hearing more about it.

Instead, he presented a strikingly simple solution to the ever-present issue of releasing 
resource handles when you're done with them. At about 40 lines of code, one implicit param and no dependencies
in sight it seems a bit too good to be true but no-one present managed to pick any real holes in it, though a few
tried.

**Code** - https://gist.github.com/densh/75d2d3063571d89ee34e161b4a61c74a
