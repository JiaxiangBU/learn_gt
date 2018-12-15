
<https://gt.rstudio.com/articles/creating-display-tables.html>

> We can think of display tables as output only, where we’d not want to
> use them as input ever again. Other features include annotations,
> table element styling, and text transformations that serve to
> communicate the subject matter more
    clearly.

这是gt产生的两个目的

1.  不是需要重复输入的
2.  增加更多解释，方便说明问题

<!-- end list -->

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
# Take the `islands` dataset and use some
# dplyr functionality to obtain the ten
# biggest islands in the world
islands_tbl <- 
  dplyr::data_frame(
    name = names(islands),
    size = islands
  ) %>%
  dplyr::arrange(desc(size)) %>%
  dplyr::slice(1:10)

# Display the table
library(gt)
gt_tbl <- 
    islands_tbl %>% 
    gt()
```

> These table parts work well together and there the possible variations
> in arrangement can handle most tabular presentation needs.

我觉得这个愿景写的很不错。

add title and subtitle

``` r
# Make a display table with the `islands_tbl`
# table; put a heading just above the column labels
gt_tbl <- 
  gt_tbl %>%
  tab_header(
    title = "Large Landmasses of the World",
    subtitle = "The top ten largest are presented"
  )

# Show the gt Table
gt_tbl
```

<!--html_preserve-->

<style>html {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Helvetica Neue', 'Fira Sans', 'Droid Sans', Arial, sans-serif;
}

#yphmshantk .gt_table {
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

#yphmshantk .gt_heading {
  background-color: #FFFFFF;
  /* heading.background.color */
  border-bottom-color: #FFFFFF;
}

#yphmshantk .gt_title {
  color: #000000;
  font-size: 125%;
  /* heading.title.font.size */
  padding-top: 4px;
  /* heading.top.padding */
  padding-bottom: 1px;
  border-bottom-color: #FFFFFF;
  border-bottom-width: 0;
}

#yphmshantk .gt_subtitle {
  color: #000000;
  font-size: 85%;
  /* heading.subtitle.font.size */
  padding-top: 1px;
  padding-bottom: 4px;
  /* heading.bottom.padding */
  border-top-color: #FFFFFF;
  border-top-width: 0;
}

#yphmshantk .gt_bottom_border {
  border-bottom-style: solid;
  /* heading.border.bottom.style */
  border-bottom-width: 2px;
  /* heading.border.bottom.width */
  border-bottom-color: #A8A8A8;
  /* heading.border.bottom.color */
}

#yphmshantk .gt_column_spanner {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #A8A8A8;
  padding-top: 4px;
  padding-bottom: 4px;
}

#yphmshantk .gt_col_heading {
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

#yphmshantk .gt_sep_right {
  border-right: 5px solid #FFFFFF;
}

#yphmshantk .gt_group_heading {
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

#yphmshantk .gt_empty_group_heading {
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

#yphmshantk .gt_striped tr:nth-child(even) {
  background-color: #f2f2f2;
}

#yphmshantk .gt_row {
  padding: 10px;
  /* row.padding */
  margin: 10px;
  vertical-align: middle;
}

#yphmshantk .gt_stub {
  border-right-style: solid;
  border-right-width: 2px;
  border-right-color: #A8A8A8;
  padding-left: 12px;
}

#yphmshantk .gt_stub.gt_row {
  background-color: #FFFFFF;
}

#yphmshantk .gt_summary_row {
  background-color: #FFFFFF;
  /* summary_row.background.color */
  padding: 6px;
  /* summary_row.padding */
  text-transform: inherit;
  /* summary_row.text_transform */
}

#yphmshantk .gt_first_summary_row {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #A8A8A8;
}

#yphmshantk .gt_table_body {
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

#yphmshantk .gt_footnote {
  font-size: 90%;
  /* footnote.font.size */
  padding: 4px;
  /* footnote.padding */
}

#yphmshantk .gt_sourcenote {
  font-size: 90%;
  /* sourcenote.font.size */
  padding: 4px;
  /* sourcenote.padding */
}

#yphmshantk .gt_center {
  text-align: center;
}

#yphmshantk .gt_left {
  text-align: left;
}

#yphmshantk .gt_right {
  text-align: right;
  font-variant-numeric: tabular-nums;
}

#yphmshantk .gt_font_normal {
  font-weight: normal;
}

#yphmshantk .gt_font_bold {
  font-weight: bold;
}

#yphmshantk .gt_font_italic {
  font-style: italic;
}

#yphmshantk .gt_super {
  font-size: 65%;
}

#yphmshantk .gt_footnote_glyph {
  font-style: italic;
  font-size: 65%;
}
</style>

<div id="yphmshantk" style="overflow-x:auto;">

<!--gt table start-->

<table class="gt_table">

<thead>

<tr>

<th class="gt_heading gt_title gt_font_normal gt_center" colspan="2">

Large Landmasses of the
World

</th>

</tr>

<tr>

<th class="gt_heading gt_subtitle gt_font_normal gt_center gt_bottom_border" colspan="2">

The top ten largest are presented

</th>

</tr>

</thead>

<tr>

<th class="gt_col_heading gt_left" rowspan="1" colspan="1">

name

</th>

<th class="gt_col_heading gt_right" rowspan="1" colspan="1">

size

</th>

</tr>

<tbody class="gt_table_body gt_striped">

<tr>

<td class="gt_row gt_left">

Asia

</td>

<td class="gt_row gt_right">

16988

</td>

</tr>

<tr>

<td class="gt_row gt_left">

Africa

</td>

<td class="gt_row gt_right">

11506

</td>

</tr>

<tr>

<td class="gt_row gt_left">

North America

</td>

<td class="gt_row gt_right">

9390

</td>

</tr>

<tr>

<td class="gt_row gt_left">

South America

</td>

<td class="gt_row gt_right">

6795

</td>

</tr>

<tr>

<td class="gt_row gt_left">

Antarctica

</td>

<td class="gt_row gt_right">

5500

</td>

</tr>

<tr>

<td class="gt_row gt_left">

Europe

</td>

<td class="gt_row gt_right">

3745

</td>

</tr>

<tr>

<td class="gt_row gt_left">

Australia

</td>

<td class="gt_row gt_right">

2968

</td>

</tr>

<tr>

<td class="gt_row gt_left">

Greenland

</td>

<td class="gt_row gt_right">

840

</td>

</tr>

<tr>

<td class="gt_row gt_left">

New Guinea

</td>

<td class="gt_row gt_right">

306

</td>

</tr>

<tr>

<td class="gt_row gt_left">

Borneo

</td>

<td class="gt_row gt_right">

280

</td>

</tr>

</tbody>

</table>

<!--gt table end-->

</div>

<!--/html_preserve-->

保证了能够像 ggplot 一样展示 table。

用md修饰一下

``` r
# Use markdown for the heading's `title` and `subtitle` to
# add bold and italicized characters
gt(islands_tbl[1:2,]) %>%
  tab_header(
    title = md("**Large Landmasses of the World**"),
    subtitle = md("The *top two* largest are presented")
  )
