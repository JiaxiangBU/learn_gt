
<https://gt.rstudio.com/articles/case-study-gtcars.html>

``` r
library(tidyverse)
```

    ## ─ Attaching packages ──────────────────────────────── tidyverse 1.2.1 ─

    ## ✔ ggplot2 3.1.0     ✔ purrr   0.2.5
    ## ✔ tibble  1.4.2     ✔ dplyr   0.7.8
    ## ✔ tidyr   0.8.2     ✔ stringr 1.3.1
    ## ✔ readr   1.1.1     ✔ forcats 0.3.0

    ## ─ Conflicts ────────────────────────────────── tidyverse_conflicts() ─
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()

``` r
library(gt)
```

``` r
gtcars_8 <-
  gtcars %>%
  dplyr::group_by(ctry_origin) %>%
  dplyr::top_n(2) %>%
  dplyr::ungroup() %>%
  dplyr::filter(ctry_origin != "United Kingdom")
```

    ## Selecting by msrp

``` r
# Use `group_by()` on `gtcars` and pass that to `gt()`
gtcars_8 %>%
  dplyr::group_by(ctry_origin) %>%
  gt()
```

<!--html_preserve-->

<style>html {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Helvetica Neue', 'Fira Sans', 'Droid Sans', Arial, sans-serif;
}

#pbcqvgtyra .gt_table {
  display: table;
  border-collapse: collapse;
  margin-left: auto;
  margin-right: auto;
  color: #000000;
  font-size: 16px;
  background-color: #FFFFFF;
  /* table.background.color */
  width: auto;
  /* table.width */
  border-top-style: solid;
  /* table.border.top.style */
  border-top-width: 2px;
  /* table.border.top.width */
  border-top-color: #A8A8A8;
  /* table.border.top.color */
}

#pbcqvgtyra .gt_heading {
  background-color: #FFFFFF;
  /* heading.background.color */
  border-bottom-color: #FFFFFF;
}

#pbcqvgtyra .gt_title {
  color: #000000;
  font-size: 125%;
  /* heading.title.font.size */
  padding-top: 4px;
  /* heading.top.padding */
  padding-bottom: 1px;
  border-bottom-color: #FFFFFF;
  border-bottom-width: 0;
}

#pbcqvgtyra .gt_subtitle {
  color: #000000;
  font-size: 85%;
  /* heading.subtitle.font.size */
  padding-top: 1px;
  padding-bottom: 4px;
  /* heading.bottom.padding */
  border-top-color: #FFFFFF;
  border-top-width: 0;
}

#pbcqvgtyra .gt_bottom_border {
  border-bottom-style: solid;
  /* heading.border.bottom.style */
  border-bottom-width: 2px;
  /* heading.border.bottom.width */
  border-bottom-color: #A8A8A8;
  /* heading.border.bottom.color */
}

#pbcqvgtyra .gt_column_spanner {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #A8A8A8;
  padding-top: 4px;
  padding-bottom: 4px;
}

#pbcqvgtyra .gt_col_heading {
  color: #000000;
  background-color: #FFFFFF;
  /* column_labels.background.color */
  font-size: 16px;
  /* column_labels.font.size */
  font-weight: initial;
  /* column_labels.font.weight */
  vertical-align: middle;
  padding: 10px;
  margin: 10px;
}

#pbcqvgtyra .gt_sep_right {
  border-right: 5px solid #FFFFFF;
}

#pbcqvgtyra .gt_group_heading {
  padding: 8px;
  color: #000000;
  background-color: #FFFFFF;
  /* stub_group.background.color */
  font-size: 16px;
  /* stub_group.font.size */
  font-weight: initial;
  /* stub_group.font.weight */
  border-top-style: solid;
  /* stub_group.border.top.style */
  border-top-width: 2px;
  /* stub_group.border.top.width */
  border-top-color: #A8A8A8;
  /* stub_group.border.top.color */
  border-bottom-style: solid;
  /* stub_group.border.bottom.style */
  border-bottom-width: 2px;
  /* stub_group.border.bottom.width */
  border-bottom-color: #A8A8A8;
  /* stub_group.border.bottom.color */
  vertical-align: middle;
}

#pbcqvgtyra .gt_empty_group_heading {
  padding: 0.5px;
  color: #000000;
  background-color: #FFFFFF;
  /* stub_group.background.color */
  font-size: 16px;
  /* stub_group.font.size */
  font-weight: initial;
  /* stub_group.font.weight */
  border-top-style: solid;
  /* stub_group.border.top.style */
  border-top-width: 2px;
  /* stub_group.border.top.width */
  border-top-color: #A8A8A8;
  /* stub_group.border.top.color */
  border-bottom-style: solid;
  /* stub_group.border.bottom.style */
  border-bottom-width: 2px;
  /* stub_group.border.bottom.width */
  border-bottom-color: #A8A8A8;
  /* stub_group.border.bottom.color */
  vertical-align: middle;
}

#pbcqvgtyra .gt_striped tr:nth-child(even) {
  background-color: #f2f2f2;
}

#pbcqvgtyra .gt_row {
  padding: 10px;
  /* row.padding */
  margin: 10px;
  vertical-align: middle;
}

#pbcqvgtyra .gt_stub {
  border-right-style: solid;
  border-right-width: 2px;
  border-right-color: #A8A8A8;
  padding-left: 12px;
}

#pbcqvgtyra .gt_stub.gt_row {
  background-color: #FFFFFF;
}

#pbcqvgtyra .gt_summary_row {
  background-color: #FFFFFF;
  /* summary_row.background.color */
  padding: 6px;
  /* summary_row.padding */
  text-transform: inherit;
  /* summary_row.text_transform */
}

#pbcqvgtyra .gt_first_summary_row {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #A8A8A8;
}

#pbcqvgtyra .gt_table_body {
  border-top-style: solid;
  /* field.border.top.style */
  border-top-width: 2px;
  /* field.border.top.width */
  border-top-color: #A8A8A8;
  /* field.border.top.color */
  border-bottom-style: solid;
  /* field.border.bottom.style */
  border-bottom-width: 2px;
  /* field.border.bottom.width */
  border-bottom-color: #A8A8A8;
  /* field.border.bottom.color */
}

#pbcqvgtyra .gt_footnote {
  font-size: 90%;
  /* footnote.font.size */
  padding: 4px;
  /* footnote.padding */
}

#pbcqvgtyra .gt_sourcenote {
  font-size: 90%;
  /* sourcenote.font.size */
  padding: 4px;
  /* sourcenote.padding */
}

#pbcqvgtyra .gt_center {
  text-align: center;
}

#pbcqvgtyra .gt_left {
  text-align: left;
}

#pbcqvgtyra .gt_right {
  text-align: right;
  font-variant-numeric: tabular-nums;
}

#pbcqvgtyra .gt_font_normal {
  font-weight: normal;
}

#pbcqvgtyra .gt_font_bold {
  font-weight: bold;
}

#pbcqvgtyra .gt_font_italic {
  font-style: italic;
}

#pbcqvgtyra .gt_super {
  font-size: 65%;
}

#pbcqvgtyra .gt_footnote_glyph {
  font-style: italic;
  font-size: 65%;
}
</style>

<div id="pbcqvgtyra" style="overflow-x:auto;">

<!--gt table start-->

<table class="gt_table">

<tr>

<th class="gt_col_heading gt_left" rowspan="1" colspan="1">

mfr

</th>

<th class="gt_col_heading gt_left" rowspan="1" colspan="1">

model

</th>

<th class="gt_col_heading gt_right" rowspan="1" colspan="1">

year

</th>

<th class="gt_col_heading gt_left" rowspan="1" colspan="1">

trim

</th>

<th class="gt_col_heading gt_left" rowspan="1" colspan="1">

bdy\_style

</th>

<th class="gt_col_heading gt_right" rowspan="1" colspan="1">

hp

</th>

<th class="gt_col_heading gt_right" rowspan="1" colspan="1">

hp\_rpm

</th>

<th class="gt_col_heading gt_right" rowspan="1" colspan="1">

trq

</th>

<th class="gt_col_heading gt_right" rowspan="1" colspan="1">

trq\_rpm

</th>

<th class="gt_col_heading gt_right" rowspan="1" colspan="1">

mpg\_c

</th>

<th class="gt_col_heading gt_right" rowspan="1" colspan="1">

mpg\_h

</th>

<th class="gt_col_heading gt_left" rowspan="1" colspan="1">

drivetrain

</th>

<th class="gt_col_heading gt_left" rowspan="1" colspan="1">

trsmn

</th>

<th class="gt_col_heading gt_right" rowspan="1" colspan="1">

msrp

</th>

</tr>

<tbody class="gt_table_body gt_striped">

<tr class="gt_group_heading_row">

<td colspan="14" class="gt_group_heading">

United States

</td>

</tr>

<tr>

<td class="gt_row gt_left">

Ford

</td>

<td class="gt_row gt_left">

GT

</td>

<td class="gt_row gt_right">

2017

</td>

<td class="gt_row gt_left">

Base Coupe

</td>

<td class="gt_row gt_left">

coupe

</td>

<td class="gt_row gt_right">

647

</td>

<td class="gt_row gt_right">

6250

</td>

<td class="gt_row gt_right">

550

</td>

<td class="gt_row gt_right">

5900

</td>

<td class="gt_row gt_right">

11

</td>

<td class="gt_row gt_right">

18

</td>

<td class="gt_row gt_left">

rwd

</td>

<td class="gt_row gt_left">

7a

</td>

<td class="gt_row gt_right">

447000

</td>

</tr>

<tr>

<td class="gt_row gt_left">

Dodge

</td>

<td class="gt_row gt_left">

Viper

</td>

<td class="gt_row gt_right">

2017

</td>

<td class="gt_row gt_left">

GT Coupe

</td>

<td class="gt_row gt_left">

coupe

</td>

<td class="gt_row gt_right">

645

</td>

<td class="gt_row gt_right">

5000

</td>

<td class="gt_row gt_right">

600

</td>

<td class="gt_row gt_right">

5000

</td>

<td class="gt_row gt_right">

12

</td>

<td class="gt_row gt_right">

19

</td>

<td class="gt_row gt_left">

rwd

</td>

<td class="gt_row gt_left">

6m

</td>

<td class="gt_row gt_right">

95895

</td>

</tr>

<tr class="gt_group_heading_row">

<td colspan="14" class="gt_group_heading">

Italy

</td>

</tr>

<tr>

<td class="gt_row gt_left">

Ferrari

</td>

<td class="gt_row gt_left">

LaFerrari

</td>

<td class="gt_row gt_right">

2015

</td>

<td class="gt_row gt_left">

Base Coupe

</td>

<td class="gt_row gt_left">

coupe

</td>

<td class="gt_row gt_right">

949

</td>

<td class="gt_row gt_right">

9000

</td>

<td class="gt_row gt_right">

664

</td>

<td class="gt_row gt_right">

6750

</td>

<td class="gt_row gt_right">

12

</td>

<td class="gt_row gt_right">

16

</td>

<td class="gt_row gt_left">

rwd

</td>

<td class="gt_row gt_left">

7a

</td>

<td class="gt_row gt_right">

1416362

</td>

</tr>

<tr>

<td class="gt_row gt_left">

Lamborghini

</td>

<td class="gt_row gt_left">

Aventador

</td>

<td class="gt_row gt_right">

2015

</td>

<td class="gt_row gt_left">

LP 700-4 Coupe

</td>

<td class="gt_row gt_left">

coupe

</td>

<td class="gt_row gt_right">

700

</td>

<td class="gt_row gt_right">

8250

</td>

<td class="gt_row gt_right">

507

</td>

<td class="gt_row gt_right">

5500

</td>

<td class="gt_row gt_right">

11

</td>

<td class="gt_row gt_right">

18

</td>

<td class="gt_row gt_left">

awd

</td>

<td class="gt_row gt_left">

7a

</td>

<td class="gt_row gt_right">

397500

</td>

</tr>

<tr class="gt_group_heading_row">

<td colspan="14" class="gt_group_heading">

Japan

</td>

</tr>

<tr>

<td class="gt_row gt_left">

Acura

</td>

<td class="gt_row gt_left">

NSX

</td>

<td class="gt_row gt_right">

2017

</td>

<td class="gt_row gt_left">

Base Coupe

</td>

<td class="gt_row gt_left">

coupe

</td>

<td class="gt_row gt_right">

573

</td>

<td class="gt_row gt_right">

6500

</td>

<td class="gt_row gt_right">

476

</td>

<td class="gt_row gt_right">

2000

</td>

<td class="gt_row gt_right">

21

</td>

<td class="gt_row gt_right">

22

</td>

<td class="gt_row gt_left">

awd

</td>

<td class="gt_row gt_left">

9a

</td>

<td class="gt_row gt_right">

156000

</td>

</tr>

<tr>

<td class="gt_row gt_left">

Nissan

</td>

<td class="gt_row gt_left">

GT-R

</td>

<td class="gt_row gt_right">

2016

</td>

<td class="gt_row gt_left">

Premium Coupe

</td>

<td class="gt_row gt_left">

coupe

</td>

<td class="gt_row gt_right">

545

</td>

<td class="gt_row gt_right">

6400

</td>

<td class="gt_row gt_right">

436

</td>

<td class="gt_row gt_right">

3200

</td>

<td class="gt_row gt_right">

16

</td>

<td class="gt_row gt_right">

22

</td>

<td class="gt_row gt_left">

awd

</td>

<td class="gt_row gt_left">

6a

</td>

<td class="gt_row gt_right">

101770

</td>

</tr>

<tr class="gt_group_heading_row">

<td colspan="14" class="gt_group_heading">

Germany

</td>

</tr>

<tr>

<td class="gt_row gt_left">

BMW

</td>

<td class="gt_row gt_left">

i8

</td>

<td class="gt_row gt_right">

2016

</td>

<td class="gt_row gt_left">

Mega World Coupe

</td>

<td class="gt_row gt_left">

coupe

</td>

<td class="gt_row gt_right">

357

</td>

<td class="gt_row gt_right">

5800

</td>

<td class="gt_row gt_right">

420

</td>

<td class="gt_row gt_right">

3700

</td>

<td class="gt_row gt_right">

28

</td>

<td class="gt_row gt_right">

29

</td>

<td class="gt_row gt_left">

awd

</td>

<td class="gt_row gt_left">

6am

</td>

<td class="gt_row gt_right">

140700

</td>

</tr>

<tr>

<td class="gt_row gt_left">

Mercedes-Benz

</td>

<td class="gt_row gt_left">

AMG GT

</td>

<td class="gt_row gt_right">

2016

</td>

<td class="gt_row gt_left">

S Coupe

</td>

<td class="gt_row gt_left">

coupe

</td>

<td class="gt_row gt_right">

503

</td>

<td class="gt_row gt_right">

6250

</td>

<td class="gt_row gt_right">

479

</td>

<td class="gt_row gt_right">

1750

</td>

<td class="gt_row gt_right">

16

</td>

<td class="gt_row gt_right">

22

</td>

<td class="gt_row gt_left">

rwd

</td>

<td class="gt_row gt_left">

7a

</td>

<td class="gt_row gt_right">

129900

</td>

</tr>

</tbody>

</table>

<!--gt table end-->

</div>

<!--/html_preserve-->

``` r
# 可以查看 group by 的效果
```

``` r
order_countries <- c("Germany", "Italy", "United States", "Japan")
# Reorder the table rows by our specific ordering of groups
tab <-
  gtcars_8 %>%
  dplyr::arrange(
    factor(ctry_origin, levels = order_countries),
    mfr, desc(msrp)
    ) %>%
  dplyr::mutate(car = paste(mfr, model)) %>%
  dplyr::select(-mfr, -model) %>%
  dplyr::group_by(ctry_origin) %>%
  gt(rowname_col = "car")
  # 增加 rowname 

# Show the table
tab
```

<!--html_preserve-->

<style>html {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Helvetica Neue', 'Fira Sans', 'Droid Sans', Arial, sans-serif;
}

#mqenufdmbt .gt_table {
  display: table;
  border-collapse: collapse;
  margin-left: auto;
  margin-right: auto;
  color: #000000;
  font-size: 16px;
  background-color: #FFFFFF;
  /* table.background.color */
  width: auto;
  /* table.width */
  border-top-style: solid;
  /* table.border.top.style */
  border-top-width: 2px;
  /* table.border.top.width */
  border-top-color: #A8A8A8;
  /* table.border.top.color */
}

#mqenufdmbt .gt_heading {
  background-color: #FFFFFF;
  /* heading.background.color */
  border-bottom-color: #FFFFFF;
}

#mqenufdmbt .gt_title {
  color: #000000;
  font-size: 125%;
  /* heading.title.font.size */
  padding-top: 4px;
  /* heading.top.padding */
  padding-bottom: 1px;
  border-bottom-color: #FFFFFF;
  border-bottom-width: 0;
}

#mqenufdmbt .gt_subtitle {
  color: #000000;
  font-size: 85%;
  /* heading.subtitle.font.size */
  padding-top: 1px;
  padding-bottom: 4px;
  /* heading.bottom.padding */
  border-top-color: #FFFFFF;
  border-top-width: 0;
}

