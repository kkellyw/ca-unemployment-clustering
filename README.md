## **California Unemployment: Urban vs. Rural County Clustering**

### Context:

The dataset contains employment and unemployment statistics on California
from the years 1990–2024. I'm passionate about economics since I think it
can give a lot of valuable insights into how society is performing and
what actions we must take based on that. With unemployment and employment
economics specifically, being able to analyze these numbers can tell us
what further steps we must take to allocate resources efficiently to solve
the issues we're seeing. For example, if we're seeing high unemployment
rates, the government can aim to provide workforce development programs
to provide education and training to help citizens find jobs. Combining
data science and economics can further expand these insights and help
even further with fixing the main issues society is facing.

I chose this specific dataset since I was born and raised in California
and have seen the differences in education, housing, poverty, and overall
quality of life between counties in California, despite the overall image
of California being a rich and glamorized state. I think analyzing
unemployment rates can tell us a lot about the economic health and issues
each county is facing, to try to help the counties that aren't as
fortunate as others utilize California's resources.

I found this dataset on data.gov by navigating to the
state of California and typing "unemployment" as a keyword, which led to
the California Employment Development Department's Labor Force and
Unemployment Rate for California Counties
dataset.

In this dataset, I wanted to look at which counties consistently
experience high unemployment, and whether there's a gap between rural and
urban counties in unemployment rates.

### Key Terms:

**Labor force**: the total number of citizens who are either employed
or unemployed but actively looking for work
**Employment**: the proportion of citizens aged 16+ who are employed
**Unemployment**: citizens 16+ who did not work when the data was
compiled but made noticeable efforts to find a job within the past four
weeks and were able to work
**Unemployment Rate**: the number unemployed as a percent of the labor
force


### Exploratory Analysis:

**Measures of Center:** the mean labor force is about 123,095, but the
median is much lower at about 7,175 which means the dataset contains areas
with very large labor forces (larger urban populations) that pull the
mean up, while most areas are much smaller. Mean unemployment rate is
around 8.38% vs. a median of 6.7%, telling us some areas regularly
experience above-average unemployment.

**Measures of Spread:** labor force ranges from 0 to 19,644,100 — a wide
range reflecting extremely small rural populations versus large city
areas. Unemployment rate ranges from 0% to 100%; the 0% likely reflects
very small counties/populations with few people employed by small or
family-owned businesses, while 100% likely reflects small rural areas
with no job opportunities.

**By area:** grouping by county, the highest unemployment rates showed up
in places like Clio, Prattville, and Keeler which are all very low-population
areas, which makes sense. The highest employment numbers showed up in
places like Los Angeles County, Orange County, and Alameda County — well
populated, well-off areas.

**By year:** employment increased steadily over the years overall, but
some years had noticeably higher unemployment, tied to economic or
societal events. Unemployment was highest during years like 2020 (COVID)
or recession years, and lowest during years of economic stability.

### The Question:

**Is there a clear difference and gap between urban and rural counties in
California concerning unemployment rates?**

### Method: K-means clustering

To answer this, I used K-means clustering to see if counties would
naturally group into two clusters based on unemployment rate; the idea
being that one cluster would end up being mostly rural counties and the
other mostly urban. I trained the model with 2 clusters, fit on
Unemployment Rate, Employment, and Unemployment (using each county's mean
values from 2007–2024), then compared the resulting clusters against an
actual list of California urban vs. rural counties I compiled from
external research and California databases, to see how accurate the
clustering really was.

### Results:

The clusters grouped themselves into pretty explainable groups: **Cluster
0** had lower unemployment rates, all under 10%, which I attributed to
urban counties. **Cluster 1** had much higher unemployment rates, ranging
from the high teens to 22%, which I attributed to rural counties. The
visualization (bar plot, Cluster 0 in purple and Cluster 1 in gold)
confirmed this. Lower unemployment rates clustered together, and higher
rates clustered together.

This makes sense given that some California counties are more on the
urban side but don't get as many resources or as much help as larger
counties, resulting in higher unemployment rates despite being urban
unlike flourishing counties such as Alameda or Los Angeles County.

### Conclusion:

My use of K-means clustering showed there is a slight gap between urban
and rural counties' unemployment rates, but resources and the help
certain counties get play an even bigger role than just the labels
"urban" and "rural."

### Ideas for Continuing this Project:

Look further into persistently high-unemployment regions; is it driven
by labor force size and rural location, or a lack of resources/support?
Look into how unemployment responds to events like recessions or
COVID-19, and how quickly (and unevenly) different counties recover
Refine the urban/rural ground-truth list, since it was compiled from
external research rather than one official source