```

<!--html_preserve-->

<style>html {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Helvetica Neue', 'Fira Sans', 'Droid Sans', Arial, sans-serif;
}

#qansewoupa .gt_table {
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

#qansewoupa .gt_heading {
  background-color: #FFFFFF;
  /* heading.background.color */
  border-bottom-color: #FFFFFF;
}

#qansewoupa .gt_title {
  color: #000000;
  font-size: 125%;
  /* heading.title.font.size */
  padding-top: 4px;
  /* heading.top.padding */
  padding-bottom: 1px;
  border-bottom-color: #FFFFFF;
  border-bottom-width: 0;
}

#qansewoupa .gt_subtitle {
  color: #000000;
  font-size: 85%;
  /* heading.subtitle.font.size */
  padding-top: 1px;
  padding-bottom: 4px;
  /* heading.bottom.padding */
  border-top-color: #FFFFFF;
  border-top-width: 0;
}

#qansewoupa .gt_bottom_border {
  border-bottom-style: solid;
  /* heading.border.bottom.style */
  border-bottom-width: 2px;
  /* heading.border.bottom.width */
  border-bottom-color: #A8A8A8;
  /* heading.border.bottom.color */
}

#qansewoupa .gt_column_spanner {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #A8A8A8;
  padding-top: 4px;
  padding-bottom: 4px;
}

#qansewoupa .gt_col_heading {
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

#qansewoupa .gt_sep_right {
  border-right: 5px solid #FFFFFF;
}

#qansewoupa .gt_group_heading {
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

#qansewoupa .gt_empty_group_heading {
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

#qansewoupa .gt_striped tr:nth-child(even) {
  background-color: #f2f2f2;
}

#qansewoupa .gt_row {
  padding: 10px;
  /* row.padding */
  margin: 10px;
  vertical-align: middle;
}

#qansewoupa .gt_stub {
  border-right-style: solid;
  border-right-width: 2px;
  border-right-color: #A8A8A8;
  padding-left: 12px;
}

#qansewoupa .gt_stub.gt_row {
  background-color: #FFFFFF;
}

#qansewoupa .gt_summary_row {
  background-color: #FFFFFF;
  /* summary_row.background.color */
  padding: 6px;
  /* summary_row.padding */
  text-transform: inherit;
  /* summary_row.text_transform */
}

#qansewoupa .gt_first_summary_row {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #A8A8A8;
}

#qansewoupa .gt_table_body {
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

#qansewoupa .gt_footnote {
  font-size: 90%;
  /* footnote.font.size */
  padding: 4px;
  /* footnote.padding */
}

#qansewoupa .gt_sourcenote {
  font-size: 90%;
  /* sourcenote.font.size */
  padding: 4px;
  /* sourcenote.padding */
}

#qansewoupa .gt_center {
  text-align: center;
}

#qansewoupa .gt_left {
  text-align: left;
}

#qansewoupa .gt_right {
  text-align: right;
  font-variant-numeric: tabular-nums;
}

#qansewoupa .gt_font_normal {
  font-weight: normal;
}

#qansewoupa .gt_font_bold {
  font-weight: bold;
}

#qansewoupa .gt_font_italic {
  font-style: italic;
}

#qansewoupa .gt_super {
  font-size: 65%;
}

#qansewoupa .gt_footnote_glyph {
  font-style: italic;
  font-size: 65%;
}
</style>

<div id="qansewoupa" style="overflow-x:auto;">

<!--gt table start-->

<table class="gt_table">

<thead>

<tr>

<th class="gt_heading gt_title gt_font_normal gt_center" colspan="2">

<strong>Large Landmasses of the
World</strong>

</th>

</tr>

<tr>

<th class="gt_heading gt_subtitle gt_font_normal gt_center gt_bottom_border" colspan="2">

The <em>top two</em> largest are presented

</th>

</tr>

</thead>

<tr>

<th class="gt_col_heading gt_left" rowspan="1" colspan="1">

name

</th>

<th class="gt_col_heading gt_right" rowspan="1" colspan="1">

size

</th>

</tr>

<tbody class="gt_table_body gt_striped">

<tr>

<td class="gt_row gt_left">

Asia

</td>

<td class="gt_row gt_right">

16988

</td>

</tr>

<tr>

<td class="gt_row gt_left">

Africa

</td>

<td class="gt_row gt_right">

11506

</td>

</tr>

</tbody>

</table>

<!--gt table end-->

</div>

<!--/html_preserve-->

<input type="checkbox" id="checkbox1" class="styled">什么时候支持`@`写在表格内
[GitHub Issue](https://github.com/rstudio/gt/issues/112)

``` r
# Display the `islands_tbl` data with a heading and
# two source notes
gt_tbl <- 
  gt_tbl %>%
  tab_source_note(
    source_note = "Source: The World Almanac and Book of Facts, 1975, page 406."
  ) %>%
  tab_source_note(
    source_note = md("Reference: McNeil, D. R. (1977) *Interactive Data Analysis*. Wiley.")
  )