#mqenufdmbt .gt_bottom_border {
  border-bottom-style: solid;
  /* heading.border.bottom.style */
  border-bottom-width: 2px;
  /* heading.border.bottom.width */
  border-bottom-color: #A8A8A8;
  /* heading.border.bottom.color */
}

#mqenufdmbt .gt_column_spanner {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #A8A8A8;
  padding-top: 4px;
  padding-bottom: 4px;
}

#mqenufdmbt .gt_col_heading {
  color: #000000;
  background-color: #FFFFFF;
  /* column_labels.background.color */
  font-size: 16px;
  /* column_labels.font.size */
  font-weight: initial;
  /* column_labels.font.weight */
  vertical-align: middle;
  padding: 10px;
  margin: 10px;
}

#mqenufdmbt .gt_sep_right {
  border-right: 5px solid #FFFFFF;
}

#mqenufdmbt .gt_group_heading {
  padding: 8px;
  color: #000000;
  background-color: #FFFFFF;
  /* stub_group.background.color */
  font-size: 16px;
  /* stub_group.font.size */
  font-weight: initial;
  /* stub_group.font.weight */
  border-top-style: solid;
  /* stub_group.border.top.style */
  border-top-width: 2px;
  /* stub_group.border.top.width */
  border-top-color: #A8A8A8;
  /* stub_group.border.top.color */
  border-bottom-style: solid;
  /* stub_group.border.bottom.style */
  border-bottom-width: 2px;
  /* stub_group.border.bottom.width */
  border-bottom-color: #A8A8A8;
  /* stub_group.border.bottom.color */
  vertical-align: middle;
}

#mqenufdmbt .gt_empty_group_heading {
  padding: 0.5px;
  color: #000000;
  background-color: #FFFFFF;
  /* stub_group.background.color */
  font-size: 16px;
  /* stub_group.font.size */
  font-weight: initial;
  /* stub_group.font.weight */
  border-top-style: solid;
  /* stub_group.border.top.style */
  border-top-width: 2px;
  /* stub_group.border.top.width */
  border-top-color: #A8A8A8;
  /* stub_group.border.top.color */
  border-bottom-style: solid;
  /* stub_group.border.bottom.style */
  border-bottom-width: 2px;
  /* stub_group.border.bottom.width */
  border-bottom-color: #A8A8A8;
  /* stub_group.border.bottom.color */
  vertical-align: middle;
}

#mqenufdmbt .gt_striped tr:nth-child(even) {
  background-color: #f2f2f2;
}

#mqenufdmbt .gt_row {
  padding: 10px;
  /* row.padding */
  margin: 10px;
  vertical-align: middle;
}

#mqenufdmbt .gt_stub {
  border-right-style: solid;
  border-right-width: 2px;
  border-right-color: #A8A8A8;
  padding-left: 12px;
}

#mqenufdmbt .gt_stub.gt_row {
  background-color: #FFFFFF;
}

#mqenufdmbt .gt_summary_row {
  background-color: #FFFFFF;
  /* summary_row.background.color */
  padding: 6px;
  /* summary_row.padding */
  text-transform: inherit;
  /* summary_row.text_transform */
}

#mqenufdmbt .gt_first_summary_row {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #A8A8A8;
}

#mqenufdmbt .gt_table_body {
  border-top-style: solid;
  /* field.border.top.style */
  border-top-width: 2px;
  /* field.border.top.width */
  border-top-color: #A8A8A8;
  /* field.border.top.color */
  border-bottom-style: solid;
  /* field.border.bottom.style */
  border-bottom-width: 2px;
  /* field.border.bottom.width */
  border-bottom-color: #A8A8A8;
  /* field.border.bottom.color */
}

#mqenufdmbt .gt_footnote {
  font-size: 90%;
  /* footnote.font.size */
  padding: 4px;
  /* footnote.padding */
}

#mqenufdmbt .gt_sourcenote {
  font-size: 90%;
  /* sourcenote.font.size */
  padding: 4px;
  /* sourcenote.padding */
}

#mqenufdmbt .gt_center {
  text-align: center;
}

#mqenufdmbt .gt_left {
  text-align: left;
}

#mqenufdmbt .gt_right {
  text-align: right;
  font-variant-numeric: tabular-nums;
}

#mqenufdmbt .gt_font_normal {
  font-weight: normal;
}

#mqenufdmbt .gt_font_bold {
  font-weight: bold;
}

#mqenufdmbt .gt_font_italic {
  font-style: italic;
}

#mqenufdmbt .gt_super {
  font-size: 65%;
}

#mqenufdmbt .gt_footnote_glyph {
  font-style: italic;
  font-size: 65%;
}
</style>

<div id="mqenufdmbt" style="overflow-x:auto;">

<!--gt table start-->

<table class="gt_table">

<tr>

<th class="gt_col_heading gt_left" rowspan="1" colspan="1">

</th>

<th class="gt_col_heading gt_right" rowspan="1" colspan="1">

year

</th>

<th class="gt_col_heading gt_left" rowspan="1" colspan="1">

trim

</th>

<th class="gt_col_heading gt_left" rowspan="1" colspan="1">

bdy\_style

</th>

<th class="gt_col_heading gt_right" rowspan="1" colspan="1">

hp

</th>

<th class="gt_col_heading gt_right" rowspan="1" colspan="1">

hp\_rpm

</th>

<th class="gt_col_heading gt_right" rowspan="1" colspan="1">

trq

</th>

<th class="gt_col_heading gt_right" rowspan="1" colspan="1">

trq\_rpm

</th>

<th class="gt_col_heading gt_right" rowspan="1" colspan="1">

mpg\_c

</th>

<th class="gt_col_heading gt_right" rowspan="1" colspan="1">

mpg\_h

</th>

<th class="gt_col_heading gt_left" rowspan="1" colspan="1">

drivetrain

</th>

<th class="gt_col_heading gt_left" rowspan="1" colspan="1">

trsmn

</th>

<th class="gt_col_heading gt_right" rowspan="1" colspan="1">

msrp

</th>

</tr>

<tbody class="gt_table_body gt_striped">

<tr class="gt_group_heading_row">

<td colspan="13" class="gt_group_heading">

Germany

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

BMW i8

</td>

<td class="gt_row gt_right">

2016

</td>

<td class="gt_row gt_left">

Mega World Coupe

</td>

<td class="gt_row gt_left">

coupe

</td>

<td class="gt_row gt_right">

357

</td>

<td class="gt_row gt_right">

5800

</td>

<td class="gt_row gt_right">

420

</td>

<td class="gt_row gt_right">

3700

</td>

<td class="gt_row gt_right">

28

</td>

<td class="gt_row gt_right">

29

</td>

<td class="gt_row gt_left">

awd

</td>

<td class="gt_row gt_left">

6am

</td>

<td class="gt_row gt_right">

140700

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Mercedes-Benz AMG GT

</td>

<td class="gt_row gt_right">

2016

</td>

<td class="gt_row gt_left">

S Coupe

</td>

<td class="gt_row gt_left">

coupe

</td>

<td class="gt_row gt_right">

503

</td>

<td class="gt_row gt_right">

6250

</td>

<td class="gt_row gt_right">

479

</td>

<td class="gt_row gt_right">

1750

</td>

<td class="gt_row gt_right">

16

</td>

<td class="gt_row gt_right">

22

</td>

<td class="gt_row gt_left">

rwd

</td>

<td class="gt_row gt_left">

7a

</td>

<td class="gt_row gt_right">

129900

</td>

</tr>

<tr class="gt_group_heading_row">

<td colspan="13" class="gt_group_heading">

Italy

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Ferrari LaFerrari

</td>

<td class="gt_row gt_right">

2015

</td>

<td class="gt_row gt_left">

Base Coupe

</td>

<td class="gt_row gt_left">

coupe

</td>

<td class="gt_row gt_right">

949

</td>

<td class="gt_row gt_right">

9000

</td>

<td class="gt_row gt_right">

664

</td>

<td class="gt_row gt_right">

6750

</td>

<td class="gt_row gt_right">

12

</td>

<td class="gt_row gt_right">

16

</td>

<td class="gt_row gt_left">

rwd

</td>

<td class="gt_row gt_left">

7a

</td>

<td class="gt_row gt_right">

1416362

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Lamborghini Aventador

</td>

<td class="gt_row gt_right">

2015

</td>

<td class="gt_row gt_left">

LP 700-4 Coupe

</td>

<td class="gt_row gt_left">

coupe

</td>

<td class="gt_row gt_right">

700

</td>

<td class="gt_row gt_right">

8250

</td>

<td class="gt_row gt_right">

507

</td>

<td class="gt_row gt_right">

5500

</td>

<td class="gt_row gt_right">

11

</td>

<td class="gt_row gt_right">

18

</td>

<td class="gt_row gt_left">

awd

</td>

<td class="gt_row gt_left">

7a

</td>

<td class="gt_row gt_right">

397500

</td>

</tr>

<tr class="gt_group_heading_row">

<td colspan="13" class="gt_group_heading">

United States

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Dodge Viper

</td>

<td class="gt_row gt_right">

2017

</td>

<td class="gt_row gt_left">

GT Coupe

</td>

<td class="gt_row gt_left">

coupe

</td>

<td class="gt_row gt_right">

645

</td>

<td class="gt_row gt_right">

5000

</td>

<td class="gt_row gt_right">

600

</td>

<td class="gt_row gt_right">

5000

</td>

<td class="gt_row gt_right">

12

</td>

<td class="gt_row gt_right">

19

</td>

<td class="gt_row gt_left">

rwd

</td>

<td class="gt_row gt_left">

6m

</td>

<td class="gt_row gt_right">

95895

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Ford GT

</td>

<td class="gt_row gt_right">

2017

</td>

<td class="gt_row gt_left">

Base Coupe

</td>

<td class="gt_row gt_left">

coupe

</td>

<td class="gt_row gt_right">

647

</td>

<td class="gt_row gt_right">

6250

</td>

<td class="gt_row gt_right">

550

</td>

<td class="gt_row gt_right">

5900

</td>

<td class="gt_row gt_right">

11

</td>

<td class="gt_row gt_right">

18

</td>

<td class="gt_row gt_left">

rwd

</td>

<td class="gt_row gt_left">

7a

</td>

<td class="gt_row gt_right">

447000

</td>

</tr>

<tr class="gt_group_heading_row">

<td colspan="13" class="gt_group_heading">

Japan

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Acura NSX

</td>

<td class="gt_row gt_right">

2017

</td>

<td class="gt_row gt_left">

Base Coupe

</td>

<td class="gt_row gt_left">

coupe

</td>

<td class="gt_row gt_right">

573

</td>

<td class="gt_row gt_right">

6500

</td>

<td class="gt_row gt_right">

476

</td>

<td class="gt_row gt_right">

2000

</td>

<td class="gt_row gt_right">

21

</td>

<td class="gt_row gt_right">

22

</td>

<td class="gt_row gt_left">

awd

</td>

<td class="gt_row gt_left">

9a

</td>

<td class="gt_row gt_right">

156000

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Nissan GT-R

</td>

<td class="gt_row gt_right">

2016

</td>

<td class="gt_row gt_left">

Premium Coupe

</td>

<td class="gt_row gt_left">

coupe

</td>

<td class="gt_row gt_right">

545

</td>

<td class="gt_row gt_right">

6400

</td>

<td class="gt_row gt_right">

436

</td>

<td class="gt_row gt_right">

3200

</td>

<td class="gt_row gt_right">

16

</td>

<td class="gt_row gt_right">

22

</td>

<td class="gt_row gt_left">

awd

</td>

<td class="gt_row gt_left">

6a

</td>

<td class="gt_row gt_right">

101770

</td>

</tr>

</tbody>

</table>

<!--gt table end-->

</div>

<!--/html_preserve-->

move column 功能比 `select` 好用，有更多选择。

  - columns  
    the column names to move to as a group to a different position. The
    order of the remaining columns will be preserved.

`cols_move`使得 col 排在 `after` 后面。

``` r
# Use a few `cols_*()` functions to hide and move columns 
tab <- 
  tab %>%
  cols_hide(columns = vars(drivetrain, bdy_style)) %>%
  cols_move(
    columns = vars(trsmn, mpg_c, mpg_h),
    after = vars(trim)
  )

# Show the table
tab
```

<!--html_preserve-->

<style>html {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Helvetica Neue', 'Fira Sans', 'Droid Sans', Arial, sans-serif;
}

#ljirhkhddg .gt_table {
  display: table;
  border-collapse: collapse;
  margin-left: auto;
  margin-right: auto;
  color: #000000;
  font-size: 16px;
  background-color: #FFFFFF;
  /* table.background.color */
  width: auto;
  /* table.width */
  border-top-style: solid;
  /* table.border.top.style */
  border-top-width: 2px;
  /* table.border.top.width */
  border-top-color: #A8A8A8;
  /* table.border.top.color */
}

#ljirhkhddg .gt_heading {
  background-color: #FFFFFF;
  /* heading.background.color */
  border-bottom-color: #FFFFFF;
}

#ljirhkhddg .gt_title {
  color: #000000;
  font-size: 125%;
  /* heading.title.font.size */
  padding-top: 4px;
  /* heading.top.padding */
  padding-bottom: 1px;
  border-bottom-color: #FFFFFF;
  border-bottom-width: 0;
}

#ljirhkhddg .gt_subtitle {
  color: #000000;
  font-size: 85%;
  /* heading.subtitle.font.size */
  padding-top: 1px;
  padding-bottom: 4px;
  /* heading.bottom.padding */
  border-top-color: #FFFFFF;
  border-top-width: 0;
}

#ljirhkhddg .gt_bottom_border {
  border-bottom-style: solid;
  /* heading.border.bottom.style */
  border-bottom-width: 2px;
  /* heading.border.bottom.width */
  border-bottom-color: #A8A8A8;
  /* heading.border.bottom.color */
}

#ljirhkhddg .gt_column_spanner {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #A8A8A8;
  padding-top: 4px;
  padding-bottom: 4px;
}

#ljirhkhddg .gt_col_heading {
  color: #000000;
  background-color: #FFFFFF;
  /* column_labels.background.color */
  font-size: 16px;
  /* column_labels.font.size */
  font-weight: initial;
  /* column_labels.font.weight */
  vertical-align: middle;
  padding: 10px;
  margin: 10px;
}

#ljirhkhddg .gt_sep_right {
  border-right: 5px solid #FFFFFF;
}

#ljirhkhddg .gt_group_heading {
  padding: 8px;
  color: #000000;
  background-color: #FFFFFF;
  /* stub_group.background.color */
  font-size: 16px;
  /* stub_group.font.size */
  font-weight: initial;
  /* stub_group.font.weight */
  border-top-style: solid;
  /* stub_group.border.top.style */
  border-top-width: 2px;
  /* stub_group.border.top.width */
  border-top-color: #A8A8A8;
  /* stub_group.border.top.color */
  border-bottom-style: solid;
  /* stub_group.border.bottom.style */
  border-bottom-width: 2px;
  /* stub_group.border.bottom.width */
  border-bottom-color: #A8A8A8;
  /* stub_group.border.bottom.color */
  vertical-align: middle;
}

#ljirhkhddg .gt_empty_group_heading {
  padding: 0.5px;
  color: #000000;
  background-color: #FFFFFF;
  /* stub_group.background.color */
  font-size: 16px;
  /* stub_group.font.size */
  font-weight: initial;
  /* stub_group.font.weight */
  border-top-style: solid;
  /* stub_group.border.top.style */
  border-top-width: 2px;
  /* stub_group.border.top.width */
  border-top-color: #A8A8A8;
  /* stub_group.border.top.color */
  border-bottom-style: solid;
  /* stub_group.border.bottom.style */
  border-bottom-width: 2px;
  /* stub_group.border.bottom.width */
  border-bottom-color: #A8A8A8;
  /* stub_group.border.bottom.color */
  vertical-align: middle;
}

#ljirhkhddg .gt_striped tr:nth-child(even) {
  background-color: #f2f2f2;
}

#ljirhkhddg .gt_row {
  padding: 10px;
  /* row.padding */
  margin: 10px;
  vertical-align: middle;
}

#ljirhkhddg .gt_stub {
  border-right-style: solid;
  border-right-width: 2px;
  border-right-color: #A8A8A8;
  padding-left: 12px;
}

#ljirhkhddg .gt_stub.gt_row {
  background-color: #FFFFFF;
}

#ljirhkhddg .gt_summary_row {
  background-color: #FFFFFF;
  /* summary_row.background.color */
  padding: 6px;
  /* summary_row.padding */
  text-transform: inherit;
  /* summary_row.text_transform */
}

#ljirhkhddg .gt_first_summary_row {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #A8A8A8;
}

#ljirhkhddg .gt_table_body {
  border-top-style: solid;
  /* field.border.top.style */
  border-top-width: 2px;
  /* field.border.top.width */
  border-top-color: #A8A8A8;
  /* field.border.top.color */
  border-bottom-style: solid;
  /* field.border.bottom.style */
  border-bottom-width: 2px;
  /* field.border.bottom.width */
  border-bottom-color: #A8A8A8;
  /* field.border.bottom.color */
}

