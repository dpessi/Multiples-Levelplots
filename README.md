# Multiples-Levelplots
How to plot more then two levelplots.

library(spaMM)
library(lattice)
library(raster)
library(rasterVis)
data(volcano)
raster <- raster(volcano)
palette <- spaMM.colors(n = 100, redshift = 1)
a=levelplot(raster, margin=FALSE,main="Volcano", cuts=length(palette)-1,col.regions=palette, xscale.components=xscale.raster.subticks,yscale.components=yscale.raster.subticks,scales=list(x=list(rot=90, cex=0.8)))
print(a,position=c(0.1,0.1,1,1),split=c(1,1,2,2),more=T)
print(a,position=c(0.1,0.1,1,1),split=c(2,2,2,2),more=T)
print(a,position=c(0.1,0.1,1,1),split=c(1,2,2,2),more=T)
print(a,position=c(0.1,0.1,1,1),split=c(2,1,2,2),more=T)