# Show the gt Table
gt_tbl
```

<!--html_preserve-->

<style>html {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Helvetica Neue', 'Fira Sans', 'Droid Sans', Arial, sans-serif;
}

#immwprmaoq .gt_table {
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

#immwprmaoq .gt_heading {
  background-color: #FFFFFF;
  /* heading.background.color */
  border-bottom-color: #FFFFFF;
}

#immwprmaoq .gt_title {
  color: #000000;
  font-size: 125%;
  /* heading.title.font.size */
  padding-top: 4px;
  /* heading.top.padding */
  padding-bottom: 1px;
  border-bottom-color: #FFFFFF;
  border-bottom-width: 0;
}

#immwprmaoq .gt_subtitle {
  color: #000000;
  font-size: 85%;
  /* heading.subtitle.font.size */
  padding-top: 1px;
  padding-bottom: 4px;
  /* heading.bottom.padding */
  border-top-color: #FFFFFF;
  border-top-width: 0;
}

#immwprmaoq .gt_bottom_border {
  border-bottom-style: solid;
  /* heading.border.bottom.style */
  border-bottom-width: 2px;
  /* heading.border.bottom.width */
  border-bottom-color: #A8A8A8;
  /* heading.border.bottom.color */
}

#immwprmaoq .gt_column_spanner {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #A8A8A8;
  padding-top: 4px;
  padding-bottom: 4px;
}

#immwprmaoq .gt_col_heading {
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

#immwprmaoq .gt_sep_right {
  border-right: 5px solid #FFFFFF;
}

#immwprmaoq .gt_group_heading {
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

#immwprmaoq .gt_empty_group_heading {
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

#immwprmaoq .gt_striped tr:nth-child(even) {
  background-color: #f2f2f2;
}

#immwprmaoq .gt_row {
  padding: 10px;
  /* row.padding */
  margin: 10px;
  vertical-align: middle;
}

#immwprmaoq .gt_stub {
  border-right-style: solid;
  border-right-width: 2px;
  border-right-color: #A8A8A8;
  padding-left: 12px;
}

#immwprmaoq .gt_stub.gt_row {
  background-color: #FFFFFF;
}

#immwprmaoq .gt_summary_row {
  background-color: #FFFFFF;
  /* summary_row.background.color */
  padding: 6px;
  /* summary_row.padding */
  text-transform: inherit;
  /* summary_row.text_transform */
}

#immwprmaoq .gt_first_summary_row {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #A8A8A8;
}

#immwprmaoq .gt_table_body {
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

#immwprmaoq .gt_footnote {
  font-size: 90%;
  /* footnote.font.size */
  padding: 4px;
  /* footnote.padding */
}

#immwprmaoq .gt_sourcenote {
  font-size: 90%;
  /* sourcenote.font.size */
  padding: 4px;
  /* sourcenote.padding */
}

#immwprmaoq .gt_center {
  text-align: center;
}

#immwprmaoq .gt_left {
  text-align: left;
}

#immwprmaoq .gt_right {
  text-align: right;
  font-variant-numeric: tabular-nums;
}

#immwprmaoq .gt_font_normal {
  font-weight: normal;
}

#immwprmaoq .gt_font_bold {
  font-weight: bold;
}

#immwprmaoq .gt_font_italic {
  font-style: italic;
}

#immwprmaoq .gt_super {
  font-size: 65%;
}

#immwprmaoq .gt_footnote_glyph {
  font-style: italic;
  font-size: 65%;
}
</style>

<div id="immwprmaoq" style="overflow-x:auto;">

<!--gt table start-->

<table class="gt_table">

<thead>

<tr>

<th class="gt_heading gt_title gt_font_normal gt_center" colspan="2">

Large Landmasses of the
World

</th>

</tr>

<tr>

<th class="gt_heading gt_subtitle gt_font_normal gt_center gt_bottom_border" colspan="2">

The top ten largest are presented

</th>

</tr>

</thead>

<tr>

<th class="gt_col_heading gt_left" rowspan="1" colspan="1">

name

</th>

<th class="gt_col_heading gt_right" rowspan="1" colspan="1">

size

</th>

</tr>

<tbody class="gt_table_body gt_striped">

<tr>

<td class="gt_row gt_left">

Asia

</td>

<td class="gt_row gt_right">

16988

</td>

</tr>

<tr>

<td class="gt_row gt_left">

Africa

</td>

<td class="gt_row gt_right">

11506

</td>

</tr>

<tr>

<td class="gt_row gt_left">

North America

</td>

<td class="gt_row gt_right">

9390

</td>

</tr>

<tr>

<td class="gt_row gt_left">

South America

</td>

<td class="gt_row gt_right">

6795

</td>

</tr>

<tr>

<td class="gt_row gt_left">

Antarctica

</td>

<td class="gt_row gt_right">

5500

</td>

</tr>

<tr>

<td class="gt_row gt_left">

Europe

</td>

<td class="gt_row gt_right">

3745

</td>

</tr>

<tr>

<td class="gt_row gt_left">

Australia

</td>

<td class="gt_row gt_right">

2968

</td>

</tr>

<tr>

<td class="gt_row gt_left">

Greenland

</td>

<td class="gt_row gt_right">

840

</td>

</tr>

<tr>

<td class="gt_row gt_left">

New Guinea

</td>

<td class="gt_row gt_right">

306

</td>

</tr>

<tr>

<td class="gt_row gt_left">

Borneo

</td>

<td class="gt_row gt_right">

280

</td>

</tr>

</tbody>

<tfoot>

<tr>

<td colspan="3" class="gt_sourcenote">

Source: The World Almanac and Book of Facts, 1975, page 406.

</td>

</tr>

<tr>

<td colspan="3" class="gt_sourcenote">

Reference: McNeil, D. R. (1977) <em>Interactive Data Analysis</em>.
Wiley.

</td>

</tr>

</tfoot>

</table>

<!--gt table end-->

</div>

<!--/html_preserve-->

footnote 可以复选单元格

``` r
# Add footnotes (the same text) to two different
# cell; data cells are targeted with `data_cells()`
gt_tbl <- 
  gt_tbl %>%
  tab_footnote(
    footnote = "The Americas.",
    locations = cells_data(
      columns = vars(name),
      rows = 3:4)
  )