#ljirhkhddg .gt_footnote {
  font-size: 90%;
  /* footnote.font.size */
  padding: 4px;
  /* footnote.padding */
}

#ljirhkhddg .gt_sourcenote {
  font-size: 90%;
  /* sourcenote.font.size */
  padding: 4px;
  /* sourcenote.padding */
}

#ljirhkhddg .gt_center {
  text-align: center;
}

#ljirhkhddg .gt_left {
  text-align: left;
}

#ljirhkhddg .gt_right {
  text-align: right;
  font-variant-numeric: tabular-nums;
}

#ljirhkhddg .gt_font_normal {
  font-weight: normal;
}

#ljirhkhddg .gt_font_bold {
  font-weight: bold;
}

#ljirhkhddg .gt_font_italic {
  font-style: italic;
}

#ljirhkhddg .gt_super {
  font-size: 65%;
}

#ljirhkhddg .gt_footnote_glyph {
  font-style: italic;
  font-size: 65%;
}
</style>

<div id="ljirhkhddg" style="overflow-x:auto;">

<!--gt table start-->

<table class="gt_table">

<tr>

<th class="gt_col_heading gt_left" rowspan="1" colspan="1">

</th>

<th class="gt_col_heading gt_right" rowspan="1" colspan="1">

year

</th>

<th class="gt_col_heading gt_left" rowspan="1" colspan="1">

trim

</th>

<th class="gt_col_heading gt_left" rowspan="1" colspan="1">

trsmn

</th>

<th class="gt_col_heading gt_right" rowspan="1" colspan="1">

mpg\_c

</th>

<th class="gt_col_heading gt_right" rowspan="1" colspan="1">

mpg\_h

</th>

<th class="gt_col_heading gt_right" rowspan="1" colspan="1">

hp

</th>

<th class="gt_col_heading gt_right" rowspan="1" colspan="1">

hp\_rpm

</th>

<th class="gt_col_heading gt_right" rowspan="1" colspan="1">

trq

</th>

<th class="gt_col_heading gt_right" rowspan="1" colspan="1">

trq\_rpm

</th>

<th class="gt_col_heading gt_right" rowspan="1" colspan="1">

msrp

</th>

</tr>

<tbody class="gt_table_body gt_striped">

<tr class="gt_group_heading_row">

<td colspan="11" class="gt_group_heading">

Germany

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

BMW i8

</td>

<td class="gt_row gt_right">

2016

</td>

<td class="gt_row gt_left">

Mega World Coupe

</td>

<td class="gt_row gt_left">

6am

</td>

<td class="gt_row gt_right">

28

</td>

<td class="gt_row gt_right">

29

</td>

<td class="gt_row gt_right">

357

</td>

<td class="gt_row gt_right">

5800

</td>

<td class="gt_row gt_right">

420

</td>

<td class="gt_row gt_right">

3700

</td>

<td class="gt_row gt_right">

140700

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Mercedes-Benz AMG GT

</td>

<td class="gt_row gt_right">

2016

</td>

<td class="gt_row gt_left">

S Coupe

</td>

<td class="gt_row gt_left">

7a

</td>

<td class="gt_row gt_right">

16

</td>

<td class="gt_row gt_right">

22

</td>

<td class="gt_row gt_right">

503

</td>

<td class="gt_row gt_right">

6250

</td>

<td class="gt_row gt_right">

479

</td>

<td class="gt_row gt_right">

1750

</td>

<td class="gt_row gt_right">

129900

</td>

</tr>

<tr class="gt_group_heading_row">

<td colspan="11" class="gt_group_heading">

Italy

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Ferrari LaFerrari

</td>

<td class="gt_row gt_right">

2015

</td>

<td class="gt_row gt_left">

Base Coupe

</td>

<td class="gt_row gt_left">

7a

</td>

<td class="gt_row gt_right">

12

</td>

<td class="gt_row gt_right">

16

</td>

<td class="gt_row gt_right">

949

</td>

<td class="gt_row gt_right">

9000

</td>

<td class="gt_row gt_right">

664

</td>

<td class="gt_row gt_right">

6750

</td>

<td class="gt_row gt_right">

1416362

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Lamborghini Aventador

</td>

<td class="gt_row gt_right">

2015

</td>

<td class="gt_row gt_left">

LP 700-4 Coupe

</td>

<td class="gt_row gt_left">

7a

</td>

<td class="gt_row gt_right">

11

</td>

<td class="gt_row gt_right">

18

</td>

<td class="gt_row gt_right">

700

</td>

<td class="gt_row gt_right">

8250

</td>

<td class="gt_row gt_right">

507

</td>

<td class="gt_row gt_right">

5500

</td>

<td class="gt_row gt_right">

397500

</td>

</tr>

<tr class="gt_group_heading_row">

<td colspan="11" class="gt_group_heading">

United States

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Dodge Viper

</td>

<td class="gt_row gt_right">

2017

</td>

<td class="gt_row gt_left">

GT Coupe

</td>

<td class="gt_row gt_left">

6m

</td>

<td class="gt_row gt_right">

12

</td>

<td class="gt_row gt_right">

19

</td>

<td class="gt_row gt_right">

645

</td>

<td class="gt_row gt_right">

5000

</td>

<td class="gt_row gt_right">

600

</td>

<td class="gt_row gt_right">

5000

</td>

<td class="gt_row gt_right">

95895

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Ford GT

</td>

<td class="gt_row gt_right">

2017

</td>

<td class="gt_row gt_left">

Base Coupe

</td>

<td class="gt_row gt_left">

7a

</td>

<td class="gt_row gt_right">

11

</td>

<td class="gt_row gt_right">

18

</td>

<td class="gt_row gt_right">

647

</td>

<td class="gt_row gt_right">

6250

</td>

<td class="gt_row gt_right">

550

</td>

<td class="gt_row gt_right">

5900

</td>

<td class="gt_row gt_right">

447000

</td>

</tr>

<tr class="gt_group_heading_row">

<td colspan="11" class="gt_group_heading">

Japan

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Acura NSX

</td>

<td class="gt_row gt_right">

2017

</td>

<td class="gt_row gt_left">

Base Coupe

</td>

<td class="gt_row gt_left">

9a

</td>

<td class="gt_row gt_right">

21

</td>

<td class="gt_row gt_right">

22

</td>

<td class="gt_row gt_right">

573

</td>

<td class="gt_row gt_right">

6500

</td>

<td class="gt_row gt_right">

476

</td>

<td class="gt_row gt_right">

2000

</td>

<td class="gt_row gt_right">

156000

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Nissan GT-R

</td>

<td class="gt_row gt_right">

2016

</td>

<td class="gt_row gt_left">

Premium Coupe

</td>

<td class="gt_row gt_left">

6a

</td>

<td class="gt_row gt_right">

16

</td>

<td class="gt_row gt_right">

22

</td>

<td class="gt_row gt_right">

545

</td>

<td class="gt_row gt_right">

6400

</td>

<td class="gt_row gt_right">

436

</td>

<td class="gt_row gt_right">

3200

</td>

<td class="gt_row gt_right">

101770

</td>

</tr>

</tbody>

</table>

<!--gt table end-->

</div>

<!--/html_preserve-->

Putting Columns Into Groups

并且支持 markdown

``` r
# Put the first three columns under a spanner
# column with the label 'Performance'
tab <- 
  tab %>%
  tab_spanner(
    label = md("*Performance*"),
    columns = vars(mpg_c, mpg_h, hp, hp_rpm, trq, trq_rpm)
  )

# Show the table
tab
```

<!--html_preserve-->

<style>html {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Helvetica Neue', 'Fira Sans', 'Droid Sans', Arial, sans-serif;
}

#dehfrrzhcf .gt_table {
  display: table;
  border-collapse: collapse;
  margin-left: auto;
  margin-right: auto;
  color: #000000;
  font-size: 16px;
  background-color: #FFFFFF;
  /* table.background.color */
  width: auto;
  /* table.width */
  border-top-style: solid;
  /* table.border.top.style */
  border-top-width: 2px;
  /* table.border.top.width */
  border-top-color: #A8A8A8;
  /* table.border.top.color */
}

#dehfrrzhcf .gt_heading {
  background-color: #FFFFFF;
  /* heading.background.color */
  border-bottom-color: #FFFFFF;
}

#dehfrrzhcf .gt_title {
  color: #000000;
  font-size: 125%;
  /* heading.title.font.size */
  padding-top: 4px;
  /* heading.top.padding */
  padding-bottom: 1px;
  border-bottom-color: #FFFFFF;
  border-bottom-width: 0;
}

#dehfrrzhcf .gt_subtitle {
  color: #000000;
  font-size: 85%;
  /* heading.subtitle.font.size */
  padding-top: 1px;
  padding-bottom: 4px;
  /* heading.bottom.padding */
  border-top-color: #FFFFFF;
  border-top-width: 0;
}

#dehfrrzhcf .gt_bottom_border {
  border-bottom-style: solid;
  /* heading.border.bottom.style */
  border-bottom-width: 2px;
  /* heading.border.bottom.width */
  border-bottom-color: #A8A8A8;
  /* heading.border.bottom.color */
}

#dehfrrzhcf .gt_column_spanner {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #A8A8A8;
  padding-top: 4px;
  padding-bottom: 4px;
}

#dehfrrzhcf .gt_col_heading {
  color: #000000;
  background-color: #FFFFFF;
  /* column_labels.background.color */
  font-size: 16px;
  /* column_labels.font.size */
  font-weight: initial;
  /* column_labels.font.weight */
  vertical-align: middle;
  padding: 10px;
  margin: 10px;
}

#dehfrrzhcf .gt_sep_right {
  border-right: 5px solid #FFFFFF;
}

#dehfrrzhcf .gt_group_heading {
  padding: 8px;
  color: #000000;
  background-color: #FFFFFF;
  /* stub_group.background.color */
  font-size: 16px;
  /* stub_group.font.size */
  font-weight: initial;
  /* stub_group.font.weight */
  border-top-style: solid;
  /* stub_group.border.top.style */
  border-top-width: 2px;
  /* stub_group.border.top.width */
  border-top-color: #A8A8A8;
  /* stub_group.border.top.color */
  border-bottom-style: solid;
  /* stub_group.border.bottom.style */
  border-bottom-width: 2px;
  /* stub_group.border.bottom.width */
  border-bottom-color: #A8A8A8;
  /* stub_group.border.bottom.color */
  vertical-align: middle;
}

#dehfrrzhcf .gt_empty_group_heading {
  padding: 0.5px;
  color: #000000;
  background-color: #FFFFFF;
  /* stub_group.background.color */
  font-size: 16px;
  /* stub_group.font.size */
  font-weight: initial;
  /* stub_group.font.weight */
  border-top-style: solid;
  /* stub_group.border.top.style */
  border-top-width: 2px;
  /* stub_group.border.top.width */
  border-top-color: #A8A8A8;
  /* stub_group.border.top.color */
  border-bottom-style: solid;
  /* stub_group.border.bottom.style */
  border-bottom-width: 2px;
  /* stub_group.border.bottom.width */
  border-bottom-color: #A8A8A8;
  /* stub_group.border.bottom.color */
  vertical-align: middle;
}

#dehfrrzhcf .gt_striped tr:nth-child(even) {
  background-color: #f2f2f2;
}

#dehfrrzhcf .gt_row {
  padding: 10px;
  /* row.padding */
  margin: 10px;
  vertical-align: middle;
}

#dehfrrzhcf .gt_stub {
  border-right-style: solid;
  border-right-width: 2px;
  border-right-color: #A8A8A8;
  padding-left: 12px;
}

#dehfrrzhcf .gt_stub.gt_row {
  background-color: #FFFFFF;
}

#dehfrrzhcf .gt_summary_row {
  background-color: #FFFFFF;
  /* summary_row.background.color */
  padding: 6px;
  /* summary_row.padding */
  text-transform: inherit;
  /* summary_row.text_transform */
}

#dehfrrzhcf .gt_first_summary_row {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #A8A8A8;
}

#dehfrrzhcf .gt_table_body {
  border-top-style: solid;
  /* field.border.top.style */
  border-top-width: 2px;
  /* field.border.top.width */
  border-top-color: #A8A8A8;
  /* field.border.top.color */
  border-bottom-style: solid;
  /* field.border.bottom.style */
  border-bottom-width: 2px;
  /* field.border.bottom.width */
  border-bottom-color: #A8A8A8;
  /* field.border.bottom.color */
}

#dehfrrzhcf .gt_footnote {
  font-size: 90%;
  /* footnote.font.size */
  padding: 4px;
  /* footnote.padding */
}

#dehfrrzhcf .gt_sourcenote {
  font-size: 90%;
  /* sourcenote.font.size */
  padding: 4px;
  /* sourcenote.padding */
}

#dehfrrzhcf .gt_center {
  text-align: center;
}

#dehfrrzhcf .gt_left {
  text-align: left;
}

#dehfrrzhcf .gt_right {
  text-align: right;
  font-variant-numeric: tabular-nums;
}

#dehfrrzhcf .gt_font_normal {
  font-weight: normal;
}

#dehfrrzhcf .gt_font_bold {
  font-weight: bold;
}

#dehfrrzhcf .gt_font_italic {
  font-style: italic;
}

#dehfrrzhcf .gt_super {
  font-size: 65%;
}

#dehfrrzhcf .gt_footnote_glyph {
  font-style: italic;
  font-size: 65%;
}
</style>

<div id="dehfrrzhcf" style="overflow-x:auto;">

<!--gt table start-->

<table class="gt_table">

<tr>

<th class="gt_col_heading gt_left" rowspan="2" colspan="1">

</th>

<th class="gt_col_heading gt_center" rowspan="2" colspan="1">

year

</th>

<th class="gt_col_heading gt_center" rowspan="2" colspan="1">

trim

</th>

<th class="gt_col_heading gt_center" rowspan="2" colspan="1">

trsmn

</th>

<th class="gt_col_heading gt_column_spanner gt_center" rowspan="1" colspan="6">

<em>Performance</em>

</th>

<th class="gt_col_heading gt_center" rowspan="2" colspan="1">

msrp

</th>

</tr>

<tr>

<th class="gt_col_heading gt_right" rowspan="1" colspan="1">

mpg\_c

</th>

<th class="gt_col_heading gt_right" rowspan="1" colspan="1">

mpg\_h

</th>

<th class="gt_col_heading gt_right" rowspan="1" colspan="1">

hp

</th>

<th class="gt_col_heading gt_right" rowspan="1" colspan="1">

hp\_rpm

</th>

<th class="gt_col_heading gt_right" rowspan="1" colspan="1">

trq

</th>

<th class="gt_col_heading gt_right" rowspan="1" colspan="1">

trq\_rpm

</th>

</tr>

<tbody class="gt_table_body gt_striped">

<tr class="gt_group_heading_row">

<td colspan="11" class="gt_group_heading">

Germany

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

BMW i8

</td>

<td class="gt_row gt_right">

2016

</td>

<td class="gt_row gt_left">

Mega World Coupe

</td>

<td class="gt_row gt_left">

6am

</td>

<td class="gt_row gt_right">

28

</td>

<td class="gt_row gt_right">

29

</td>

<td class="gt_row gt_right">

357

</td>

<td class="gt_row gt_right">

5800

</td>

<td class="gt_row gt_right">

420

</td>

<td class="gt_row gt_right">

3700

</td>

<td class="gt_row gt_right">

140700

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Mercedes-Benz AMG GT

</td>

<td class="gt_row gt_right">

2016

</td>

<td class="gt_row gt_left">

S Coupe

</td>

<td class="gt_row gt_left">

7a

</td>

<td class="gt_row gt_right">

16

</td>

<td class="gt_row gt_right">

22

</td>

<td class="gt_row gt_right">

503

</td>

<td class="gt_row gt_right">

6250

</td>

<td class="gt_row gt_right">

479

</td>

<td class="gt_row gt_right">

1750

</td>

<td class="gt_row gt_right">

129900

</td>

</tr>

<tr class="gt_group_heading_row">

<td colspan="11" class="gt_group_heading">

Italy

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Ferrari LaFerrari

</td>

<td class="gt_row gt_right">

2015

</td>

<td class="gt_row gt_left">

Base Coupe

</td>

<td class="gt_row gt_left">

7a

</td>

<td class="gt_row gt_right">

12

</td>

<td class="gt_row gt_right">

16

</td>

<td class="gt_row gt_right">

949

</td>

<td class="gt_row gt_right">

9000

</td>

<td class="gt_row gt_right">

664

</td>

<td class="gt_row gt_right">

6750

</td>

<td class="gt_row gt_right">

1416362

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Lamborghini Aventador

</td>

<td class="gt_row gt_right">

2015

</td>

<td class="gt_row gt_left">

LP 700-4 Coupe

</td>

<td class="gt_row gt_left">

7a

</td>

<td class="gt_row gt_right">

11

</td>

<td class="gt_row gt_right">

18

</td>

<td class="gt_row gt_right">

700

</td>

