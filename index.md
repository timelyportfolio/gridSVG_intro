It seems computer history is [full of examples](http://worrydream.com/#!/TheFutureOfProgramming) of forgotten concepts from programmers ahead of their time.

### Before [d3 (2011)](https://github.com/mbostock/d3/releases?after=v1.20.2) and Even [Protovis (2009)](http://mbostock.github.io/protovis/)

Long before the 2011 release of [d3.js](http://d3js.org) and 2009 launch of [Protovis](http://mbostock.github.io/protovis/), the folks at [carto.net](http://www.carto.net/papers/) were doing amazing and revolutionary interactive graphics in SVG.

<iframe height = "400"  width = "900" src = "http://www.carto.net/williams/yosemite/"></iframe>





```r
#get the latest version of gridSVG
#install.packages("gridSVG", repos="http://R-Forge.R-project.org")

require(ggplot2)


set.seed(955)
# Make some noisily increasing data
dat <- data.frame(cond = rep(c("A", "B"), each=10),
                  xvar = 1:20 + rnorm(20,sd=3),
                  yvar = 1:20 + rnorm(20,sd=3))
# cond         xvar         yvar
#    A -4.252354091  3.473157275
#    A  1.702317971  0.005939612
#   ... 
#    B 17.793359218 19.718587761
#    B 19.319909163 19.647899863


g4<- ggplot(dat, aes(x=xvar, y=yvar)) +
  geom_point(shape=1) +    # Use hollow circles
  geom_smooth()
```

