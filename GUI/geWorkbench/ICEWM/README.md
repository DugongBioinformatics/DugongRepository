# DugongGUI - geWorkbench

***geWorkbench*** (genomics Workbench) is a Java-based open-source platform for integrated genomics. Using a component architecture it allows individually developed plug-ins to be configured into complex bioinformatic applications. At present there are more than 70 available plug-ins supporting the visualization and analysis of gene expression and sequence data.

![geWorkbench](http://wiki.c2b2.columbia.edu/workbench/images/thumb/d/dd/GeWorkbench_full_GUI_color_mosaic.png/760px-GeWorkbench_full_GUI_color_mosaic.png)

## Quick install

    docker pull dugong/dugong-geworkbench
    docker run -d -p 5901:5901 -p 6901:6901 -v $HOME/dugong/:/data/ \
    --name Dugong -h Dugong --privileged dugong/dugong-geworkbench
    
## Site geWorkbench

http://wiki.c2b2.columbia.edu/workbench/index.php/Home