<td class="gt_row gt_right">

8250

</td>

<td class="gt_row gt_right">

507

</td>

<td class="gt_row gt_right">

5500

</td>

<td class="gt_row gt_right">

397500

</td>

</tr>

<tr class="gt_group_heading_row">

<td colspan="11" class="gt_group_heading">

United States

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Dodge Viper

</td>

<td class="gt_row gt_right">

2017

</td>

<td class="gt_row gt_left">

GT Coupe

</td>

<td class="gt_row gt_left">

6m

</td>

<td class="gt_row gt_right">

12

</td>

<td class="gt_row gt_right">

19

</td>

<td class="gt_row gt_right">

645

</td>

<td class="gt_row gt_right">

5000

</td>

<td class="gt_row gt_right">

600

</td>

<td class="gt_row gt_right">

5000

</td>

<td class="gt_row gt_right">

95895

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Ford GT

</td>

<td class="gt_row gt_right">

2017

</td>

<td class="gt_row gt_left">

Base Coupe

</td>

<td class="gt_row gt_left">

7a

</td>

<td class="gt_row gt_right">

11

</td>

<td class="gt_row gt_right">

18

</td>

<td class="gt_row gt_right">

647

</td>

<td class="gt_row gt_right">

6250

</td>

<td class="gt_row gt_right">

550

</td>

<td class="gt_row gt_right">

5900

</td>

<td class="gt_row gt_right">

447000

</td>

</tr>

<tr class="gt_group_heading_row">

<td colspan="11" class="gt_group_heading">

Japan

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Acura NSX

</td>

<td class="gt_row gt_right">

2017

</td>

<td class="gt_row gt_left">

Base Coupe

</td>

<td class="gt_row gt_left">

9a

</td>

<td class="gt_row gt_right">

21

</td>

<td class="gt_row gt_right">

22

</td>

<td class="gt_row gt_right">

573

</td>

<td class="gt_row gt_right">

6500

</td>

<td class="gt_row gt_right">

476

</td>

<td class="gt_row gt_right">

2000

</td>

<td class="gt_row gt_right">

156000

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Nissan GT-R

</td>

<td class="gt_row gt_right">

2016

</td>

<td class="gt_row gt_left">

Premium Coupe

</td>

<td class="gt_row gt_left">

6a

</td>

<td class="gt_row gt_right">

16

</td>

<td class="gt_row gt_right">

22

</td>

<td class="gt_row gt_right">

545

</td>

<td class="gt_row gt_right">

6400

</td>

<td class="gt_row gt_right">

436

</td>

<td class="gt_row gt_right">

3200

</td>

<td class="gt_row gt_right">

101770

</td>

</tr>

</tbody>

</table>

<!--gt table end-->

</div>

<!--/html_preserve-->

Merge col

``` r
# Perform three column merges to better present
# MPG, HP, and torque; relabel all the remaining
# columns for a nicer-looking presentation
tab <- 
  tab %>%
  cols_merge(
    col_1 = vars(mpg_c),
    col_2 = vars(mpg_h),
    pattern = "{1}c<br>{2}h"
    ) %>%
  cols_merge(
    col_1 = vars(hp),
    col_2 = vars(hp_rpm),
    pattern = "{1}<br>@{2}rpm"
  ) %>%
  cols_merge(
    col_1 = vars(trq),
    col_2 = vars(trq_rpm),
    pattern = "{1}<br>@{2}rpm"
  ) %>%
  cols_label(
    mpg_c = "MPG",
    hp = "HP",
    trq = "Torque",
    year = "Year",
    trim = "Trim",
    trsmn = "Transmission",
    msrp = "MSRP"
  )

# Show the table
tab
```

<!--html_preserve-->

<style>html {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Helvetica Neue', 'Fira Sans', 'Droid Sans', Arial, sans-serif;
}

#tyxciekwae .gt_table {
  display: table;
  border-collapse: collapse;
  margin-left: auto;
  margin-right: auto;
  color: #000000;
  font-size: 16px;
  background-color: #FFFFFF;
  /* table.background.color */
  width: auto;
  /* table.width */
  border-top-style: solid;
  /* table.border.top.style */
  border-top-width: 2px;
  /* table.border.top.width */
  border-top-color: #A8A8A8;
  /* table.border.top.color */
}

#tyxciekwae .gt_heading {
  background-color: #FFFFFF;
  /* heading.background.color */
  border-bottom-color: #FFFFFF;
}

#tyxciekwae .gt_title {
  color: #000000;
  font-size: 125%;
  /* heading.title.font.size */
  padding-top: 4px;
  /* heading.top.padding */
  padding-bottom: 1px;
  border-bottom-color: #FFFFFF;
  border-bottom-width: 0;
}

#tyxciekwae .gt_subtitle {
  color: #000000;
  font-size: 85%;
  /* heading.subtitle.font.size */
  padding-top: 1px;
  padding-bottom: 4px;
  /* heading.bottom.padding */
  border-top-color: #FFFFFF;
  border-top-width: 0;
}

#tyxciekwae .gt_bottom_border {
  border-bottom-style: solid;
  /* heading.border.bottom.style */
  border-bottom-width: 2px;
  /* heading.border.bottom.width */
  border-bottom-color: #A8A8A8;
  /* heading.border.bottom.color */
}

#tyxciekwae .gt_column_spanner {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #A8A8A8;
  padding-top: 4px;
  padding-bottom: 4px;
}

#tyxciekwae .gt_col_heading {
  color: #000000;
  background-color: #FFFFFF;
  /* column_labels.background.color */
  font-size: 16px;
  /* column_labels.font.size */
  font-weight: initial;
  /* column_labels.font.weight */
  vertical-align: middle;
  padding: 10px;
  margin: 10px;
}

#tyxciekwae .gt_sep_right {
  border-right: 5px solid #FFFFFF;
}

#tyxciekwae .gt_group_heading {
  padding: 8px;
  color: #000000;
  background-color: #FFFFFF;
  /* stub_group.background.color */
  font-size: 16px;
  /* stub_group.font.size */
  font-weight: initial;
  /* stub_group.font.weight */
  border-top-style: solid;
  /* stub_group.border.top.style */
  border-top-width: 2px;
  /* stub_group.border.top.width */
  border-top-color: #A8A8A8;
  /* stub_group.border.top.color */
  border-bottom-style: solid;
  /* stub_group.border.bottom.style */
  border-bottom-width: 2px;
  /* stub_group.border.bottom.width */
  border-bottom-color: #A8A8A8;
  /* stub_group.border.bottom.color */
  vertical-align: middle;
}

#tyxciekwae .gt_empty_group_heading {
  padding: 0.5px;
  color: #000000;
  background-color: #FFFFFF;
  /* stub_group.background.color */
  font-size: 16px;
  /* stub_group.font.size */
  font-weight: initial;
  /* stub_group.font.weight */
  border-top-style: solid;
  /* stub_group.border.top.style */
  border-top-width: 2px;
  /* stub_group.border.top.width */
  border-top-color: #A8A8A8;
  /* stub_group.border.top.color */
  border-bottom-style: solid;
  /* stub_group.border.bottom.style */
  border-bottom-width: 2px;
  /* stub_group.border.bottom.width */
  border-bottom-color: #A8A8A8;
  /* stub_group.border.bottom.color */
  vertical-align: middle;
}

#tyxciekwae .gt_striped tr:nth-child(even) {
  background-color: #f2f2f2;
}

#tyxciekwae .gt_row {
  padding: 10px;
  /* row.padding */
  margin: 10px;
  vertical-align: middle;
}

#tyxciekwae .gt_stub {
  border-right-style: solid;
  border-right-width: 2px;
  border-right-color: #A8A8A8;
  padding-left: 12px;
}

#tyxciekwae .gt_stub.gt_row {
  background-color: #FFFFFF;
}

#tyxciekwae .gt_summary_row {
  background-color: #FFFFFF;
  /* summary_row.background.color */
  padding: 6px;
  /* summary_row.padding */
  text-transform: inherit;
  /* summary_row.text_transform */
}

#tyxciekwae .gt_first_summary_row {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #A8A8A8;
}

#tyxciekwae .gt_table_body {
  border-top-style: solid;
  /* field.border.top.style */
  border-top-width: 2px;
  /* field.border.top.width */
  border-top-color: #A8A8A8;
  /* field.border.top.color */
  border-bottom-style: solid;
  /* field.border.bottom.style */
  border-bottom-width: 2px;
  /* field.border.bottom.width */
  border-bottom-color: #A8A8A8;
  /* field.border.bottom.color */
}

#tyxciekwae .gt_footnote {
  font-size: 90%;
  /* footnote.font.size */
  padding: 4px;
  /* footnote.padding */
}

#tyxciekwae .gt_sourcenote {
  font-size: 90%;
  /* sourcenote.font.size */
  padding: 4px;
  /* sourcenote.padding */
}

#tyxciekwae .gt_center {
  text-align: center;
}

#tyxciekwae .gt_left {
  text-align: left;
}

#tyxciekwae .gt_right {
  text-align: right;
  font-variant-numeric: tabular-nums;
}

#tyxciekwae .gt_font_normal {
  font-weight: normal;
}

#tyxciekwae .gt_font_bold {
  font-weight: bold;
}

#tyxciekwae .gt_font_italic {
  font-style: italic;
}

#tyxciekwae .gt_super {
  font-size: 65%;
}

#tyxciekwae .gt_footnote_glyph {
  font-style: italic;
  font-size: 65%;
}
</style>

<div id="tyxciekwae" style="overflow-x:auto;">

<!--gt table start-->

<table class="gt_table">

<tr>

<th class="gt_col_heading gt_left" rowspan="2" colspan="1">

</th>

<th class="gt_col_heading gt_center" rowspan="2" colspan="1">

Year

</th>

<th class="gt_col_heading gt_center" rowspan="2" colspan="1">

Trim

</th>

<th class="gt_col_heading gt_center" rowspan="2" colspan="1">

Transmission

</th>

<th class="gt_col_heading gt_column_spanner gt_center" rowspan="1" colspan="3">

<em>Performance</em>

</th>

<th class="gt_col_heading gt_center" rowspan="2" colspan="1">

MSRP

</th>

</tr>

<tr>

<th class="gt_col_heading gt_right" rowspan="1" colspan="1">

MPG

</th>

<th class="gt_col_heading gt_right" rowspan="1" colspan="1">

HP

</th>

<th class="gt_col_heading gt_right" rowspan="1" colspan="1">

Torque

</th>

</tr>

<tbody class="gt_table_body gt_striped">

<tr class="gt_group_heading_row">

<td colspan="8" class="gt_group_heading">

Germany

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

BMW i8

</td>

<td class="gt_row gt_right">

2016

</td>

<td class="gt_row gt_left">

Mega World Coupe

</td>

<td class="gt_row gt_left">

6am

</td>

<td class="gt_row gt_right">

28c<br>29h

</td>

<td class="gt_row gt_right">

357<br>@5800rpm

</td>

<td class="gt_row gt_right">

420<br>@3700rpm

</td>

<td class="gt_row gt_right">

140700

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Mercedes-Benz AMG GT

</td>

<td class="gt_row gt_right">

2016

</td>

<td class="gt_row gt_left">

S Coupe

</td>

<td class="gt_row gt_left">

7a

</td>

<td class="gt_row gt_right">

16c<br>22h

</td>

<td class="gt_row gt_right">

503<br>@6250rpm

</td>

<td class="gt_row gt_right">

479<br>@1750rpm

</td>

<td class="gt_row gt_right">

129900

</td>

</tr>

<tr class="gt_group_heading_row">

<td colspan="8" class="gt_group_heading">

Italy

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Ferrari LaFerrari

</td>

<td class="gt_row gt_right">

2015

</td>

<td class="gt_row gt_left">

Base Coupe

</td>

<td class="gt_row gt_left">

7a

</td>

<td class="gt_row gt_right">

12c<br>16h

</td>

<td class="gt_row gt_right">

949<br>@9000rpm

</td>

<td class="gt_row gt_right">

664<br>@6750rpm

</td>

<td class="gt_row gt_right">

1416362

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Lamborghini Aventador

</td>

<td class="gt_row gt_right">

2015

</td>

<td class="gt_row gt_left">

LP 700-4 Coupe

</td>

<td class="gt_row gt_left">

7a

</td>

<td class="gt_row gt_right">

11c<br>18h

</td>

<td class="gt_row gt_right">

700<br>@8250rpm

</td>

<td class="gt_row gt_right">

507<br>@5500rpm

</td>

<td class="gt_row gt_right">

397500

</td>

</tr>

<tr class="gt_group_heading_row">

<td colspan="8" class="gt_group_heading">

United States

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Dodge Viper

</td>

<td class="gt_row gt_right">

2017

</td>

<td class="gt_row gt_left">

GT Coupe

</td>

<td class="gt_row gt_left">

6m

</td>

<td class="gt_row gt_right">

12c<br>19h

</td>

<td class="gt_row gt_right">

645<br>@5000rpm

</td>

<td class="gt_row gt_right">

600<br>@5000rpm

</td>

<td class="gt_row gt_right">

95895

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Ford GT

</td>

<td class="gt_row gt_right">

2017

</td>

<td class="gt_row gt_left">

Base Coupe

</td>

<td class="gt_row gt_left">

7a

</td>

<td class="gt_row gt_right">

11c<br>18h

</td>

<td class="gt_row gt_right">

647<br>@6250rpm

</td>

<td class="gt_row gt_right">

550<br>@5900rpm

</td>

<td class="gt_row gt_right">

447000

</td>

</tr>

<tr class="gt_group_heading_row">

<td colspan="8" class="gt_group_heading">

Japan

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Acura NSX

</td>

<td class="gt_row gt_right">

2017

</td>

<td class="gt_row gt_left">

Base Coupe

</td>

<td class="gt_row gt_left">

9a

</td>

<td class="gt_row gt_right">

21c<br>22h

</td>

<td class="gt_row gt_right">

573<br>@6500rpm

</td>

<td class="gt_row gt_right">

476<br>@2000rpm

</td>

<td class="gt_row gt_right">

156000

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Nissan GT-R

</td>

<td class="gt_row gt_right">

2016

</td>

<td class="gt_row gt_left">

Premium Coupe

</td>

<td class="gt_row gt_left">

6a

</td>

<td class="gt_row gt_right">

16c<br>22h

</td>

<td class="gt_row gt_right">

545<br>@6400rpm

</td>

<td class="gt_row gt_right">

436<br>@3200rpm

</td>

<td class="gt_row gt_right">

101770

</td>

</tr>

</tbody>

</table>

<!--gt table end-->

</div>

<!--/html_preserve-->

  - `<br>`  
    break

单独修改字体大小和居中等等

``` r
# Center-align three columns in the gt table
# and modify the text size of a few columns
# of data
tab <- 
  tab %>%
  cols_align(
    align = "center",
    columns = vars(mpg_c, hp, trq)
  ) %>%
  tab_style(
    style = cells_styles(
      text_size = px(12)),
    locations = cells_data(
      columns = vars(trim, trsmn, mpg_c, hp, trq))
  )

# Show the table
tab
```

<!--html_preserve-->

<style>html {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Helvetica Neue', 'Fira Sans', 'Droid Sans', Arial, sans-serif;
}

#bfgflrxgxt .gt_table {
  display: table;
  border-collapse: collapse;
  margin-left: auto;
  margin-right: auto;
  color: #000000;
  font-size: 16px;
  background-color: #FFFFFF;
  /* table.background.color */
  width: auto;
  /* table.width */
  border-top-style: solid;
  /* table.border.top.style */
  border-top-width: 2px;
  /* table.border.top.width */
  border-top-color: #A8A8A8;
  /* table.border.top.color */
}

#bfgflrxgxt .gt_heading {
  background-color: #FFFFFF;
  /* heading.background.color */
  border-bottom-color: #FFFFFF;
}

#bfgflrxgxt .gt_title {
  color: #000000;
  font-size: 125%;
  /* heading.title.font.size */
  padding-top: 4px;
  /* heading.top.padding */
  padding-bottom: 1px;
  border-bottom-color: #FFFFFF;
  border-bottom-width: 0;
}

#bfgflrxgxt .gt_subtitle {
  color: #000000;
  font-size: 85%;
  /* heading.subtitle.font.size */
  padding-top: 1px;
  padding-bottom: 4px;
  /* heading.bottom.padding */
  border-top-color: #FFFFFF;
  border-top-width: 0;
}

#bfgflrxgxt .gt_bottom_border {
  border-bottom-style: solid;
  /* heading.border.bottom.style */
  border-bottom-width: 2px;
  /* heading.border.bottom.width */
  border-bottom-color: #A8A8A8;
  /* heading.border.bottom.color */
}

#bfgflrxgxt .gt_column_spanner {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #A8A8A8;
  padding-top: 4px;
  padding-bottom: 4px;
}

#bfgflrxgxt .gt_col_heading {
  color: #000000;
  background-color: #FFFFFF;
  /* column_labels.background.color */
  font-size: 16px;
  /* column_labels.font.size */
  font-weight: initial;
  /* column_labels.font.weight */
  vertical-align: middle;
  padding: 10px;
  margin: 10px;
}

