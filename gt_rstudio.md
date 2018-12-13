R Notebook
================

<https://gt.rstudio.com/>

完成第一个例子

1.  增加 (sub)title
2.  日期、货币、数字表示

<!-- end list -->

``` r
library(gt)
library(tidyverse)
library(glue)

# Define the start and end dates for the data range
start_date <- "2010-06-07"
end_date <- "2010-06-14"

# Create a gt table based on preprocessed
# `sp500` table data
sp500 %>%
  dplyr::filter(date >= start_date & date <= end_date) %>%
  dplyr::select(-adj_close) %>%
  dplyr::mutate(date = as.character(date)) %>%
  gt() %>%
  # 是 DT 的改版
  tab_header(
    title = "S&P 500",
    subtitle = glue::glue("{start_date} to {end_date}")
  ) %>%
  # subtitle 可以使用变量引用很好
  fmt_date(
    columns = vars(date),
    date_style = 1
  ) %>%
  # date_style 见 Details
  # 偏好1
  fmt_currency(
    columns = vars(open, high, low, close),
    currency = "CNY"
  ) %>%
  # 可以指定货币
  fmt_number(
    columns = vars(volume),
    scale_by = 1 / 1E9,
    pattern = "{x}B"
  )
```

<!--html_preserve-->

<style>html {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Helvetica Neue', 'Fira Sans', 'Droid Sans', Arial, sans-serif;
}

#mwsewceimh .gt_table {
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

#mwsewceimh .gt_heading {
  background-color: #FFFFFF;
  /* heading.background.color */
  border-bottom-color: #FFFFFF;
}

#mwsewceimh .gt_title {
  color: #000000;
  font-size: 125%;
  /* heading.title.font.size */
  padding-top: 4px;
  /* heading.top.padding */
  padding-bottom: 1px;
  border-bottom-color: #FFFFFF;
  border-bottom-width: 0;
}

#mwsewceimh .gt_subtitle {
  color: #000000;
  font-size: 85%;
  /* heading.subtitle.font.size */
  padding-top: 1px;
  padding-bottom: 4px;
  /* heading.bottom.padding */
  border-top-color: #FFFFFF;
  border-top-width: 0;
}

#mwsewceimh .gt_bottom_border {
  border-bottom-style: solid;
  /* heading.border.bottom.style */
  border-bottom-width: 2px;
  /* heading.border.bottom.width */
  border-bottom-color: #A8A8A8;
  /* heading.border.bottom.color */
}

#mwsewceimh .gt_column_spanner {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #A8A8A8;
  padding-top: 4px;
  padding-bottom: 4px;
}

#mwsewceimh .gt_col_heading {
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

#mwsewceimh .gt_sep_right {
  border-right: 5px solid #FFFFFF;
}

#mwsewceimh .gt_group_heading {
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

#mwsewceimh .gt_empty_group_heading {
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

#mwsewceimh .gt_striped tr:nth-child(even) {
  background-color: #f2f2f2;
}

#mwsewceimh .gt_row {
  padding: 10px;
  /* row.padding */
  margin: 10px;
  vertical-align: middle;
}

#mwsewceimh .gt_stub {
  border-right-style: solid;
  border-right-width: 2px;
  border-right-color: #A8A8A8;
  padding-left: 12px;
}

#mwsewceimh .gt_stub.gt_row {
  background-color: #FFFFFF;
}

#mwsewceimh .gt_summary_row {
  background-color: #FFFFFF;
  /* summary_row.background.color */
  padding: 6px;
  /* summary_row.padding */
  text-transform: inherit;
  /* summary_row.text_transform */
}

#mwsewceimh .gt_first_summary_row {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #A8A8A8;
}

#mwsewceimh .gt_table_body {
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

#mwsewceimh .gt_footnote {
  font-size: 90%;
  /* footnote.font.size */
  padding: 4px;
  /* footnote.padding */
}

#mwsewceimh .gt_sourcenote {
  font-size: 90%;
  /* sourcenote.font.size */
  padding: 4px;
  /* sourcenote.padding */
}

#mwsewceimh .gt_center {
  text-align: center;
}

#mwsewceimh .gt_left {
  text-align: left;
}