# Show the gt Table
gt_tbl
```

<!--html_preserve-->

<style>html {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Helvetica Neue', 'Fira Sans', 'Droid Sans', Arial, sans-serif;
}

#awdcykrrvl .gt_table {
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

#awdcykrrvl .gt_heading {
  background-color: #FFFFFF;
  /* heading.background.color */
  border-bottom-color: #FFFFFF;
}

#awdcykrrvl .gt_title {
  color: #000000;
  font-size: 125%;
  /* heading.title.font.size */
  padding-top: 4px;
  /* heading.top.padding */
  padding-bottom: 1px;
  border-bottom-color: #FFFFFF;
  border-bottom-width: 0;
}

#awdcykrrvl .gt_subtitle {
  color: #000000;
  font-size: 85%;
  /* heading.subtitle.font.size */
  padding-top: 1px;
  padding-bottom: 4px;
  /* heading.bottom.padding */
  border-top-color: #FFFFFF;
  border-top-width: 0;
}

#awdcykrrvl .gt_bottom_border {
  border-bottom-style: solid;
  /* heading.border.bottom.style */
  border-bottom-width: 2px;
  /* heading.border.bottom.width */
  border-bottom-color: #A8A8A8;
  /* heading.border.bottom.color */
}

#awdcykrrvl .gt_column_spanner {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #A8A8A8;
  padding-top: 4px;
  padding-bottom: 4px;
}

#awdcykrrvl .gt_col_heading {
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

#awdcykrrvl .gt_sep_right {
  border-right: 5px solid #FFFFFF;
}

#awdcykrrvl .gt_group_heading {
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

#awdcykrrvl .gt_empty_group_heading {
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

#awdcykrrvl .gt_striped tr:nth-child(even) {
  background-color: #f2f2f2;
}

#awdcykrrvl .gt_row {
  padding: 10px;
  /* row.padding */
  margin: 10px;
  vertical-align: middle;
}

#awdcykrrvl .gt_stub {
  border-right-style: solid;
  border-right-width: 2px;
  border-right-color: #A8A8A8;
  padding-left: 12px;
}

#awdcykrrvl .gt_stub.gt_row {
  background-color: #FFFFFF;
}

#awdcykrrvl .gt_summary_row {
  background-color: #FFFFFF;
  /* summary_row.background.color */
  padding: 6px;
  /* summary_row.padding */
  text-transform: inherit;
  /* summary_row.text_transform */
}

#awdcykrrvl .gt_first_summary_row {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #A8A8A8;
}

#awdcykrrvl .gt_table_body {
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

#awdcykrrvl .gt_footnote {
  font-size: 90%;
  /* footnote.font.size */
  padding: 4px;
  /* footnote.padding */
}

#awdcykrrvl .gt_sourcenote {
  font-size: 90%;
  /* sourcenote.font.size */
  padding: 4px;
  /* sourcenote.padding */
}

#awdcykrrvl .gt_center {
  text-align: center;
}

#awdcykrrvl .gt_left {
  text-align: left;
}

#awdcykrrvl .gt_right {
  text-align: right;
  font-variant-numeric: tabular-nums;
}

#awdcykrrvl .gt_font_normal {
  font-weight: normal;
}

#awdcykrrvl .gt_font_bold {
  font-weight: bold;
}

#awdcykrrvl .gt_font_italic {
  font-style: italic;
}

#awdcykrrvl .gt_super {
  font-size: 65%;
}

#awdcykrrvl .gt_footnote_glyph {
  font-style: italic;
  font-size: 65%;
}
</style>

<div id="awdcykrrvl" style="overflow-x:auto;">

<!--gt table start-->

<table class="gt_table">

<thead>

<tr>

<th class="gt_heading gt_title gt_font_normal gt_center" colspan="2">

Large Landmasses of the
World

</th>

</tr>

<tr>

<th class="gt_heading gt_subtitle gt_font_normal gt_center gt_bottom_border" colspan="2">

The top ten largest are presented

</th>

</tr>

</thead>

<tr>

<th class="gt_col_heading gt_left" rowspan="1" colspan="1">

name

</th>

<th class="gt_col_heading gt_right" rowspan="1" colspan="1">

size

</th>

</tr>

<tbody class="gt_table_body gt_striped">

<tr>

<td class="gt_row gt_left">

Asia

</td>

<td class="gt_row gt_right">

16988

</td>

</tr>

<tr>

<td class="gt_row gt_left">

Africa

</td>

<td class="gt_row gt_right">

11506

</td>

</tr>

<tr>

<td class="gt_row gt_left">

North America<sup class='gt_footnote_glyph'>1</sup>

</td>

<td class="gt_row gt_right">

9390

</td>

</tr>

<tr>

<td class="gt_row gt_left">

South America<sup class='gt_footnote_glyph'>1</sup>

</td>

<td class="gt_row gt_right">

6795

</td>

</tr>

<tr>

<td class="gt_row gt_left">

Antarctica

</td>

<td class="gt_row gt_right">

5500

</td>

</tr>

<tr>

<td class="gt_row gt_left">

Europe

</td>

<td class="gt_row gt_right">

3745

</td>

</tr>

<tr>

<td class="gt_row gt_left">

Australia

</td>

<td class="gt_row gt_right">

2968

</td>

</tr>

<tr>

<td class="gt_row gt_left">

Greenland

</td>

<td class="gt_row gt_right">

840

</td>

</tr>

<tr>

<td class="gt_row gt_left">

New Guinea

</td>

<td class="gt_row gt_right">

306

</td>

</tr>

<tr>

<td class="gt_row gt_left">

Borneo

</td>

<td class="gt_row gt_right">

280

</td>

</tr>

</tbody>

<tfoot>

<tr>

<td colspan="3" class="gt_sourcenote">

Source: The World Almanac and Book of Facts, 1975, page 406.

</td>

</tr>

<tr>

<td colspan="3" class="gt_sourcenote">

Reference: McNeil, D. R. (1977) <em>Interactive Data Analysis</em>.
Wiley.

</td>

</tr>

</tfoot>

<tfoot>

<tr>

<td colspan="2" class="gt_footnote">

<sup class='gt_footnote_glyph'><em>1</em></sup> The Americas.

</td>

</tr>

</tfoot>

</table>

<!--gt table end-->

</div>

<!--/html_preserve-->

可以使用index T或者F的方式插入‘

``` r
# Determine the row that contains the
# largest landmass ('Asia')
largest <- 
  islands_tbl %>% 
  arrange(desc(size)) %>%
  slice(1) %>%
  pull(name)

# Create two additional footnotes, using the
# `columns` and `where` arguments of `data_cells()`
gt_tbl <- 
  gt_tbl %>%
  tab_footnote(
    footnote = md("The **largest** by area."),
    locations = cells_data(
      columns = vars(size),
      rows = name == largest)
  ) %>%
  tab_footnote(
    footnote = "The lowest by population.",
    locations = cells_data(
      columns = vars(size),
      rows = name == "Antarctica")
  )