#bfgflrxgxt .gt_sep_right {
  border-right: 5px solid #FFFFFF;
}

#bfgflrxgxt .gt_group_heading {
  padding: 8px;
  color: #000000;
  background-color: #FFFFFF;
  /* stub_group.background.color */
  font-size: 16px;
  /* stub_group.font.size */
  font-weight: initial;
  /* stub_group.font.weight */
  border-top-style: solid;
  /* stub_group.border.top.style */
  border-top-width: 2px;
  /* stub_group.border.top.width */
  border-top-color: #A8A8A8;
  /* stub_group.border.top.color */
  border-bottom-style: solid;
  /* stub_group.border.bottom.style */
  border-bottom-width: 2px;
  /* stub_group.border.bottom.width */
  border-bottom-color: #A8A8A8;
  /* stub_group.border.bottom.color */
  vertical-align: middle;
}

#bfgflrxgxt .gt_empty_group_heading {
  padding: 0.5px;
  color: #000000;
  background-color: #FFFFFF;
  /* stub_group.background.color */
  font-size: 16px;
  /* stub_group.font.size */
  font-weight: initial;
  /* stub_group.font.weight */
  border-top-style: solid;
  /* stub_group.border.top.style */
  border-top-width: 2px;
  /* stub_group.border.top.width */
  border-top-color: #A8A8A8;
  /* stub_group.border.top.color */
  border-bottom-style: solid;
  /* stub_group.border.bottom.style */
  border-bottom-width: 2px;
  /* stub_group.border.bottom.width */
  border-bottom-color: #A8A8A8;
  /* stub_group.border.bottom.color */
  vertical-align: middle;
}

#bfgflrxgxt .gt_striped tr:nth-child(even) {
  background-color: #f2f2f2;
}

#bfgflrxgxt .gt_row {
  padding: 10px;
  /* row.padding */
  margin: 10px;
  vertical-align: middle;
}

#bfgflrxgxt .gt_stub {
  border-right-style: solid;
  border-right-width: 2px;
  border-right-color: #A8A8A8;
  padding-left: 12px;
}

#bfgflrxgxt .gt_stub.gt_row {
  background-color: #FFFFFF;
}

#bfgflrxgxt .gt_summary_row {
  background-color: #FFFFFF;
  /* summary_row.background.color */
  padding: 6px;
  /* summary_row.padding */
  text-transform: inherit;
  /* summary_row.text_transform */
}

#bfgflrxgxt .gt_first_summary_row {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #A8A8A8;
}

#bfgflrxgxt .gt_table_body {
  border-top-style: solid;
  /* field.border.top.style */
  border-top-width: 2px;
  /* field.border.top.width */
  border-top-color: #A8A8A8;
  /* field.border.top.color */
  border-bottom-style: solid;
  /* field.border.bottom.style */
  border-bottom-width: 2px;
  /* field.border.bottom.width */
  border-bottom-color: #A8A8A8;
  /* field.border.bottom.color */
}

#bfgflrxgxt .gt_footnote {
  font-size: 90%;
  /* footnote.font.size */
  padding: 4px;
  /* footnote.padding */
}

#bfgflrxgxt .gt_sourcenote {
  font-size: 90%;
  /* sourcenote.font.size */
  padding: 4px;
  /* sourcenote.padding */
}

#bfgflrxgxt .gt_center {
  text-align: center;
}

#bfgflrxgxt .gt_left {
  text-align: left;
}

#bfgflrxgxt .gt_right {
  text-align: right;
  font-variant-numeric: tabular-nums;
}

#bfgflrxgxt .gt_font_normal {
  font-weight: normal;
}

#bfgflrxgxt .gt_font_bold {
  font-weight: bold;
}

#bfgflrxgxt .gt_font_italic {
  font-style: italic;
}

#bfgflrxgxt .gt_super {
  font-size: 65%;
}

#bfgflrxgxt .gt_footnote_glyph {
  font-style: italic;
  font-size: 65%;
}
</style>

<div id="bfgflrxgxt" style="overflow-x:auto;">

<!--gt table start-->

<table class="gt_table">

<tr>

<th class="gt_col_heading gt_left" rowspan="2" colspan="1">

</th>

<th class="gt_col_heading gt_center" rowspan="2" colspan="1">

Year

</th>

<th class="gt_col_heading gt_center" rowspan="2" colspan="1">

Trim

</th>

<th class="gt_col_heading gt_center" rowspan="2" colspan="1">

Transmission

</th>

<th class="gt_col_heading gt_column_spanner gt_center" rowspan="1" colspan="3">

<em>Performance</em>

</th>

<th class="gt_col_heading gt_center" rowspan="2" colspan="1">

MSRP

</th>

</tr>

<tr>

<th class="gt_col_heading gt_center" rowspan="1" colspan="1">

MPG

</th>

<th class="gt_col_heading gt_center" rowspan="1" colspan="1">

HP

</th>

<th class="gt_col_heading gt_center" rowspan="1" colspan="1">

Torque

</th>

</tr>

<tbody class="gt_table_body gt_striped">

<tr class="gt_group_heading_row">

<td colspan="8" class="gt_group_heading">

Germany

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

BMW i8

</td>

<td class="gt_row gt_right">

2016

</td>

<td class="gt_row gt_left" style="font-size:12px;">

Mega World Coupe

</td>

<td class="gt_row gt_left" style="font-size:12px;">

6am

</td>

<td class="gt_row gt_center" style="font-size:12px;">

28c<br>29h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

357<br>@5800rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

420<br>@3700rpm

</td>

<td class="gt_row gt_right">

140700

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Mercedes-Benz AMG GT

</td>

<td class="gt_row gt_right">

2016

</td>

<td class="gt_row gt_left" style="font-size:12px;">

S Coupe

</td>

<td class="gt_row gt_left" style="font-size:12px;">

7a

</td>

<td class="gt_row gt_center" style="font-size:12px;">

16c<br>22h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

503<br>@6250rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

479<br>@1750rpm

</td>

<td class="gt_row gt_right">

129900

</td>

</tr>

<tr class="gt_group_heading_row">

<td colspan="8" class="gt_group_heading">

Italy

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Ferrari LaFerrari

</td>

<td class="gt_row gt_right">

2015

</td>

<td class="gt_row gt_left" style="font-size:12px;">

Base Coupe

</td>

<td class="gt_row gt_left" style="font-size:12px;">

7a

</td>

<td class="gt_row gt_center" style="font-size:12px;">

12c<br>16h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

949<br>@9000rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

664<br>@6750rpm

</td>

<td class="gt_row gt_right">

1416362

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Lamborghini Aventador

</td>

<td class="gt_row gt_right">

2015

</td>

<td class="gt_row gt_left" style="font-size:12px;">

LP 700-4 Coupe

</td>

<td class="gt_row gt_left" style="font-size:12px;">

7a

</td>

<td class="gt_row gt_center" style="font-size:12px;">

11c<br>18h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

700<br>@8250rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

507<br>@5500rpm

</td>

<td class="gt_row gt_right">

397500

</td>

</tr>

<tr class="gt_group_heading_row">

<td colspan="8" class="gt_group_heading">

United States

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Dodge Viper

</td>

<td class="gt_row gt_right">

2017

</td>

<td class="gt_row gt_left" style="font-size:12px;">

GT Coupe

</td>

<td class="gt_row gt_left" style="font-size:12px;">

6m

</td>

<td class="gt_row gt_center" style="font-size:12px;">

12c<br>19h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

645<br>@5000rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

600<br>@5000rpm

</td>

<td class="gt_row gt_right">

95895

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Ford GT

</td>

<td class="gt_row gt_right">

2017

</td>

<td class="gt_row gt_left" style="font-size:12px;">

Base Coupe

</td>

<td class="gt_row gt_left" style="font-size:12px;">

7a

</td>

<td class="gt_row gt_center" style="font-size:12px;">

11c<br>18h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

647<br>@6250rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

550<br>@5900rpm

</td>

<td class="gt_row gt_right">

447000

</td>

</tr>

<tr class="gt_group_heading_row">

<td colspan="8" class="gt_group_heading">

Japan

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Acura NSX

</td>

<td class="gt_row gt_right">

2017

</td>

<td class="gt_row gt_left" style="font-size:12px;">

Base Coupe

</td>

<td class="gt_row gt_left" style="font-size:12px;">

9a

</td>

<td class="gt_row gt_center" style="font-size:12px;">

21c<br>22h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

573<br>@6500rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

476<br>@2000rpm

</td>

<td class="gt_row gt_right">

156000

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Nissan GT-R

</td>

<td class="gt_row gt_right">

2016

</td>

<td class="gt_row gt_left" style="font-size:12px;">

Premium Coupe

</td>

<td class="gt_row gt_left" style="font-size:12px;">

6a

</td>

<td class="gt_row gt_center" style="font-size:12px;">

16c<br>22h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

545<br>@6400rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

436<br>@3200rpm

</td>

<td class="gt_row gt_right">

101770

</td>

</tr>

</tbody>

</table>

<!--gt table end-->

</div>

<!--/html_preserve-->

加 title

``` r
# Add a table title and subtitle; we can use
# markdown with the `md()` helper function
tab <- 
  tab %>%
  tab_header(
    title = md("The Cars of **gtcars**"),
    subtitle = "These are some fine automobiles"
  )

# Show the table
tab
```

<!--html_preserve-->

<style>html {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Helvetica Neue', 'Fira Sans', 'Droid Sans', Arial, sans-serif;
}

#epwxrjtimx .gt_table {
  display: table;
  border-collapse: collapse;
  margin-left: auto;
  margin-right: auto;
  color: #000000;
  font-size: 16px;
  background-color: #FFFFFF;
  /* table.background.color */
  width: auto;
  /* table.width */
  border-top-style: solid;
  /* table.border.top.style */
  border-top-width: 2px;
  /* table.border.top.width */
  border-top-color: #A8A8A8;
  /* table.border.top.color */
}

#epwxrjtimx .gt_heading {
  background-color: #FFFFFF;
  /* heading.background.color */
  border-bottom-color: #FFFFFF;
}

#epwxrjtimx .gt_title {
  color: #000000;
  font-size: 125%;
  /* heading.title.font.size */
  padding-top: 4px;
  /* heading.top.padding */
  padding-bottom: 1px;
  border-bottom-color: #FFFFFF;
  border-bottom-width: 0;
}

#epwxrjtimx .gt_subtitle {
  color: #000000;
  font-size: 85%;
  /* heading.subtitle.font.size */
  padding-top: 1px;
  padding-bottom: 4px;
  /* heading.bottom.padding */
  border-top-color: #FFFFFF;
  border-top-width: 0;
}

#epwxrjtimx .gt_bottom_border {
  border-bottom-style: solid;
  /* heading.border.bottom.style */
  border-bottom-width: 2px;
  /* heading.border.bottom.width */
  border-bottom-color: #A8A8A8;
  /* heading.border.bottom.color */
}

#epwxrjtimx .gt_column_spanner {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #A8A8A8;
  padding-top: 4px;
  padding-bottom: 4px;
}

#epwxrjtimx .gt_col_heading {
  color: #000000;
  background-color: #FFFFFF;
  /* column_labels.background.color */
  font-size: 16px;
  /* column_labels.font.size */
  font-weight: initial;
  /* column_labels.font.weight */
  vertical-align: middle;
  padding: 10px;
  margin: 10px;
}

#epwxrjtimx .gt_sep_right {
  border-right: 5px solid #FFFFFF;
}

#epwxrjtimx .gt_group_heading {
  padding: 8px;
  color: #000000;
  background-color: #FFFFFF;
  /* stub_group.background.color */
  font-size: 16px;
  /* stub_group.font.size */
  font-weight: initial;
  /* stub_group.font.weight */
  border-top-style: solid;
  /* stub_group.border.top.style */
  border-top-width: 2px;
  /* stub_group.border.top.width */
  border-top-color: #A8A8A8;
  /* stub_group.border.top.color */
  border-bottom-style: solid;
  /* stub_group.border.bottom.style */
  border-bottom-width: 2px;
  /* stub_group.border.bottom.width */
  border-bottom-color: #A8A8A8;
  /* stub_group.border.bottom.color */
  vertical-align: middle;
}

#epwxrjtimx .gt_empty_group_heading {
  padding: 0.5px;
  color: #000000;
  background-color: #FFFFFF;
  /* stub_group.background.color */
  font-size: 16px;
  /* stub_group.font.size */
  font-weight: initial;
  /* stub_group.font.weight */
  border-top-style: solid;
  /* stub_group.border.top.style */
  border-top-width: 2px;
  /* stub_group.border.top.width */
  border-top-color: #A8A8A8;
  /* stub_group.border.top.color */
  border-bottom-style: solid;
  /* stub_group.border.bottom.style */
  border-bottom-width: 2px;
  /* stub_group.border.bottom.width */
  border-bottom-color: #A8A8A8;
  /* stub_group.border.bottom.color */
  vertical-align: middle;
}

#epwxrjtimx .gt_striped tr:nth-child(even) {
  background-color: #f2f2f2;
}

#epwxrjtimx .gt_row {
  padding: 10px;
  /* row.padding */
  margin: 10px;
  vertical-align: middle;
}

#epwxrjtimx .gt_stub {
  border-right-style: solid;
  border-right-width: 2px;
  border-right-color: #A8A8A8;
  padding-left: 12px;
}

#epwxrjtimx .gt_stub.gt_row {
  background-color: #FFFFFF;
}

#epwxrjtimx .gt_summary_row {
  background-color: #FFFFFF;
  /* summary_row.background.color */
  padding: 6px;
  /* summary_row.padding */
  text-transform: inherit;
  /* summary_row.text_transform */
}

#epwxrjtimx .gt_first_summary_row {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #A8A8A8;
}

#epwxrjtimx .gt_table_body {
  border-top-style: solid;
  /* field.border.top.style */
  border-top-width: 2px;
  /* field.border.top.width */
  border-top-color: #A8A8A8;
  /* field.border.top.color */
  border-bottom-style: solid;
  /* field.border.bottom.style */
  border-bottom-width: 2px;
  /* field.border.bottom.width */
  border-bottom-color: #A8A8A8;
  /* field.border.bottom.color */
}

#epwxrjtimx .gt_footnote {
  font-size: 90%;
  /* footnote.font.size */
  padding: 4px;
  /* footnote.padding */
}

#epwxrjtimx .gt_sourcenote {
  font-size: 90%;
  /* sourcenote.font.size */
  padding: 4px;
  /* sourcenote.padding */
}

#epwxrjtimx .gt_center {
  text-align: center;
}

#epwxrjtimx .gt_left {
  text-align: left;
}

#epwxrjtimx .gt_right {
  text-align: right;
  font-variant-numeric: tabular-nums;
}

#epwxrjtimx .gt_font_normal {
  font-weight: normal;
}

#epwxrjtimx .gt_font_bold {
  font-weight: bold;
}

#epwxrjtimx .gt_font_italic {
  font-style: italic;
}

#epwxrjtimx .gt_super {
  font-size: 65%;
}

#epwxrjtimx .gt_footnote_glyph {
  font-style: italic;
  font-size: 65%;
}
</style>

<div id="epwxrjtimx" style="overflow-x:auto;">

<!--gt table start-->

<table class="gt_table">

<thead>

<tr>

<th class="gt_heading gt_title gt_font_normal gt_center" colspan="8">

The Cars of
<strong>gtcars</strong>

</th>

</tr>

<tr>

<th class="gt_heading gt_subtitle gt_font_normal gt_center gt_bottom_border" colspan="8">

These are some fine
automobiles

</th>

</tr>

</thead>

<tr>

<th class="gt_col_heading gt_left" rowspan="2" colspan="1">

</th>

<th class="gt_col_heading gt_center" rowspan="2" colspan="1">

Year

</th>

<th class="gt_col_heading gt_center" rowspan="2" colspan="1">

Trim

</th>

<th class="gt_col_heading gt_center" rowspan="2" colspan="1">

Transmission

</th>

<th class="gt_col_heading gt_column_spanner gt_center" rowspan="1" colspan="3">

<em>Performance</em>

</th>

<th class="gt_col_heading gt_center" rowspan="2" colspan="1">

MSRP

</th>

</tr>

<tr>

<th class="gt_col_heading gt_center" rowspan="1" colspan="1">

MPG

</th>

<th class="gt_col_heading gt_center" rowspan="1" colspan="1">

HP

</th>

<th class="gt_col_heading gt_center" rowspan="1" colspan="1">

Torque

</th>

</tr>

<tbody class="gt_table_body gt_striped">

<tr class="gt_group_heading_row">

<td colspan="8" class="gt_group_heading">

Germany

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

BMW i8

</td>

<td class="gt_row gt_right">

2016

</td>

<td class="gt_row gt_left" style="font-size:12px;">

Mega World Coupe

</td>

<td class="gt_row gt_left" style="font-size:12px;">

6am

</td>

<td class="gt_row gt_center" style="font-size:12px;">

28c<br>29h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

357<br>@5800rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

420<br>@3700rpm

</td>

<td class="gt_row gt_right">