#mwsewceimh .gt_right {
  text-align: right;
  font-variant-numeric: tabular-nums;
}

#mwsewceimh .gt_font_normal {
  font-weight: normal;
}

#mwsewceimh .gt_font_bold {
  font-weight: bold;
}

#mwsewceimh .gt_font_italic {
  font-style: italic;
}

#mwsewceimh .gt_super {
  font-size: 65%;
}

#mwsewceimh .gt_footnote_glyph {
  font-style: italic;
  font-size: 65%;
}
</style>

<div id="mwsewceimh" style="overflow-x:auto;">

<!--gt table start-->

<table class="gt_table">

<thead>

<tr>

<th class="gt_heading gt_title gt_font_normal gt_center" colspan="6">

S\&P
500

</th>

</tr>

<tr>

<th class="gt_heading gt_subtitle gt_font_normal gt_center gt_bottom_border" colspan="6">

2010-06-07 to 2010-06-14

</th>

</tr>

</thead>

<tr>

<th class="gt_col_heading gt_left" rowspan="1" colspan="1">

date

</th>

<th class="gt_col_heading gt_right" rowspan="1" colspan="1">

open

</th>

<th class="gt_col_heading gt_right" rowspan="1" colspan="1">

high

</th>

<th class="gt_col_heading gt_right" rowspan="1" colspan="1">

low

</th>

<th class="gt_col_heading gt_right" rowspan="1" colspan="1">

close

</th>

<th class="gt_col_heading gt_right" rowspan="1" colspan="1">

volume

</th>

</tr>

<tbody class="gt_table_body gt_striped">

<tr>

<td class="gt_row gt_left">

2010-06-14

</td>

<td class="gt_row gt_right">

¥1,095.00

</td>

<td class="gt_row gt_right">

¥1,105.91

</td>

<td class="gt_row gt_right">

¥1,089.03

</td>

<td class="gt_row gt_right">

¥1,089.63

</td>

<td class="gt_row gt_right">

4.43B

</td>

</tr>

<tr>

<td class="gt_row gt_left">

2010-06-11

</td>

<td class="gt_row gt_right">

¥1,082.65

</td>

<td class="gt_row gt_right">

¥1,092.25

</td>

<td class="gt_row gt_right">

¥1,077.12

</td>

<td class="gt_row gt_right">

¥1,091.60

</td>

<td class="gt_row gt_right">

4.06B

</td>

</tr>

<tr>

<td class="gt_row gt_left">

2010-06-10

</td>

<td class="gt_row gt_right">

¥1,058.77

</td>

<td class="gt_row gt_right">

¥1,087.85

</td>

<td class="gt_row gt_right">

¥1,058.77

</td>

<td class="gt_row gt_right">

¥1,086.84

</td>

<td class="gt_row gt_right">

5.14B

</td>

</tr>

<tr>

<td class="gt_row gt_left">

2010-06-09

</td>

<td class="gt_row gt_right">

¥1,062.75

</td>

<td class="gt_row gt_right">

¥1,077.74

</td>

<td class="gt_row gt_right">

¥1,052.25

</td>

<td class="gt_row gt_right">

¥1,055.69

</td>

<td class="gt_row gt_right">

5.98B

</td>

</tr>

<tr>

<td class="gt_row gt_left">

2010-06-08

</td>

<td class="gt_row gt_right">

¥1,050.81

</td>

<td class="gt_row gt_right">

¥1,063.15

</td>

<td class="gt_row gt_right">

¥1,042.17

</td>

<td class="gt_row gt_right">

¥1,062.00

</td>

<td class="gt_row gt_right">

6.19B

</td>

</tr>

<tr>

<td class="gt_row gt_left">

2010-06-07

</td>

<td class="gt_row gt_right">

¥1,065.84

</td>

<td class="gt_row gt_right">

¥1,071.36

</td>

<td class="gt_row gt_right">

¥1,049.86

</td>

<td class="gt_row gt_right">

¥1,050.47

</td>

<td class="gt_row gt_right">

5.47B

</td>

</tr>

</tbody>

</table>

<!--gt table end-->

</div>

<!--/html_preserve-->

``` r
  # 1E9除以10的9次方，因此是billion
```
