# Billboard and Data Dictionary

For this project, the data of interest was retrieved from two sources: [Billboard](https://www.billboard.com/charts/) 
and [Kworb.net](https://kworb.net). 

The primary data source of interest in the [Billboard](https://www.billboard.com/charts/) website relates to the **Global Hot 200 Chart** 
which specifies the top ranking songs worldwide for a given week spanning from Friday to Thursday for any given week 
([Billboard Legend](https://www.billboard.com/billboard-charts-legend/)).The ranking of these songs is determined by a 
myriad of factors including: streaming, sales, airplay, etc. For the purpose of this project, we are primarily interested
in exploring the performance or impact of the *Global Hot 200* songs at the individual country level. Given the limited 
scope of streaming data available, this will be done by considering two distinct data sources and ranking perspectives.

First, from the Billboard website we retrieve the individual Hot 100 charts for available countries. With this information,
we are able to explore whether *Global Hot 200 Chart* songs are themselves charting in an individual country. There are two big
limitations from this perspective. Specifically, the individual Hot 100 charts only provide 25 publicly available and english translated
records. The remaining song entries from the charts can be found in the distinct Billboard pages hosted by an individual 
country, many of which contain entries in non-english (not romanized) languages. As such, to standardize the analysis from 
the Billboards Charts perspective, we restrict to analyzing if songs from the *Global Hot 200 Chart* are ranking in the top
25 slots of the Hot 100 Billboard charts for distinct countries. 

Second, a big driver for Billboard chart rankings lies in the streaming of a song. As such, we consider two different 
streaming platforms, Spotify and Apple Music, and consider the performance of these songs on both of these platforms. 
From [Kworb.net](https://kworb.net), we are able to retreive the charts and streaming figures for songs in individual 
countries on the Spotify platform. This provides a valuable perspective as to the magnitude of a song's streaming 
distribution worldwide. However, it is important to recognize that even though Spotify currently holds 751 million users, 
the proportion of users is not equally balanced worldwide ([About Spotify](https://newsroom.spotify.com/company-info/))
nor accross demographics. As such, we aim to provide an additional perspective on streaming by including the Apple Music
top song charts for individual countries. These charts do not provide specific individual streaming figures, but the charts
do provide an indication of the most streamed songs on the Apple Music platform for an individual country. 

We recognize there are important factors that this exploratory analysis does not consider, including sales and airplay.
However, given the age of digital media and streaming, understanding the digital influence of a song and its distribution
worldwide can provide an important indicator to artists and music companies as to their primary target audiences. Below,
we provide a summary of the available datasets, corresponding variables, and additional data insights when necessary.

## Database
All the available tables can be retrieved from the data.db file. This file contains a total of 7 tables with over 65,321 observations.
Individual data table can be found below.

### BillboardCharts

Total Observations: 1650

Columns: 9

1. **artist**: The artist(s) name(s) associated with a Billboard charting song.
2. **song_name**: The name of the Billboard charting song.
3. **rank**: The week ranking for the Billboard charting song. 
4. **artist_link**: The link(s) associated with the artist(s).
5. **last_week_rank**: The previous week ranking for the Billboard charting song.
6. **peak**: The maximum position attained by the Billboard charting song across all charting weeks.
7. **weeks_chart**: The total number of weeks a song has been in the Billboard chart.
8. **week**: The week the Billboard chart was released.
9. **chart**: The name of the Billboard chart. 

### IndividualArtistMentions

Total Observations: 912

Columns:3

1. **artist**: The individual name for every artist that is mentioned in the Billboard charts.
2. **count**: The total number of times an individual artist can be found in the Billboard charts (across varying songs).
3. **week**: The Billboard week for which the charts and count was produced.


### SongArtistMentions

Total Observations: 701

Columns: 3

1. **artist**: The artist(s) name(s) associated with a Billboard charting song.
2. **count**: The total number of times the artist(s) associated with a Billboard charting song can be found.
3. **week**: The Billboard week for which the charts and count was produced.

### SongArtistChartAppearances

Total Observations: 701

Columns: 3

1. **artist**: The artist(s) name(s) associated with a Billboard charting song.
2. **count**: The total number of charts that the artist(s) associated with a Billboard charting song can be found in.
3. **week**: The Billboard week for which the charts and count was produced.

### SpotifyDailyStreamingCharts

Total Observations: 14699

Columns: 12

1. **rank**: The daily ranking for the Spotify charting song.
2. **artist**: The artist(s) name(s) associated with a Spotify charting song.
3. **song_name**: The name of the Spotify charting song.
4. **Days**: The total number of days the song has been on the Spotify charting song.
5. **peak**: The maximum position attained by the Spotify charting song across all charting days.
6. **Streams**: The total number of daily streams on Spotify for that individual chart.
7. **Streams+**: The total number of daily streams gained compared to the previous day.
8. **7Day**: The total number of streams across a seven-day period on Spotify.
9. **7Day+**: The total number of streams gained compared to the previous seven-day interval.
10. **Total**: The total number of streams on the Spotify platform for that chart.
11. **country**: The name of the country for the Spotify Music chart.
12. **chart_name**: The Spotify chart for where the song can be found.
13. **date**: The date when the Spotify daily streams was retrieved. 

**Note: The streams are chart dependent. If the Spotify chart focuses on a specific country, then streams will be for 
that specific country.**

### SpotifyWeeklyStreamingCharts

Total Observations: 15258

Columns: 10

1. **rank**: The weekly ranking for the Spotify charting song.
2. **artist**: The artist(s) name(s) associated with a Spotify charting song.
3. **song_name**: The name of the Spotify charting song.
4. **peak**: The maximum position attained by the Spotify charting song across all charting weeks.
5. **weeks**: The total number of weeks the song has been on the Spotify charting song.
6. **Streams**: The total number of weekly streams on Spotify for that individual chart.
7. **Streams+**: The total number of weekly streams gained compared to the previous week.
8. **Total**: The total number of streams on the Spotify platform for that chart.
9. **country**: The name of the country for the Spotify Music chart.
10. **chart_name**: The Spotify chart for where the song can be found.
11. **date**: The week when the Spotify weekly streams was retrieved. 

**Note: The streams are chart dependent. If the Spotify chart focuses on a specific country, then streams will be for 
that specific country.**

### AppleChartRankings

Total Observations: 31400

Columns: 5

1. **rank**: The daily ranking for the Apple Music charting song.
2. **artist**: The artist(s) name(s) associated with an Apple Music charting song.
3. **song_name**: The name of the Apple Music charting song.
4. **country**: The name of the country for the Apple Music chart.
5. **chart_name**: The Apple Music chart for where the song can be found.
6. **date**: The week when the Spotify weekly streams was retrieved.

**Note: The streams are chart dependent. If the Spotify chart focuses on a specific country, then streams will be for 
that specific country.**