140700

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Mercedes-Benz AMG GT

</td>

<td class="gt_row gt_right">

2016

</td>

<td class="gt_row gt_left" style="font-size:12px;">

S Coupe

</td>

<td class="gt_row gt_left" style="font-size:12px;">

7a

</td>

<td class="gt_row gt_center" style="font-size:12px;">

16c<br>22h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

503<br>@6250rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

479<br>@1750rpm

</td>

<td class="gt_row gt_right">

129900

</td>

</tr>

<tr class="gt_group_heading_row">

<td colspan="8" class="gt_group_heading">

Italy

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Ferrari LaFerrari

</td>

<td class="gt_row gt_right">

2015

</td>

<td class="gt_row gt_left" style="font-size:12px;">

Base Coupe

</td>

<td class="gt_row gt_left" style="font-size:12px;">

7a

</td>

<td class="gt_row gt_center" style="font-size:12px;">

12c<br>16h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

949<br>@9000rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

664<br>@6750rpm

</td>

<td class="gt_row gt_right">

1416362

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Lamborghini Aventador

</td>

<td class="gt_row gt_right">

2015

</td>

<td class="gt_row gt_left" style="font-size:12px;">

LP 700-4 Coupe

</td>

<td class="gt_row gt_left" style="font-size:12px;">

7a

</td>

<td class="gt_row gt_center" style="font-size:12px;">

11c<br>18h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

700<br>@8250rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

507<br>@5500rpm

</td>

<td class="gt_row gt_right">

397500

</td>

</tr>

<tr class="gt_group_heading_row">

<td colspan="8" class="gt_group_heading">

United States

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Dodge Viper

</td>

<td class="gt_row gt_right">

2017

</td>

<td class="gt_row gt_left" style="font-size:12px;">

GT Coupe

</td>

<td class="gt_row gt_left" style="font-size:12px;">

6m

</td>

<td class="gt_row gt_center" style="font-size:12px;">

12c<br>19h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

645<br>@5000rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

600<br>@5000rpm

</td>

<td class="gt_row gt_right">

95895

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Ford GT

</td>

<td class="gt_row gt_right">

2017

</td>

<td class="gt_row gt_left" style="font-size:12px;">

Base Coupe

</td>

<td class="gt_row gt_left" style="font-size:12px;">

7a

</td>

<td class="gt_row gt_center" style="font-size:12px;">

11c<br>18h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

647<br>@6250rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

550<br>@5900rpm

</td>

<td class="gt_row gt_right">

447000

</td>

</tr>

<tr class="gt_group_heading_row">

<td colspan="8" class="gt_group_heading">

Japan

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Acura NSX

</td>

<td class="gt_row gt_right">

2017

</td>

<td class="gt_row gt_left" style="font-size:12px;">

Base Coupe

</td>

<td class="gt_row gt_left" style="font-size:12px;">

9a

</td>

<td class="gt_row gt_center" style="font-size:12px;">

21c<br>22h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

573<br>@6500rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

476<br>@2000rpm

</td>

<td class="gt_row gt_right">

156000

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Nissan GT-R

</td>

<td class="gt_row gt_right">

2016

</td>

<td class="gt_row gt_left" style="font-size:12px;">

Premium Coupe

</td>

<td class="gt_row gt_left" style="font-size:12px;">

6a

</td>

<td class="gt_row gt_center" style="font-size:12px;">

16c<br>22h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

545<br>@6400rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

436<br>@3200rpm

</td>

<td class="gt_row gt_right">

101770

</td>

</tr>

</tbody>

</table>

<!--gt table end-->

</div>

<!--/html_preserve-->

加 citation

可以加超链接

``` r
# Add a source note to the bottom of the table; this
# appears below the footnotes
tab <- 
  tab %>%
  tab_source_note(
    source_note = md(
      "Source: Various pages within [edmunds.com](https://www.edmunds.com).")
  )

# Show the table
tab
```

<!--html_preserve-->

<style>html {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Helvetica Neue', 'Fira Sans', 'Droid Sans', Arial, sans-serif;
}

#ckjzroaigs .gt_table {
  display: table;
  border-collapse: collapse;
  margin-left: auto;
  margin-right: auto;
  color: #000000;
  font-size: 16px;
  background-color: #FFFFFF;
  /* table.background.color */
  width: auto;
  /* table.width */
  border-top-style: solid;
  /* table.border.top.style */
  border-top-width: 2px;
  /* table.border.top.width */
  border-top-color: #A8A8A8;
  /* table.border.top.color */
}

#ckjzroaigs .gt_heading {
  background-color: #FFFFFF;
  /* heading.background.color */
  border-bottom-color: #FFFFFF;
}

#ckjzroaigs .gt_title {
  color: #000000;
  font-size: 125%;
  /* heading.title.font.size */
  padding-top: 4px;
  /* heading.top.padding */
  padding-bottom: 1px;
  border-bottom-color: #FFFFFF;
  border-bottom-width: 0;
}

#ckjzroaigs .gt_subtitle {
  color: #000000;
  font-size: 85%;
  /* heading.subtitle.font.size */
  padding-top: 1px;
  padding-bottom: 4px;
  /* heading.bottom.padding */
  border-top-color: #FFFFFF;
  border-top-width: 0;
}

#ckjzroaigs .gt_bottom_border {
  border-bottom-style: solid;
  /* heading.border.bottom.style */
  border-bottom-width: 2px;
  /* heading.border.bottom.width */
  border-bottom-color: #A8A8A8;
  /* heading.border.bottom.color */
}

#ckjzroaigs .gt_column_spanner {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #A8A8A8;
  padding-top: 4px;
  padding-bottom: 4px;
}

#ckjzroaigs .gt_col_heading {
  color: #000000;
  background-color: #FFFFFF;
  /* column_labels.background.color */
  font-size: 16px;
  /* column_labels.font.size */
  font-weight: initial;
  /* column_labels.font.weight */
  vertical-align: middle;
  padding: 10px;
  margin: 10px;
}

#ckjzroaigs .gt_sep_right {
  border-right: 5px solid #FFFFFF;
}

#ckjzroaigs .gt_group_heading {
  padding: 8px;
  color: #000000;
  background-color: #FFFFFF;
  /* stub_group.background.color */
  font-size: 16px;
  /* stub_group.font.size */
  font-weight: initial;
  /* stub_group.font.weight */
  border-top-style: solid;
  /* stub_group.border.top.style */
  border-top-width: 2px;
  /* stub_group.border.top.width */
  border-top-color: #A8A8A8;
  /* stub_group.border.top.color */
  border-bottom-style: solid;
  /* stub_group.border.bottom.style */
  border-bottom-width: 2px;
  /* stub_group.border.bottom.width */
  border-bottom-color: #A8A8A8;
  /* stub_group.border.bottom.color */
  vertical-align: middle;
}

#ckjzroaigs .gt_empty_group_heading {
  padding: 0.5px;
  color: #000000;
  background-color: #FFFFFF;
  /* stub_group.background.color */
  font-size: 16px;
  /* stub_group.font.size */
  font-weight: initial;
  /* stub_group.font.weight */
  border-top-style: solid;
  /* stub_group.border.top.style */
  border-top-width: 2px;
  /* stub_group.border.top.width */
  border-top-color: #A8A8A8;
  /* stub_group.border.top.color */
  border-bottom-style: solid;
  /* stub_group.border.bottom.style */
  border-bottom-width: 2px;
  /* stub_group.border.bottom.width */
  border-bottom-color: #A8A8A8;
  /* stub_group.border.bottom.color */
  vertical-align: middle;
}

#ckjzroaigs .gt_striped tr:nth-child(even) {
  background-color: #f2f2f2;
}

#ckjzroaigs .gt_row {
  padding: 10px;
  /* row.padding */
  margin: 10px;
  vertical-align: middle;
}

#ckjzroaigs .gt_stub {
  border-right-style: solid;
  border-right-width: 2px;
  border-right-color: #A8A8A8;
  padding-left: 12px;
}

#ckjzroaigs .gt_stub.gt_row {
  background-color: #FFFFFF;
}

#ckjzroaigs .gt_summary_row {
  background-color: #FFFFFF;
  /* summary_row.background.color */
  padding: 6px;
  /* summary_row.padding */
  text-transform: inherit;
  /* summary_row.text_transform */
}

#ckjzroaigs .gt_first_summary_row {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #A8A8A8;
}

#ckjzroaigs .gt_table_body {
  border-top-style: solid;
  /* field.border.top.style */
  border-top-width: 2px;
  /* field.border.top.width */
  border-top-color: #A8A8A8;
  /* field.border.top.color */
  border-bottom-style: solid;
  /* field.border.bottom.style */
  border-bottom-width: 2px;
  /* field.border.bottom.width */
  border-bottom-color: #A8A8A8;
  /* field.border.bottom.color */
}

#ckjzroaigs .gt_footnote {
  font-size: 90%;
  /* footnote.font.size */
  padding: 4px;
  /* footnote.padding */
}

#ckjzroaigs .gt_sourcenote {
  font-size: 90%;
  /* sourcenote.font.size */
  padding: 4px;
  /* sourcenote.padding */
}

#ckjzroaigs .gt_center {
  text-align: center;
}

#ckjzroaigs .gt_left {
  text-align: left;
}

#ckjzroaigs .gt_right {
  text-align: right;
  font-variant-numeric: tabular-nums;
}

#ckjzroaigs .gt_font_normal {
  font-weight: normal;
}

#ckjzroaigs .gt_font_bold {
  font-weight: bold;
}

#ckjzroaigs .gt_font_italic {
  font-style: italic;
}

#ckjzroaigs .gt_super {
  font-size: 65%;
}

#ckjzroaigs .gt_footnote_glyph {
  font-style: italic;
  font-size: 65%;
}
</style>

<div id="ckjzroaigs" style="overflow-x:auto;">

<!--gt table start-->

<table class="gt_table">

<thead>

<tr>

<th class="gt_heading gt_title gt_font_normal gt_center" colspan="8">

The Cars of
<strong>gtcars</strong>

</th>

</tr>

<tr>

<th class="gt_heading gt_subtitle gt_font_normal gt_center gt_bottom_border" colspan="8">

These are some fine
automobiles

</th>

</tr>

</thead>

<tr>

<th class="gt_col_heading gt_left" rowspan="2" colspan="1">

</th>

<th class="gt_col_heading gt_center" rowspan="2" colspan="1">

Year

</th>

<th class="gt_col_heading gt_center" rowspan="2" colspan="1">

Trim

</th>

<th class="gt_col_heading gt_center" rowspan="2" colspan="1">

Transmission

</th>

<th class="gt_col_heading gt_column_spanner gt_center" rowspan="1" colspan="3">

<em>Performance</em>

</th>

<th class="gt_col_heading gt_center" rowspan="2" colspan="1">

MSRP

</th>

</tr>

<tr>

<th class="gt_col_heading gt_center" rowspan="1" colspan="1">

MPG

</th>

<th class="gt_col_heading gt_center" rowspan="1" colspan="1">

HP

</th>

<th class="gt_col_heading gt_center" rowspan="1" colspan="1">

Torque

</th>

</tr>

<tbody class="gt_table_body gt_striped">

<tr class="gt_group_heading_row">

<td colspan="8" class="gt_group_heading">

Germany

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

BMW i8

</td>

<td class="gt_row gt_right">

2016

</td>

<td class="gt_row gt_left" style="font-size:12px;">

Mega World Coupe

</td>

<td class="gt_row gt_left" style="font-size:12px;">

6am

</td>

<td class="gt_row gt_center" style="font-size:12px;">

28c<br>29h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

357<br>@5800rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

420<br>@3700rpm

</td>

<td class="gt_row gt_right">

140700

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Mercedes-Benz AMG GT

</td>

<td class="gt_row gt_right">

2016

</td>

<td class="gt_row gt_left" style="font-size:12px;">

S Coupe

</td>

<td class="gt_row gt_left" style="font-size:12px;">

7a

</td>

<td class="gt_row gt_center" style="font-size:12px;">

16c<br>22h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

503<br>@6250rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

479<br>@1750rpm

</td>

<td class="gt_row gt_right">

129900

</td>

</tr>

<tr class="gt_group_heading_row">

<td colspan="8" class="gt_group_heading">

Italy

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Ferrari LaFerrari

</td>

<td class="gt_row gt_right">

2015

</td>

<td class="gt_row gt_left" style="font-size:12px;">

Base Coupe

</td>

<td class="gt_row gt_left" style="font-size:12px;">

7a

</td>

<td class="gt_row gt_center" style="font-size:12px;">

12c<br>16h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

949<br>@9000rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

664<br>@6750rpm

</td>

<td class="gt_row gt_right">

1416362

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Lamborghini Aventador

</td>

<td class="gt_row gt_right">

2015

</td>

<td class="gt_row gt_left" style="font-size:12px;">

LP 700-4 Coupe

</td>

<td class="gt_row gt_left" style="font-size:12px;">

7a

</td>

<td class="gt_row gt_center" style="font-size:12px;">

11c<br>18h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

700<br>@8250rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

507<br>@5500rpm

</td>

<td class="gt_row gt_right">

397500

</td>

</tr>

<tr class="gt_group_heading_row">

<td colspan="8" class="gt_group_heading">

United States

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Dodge Viper

</td>

<td class="gt_row gt_right">

2017

</td>

<td class="gt_row gt_left" style="font-size:12px;">

GT Coupe

</td>

<td class="gt_row gt_left" style="font-size:12px;">

6m

</td>

<td class="gt_row gt_center" style="font-size:12px;">

12c<br>19h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

645<br>@5000rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

600<br>@5000rpm

</td>

<td class="gt_row gt_right">

95895

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Ford GT

</td>

<td class="gt_row gt_right">

2017

</td>

<td class="gt_row gt_left" style="font-size:12px;">

Base Coupe

</td>

<td class="gt_row gt_left" style="font-size:12px;">

7a

</td>

<td class="gt_row gt_center" style="font-size:12px;">

11c<br>18h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

647<br>@6250rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

550<br>@5900rpm

</td>

<td class="gt_row gt_right">

447000

</td>

</tr>

<tr class="gt_group_heading_row">

<td colspan="8" class="gt_group_heading">

Japan

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Acura NSX

</td>

<td class="gt_row gt_right">

2017

</td>

<td class="gt_row gt_left" style="font-size:12px;">

Base Coupe

</td>

<td class="gt_row gt_left" style="font-size:12px;">

9a

</td>

<td class="gt_row gt_center" style="font-size:12px;">

21c<br>22h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

573<br>@6500rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

476<br>@2000rpm

</td>

<td class="gt_row gt_right">

156000

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Nissan GT-R

</td>

<td class="gt_row gt_right">

2016

</td>

<td class="gt_row gt_left" style="font-size:12px;">

Premium Coupe

</td>

<td class="gt_row gt_left" style="font-size:12px;">

6a

</td>

<td class="gt_row gt_center" style="font-size:12px;">

16c<br>22h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

545<br>@6400rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

436<br>@3200rpm

</td>

<td class="gt_row gt_right">

101770

</td>

</tr>

</tbody>

<tfoot>

<tr>

<td colspan="9" class="gt_sourcenote">

Source: Various pages within
<a href="https://www.edmunds.com">edmunds.com</a>.

</td>

</tr>

</tfoot>

</table>

<!--gt table end-->

</div>

<!--/html_preserve-->

footnote

