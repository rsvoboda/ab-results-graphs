# ab-resuts-graphs

Apache Bench tool can generate data (using -g option) for plotting the graphs using gnuplot. Included gnuplot script generates 2 graphs. First one is about overall distribution of request-response times (in ms). Second graph is about responses (in ms) over time (seconds, serially)

Script is based on article http://www.bradlanders.com/2013/04/15/apache-bench-and-gnuplot-youre-probably-doing-it-wrong/ It's highly recommended to read the article to understand the graphs correctly. Script expects 

Script is parameterized with defaults for all parameters, when no parameter is defined it expects file with ab tool output named out.data, generated graphs are out.jpg and out-timeseries.jpg.

## example usage
> $ ab -n 4500000 -c 150 -g resteasy.data "http://10.20.30.40:8080/jaxrs-resteasy/hello/advanced/?firstName=AA&lastName=BB" | tee resteasy.log

> $ gnuplot -e "filename='resteasy.data'" -e "outfilename='resteasy.data.jpg'" -e "toutfilename='resteasy.data-timeseries.jpg'" plot-parametrized.plg