# Show the gt Table
gt_tbl
```

<!--html_preserve-->

<style>html {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Helvetica Neue', 'Fira Sans', 'Droid Sans', Arial, sans-serif;
}

#qxrymhaihn .gt_table {
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

#qxrymhaihn .gt_heading {
  background-color: #FFFFFF;
  /* heading.background.color */
  border-bottom-color: #FFFFFF;
}

#qxrymhaihn .gt_title {
  color: #000000;
  font-size: 125%;
  /* heading.title.font.size */
  padding-top: 4px;
  /* heading.top.padding */
  padding-bottom: 1px;
  border-bottom-color: #FFFFFF;
  border-bottom-width: 0;
}

#qxrymhaihn .gt_subtitle {
  color: #000000;
  font-size: 85%;
  /* heading.subtitle.font.size */
  padding-top: 1px;
  padding-bottom: 4px;
  /* heading.bottom.padding */
  border-top-color: #FFFFFF;
  border-top-width: 0;
}

#qxrymhaihn .gt_bottom_border {
  border-bottom-style: solid;
  /* heading.border.bottom.style */
  border-bottom-width: 2px;
  /* heading.border.bottom.width */
  border-bottom-color: #A8A8A8;
  /* heading.border.bottom.color */
}

#qxrymhaihn .gt_column_spanner {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #A8A8A8;
  padding-top: 4px;
  padding-bottom: 4px;
}

#qxrymhaihn .gt_col_heading {
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

#qxrymhaihn .gt_sep_right {
  border-right: 5px solid #FFFFFF;
}

#qxrymhaihn .gt_group_heading {
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

#qxrymhaihn .gt_empty_group_heading {
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

#qxrymhaihn .gt_striped tr:nth-child(even) {
  background-color: #f2f2f2;
}

#qxrymhaihn .gt_row {
  padding: 10px;
  /* row.padding */
  margin: 10px;
  vertical-align: middle;
}

#qxrymhaihn .gt_stub {
  border-right-style: solid;
  border-right-width: 2px;
  border-right-color: #A8A8A8;
  padding-left: 12px;
}

#qxrymhaihn .gt_stub.gt_row {
  background-color: #FFFFFF;
}

#qxrymhaihn .gt_summary_row {
  background-color: #FFFFFF;
  /* summary_row.background.color */
  padding: 6px;
  /* summary_row.padding */
  text-transform: inherit;
  /* summary_row.text_transform */
}

#qxrymhaihn .gt_first_summary_row {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #A8A8A8;
}

#qxrymhaihn .gt_table_body {
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

#qxrymhaihn .gt_footnote {
  font-size: 90%;
  /* footnote.font.size */
  padding: 4px;
  /* footnote.padding */
}

#qxrymhaihn .gt_sourcenote {
  font-size: 90%;
  /* sourcenote.font.size */
  padding: 4px;
  /* sourcenote.padding */
}

#qxrymhaihn .gt_center {
  text-align: center;
}

#qxrymhaihn .gt_left {
  text-align: left;
}

#qxrymhaihn .gt_right {
  text-align: right;
  font-variant-numeric: tabular-nums;
}

#qxrymhaihn .gt_font_normal {
  font-weight: normal;
}

#qxrymhaihn .gt_font_bold {
  font-weight: bold;
}

#qxrymhaihn .gt_font_italic {
  font-style: italic;
}

#qxrymhaihn .gt_super {
  font-size: 65%;
}

#qxrymhaihn .gt_footnote_glyph {
  font-style: italic;
  font-size: 65%;
}
</style>

<div id="qxrymhaihn" style="overflow-x:auto;">

<!--gt table start-->

<table class="gt_table">

<thead>

<tr>

<th class="gt_heading gt_title gt_font_normal gt_center" colspan="2">

Large Landmasses of the
World

</th>

</tr>

<tr>

<th class="gt_heading gt_subtitle gt_font_normal gt_center gt_bottom_border" colspan="2">

The top ten largest are presented

</th>

</tr>

</thead>

<tr>

<th class="gt_col_heading gt_left" rowspan="1" colspan="1">

name

</th>

<th class="gt_col_heading gt_right" rowspan="1" colspan="1">

size

</th>

</tr>

<tbody class="gt_table_body gt_striped">

<tr>

<td class="gt_row gt_left">

Asia

</td>

<td class="gt_row gt_right">

16988<sup class='gt_footnote_glyph'>1</sup>

</td>

</tr>

<tr>

<td class="gt_row gt_left">

Africa

</td>

<td class="gt_row gt_right">

11506

</td>

</tr>

<tr>

<td class="gt_row gt_left">

North America<sup class='gt_footnote_glyph'>2</sup>

</td>

<td class="gt_row gt_right">

9390

</td>

</tr>

<tr>

<td class="gt_row gt_left">

South America<sup class='gt_footnote_glyph'>2</sup>

</td>

<td class="gt_row gt_right">

6795

</td>

</tr>

<tr>

<td class="gt_row gt_left">

Antarctica

</td>

<td class="gt_row gt_right">

5500<sup class='gt_footnote_glyph'>3</sup>

</td>

</tr>

<tr>

<td class="gt_row gt_left">

Europe

</td>

<td class="gt_row gt_right">

3745

</td>

</tr>

<tr>

<td class="gt_row gt_left">

Australia

</td>

<td class="gt_row gt_right">

2968

</td>

</tr>

<tr>

<td class="gt_row gt_left">

Greenland

</td>

<td class="gt_row gt_right">

840

</td>

</tr>

<tr>

<td class="gt_row gt_left">

New Guinea

</td>

<td class="gt_row gt_right">

306

</td>

</tr>

<tr>

<td class="gt_row gt_left">

Borneo

</td>

<td class="gt_row gt_right">

280

</td>

</tr>

</tbody>

<tfoot>

<tr>

<td colspan="3" class="gt_sourcenote">

Source: The World Almanac and Book of Facts, 1975, page 406.

</td>

</tr>

<tr>

<td colspan="3" class="gt_sourcenote">

Reference: McNeil, D. R. (1977) <em>Interactive Data Analysis</em>.
Wiley.

</td>

</tr>

</tfoot>

<tfoot>

<tr>

<td colspan="2" class="gt_footnote">

<sup class='gt_footnote_glyph'><em>1</em></sup> The
<strong>largest</strong> by
area.<br /><sup class='gt_footnote_glyph'><em>2</em></sup> The
Americas.<br /><sup class='gt_footnote_glyph'><em>3</em></sup> The
lowest by population.

</td>

</tr>

</tfoot>

</table>

<!--gt table end-->

</div>

<!--/html_preserve-->

``` r
# Modify the `airquality` dataset by adding the year
# of the measurements (1973) and limiting to 10 rows
airquality_m <- 
  airquality %>%
  mutate(Year = 1973L) %>%
  slice(1:10)
  