``` r
# Use dplyr functions to get the car with the best city gas mileage;
# this will be used to target the correct cell for a footnote
best_gas_mileage_city <- 
  gtcars %>% 
  dplyr::arrange(desc(mpg_c)) %>%
  dplyr::slice(1) %>%
  dplyr::mutate(car = paste(mfr, model)) %>%
  dplyr::pull(car)

# Use dplyr functions to get the car with the highest horsepower
# this will be used to target the correct cell for a footnote
highest_horsepower <- 
  gtcars %>% 
  dplyr::arrange(desc(hp)) %>%
  dplyr::slice(1) %>%
  dplyr::mutate(car = paste(mfr, model)) %>%
  dplyr::pull(car)

# Create a display table with `gtcars`, using all of the previous
# statements piped together + additional `tab_footnote()` stmts
tab <-
  gtcars %>%
  dplyr::arrange(
    factor(ctry_origin, levels = order_countries),
    mfr, desc(msrp)
  ) %>%
  dplyr::mutate(car = paste(mfr, model)) %>%
  dplyr::select(-mfr, -model) %>%
  dplyr::group_by(ctry_origin) %>%
  gt(rowname_col = "car") %>%
  cols_hide(columns = vars(drivetrain, bdy_style)) %>%
  cols_move(
    columns = vars(trsmn, mpg_c, mpg_h),
    after = vars(trim)
  ) %>%
  tab_spanner(
    label = md("*Performance*"),
    columns = vars(mpg_c, mpg_h, hp, hp_rpm, trq, trq_rpm)
  ) %>%
  cols_merge(
    col_1 = vars(mpg_c),
    col_2 = vars(mpg_h),
    pattern = "{1}c<br>{2}h"
  ) %>%
  cols_merge(
    col_1 = vars(hp),
    col_2 = vars(hp_rpm),
    pattern = "{1}<br>@{2}rpm"
  ) %>%
  cols_merge(
    col_1 = vars(trq),
    col_2 = vars(trq_rpm),
    pattern = "{1}<br>@{2}rpm"
  ) %>%
  cols_label(
    mpg_c = "MPG",
    hp = "HP",
    trq = "Torque",
    year = "Year",
    trim = "Trim",
    trsmn = "Transmission",
    msrp = "MSRP"
  ) %>%
  fmt_currency(
    columns = vars(msrp),
    currency = "USD",
    decimals = 0
  ) %>%
  cols_align(
    align = "center",
    columns = vars(mpg_c, hp, trq)
  ) %>%
  tab_style(
    style = cells_styles(text_size = px(12)),
    locations = cells_data(columns = vars(trim, trsmn, mpg_c, hp, trq))
  ) %>%
  text_transform(
    locations = cells_data(columns = vars(trsmn)),
    fn = function(x) {
      
      speed <- substr(x, 1, 1)
      
      type <-
        dplyr::case_when(
          substr(x, 2, 3) == "am" ~ "Automatic/Manual",
          substr(x, 2, 2) == "m" ~ "Manual",
          substr(x, 2, 2) == "a" ~ "Automatic",
          substr(x, 2, 3) == "dd" ~ "Direct Drive"
        )
      
      paste(speed, " Speed<br><em>", type, "</em>")
    }
  ) %>%
  tab_header(
    title = md("The Cars of **gtcars**"),
    subtitle = "These are some fine automobiles"
  ) %>%
  tab_source_note(
    source_note = md(
      "Source: Various pages within [edmunds.com](https://www.edmunds.com).")
  ) %>%
  tab_footnote(
    footnote = md("Best gas mileage (city) of all the **gtcars**."),
    locations = cells_data(
      columns = vars(mpg_c),
      rows = best_gas_mileage_city)
  ) %>%
  tab_footnote(
    footnote = md("The highest horsepower of all the **gtcars**."),
    locations = cells_data(
      columns = vars(hp),
      rows = highest_horsepower)
  ) %>%
  tab_footnote(
    footnote = "All prices in U.S. dollars (USD).",
    locations = cells_column_labels(
      columns = vars(msrp))
  )

# Show the table
tab
```

<!--html_preserve-->

<style>html {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Helvetica Neue', 'Fira Sans', 'Droid Sans', Arial, sans-serif;
}

#fugdjqdwhn .gt_table {
  display: table;
  border-collapse: collapse;
  margin-left: auto;
  margin-right: auto;
  color: #000000;
  font-size: 16px;
  background-color: #FFFFFF;
  /* table.background.color */
  width: auto;
  /* table.width */
  border-top-style: solid;
  /* table.border.top.style */
  border-top-width: 2px;
  /* table.border.top.width */
  border-top-color: #A8A8A8;
  /* table.border.top.color */
}

#fugdjqdwhn .gt_heading {
  background-color: #FFFFFF;
  /* heading.background.color */
  border-bottom-color: #FFFFFF;
}

#fugdjqdwhn .gt_title {
  color: #000000;
  font-size: 125%;
  /* heading.title.font.size */
  padding-top: 4px;
  /* heading.top.padding */
  padding-bottom: 1px;
  border-bottom-color: #FFFFFF;
  border-bottom-width: 0;
}

#fugdjqdwhn .gt_subtitle {
  color: #000000;
  font-size: 85%;
  /* heading.subtitle.font.size */
  padding-top: 1px;
  padding-bottom: 4px;
  /* heading.bottom.padding */
  border-top-color: #FFFFFF;
  border-top-width: 0;
}

#fugdjqdwhn .gt_bottom_border {
  border-bottom-style: solid;
  /* heading.border.bottom.style */
  border-bottom-width: 2px;
  /* heading.border.bottom.width */
  border-bottom-color: #A8A8A8;
  /* heading.border.bottom.color */
}

#fugdjqdwhn .gt_column_spanner {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #A8A8A8;
  padding-top: 4px;
  padding-bottom: 4px;
}

#fugdjqdwhn .gt_col_heading {
  color: #000000;
  background-color: #FFFFFF;
  /* column_labels.background.color */
  font-size: 16px;
  /* column_labels.font.size */
  font-weight: initial;
  /* column_labels.font.weight */
  vertical-align: middle;
  padding: 10px;
  margin: 10px;
}

#fugdjqdwhn .gt_sep_right {
  border-right: 5px solid #FFFFFF;
}

#fugdjqdwhn .gt_group_heading {
  padding: 8px;
  color: #000000;
  background-color: #FFFFFF;
  /* stub_group.background.color */
  font-size: 16px;
  /* stub_group.font.size */
  font-weight: initial;
  /* stub_group.font.weight */
  border-top-style: solid;
  /* stub_group.border.top.style */
  border-top-width: 2px;
  /* stub_group.border.top.width */
  border-top-color: #A8A8A8;
  /* stub_group.border.top.color */
  border-bottom-style: solid;
  /* stub_group.border.bottom.style */
  border-bottom-width: 2px;
  /* stub_group.border.bottom.width */
  border-bottom-color: #A8A8A8;
  /* stub_group.border.bottom.color */
  vertical-align: middle;
}

#fugdjqdwhn .gt_empty_group_heading {
  padding: 0.5px;
  color: #000000;
  background-color: #FFFFFF;
  /* stub_group.background.color */
  font-size: 16px;
  /* stub_group.font.size */
  font-weight: initial;
  /* stub_group.font.weight */
  border-top-style: solid;
  /* stub_group.border.top.style */
  border-top-width: 2px;
  /* stub_group.border.top.width */
  border-top-color: #A8A8A8;
  /* stub_group.border.top.color */
  border-bottom-style: solid;
  /* stub_group.border.bottom.style */
  border-bottom-width: 2px;
  /* stub_group.border.bottom.width */
  border-bottom-color: #A8A8A8;
  /* stub_group.border.bottom.color */
  vertical-align: middle;
}

#fugdjqdwhn .gt_striped tr:nth-child(even) {
  background-color: #f2f2f2;
}

#fugdjqdwhn .gt_row {
  padding: 10px;
  /* row.padding */
  margin: 10px;
  vertical-align: middle;
}

#fugdjqdwhn .gt_stub {
  border-right-style: solid;
  border-right-width: 2px;
  border-right-color: #A8A8A8;
  padding-left: 12px;
}

#fugdjqdwhn .gt_stub.gt_row {
  background-color: #FFFFFF;
}

#fugdjqdwhn .gt_summary_row {
  background-color: #FFFFFF;
  /* summary_row.background.color */
  padding: 6px;
  /* summary_row.padding */
  text-transform: inherit;
  /* summary_row.text_transform */
}

#fugdjqdwhn .gt_first_summary_row {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #A8A8A8;
}

#fugdjqdwhn .gt_table_body {
  border-top-style: solid;
  /* field.border.top.style */
  border-top-width: 2px;
  /* field.border.top.width */
  border-top-color: #A8A8A8;
  /* field.border.top.color */
  border-bottom-style: solid;
  /* field.border.bottom.style */
  border-bottom-width: 2px;
  /* field.border.bottom.width */
  border-bottom-color: #A8A8A8;
  /* field.border.bottom.color */
}

#fugdjqdwhn .gt_footnote {
  font-size: 90%;
  /* footnote.font.size */
  padding: 4px;
  /* footnote.padding */
}

#fugdjqdwhn .gt_sourcenote {
  font-size: 90%;
  /* sourcenote.font.size */
  padding: 4px;
  /* sourcenote.padding */
}

#fugdjqdwhn .gt_center {
  text-align: center;
}

#fugdjqdwhn .gt_left {
  text-align: left;
}

#fugdjqdwhn .gt_right {
  text-align: right;
  font-variant-numeric: tabular-nums;
}

#fugdjqdwhn .gt_font_normal {
  font-weight: normal;
}

#fugdjqdwhn .gt_font_bold {
  font-weight: bold;
}

#fugdjqdwhn .gt_font_italic {
  font-style: italic;
}

#fugdjqdwhn .gt_super {
  font-size: 65%;
}

#fugdjqdwhn .gt_footnote_glyph {
  font-style: italic;
  font-size: 65%;
}
</style>

<div id="fugdjqdwhn" style="overflow-x:auto;">

<!--gt table start-->

<table class="gt_table">

<thead>

<tr>

<th class="gt_heading gt_title gt_font_normal gt_center" colspan="8">

The Cars of
<strong>gtcars</strong>

</th>

</tr>

<tr>

<th class="gt_heading gt_subtitle gt_font_normal gt_center gt_bottom_border" colspan="8">

These are some fine
automobiles

</th>

</tr>

</thead>

<tr>

<th class="gt_col_heading gt_left" rowspan="2" colspan="1">

</th>

<th class="gt_col_heading gt_center" rowspan="2" colspan="1">

Year

</th>

<th class="gt_col_heading gt_center" rowspan="2" colspan="1">

Trim

</th>

<th class="gt_col_heading gt_center" rowspan="2" colspan="1">

Transmission

</th>

<th class="gt_col_heading gt_column_spanner gt_center" rowspan="1" colspan="3">

<em>Performance</em>

</th>

<th class="gt_col_heading gt_center" rowspan="2" colspan="1">

MSRP<sup class='gt_footnote_glyph'>1</sup>

</th>

</tr>

<tr>

<th class="gt_col_heading gt_center" rowspan="1" colspan="1">

MPG

</th>

<th class="gt_col_heading gt_center" rowspan="1" colspan="1">

HP

</th>

<th class="gt_col_heading gt_center" rowspan="1" colspan="1">

Torque

</th>

</tr>

<tbody class="gt_table_body gt_striped">

<tr class="gt_group_heading_row">

<td colspan="8" class="gt_group_heading">

Germany

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Audi R8

</td>

<td class="gt_row gt_right">

2015

</td>

<td class="gt_row gt_left" style="font-size:12px;">

4.2 (Manual) Coupe

</td>

<td class="gt_row gt_left" style="font-size:12px;">

6 Speed<br><em> Manual </em>

</td>

<td class="gt_row gt_center" style="font-size:12px;">

11c<br>20h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

430<br>@7900rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

317<br>@4500rpm

</td>

<td class="gt_row gt_right">

$115,900

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Audi S8

</td>

<td class="gt_row gt_right">

2016

</td>

<td class="gt_row gt_left" style="font-size:12px;">

Base Sedan

</td>

<td class="gt_row gt_left" style="font-size:12px;">

8 Speed<br><em> Automatic/Manual </em>

</td>

<td class="gt_row gt_center" style="font-size:12px;">

15c<br>25h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

520<br>@5800rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

481<br>@1700rpm

</td>

<td class="gt_row gt_right">

$114,900

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Audi RS 7

</td>

<td class="gt_row gt_right">

2016

</td>

<td class="gt_row gt_left" style="font-size:12px;">

Quattro Hatchback

</td>

<td class="gt_row gt_left" style="font-size:12px;">

8 Speed<br><em> Automatic/Manual </em>

</td>

<td class="gt_row gt_center" style="font-size:12px;">

15c<br>25h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

560<br>@5700rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

516<br>@1750rpm

</td>

<td class="gt_row gt_right">

$108,900

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Audi S7

</td>

<td class="gt_row gt_right">

2016

</td>

<td class="gt_row gt_left" style="font-size:12px;">

Prestige quattro Hatchback

</td>

<td class="gt_row gt_left" style="font-size:12px;">

7 Speed<br><em> Automatic </em>

</td>

<td class="gt_row gt_center" style="font-size:12px;">

17c<br>27h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

450<br>@5800rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

406<br>@1400rpm

</td>

<td class="gt_row gt_right">

$82,900

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Audi S6

</td>

<td class="gt_row gt_right">

2016

</td>

<td class="gt_row gt_left" style="font-size:12px;">

Premium Plus quattro Sedan

</td>

<td class="gt_row gt_left" style="font-size:12px;">

7 Speed<br><em> Automatic </em>

</td>

<td class="gt_row gt_center" style="font-size:12px;">

18c<br>27h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

450<br>@5800rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

406<br>@1400rpm

</td>

<td class="gt_row gt_right">

$70,900

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

BMW i8

</td>

<td class="gt_row gt_right">

2016

</td>

<td class="gt_row gt_left" style="font-size:12px;">

Mega World Coupe

</td>

<td class="gt_row gt_left" style="font-size:12px;">

6 Speed<br><em> Automatic/Manual </em>

</td>

<td class="gt_row gt_center" style="font-size:12px;">

28c<br>29h<sup class='gt_footnote_glyph'>2</sup>

</td>

<td class="gt_row gt_center" style="font-size:12px;">

357<br>@5800rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

420<br>@3700rpm

</td>

<td class="gt_row gt_right">

$140,700

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

BMW M6

</td>

<td class="gt_row gt_right">

2016

</td>

<td class="gt_row gt_left" style="font-size:12px;">

Base Coupe

</td>

<td class="gt_row gt_left" style="font-size:12px;">

7 Speed<br><em> Automatic </em>

</td>

<td class="gt_row gt_center" style="font-size:12px;">

15c<br>22h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

560<br>@6000rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

500<br>@1500rpm

</td>

<td class="gt_row gt_right">

$113,400

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

BMW M5

</td>

<td class="gt_row gt_right">

2016

</td>

<td class="gt_row gt_left" style="font-size:12px;">

Base Sedan

</td>

<td class="gt_row gt_left" style="font-size:12px;">

7 Speed<br><em> Automatic/Manual </em>

</td>

<td class="gt_row gt_center" style="font-size:12px;">

15c<br>22h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

560<br>@6000rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

500<br>@1500rpm

</td>

<td class="gt_row gt_right">

$94,100

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

BMW 6-Series

</td>

<td class="gt_row gt_right">

2016

</td>

<td class="gt_row gt_left" style="font-size:12px;">

640 I Coupe

</td>

<td class="gt_row gt_left" style="font-size:12px;">

8 Speed<br><em> Automatic/Manual </em>

</td>

<td class="gt_row gt_center" style="font-size:12px;">

20c<br>30h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

315<br>@5800rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

330<br>@1400rpm

</td>

<td class="gt_row gt_right">

$77,300

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

BMW M4

</td>

<td class="gt_row gt_right">

2016

</td>

<td class="gt_row gt_left" style="font-size:12px;">

Base Coupe

</td>

<td class="gt_row gt_left" style="font-size:12px;">

6 Speed<br><em> Manual </em>

</td>

<td class="gt_row gt_center" style="font-size:12px;">

17c<br>24h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

425<br>@5500rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

406<br>@1850rpm

</td>

<td class="gt_row gt_right">

$65,700

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Mercedes-Benz AMG GT

</td>

<td class="gt_row gt_right">

2016

</td>

<td class="gt_row gt_left" style="font-size:12px;">

S Coupe

</td>

<td class="gt_row gt_left" style="font-size:12px;">

7 Speed<br><em> Automatic </em>

</td>

<td class="gt_row gt_center" style="font-size:12px;">

16c<br>22h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

503<br>@6250rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

479<br>@1750rpm

</td>

<td class="gt_row gt_right">

$129,900

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Mercedes-Benz SL-Class

</td>

<td class="gt_row gt_right">

2016

</td>

<td class="gt_row gt_left" style="font-size:12px;">

SL400 Convertible

</td>

<td class="gt_row gt_left" style="font-size:12px;">

7 Speed<br><em> Automatic/Manual </em>

</td>

<td class="gt_row gt_center" style="font-size:12px;">

20c<br>27h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

329<br>@5250rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

354<br>@1600rpm

</td>

<td class="gt_row gt_right">

$85,050

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Porsche 911

</td>

<td class="gt_row gt_right">

2016

</td>

<td class="gt_row gt_left" style="font-size:12px;">

Carrera Coupe

</td>

<td class="gt_row gt_left" style="font-size:12px;">

7 Speed<br><em> Manual </em>

</td>

<td class="gt_row gt_center" style="font-size:12px;">

20c<br>28h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

350<br>@7400rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

287<br>@5600rpm

</td>

<td class="gt_row gt_right">

$84,300

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Porsche Panamera

</td>

<td class="gt_row gt_right">

2016

</td>

<td class="gt_row gt_left" style="font-size:12px;">

Base Sedan

</td>

<td class="gt_row gt_left" style="font-size:12px;">

7 Speed<br><em> Automatic </em>

</td>

<td class="gt_row gt_center" style="font-size:12px;">

18c<br>28h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

310<br>@6200rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

295<br>@3750rpm

</td>

<td class="gt_row gt_right">

$78,100

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Porsche 718 Boxster

</td>

<td class="gt_row gt_right">

2017

</td>

<td class="gt_row gt_left" style="font-size:12px;">

Base Convertible

</td>

<td class="gt_row gt_left" style="font-size:12px;">

6 Speed<br><em> Manual </em>

</td>

<td class="gt_row gt_center" style="font-size:12px;">

21c<br>28h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

300<br>@6500rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

280<br>@1950rpm

</td>

<td class="gt_row gt_right">

