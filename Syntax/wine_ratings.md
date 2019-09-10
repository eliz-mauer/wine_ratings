---
title: "Wine Ratings"
author: "Elizabeth A. Mauer"
date: "2019-09-10"
output:
 html_document:
   toc: true
   toc_depth: 4
   keep_md: true
   toc_float:
     collapsed: false
     smooth_scroll: false
params:
  glimpse: TRUE
  country:
    label: "Country"
    value: [US, France, Italy]
    input: select
    choices: [US, France, Italy, Argentina, Australia, Germany, Chile, South Africa]
    multiple: TRUE
  variety: 
    label: "Variety"
    value: ["Cabernet Sauvignon", "Chardonnay", "Merlot", "Sauvignon Blanc"]
    choices: ["Cabernet Sauvignon", "Chardonnay", "Merlot", "Sauvignon Blanc", "Malbec", "Pinot Noir"]
    multiple: TRUE
  maxprice:
    label: "Max Price"
    value: 20
    input: slider
    min: 0
    max: 2000
---




## Data Summary Statistics 


```
## Observations: 20,330
## Variables: 14
## $ X1                    <dbl> 10, 12, 14, 23, 34, 37, 43, 48, 55, 56, ...
## $ country               <chr> "US", "US", "US", "US", "US", "Italy", "...
## $ description           <chr> "Soft, supple plum envelopes an oaky str...
## $ designation           <chr> "Mountain Cuvée", NA, NA, "Signature Sel...
## $ points                <dbl> 87, 87, 87, 87, 86, 86, 86, 86, 85, 85, ...
## $ price                 <dbl> 19, 34, 12, 22, 20, 21, 14, 16, 30, 14, ...
## $ province              <chr> "California", "California", "California"...
## $ region_1              <chr> "Napa Valley", "Alexander Valley", "Cent...
## $ region_2              <chr> "Napa", "Sonoma", "Central Coast", "Cent...
## $ taster_name           <chr> "Virginie Boone", "Virginie Boone", "Mat...
## $ taster_twitter_handle <chr> "@vboone", "@vboone", "@mattkettmann", "...
## $ title                 <chr> "Kirkland Signature 2011 Mountain Cuvée ...
## $ variety               <chr> "Cabernet Sauvignon", "Cabernet Sauvigno...
## $ winery                <chr> "Kirkland Signature", "Louis M. Martini"...
```


<!--html_preserve--><div class="Rtable1"><table class="Rtable1">
<thead>
<tr>
<th class='rowlabel firstrow lastrow'></th>
<th class='firstrow lastrow'><span class='stratlabel'>Overall<br><span class='stratn'>(n=20330)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td class='rowlabel firstrow'><span class='varlabel'>country</span></td>
<td class='firstrow'></td>
</tr>
<tr>
<td class='rowlabel'>France</td>
<td>2810 (13.8%)</td>
</tr>
<tr>
<td class='rowlabel'>Italy</td>
<td>556 (2.7%)</td>
</tr>
<tr>
<td class='rowlabel lastrow'>US</td>
<td class='lastrow'>16964 (83.4%)</td>
</tr>
<tr>
<td class='rowlabel firstrow'><span class='varlabel'>points</span></td>
<td class='firstrow'></td>
</tr>
<tr>
<td class='rowlabel'>Mean (SD)</td>
<td>88.2 (3.01)</td>
</tr>
<tr>
<td class='rowlabel lastrow'>Median [Min, Max]</td>
<td class='lastrow'>88.0 [80.0, 99.0]</td>
</tr>
<tr>
<td class='rowlabel firstrow'><span class='varlabel'>price</span></td>
<td class='firstrow'></td>
</tr>
<tr>
<td class='rowlabel'>Mean (SD)</td>
<td>31.5 (16.6)</td>
</tr>
<tr>
<td class='rowlabel lastrow'>Median [Min, Max]</td>
<td class='lastrow'>28.0 [4.00, 79.0]</td>
</tr>
<tr>
<td class='rowlabel firstrow'><span class='varlabel'>variety</span></td>
<td class='firstrow'></td>
</tr>
<tr>
<td class='rowlabel'>Cabernet Sauvignon</td>
<td>5992 (29.5%)</td>
</tr>
<tr>
<td class='rowlabel'>Chardonnay</td>
<td>8860 (43.6%)</td>
</tr>
<tr>
<td class='rowlabel'>Merlot</td>
<td>2463 (12.1%)</td>
</tr>
<tr>
<td class='rowlabel lastrow'>Sauvignon Blanc</td>
<td class='lastrow'>3015 (14.8%)</td>
</tr>
</tbody>
</table>
</div><!--/html_preserve-->![](O:/Main/Research/Research_share/Liz Mauer/wine_ratings/Outputunnamed-chunk-2-1.png)<!-- -->![](O:/Main/Research/Research_share/Liz Mauer/wine_ratings/Outputunnamed-chunk-2-2.png)<!-- -->

## Bivariate Relationships with Price {.tabset .tabset-fade .tabset-pills}

### Country


```
## 
## --------Summary descriptives table by 'country'---------
## 
## ________________________________________________________________________ 
##            France           Italy              US        p.overall   N   
##            N=2810           N=556           N=16964                      
## ¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯ 
## price 28.0 [19.0;40.0] 29.0 [17.8;43.2] 28.0 [18.0;40.0]   0.618   20330 
## ¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯
```

![](O:/Main/Research/Research_share/Liz Mauer/wine_ratings/Outputunnamed-chunk-3-1.png)<!-- -->

### Variety


```
## 
## --------Summary descriptives table by 'variety'---------
## 
## ___________________________________________________________________________________________ 
##       Cabernet Sauvignon    Chardonnay         Merlot      Sauvignon Blanc  p.overall   N   
##             N=5992            N=8860           N=2463           N=3015                      
## ¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯ 
## price  36.0 [24.0;50.0]  28.0 [19.0;40.0] 25.0 [17.0;35.0] 20.0 [15.0;26.0]   0.000   20330 
## ¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯
```

![](O:/Main/Research/Research_share/Liz Mauer/wine_ratings/Outputunnamed-chunk-4-1.png)<!-- -->


### Points


```
## [1] "Linear Regression:"
```

```
## # A tibble: 2 x 5
##   term        estimate std.error statistic p.value
##   <chr>          <dbl>     <dbl>     <dbl>   <dbl>
## 1 (Intercept)  -229.      2.89       -79.3       0
## 2 points          2.95    0.0327      90.3       0
```

![](O:/Main/Research/Research_share/Liz Mauer/wine_ratings/Outputunnamed-chunk-5-1.png)<!-- -->


## Price by Points, Stratified by Variety


![](O:/Main/Research/Research_share/Liz Mauer/wine_ratings/Outputunnamed-chunk-6-1.png)<!-- -->![](O:/Main/Research/Research_share/Liz Mauer/wine_ratings/Outputunnamed-chunk-6-2.png)<!-- -->