# Create a display table using the `airquality`
# dataset; arrange columns into groups
gt_tbl <- 
  gt(data = airquality_m) %>%
  tab_header(
    title = "New York Air Quality Measurements",
    subtitle = "Daily measurements in New York City (May 1-10, 1973)"
  ) %>%
  tab_spanner(
    label = "Time",
    columns = vars(Year, Month, Day)
  ) %>%
  tab_spanner(
    label = "Measurement",
    columns = vars(Ozone, Solar.R, Wind, Temp)
  )

# Show the gt Table
gt_tbl
```

<!--html_preserve-->

<style>html {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Helvetica Neue', 'Fira Sans', 'Droid Sans', Arial, sans-serif;
}

#vrutptvhlf .gt_table {
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

#vrutptvhlf .gt_heading {
  background-color: #FFFFFF;
  /* heading.background.color */
  border-bottom-color: #FFFFFF;
}

#vrutptvhlf .gt_title {
  color: #000000;
  font-size: 125%;
  /* heading.title.font.size */
  padding-top: 4px;
  /* heading.top.padding */
  padding-bottom: 1px;
  border-bottom-color: #FFFFFF;
  border-bottom-width: 0;
}

#vrutptvhlf .gt_subtitle {
  color: #000000;
  font-size: 85%;
  /* heading.subtitle.font.size */
  padding-top: 1px;
  padding-bottom: 4px;
  /* heading.bottom.padding */
  border-top-color: #FFFFFF;
  border-top-width: 0;
}

#vrutptvhlf .gt_bottom_border {
  border-bottom-style: solid;
  /* heading.border.bottom.style */
  border-bottom-width: 2px;
  /* heading.border.bottom.width */
  border-bottom-color: #A8A8A8;
  /* heading.border.bottom.color */
}

#vrutptvhlf .gt_column_spanner {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #A8A8A8;
  padding-top: 4px;
  padding-bottom: 4px;
}

#vrutptvhlf .gt_col_heading {
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

#vrutptvhlf .gt_sep_right {
  border-right: 5px solid #FFFFFF;
}

#vrutptvhlf .gt_group_heading {
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

#vrutptvhlf .gt_empty_group_heading {
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

#vrutptvhlf .gt_striped tr:nth-child(even) {
  background-color: #f2f2f2;
}

#vrutptvhlf .gt_row {
  padding: 10px;
  /* row.padding */
  margin: 10px;
  vertical-align: middle;
}

#vrutptvhlf .gt_stub {
  border-right-style: solid;
  border-right-width: 2px;
  border-right-color: #A8A8A8;
  padding-left: 12px;
}

#vrutptvhlf .gt_stub.gt_row {
  background-color: #FFFFFF;
}

#vrutptvhlf .gt_summary_row {
  background-color: #FFFFFF;
  /* summary_row.background.color */
  padding: 6px;
  /* summary_row.padding */
  text-transform: inherit;
  /* summary_row.text_transform */
}

#vrutptvhlf .gt_first_summary_row {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #A8A8A8;
}

#vrutptvhlf .gt_table_body {
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

#vrutptvhlf .gt_footnote {
  font-size: 90%;
  /* footnote.font.size */
  padding: 4px;
  /* footnote.padding */
}

#vrutptvhlf .gt_sourcenote {
  font-size: 90%;
  /* sourcenote.font.size */
  padding: 4px;
  /* sourcenote.padding */
}

#vrutptvhlf .gt_center {
  text-align: center;
}

#vrutptvhlf .gt_left {
  text-align: left;
}

#vrutptvhlf .gt_right {
  text-align: right;
  font-variant-numeric: tabular-nums;
}

#vrutptvhlf .gt_font_normal {
  font-weight: normal;
}

#vrutptvhlf .gt_font_bold {
  font-weight: bold;
}

#vrutptvhlf .gt_font_italic {
  font-style: italic;
}

#vrutptvhlf .gt_super {
  font-size: 65%;
}

#vrutptvhlf .gt_footnote_glyph {
  font-style: italic;
  font-size: 65%;
}
</style>

<div id="vrutptvhlf" style="overflow-x:auto;">

<!--gt table start-->

<table class="gt_table">

<thead>

<tr>

<th class="gt_heading gt_title gt_font_normal gt_center" colspan="7">

New York Air Quality
Measurements

</th>

</tr>

<tr>

<th class="gt_heading gt_subtitle gt_font_normal gt_center gt_bottom_border" colspan="7">

Daily measurements in New York City (May 1-10,
1973)

</th>

</tr>

</thead>

<tr>

<th class="gt_col_heading gt_column_spanner gt_sep_right gt_center" rowspan="1" colspan="4">

Measurement

</th>

<th class="gt_col_heading gt_column_spanner gt_center" rowspan="1" colspan="3">

Time

</th>

</tr>

<tr>

<th class="gt_col_heading gt_right" rowspan="1" colspan="1">

Ozone

</th>

<th class="gt_col_heading gt_right" rowspan="1" colspan="1">

Solar.R

</th>

<th class="gt_col_heading gt_right" rowspan="1" colspan="1">

Wind

</th>

<th class="gt_col_heading gt_right" rowspan="1" colspan="1">

Temp

</th>

<th class="gt_col_heading gt_right" rowspan="1" colspan="1">

Month

</th>

<th class="gt_col_heading gt_right" rowspan="1" colspan="1">

Day

</th>

<th class="gt_col_heading gt_NA" rowspan="1" colspan="1">

Year

</th>

</tr>

<tbody class="gt_table_body gt_striped">

<tr>

<td class="gt_row gt_right">

41

</td>

<td class="gt_row gt_right">

190

</td>

<td class="gt_row gt_right">

7.4

</td>

<td class="gt_row gt_right">

67

</td>

<td class="gt_row gt_right">

5

</td>

<td class="gt_row gt_right">

1

</td>

<td class="gt_row gt_right">

1973

</td>

</tr>

<tr>

<td class="gt_row gt_right">

36

</td>

<td class="gt_row gt_right">

118

</td>

<td class="gt_row gt_right">

8.0

</td>

<td class="gt_row gt_right">

72

</td>

<td class="gt_row gt_right">

5

</td>

<td class="gt_row gt_right">

2

</td>

<td class="gt_row gt_right">

1973

</td>

</tr>

<tr>

<td class="gt_row gt_right">

12

</td>

<td class="gt_row gt_right">

149

</td>

<td class="gt_row gt_right">

12.6

</td>

<td class="gt_row gt_right">

74

</td>

<td class="gt_row gt_right">

5

</td>

<td class="gt_row gt_right">

3

</td>

<td class="gt_row gt_right">

1973

</td>

</tr>

<tr>

<td class="gt_row gt_right">

18

</td>

<td class="gt_row gt_right">

313

</td>

<td class="gt_row gt_right">

11.5

</td>

<td class="gt_row gt_right">

62

</td>

<td class="gt_row gt_right">

5

</td>

<td class="gt_row gt_right">

4

</td>

<td class="gt_row gt_right">

1973

</td>

</tr>

<tr>

<td class="gt_row gt_right">

NA

</td>

<td class="gt_row gt_right">

NA

</td>

<td class="gt_row gt_right">

14.3

</td>

<td class="gt_row gt_right">

56

</td>

<td class="gt_row gt_right">

5

</td>

<td class="gt_row gt_right">

5

</td>

<td class="gt_row gt_right">

1973

</td>

</tr>

<tr>

<td class="gt_row gt_right">

28

</td>

<td class="gt_row gt_right">

NA

</td>

<td class="gt_row gt_right">

14.9

</td>

<td class="gt_row gt_right">

66

</td>

<td class="gt_row gt_right">

5

</td>

<td class="gt_row gt_right">

6

</td>

<td class="gt_row gt_right">

1973

</td>

</tr>

<tr>

<td class="gt_row gt_right">

23

</td>

<td class="gt_row gt_right">

299

</td>

<td class="gt_row gt_right">

8.6

</td>

<td class="gt_row gt_right">

65

</td>

<td class="gt_row gt_right">

5

</td>

<td class="gt_row gt_right">

7

</td>

<td class="gt_row gt_right">

1973

</td>

</tr>

<tr>

<td class="gt_row gt_right">

19

</td>

<td class="gt_row gt_right">

99

</td>

<td class="gt_row gt_right">

13.8

</td>

<td class="gt_row gt_right">

59

</td>

<td class="gt_row gt_right">

5

</td>

<td class="gt_row gt_right">

8

</td>

<td class="gt_row gt_right">

1973

</td>

</tr>

<tr>

<td class="gt_row gt_right">

8

</td>

<td class="gt_row gt_right">

19

</td>

<td class="gt_row gt_right">

20.1

</td>

<td class="gt_row gt_right">

61

</td>

<td class="gt_row gt_right">

5

</td>

<td class="gt_row gt_right">

9

</td>

<td class="gt_row gt_right">

1973

</td>

</tr>

<tr>

<td class="gt_row gt_right">

NA

</td>

<td class="gt_row gt_right">

194

</td>

<td class="gt_row gt_right">

8.6

</td>

<td class="gt_row gt_right">

69

</td>

<td class="gt_row gt_right">

5

</td>

<td class="gt_row gt_right">

10

</td>

<td class="gt_row gt_right">

1973

</td>

</tr>

</tbody>

</table>

<!--gt table end-->

</div>

<!--/html_preserve-->

``` r
# Move the time-based columns to the start of
# the column series; modify the column labels of
# the measurement-based columns
gt_tbl <- 
  gt_tbl %>%
  cols_move_to_start(
    columns = vars(Year, Month, Day)
  ) %>%
  cols_label(
    Ozone = html("Ozone,<br>ppbV"),
    Solar.R = html("Solar R.,<br>cal/m<sup>2</sup>"),
    Wind = html("Wind,<br>mph"),
    Temp = html("Temp,<br>&deg;F")
  )