$56,000

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Porsche 718 Cayman

</td>

<td class="gt_row gt_right">

2017

</td>

<td class="gt_row gt_left" style="font-size:12px;">

Base Coupe

</td>

<td class="gt_row gt_left" style="font-size:12px;">

6 Speed<br><em> Manual </em>

</td>

<td class="gt_row gt_center" style="font-size:12px;">

20c<br>29h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

300<br>@6500rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

280<br>@1950rpm

</td>

<td class="gt_row gt_right">

$53,900

</td>

</tr>

<tr class="gt_group_heading_row">

<td colspan="8" class="gt_group_heading">

Italy

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Ferrari LaFerrari

</td>

<td class="gt_row gt_right">

2015

</td>

<td class="gt_row gt_left" style="font-size:12px;">

Base Coupe

</td>

<td class="gt_row gt_left" style="font-size:12px;">

7 Speed<br><em> Automatic </em>

</td>

<td class="gt_row gt_center" style="font-size:12px;">

12c<br>16h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

949<br>@9000rpm\<sup class=‘gt\_footnote\_glyph’\>3</sup>

</td>

<td class="gt_row gt_center" style="font-size:12px;">

664<br>@6750rpm

</td>

<td class="gt_row gt_right">

$1,416,362

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Ferrari F12Berlinetta

</td>

<td class="gt_row gt_right">

2015

</td>

<td class="gt_row gt_left" style="font-size:12px;">

Base Coupe

</td>

<td class="gt_row gt_left" style="font-size:12px;">

7 Speed<br><em> Automatic </em>

</td>

<td class="gt_row gt_center" style="font-size:12px;">

11c<br>16h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

731<br>@8250rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

509<br>@6000rpm

</td>

<td class="gt_row gt_right">

$319,995

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Ferrari GTC4Lusso

</td>

<td class="gt_row gt_right">

2017

</td>

<td class="gt_row gt_left" style="font-size:12px;">

Base Coupe

</td>

<td class="gt_row gt_left" style="font-size:12px;">

7 Speed<br><em> Automatic </em>

</td>

<td class="gt_row gt_center" style="font-size:12px;">

12c<br>17h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

680<br>@8250rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

514<br>@5750rpm

</td>

<td class="gt_row gt_right">

$298,000

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Ferrari FF

</td>

<td class="gt_row gt_right">

2015

</td>

<td class="gt_row gt_left" style="font-size:12px;">

Base Coupe

</td>

<td class="gt_row gt_left" style="font-size:12px;">

7 Speed<br><em> Automatic </em>

</td>

<td class="gt_row gt_center" style="font-size:12px;">

11c<br>16h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

652<br>@8000rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

504<br>@6000rpm

</td>

<td class="gt_row gt_right">

$295,000

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Ferrari 458 Speciale

</td>

<td class="gt_row gt_right">

2015

</td>

<td class="gt_row gt_left" style="font-size:12px;">

Base Coupe

</td>

<td class="gt_row gt_left" style="font-size:12px;">

7 Speed<br><em> Automatic </em>

</td>

<td class="gt_row gt_center" style="font-size:12px;">

13c<br>17h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

597<br>@9000rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

398<br>@6000rpm

</td>

<td class="gt_row gt_right">

$291,744

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Ferrari 458 Spider

</td>

<td class="gt_row gt_right">

2015

</td>

<td class="gt_row gt_left" style="font-size:12px;">

Base

</td>

<td class="gt_row gt_left" style="font-size:12px;">

7 Speed<br><em> Automatic </em>

</td>

<td class="gt_row gt_center" style="font-size:12px;">

13c<br>17h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

562<br>@9000rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

398<br>@6000rpm

</td>

<td class="gt_row gt_right">

$263,553

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Ferrari 488 GTB

</td>

<td class="gt_row gt_right">

2016

</td>

<td class="gt_row gt_left" style="font-size:12px;">

Base Coupe

</td>

<td class="gt_row gt_left" style="font-size:12px;">

7 Speed<br><em> Automatic </em>

</td>

<td class="gt_row gt_center" style="font-size:12px;">

15c<br>22h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

661<br>@8000rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

561<br>@3000rpm

</td>

<td class="gt_row gt_right">

$245,400

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Ferrari 458 Italia

</td>

<td class="gt_row gt_right">

2014

</td>

<td class="gt_row gt_left" style="font-size:12px;">

Base Coupe

</td>

<td class="gt_row gt_left" style="font-size:12px;">

7 Speed<br><em> Automatic </em>

</td>

<td class="gt_row gt_center" style="font-size:12px;">

13c<br>17h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

562<br>@9000rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

398<br>@6000rpm

</td>

<td class="gt_row gt_right">

$233,509

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Ferrari California

</td>

<td class="gt_row gt_right">

2015

</td>

<td class="gt_row gt_left" style="font-size:12px;">

Base Convertible

</td>

<td class="gt_row gt_left" style="font-size:12px;">

7 Speed<br><em> Automatic </em>

</td>

<td class="gt_row gt_center" style="font-size:12px;">

16c<br>23h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

553<br>@7500rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

557<br>@4750rpm

</td>

<td class="gt_row gt_right">

$198,973

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Lamborghini Aventador

</td>

<td class="gt_row gt_right">

2015

</td>

<td class="gt_row gt_left" style="font-size:12px;">

LP 700-4 Coupe

</td>

<td class="gt_row gt_left" style="font-size:12px;">

7 Speed<br><em> Automatic </em>

</td>

<td class="gt_row gt_center" style="font-size:12px;">

11c<br>18h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

700<br>@8250rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

507<br>@5500rpm

</td>

<td class="gt_row gt_right">

$397,500

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Lamborghini Huracan

</td>

<td class="gt_row gt_right">

2015

</td>

<td class="gt_row gt_left" style="font-size:12px;">

LP 610-4 Coupe

</td>

<td class="gt_row gt_left" style="font-size:12px;">

7 Speed<br><em> Automatic </em>

</td>

<td class="gt_row gt_center" style="font-size:12px;">

16c<br>20h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

610<br>@8250rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

413<br>@6500rpm

</td>

<td class="gt_row gt_right">

$237,250

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Lamborghini Gallardo

</td>

<td class="gt_row gt_right">

2014

</td>

<td class="gt_row gt_left" style="font-size:12px;">

LP 550-2 Coupe

</td>

<td class="gt_row gt_left" style="font-size:12px;">

6 Speed<br><em> Automatic </em>

</td>

<td class="gt_row gt_center" style="font-size:12px;">

12c<br>20h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

550<br>@8000rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

398<br>@6500rpm

</td>

<td class="gt_row gt_right">

$191,900

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Maserati Granturismo

</td>

<td class="gt_row gt_right">

2016

</td>

<td class="gt_row gt_left" style="font-size:12px;">

Sport Coupe

</td>

<td class="gt_row gt_left" style="font-size:12px;">

6 Speed<br><em> Automatic/Manual </em>

</td>

<td class="gt_row gt_center" style="font-size:12px;">

13c<br>21h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

454<br>@7600rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

384<br>@4750rpm

</td>

<td class="gt_row gt_right">

$132,825

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Maserati Quattroporte

</td>

<td class="gt_row gt_right">

2016

</td>

<td class="gt_row gt_left" style="font-size:12px;">

S Sedan

</td>

<td class="gt_row gt_left" style="font-size:12px;">

8 Speed<br><em> Automatic/Manual </em>

</td>

<td class="gt_row gt_center" style="font-size:12px;">

16c<br>23h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

404<br>@5500rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

406<br>@1500rpm

</td>

<td class="gt_row gt_right">

$99,900

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Maserati Ghibli

</td>

<td class="gt_row gt_right">

2016

</td>

<td class="gt_row gt_left" style="font-size:12px;">

Base Sedan

</td>

<td class="gt_row gt_left" style="font-size:12px;">

8 Speed<br><em> Automatic/Manual </em>

</td>

<td class="gt_row gt_center" style="font-size:12px;">

17c<br>24h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

345<br>@5250rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

369<br>@1750rpm

</td>

<td class="gt_row gt_right">

$70,600

</td>

</tr>

<tr class="gt_group_heading_row">

<td colspan="8" class="gt_group_heading">

United States

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Chevrolet Corvette

</td>

<td class="gt_row gt_right">

2016

</td>

<td class="gt_row gt_left" style="font-size:12px;">

Z06 Coupe

</td>

<td class="gt_row gt_left" style="font-size:12px;">

7 Speed<br><em> Manual </em>

</td>

<td class="gt_row gt_center" style="font-size:12px;">

15c<br>22h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

650<br>@6400rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

650<br>@3600rpm

</td>

<td class="gt_row gt_right">

$88,345

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Dodge Viper

</td>

<td class="gt_row gt_right">

2017

</td>

<td class="gt_row gt_left" style="font-size:12px;">

GT Coupe

</td>

<td class="gt_row gt_left" style="font-size:12px;">

6 Speed<br><em> Manual </em>

</td>

<td class="gt_row gt_center" style="font-size:12px;">

12c<br>19h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

645<br>@5000rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

600<br>@5000rpm

</td>

<td class="gt_row gt_right">

$95,895

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Ford GT

</td>

<td class="gt_row gt_right">

2017

</td>

<td class="gt_row gt_left" style="font-size:12px;">

Base Coupe

</td>

<td class="gt_row gt_left" style="font-size:12px;">

7 Speed<br><em> Automatic </em>

</td>

<td class="gt_row gt_center" style="font-size:12px;">

11c<br>18h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

647<br>@6250rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

550<br>@5900rpm

</td>

<td class="gt_row gt_right">

$447,000

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Tesla Model S

</td>

<td class="gt_row gt_right">

2017

</td>

<td class="gt_row gt_left" style="font-size:12px;">

75D

</td>

<td class="gt_row gt_left" style="font-size:12px;">

1 Speed<br><em> Direct Drive </em>

</td>

<td class="gt_row gt_center" style="font-size:12px;">

NA

</td>

<td class="gt_row gt_center" style="font-size:12px;">

259<br>@6100rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

243

</td>

<td class="gt_row gt_right">

$74,500

</td>

</tr>

<tr class="gt_group_heading_row">

<td colspan="8" class="gt_group_heading">

Japan

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Acura NSX

</td>

<td class="gt_row gt_right">

2017

</td>

<td class="gt_row gt_left" style="font-size:12px;">

Base Coupe

</td>

<td class="gt_row gt_left" style="font-size:12px;">

9 Speed<br><em> Automatic </em>

</td>

<td class="gt_row gt_center" style="font-size:12px;">

21c<br>22h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

573<br>@6500rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

476<br>@2000rpm

</td>

<td class="gt_row gt_right">

$156,000

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Nissan GT-R

</td>

<td class="gt_row gt_right">

2016

</td>

<td class="gt_row gt_left" style="font-size:12px;">

Premium Coupe

</td>

<td class="gt_row gt_left" style="font-size:12px;">

6 Speed<br><em> Automatic </em>

</td>

<td class="gt_row gt_center" style="font-size:12px;">

16c<br>22h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

545<br>@6400rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

436<br>@3200rpm

</td>

<td class="gt_row gt_right">

$101,770

</td>

</tr>

<tr class="gt_group_heading_row">

<td colspan="8" class="gt_group_heading">

United Kingdom

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Aston Martin Vanquish

</td>

<td class="gt_row gt_right">

2016

</td>

<td class="gt_row gt_left" style="font-size:12px;">

Base Coupe

</td>

<td class="gt_row gt_left" style="font-size:12px;">

8 Speed<br><em> Automatic/Manual </em>

</td>

<td class="gt_row gt_center" style="font-size:12px;">

13c<br>21h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

568<br>@6650rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

465<br>@5500rpm

</td>

<td class="gt_row gt_right">

$287,250

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Aston Martin DB11

</td>

<td class="gt_row gt_right">

2017

</td>

<td class="gt_row gt_left" style="font-size:12px;">

Base Coupe

</td>

<td class="gt_row gt_left" style="font-size:12px;">

8 Speed<br><em> Automatic/Manual </em>

</td>

<td class="gt_row gt_center" style="font-size:12px;">

15c<br>21h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

608<br>@6500rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

516<br>@1500rpm

</td>

<td class="gt_row gt_right">

$211,195

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Aston Martin Rapide S

</td>

<td class="gt_row gt_right">

2016

</td>

<td class="gt_row gt_left" style="font-size:12px;">

Base Sedan

</td>

<td class="gt_row gt_left" style="font-size:12px;">

8 Speed<br><em> Automatic/Manual </em>

</td>

<td class="gt_row gt_center" style="font-size:12px;">

14c<br>21h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

552<br>@6650rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

465<br>@5500rpm

</td>

<td class="gt_row gt_right">

$205,300

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Aston Martin Vantage

</td>

<td class="gt_row gt_right">

2016

</td>

<td class="gt_row gt_left" style="font-size:12px;">

V8 GT (Manual) Coupe

</td>

<td class="gt_row gt_left" style="font-size:12px;">

6 Speed<br><em> Manual </em>

</td>

<td class="gt_row gt_center" style="font-size:12px;">

13c<br>19h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

430<br>@7300rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

361<br>@5000rpm

</td>

<td class="gt_row gt_right">

$103,300

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Bentley Continental GT

</td>

<td class="gt_row gt_right">

2016

</td>

<td class="gt_row gt_left" style="font-size:12px;">

V8 Coupe

</td>

<td class="gt_row gt_left" style="font-size:12px;">

8 Speed<br><em> Automatic/Manual </em>

</td>

<td class="gt_row gt_center" style="font-size:12px;">

15c<br>25h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

500<br>@6000rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

487<br>@1700rpm

</td>

<td class="gt_row gt_right">

$198,500

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Jaguar F-Type

</td>

<td class="gt_row gt_right">

2016

</td>

<td class="gt_row gt_left" style="font-size:12px;">

Base (Manual) Coupe

</td>

<td class="gt_row gt_left" style="font-size:12px;">

6 Speed<br><em> Manual </em>

</td>

<td class="gt_row gt_center" style="font-size:12px;">

16c<br>24h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

340<br>@6500rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

332<br>@3500rpm

</td>

<td class="gt_row gt_right">

$65,000

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Lotus Evora

</td>

<td class="gt_row gt_right">

2017

</td>

<td class="gt_row gt_left" style="font-size:12px;">

2+2 Coupe

</td>

<td class="gt_row gt_left" style="font-size:12px;">

6 Speed<br><em> Manual </em>

</td>

<td class="gt_row gt_center" style="font-size:12px;">

16c<br>24h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

400<br>@7000rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

302<br>@3500rpm

</td>

<td class="gt_row gt_right">

$91,900

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

McLaren 570

</td>

<td class="gt_row gt_right">

2016

</td>

<td class="gt_row gt_left" style="font-size:12px;">

Base Coupe

</td>

<td class="gt_row gt_left" style="font-size:12px;">

7 Speed<br><em> Automatic </em>

</td>

<td class="gt_row gt_center" style="font-size:12px;">

16c<br>23h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

570<br>@7500rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

443<br>@5000rpm

</td>

<td class="gt_row gt_right">

$184,900

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Rolls-Royce Dawn

</td>

<td class="gt_row gt_right">

2016

</td>

<td class="gt_row gt_left" style="font-size:12px;">

Base Convertible

</td>

<td class="gt_row gt_left" style="font-size:12px;">

8 Speed<br><em> Automatic </em>

</td>

<td class="gt_row gt_center" style="font-size:12px;">

12c<br>19h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

563<br>@5250rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

575<br>@1500rpm

</td>

<td class="gt_row gt_right">

$335,000

</td>

</tr>

<tr>

<td class="gt_row gt_stub gt_left">

Rolls-Royce Wraith

</td>

<td class="gt_row gt_right">

2016

</td>

<td class="gt_row gt_left" style="font-size:12px;">

Base Coupe

</td>

<td class="gt_row gt_left" style="font-size:12px;">

8 Speed<br><em> Automatic </em>

</td>

<td class="gt_row gt_center" style="font-size:12px;">

13c<br>21h

</td>

<td class="gt_row gt_center" style="font-size:12px;">

624<br>@5600rpm

</td>

<td class="gt_row gt_center" style="font-size:12px;">

590<br>@1500rpm

</td>

<td class="gt_row gt_right">

$304,350

</td>

</tr>

</tbody>

<tfoot>

<tr>

<td colspan="9" class="gt_sourcenote">

Source: Various pages within
<a href="https://www.edmunds.com">edmunds.com</a>.

</td>

</tr>

</tfoot>

<tfoot>

<tr>

<td colspan="8" class="gt_footnote">

<sup class='gt_footnote_glyph'><em>1</em></sup> All prices in U.S.
dollars (USD).<br /><sup class='gt_footnote_glyph'><em>2</em></sup> Best
gas mileage (city) of all the
<strong>gtcars</strong>.<br /><sup class='gt_footnote_glyph'><em>3</em></sup>
The highest horsepower of all the <strong>gtcars</strong>.

</td>

</tr>

</tfoot>

</table>

<!--gt table end-->

</div>

<!--/html_preserve-->

这个 footnote 可以定义具体哪个单元格，很好。
