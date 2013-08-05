It seems computer history is [full of examples](http://worrydream.com/#!/TheFutureOfProgramming) of forgotten concepts from programmers ahead of their time.

### Before [d3 (2011)](https://github.com/mbostock/d3/releases?after=v1.20.2) and Even [Protovis (2009)](http://mbostock.github.io/protovis/)

Long before the 2011 release of [d3.js](http://d3js.org) and 2009 launch of [Protovis](http://mbostock.github.io/protovis/), the folks at [carto.net](http://www.carto.net/papers/) were doing amazing and revolutionary interactive graphics in SVG.  Consider this 2006 [Interactive Map of Yosemite](http://www.carto.net/williams/yosemite/) described in the [paper by Juliana Williams and Andreas Neumann](http://www.carto.net/neumann/papers/2006/bohinj_slovenia_2006_williams_neumann.pdf).

<iframe height = "400"  width = "900" src = "http://www.carto.net/williams/yosemite/"></iframe>

Building on this body of knowledge, some well known R contributors Deborah Nolan and Duncan Temple Lang created the R package `SVGAnnotation` described in **Journal of Statistical Software** *Vol 46 Issue 1* ([orig. ref](http://www.jstatsoft.org/v46/i01) and [html version](http://www.omegahat.org/SVGAnnotation/SVGAnnotationPaper/SVGAnnotationPaper.html#bib:SVGAnnotation).  The article demonstrates how to achieve SVG interactivity straight in 2010 still a year before [d3.js](http://d3js.org) first release.  Embedded below are two examples of [many](http://www.omegahat.org/SVGAnnotation/SVGAnnotationPaper/XMLExamples/quakes_tips.svg), each created directly from R.  You should see some animation and tooltips on hover.

<iframe height = "400"  width = "900" src = "http://www.omegahat.org/SVGAnnotation/SVGAnnotationPaper/XMLExamples/gapM.svg"></iframe>

<iframe height = "400"  width = "900" src = "http://www.omegahat.org/SVGAnnotation/SVGAnnotationPaper/XMLExamples/quakes_tips.svg"></iframe>

Now let's fast forward 3 years to 2013 where the concept of the HTML5/SVG/javascript combination for interactive graphics is [ultra popular](https://github.com/popular/starred) and [well established](http://biovisualize.github.io/d3visualization/) through [d3.js](http://d3js.org).  The novel element of d3 is its ability to bind data to elements to create dynamic documents.





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

g4 <- ggplot(dat, aes(x=xvar, y=yvar, colour = cond)) +
  geom_point(shape=1) +    # Use hollow circles
  geom_smooth()
```