# Show the gt Table
gt_tbl
```

<!--html_preserve-->

<style>html {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Helvetica Neue', 'Fira Sans', 'Droid Sans', Arial, sans-serif;
}

#whetdzjdgz .gt_table {
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

#whetdzjdgz .gt_heading {
  background-color: #FFFFFF;
  /* heading.background.color */
  border-bottom-color: #FFFFFF;
}

#whetdzjdgz .gt_title {
  color: #000000;
  font-size: 125%;
  /* heading.title.font.size */
  padding-top: 4px;
  /* heading.top.padding */
  padding-bottom: 1px;
  border-bottom-color: #FFFFFF;
  border-bottom-width: 0;
}

#whetdzjdgz .gt_subtitle {
  color: #000000;
  font-size: 85%;
  /* heading.subtitle.font.size */
  padding-top: 1px;
  padding-bottom: 4px;
  /* heading.bottom.padding */
  border-top-color: #FFFFFF;
  border-top-width: 0;
}

#whetdzjdgz .gt_bottom_border {
  border-bottom-style: solid;
  /* heading.border.bottom.style */
  border-bottom-width: 2px;
  /* heading.border.bottom.width */
  border-bottom-color: #A8A8A8;
  /* heading.border.bottom.color */
}

#whetdzjdgz .gt_column_spanner {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #A8A8A8;
  padding-top: 4px;
  padding-bottom: 4px;
}

#whetdzjdgz .gt_col_heading {
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

#whetdzjdgz .gt_sep_right {
  border-right: 5px solid #FFFFFF;
}

#whetdzjdgz .gt_group_heading {
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

#whetdzjdgz .gt_empty_group_heading {
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

#whetdzjdgz .gt_striped tr:nth-child(even) {
  background-color: #f2f2f2;
}

#whetdzjdgz .gt_row {
  padding: 10px;
  /* row.padding */
  margin: 10px;
  vertical-align: middle;
}

#whetdzjdgz .gt_stub {
  border-right-style: solid;
  border-right-width: 2px;
  border-right-color: #A8A8A8;
  padding-left: 12px;
}

#whetdzjdgz .gt_stub.gt_row {
  background-color: #FFFFFF;
}

#whetdzjdgz .gt_summary_row {
  background-color: #FFFFFF;
  /* summary_row.background.color */
  padding: 6px;
  /* summary_row.padding */
  text-transform: inherit;
  /* summary_row.text_transform */
}

#whetdzjdgz .gt_first_summary_row {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #A8A8A8;
}

#whetdzjdgz .gt_table_body {
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

#whetdzjdgz .gt_footnote {
  font-size: 90%;
  /* footnote.font.size */
  padding: 4px;
  /* footnote.padding */
}

#whetdzjdgz .gt_sourcenote {
  font-size: 90%;
  /* sourcenote.font.size */
  padding: 4px;
  /* sourcenote.padding */
}

#whetdzjdgz .gt_center {
  text-align: center;
}

#whetdzjdgz .gt_left {
  text-align: left;
}

#whetdzjdgz .gt_right {
  text-align: right;
  font-variant-numeric: tabular-nums;
}

#whetdzjdgz .gt_font_normal {
  font-weight: normal;
}

#whetdzjdgz .gt_font_bold {
  font-weight: bold;
}

#whetdzjdgz .gt_font_italic {
  font-style: italic;
}

#whetdzjdgz .gt_super {
  font-size: 65%;
}

#whetdzjdgz .gt_footnote_glyph {
  font-style: italic;
  font-size: 65%;
}
</style>

<div id="whetdzjdgz" style="overflow-x:auto;">

<!--gt table start-->

<table class="gt_table">

<thead>

<tr>

<th class="gt_heading gt_title gt_font_normal gt_center" colspan="7">

New York Air Quality
Measurements

</th>

</tr>

<tr>

<th class="gt_heading gt_subtitle gt_font_normal gt_center gt_bottom_border" colspan="7">

Daily measurements in New York City (May 1-10,
1973)

</th>

</tr>

</thead>

<tr>

<th class="gt_col_heading gt_column_spanner gt_sep_right gt_center" rowspan="1" colspan="3">

Time

</th>

<th class="gt_col_heading gt_column_spanner gt_center" rowspan="1" colspan="4">

Measurement

</th>

</tr>

<tr>

<th class="gt_col_heading gt_right" rowspan="1" colspan="1">

Year

</th>

<th class="gt_col_heading gt_right" rowspan="1" colspan="1">

Month

</th>

<th class="gt_col_heading gt_right" rowspan="1" colspan="1">

Day

</th>

<th class="gt_col_heading gt_right" rowspan="1" colspan="1">

Ozone,<br>ppbV

</th>

<th class="gt_col_heading gt_right" rowspan="1" colspan="1">

Solar R.,<br>cal/m<sup>2</sup>

</th>

<th class="gt_col_heading gt_right" rowspan="1" colspan="1">

Wind,<br>mph

</th>

<th class="gt_col_heading gt_NA" rowspan="1" colspan="1">

Temp,<br>°F

</th>

</tr>

<tbody class="gt_table_body gt_striped">

<tr>

<td class="gt_row gt_right">

1973

</td>

<td class="gt_row gt_right">

5

</td>

<td class="gt_row gt_right">

1

</td>

<td class="gt_row gt_right">

41

</td>

<td class="gt_row gt_right">

190

</td>

<td class="gt_row gt_right">

7.4

</td>

<td class="gt_row gt_right">

67

</td>

</tr>

<tr>

<td class="gt_row gt_right">

1973

</td>

<td class="gt_row gt_right">

5

</td>

<td class="gt_row gt_right">

2

</td>

<td class="gt_row gt_right">

36

</td>

<td class="gt_row gt_right">

118

</td>

<td class="gt_row gt_right">

8.0

</td>

<td class="gt_row gt_right">

72

</td>

</tr>

<tr>

<td class="gt_row gt_right">

1973

</td>

<td class="gt_row gt_right">

5

</td>

<td class="gt_row gt_right">

3

</td>

<td class="gt_row gt_right">

12

</td>

<td class="gt_row gt_right">

149

</td>

<td class="gt_row gt_right">

12.6

</td>

<td class="gt_row gt_right">

74

</td>

</tr>

<tr>

<td class="gt_row gt_right">

1973

</td>

<td class="gt_row gt_right">

5

</td>

<td class="gt_row gt_right">

4

</td>

<td class="gt_row gt_right">

18

</td>

<td class="gt_row gt_right">

313

</td>

<td class="gt_row gt_right">

11.5

</td>

<td class="gt_row gt_right">

62

</td>

</tr>

<tr>

<td class="gt_row gt_right">

1973

</td>

<td class="gt_row gt_right">

5

</td>

<td class="gt_row gt_right">

5

</td>

<td class="gt_row gt_right">

NA

</td>

<td class="gt_row gt_right">

NA

</td>

<td class="gt_row gt_right">

14.3

</td>

<td class="gt_row gt_right">

56

</td>

</tr>

<tr>

<td class="gt_row gt_right">

1973

</td>

<td class="gt_row gt_right">

5

</td>

<td class="gt_row gt_right">

6

</td>

<td class="gt_row gt_right">

28

</td>

<td class="gt_row gt_right">

NA

</td>

<td class="gt_row gt_right">

14.9

</td>

<td class="gt_row gt_right">

66

</td>

</tr>

<tr>

<td class="gt_row gt_right">

1973

</td>

<td class="gt_row gt_right">

5

</td>

<td class="gt_row gt_right">

7

</td>

<td class="gt_row gt_right">

23

</td>

<td class="gt_row gt_right">

299

</td>

<td class="gt_row gt_right">

8.6

</td>

<td class="gt_row gt_right">

65

</td>

</tr>

<tr>

<td class="gt_row gt_right">

1973

</td>

<td class="gt_row gt_right">

5

</td>

<td class="gt_row gt_right">

8

</td>

<td class="gt_row gt_right">

19

</td>

<td class="gt_row gt_right">

99

</td>

<td class="gt_row gt_right">

13.8

</td>

<td class="gt_row gt_right">

59

</td>

</tr>

<tr>

<td class="gt_row gt_right">

1973

</td>

<td class="gt_row gt_right">

5

</td>

<td class="gt_row gt_right">

9

</td>

<td class="gt_row gt_right">

8

</td>

<td class="gt_row gt_right">

19

</td>

<td class="gt_row gt_right">

20.1

</td>

<td class="gt_row gt_right">

61

</td>

</tr>

<tr>

<td class="gt_row gt_right">

1973

</td>

<td class="gt_row gt_right">

5

</td>

<td class="gt_row gt_right">

10

</td>

<td class="gt_row gt_right">

NA

</td>

<td class="gt_row gt_right">

194

</td>

<td class="gt_row gt_right">

8.6

</td>

<td class="gt_row gt_right">

69

</td>

</tr>

</tbody>

</table>

<!--gt table end-->

</div>

<!--/html_preserve-->

<input type="checkbox" id="checkbox1" class="styled">`&deg`正如`&copy`是
html 的展示方式，非latex可以学习一下

这里很好的完成了变量命名的换行功能。
