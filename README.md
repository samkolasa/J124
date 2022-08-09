# Arts Education in LA County
Data Sources:
Data is compiled by districts in LA County and include information for all levels of elementary and secondary schools.
* Number of Classes by Subject by District: downloaded from the [California Department of Education Data Reporting Office](https://dq.cde.ca.gov/dataquest/CourseReports/ClassesbySubject.aspx?Filter=A&TheYear=2018-19&cTopic=Course&cChoice=CoNumClas1&cLevel=County&cdscode=19000000000000&AP=&IB=), filtered for only districts in LA County and all courses. 
* Course Enrollment by Subject by County: downloaded from the [California Department of Education Data Reporting Office](https://dq.cde.ca.gov/dataquest/CourseReports/CourseResults.aspx?Filter=A&TheYear=2018-19&cTopic=Course&cChoice=CrseEnroll&cLevel=County&cdscode=19000000000000&Subject=Y&AP=Y&IB=Y&CTE=Y&lNotAll=True), filtered by all assignments by subject area and the "Arts, Media, and Entertainment" teaching assingment by career technical education.
* Map of LA County School Districts from the County of [Los Angeles Enterprise Geographic Information Systems](https://egis-lacounty.hub.arcgis.com/datasets/lacounty::school-district-boundaries-2/explore?location=34.220143%2C-117.957018%2C8.05)
* 2018-19 Enrollment by Ethnicity for LA County from the [California Department of Education Data Reporting Office](https://dq.cde.ca.gov/dataquest/dqcensus/EnrEthLevels.aspx?cds=19&agglevel=county&year=2018-19)
* 2018-2019 Percent Free and Reduced Priced Meals 2018-2019 for LA County Districts from the [California Department of Education Data Reporting Office](https://dq.cde.ca.gov/dataquest/Cbeds2.asp?FreeLunch=on&cChoice=CoProf2&cYear=2018-19&TheCounty=19%2CLOS%5EANGELES&cLevel=County&cTopic=FRPM&myTimeFrame=S&submit1=Submit)
 

Leading Questions:
* Is there a trend in growth based on location? Student demographics?
* How do class sizes compare to other subjects? How do class sizes per class differ between schools and demographics?

## Part I: How many art classes are offered per school for LA County? How does that compare to other course subjects?
#### Question 1:
The [Number of Classes by Subject 2018-2019](https://dq.cde.ca.gov/dataquest/CourseReports/ClassesbySubject.aspx?Filter=A&TheYear=2018-19&cTopic=Course&cChoice=CoNumClas1&cLevel=County&cdscode=19000000000000&AP=&IB=) datasheet has records for the number of schools and the number of courses offered for nine main subjects of classes, as well as total numbers for all of LA County. I wanted to find the average classes offered per school so that I could look at the emphasis of arts courses in education without being biased towards districts with more schools. This way if a district with only a couple schools is not inherently at a disadvantage compared to larger districts. However, it will highlight any districts with arts-heavy schools or no arts offered at all. For each subject I created an equation dividing the number of courses by the number of schools. To start, I found the average for LA County by isolating the total value and moved it to a new sheet to sort by least to greatest courses per school.

![A chart showing the average number classes per school for nine subjects. In increasing order: Fine Arts, Physical Education, Foreign Language, Self-contained, Other, Science, History/Social Science, Mathematics, and English Language Arts](https://user-images.githubusercontent.com/85646498/183397674-e117ff32-1a09-4184-a37b-624c8f864b89.png)

The Fine Arts subject had the fewest average courses per school. However, the comparison was largely against core subjects like English, Math, and Science which would be expected to have more courses that arts courses which are usually electives especially in higher education. 

#### Question 2:
To get a broader understanding of where art fell when compared to a wider range of course subjects, I looked at the [Course Enrollment Listing 2018-19 for LA County](https://dq.cde.ca.gov/dataquest/CourseReports/CourseResults.aspx?Filter=A&TheYear=2018-19&cTopic=Course&cChoice=CrseEnroll&cLevel=County&cdscode=19000000000000&Subject=Y&AP=Y&IB=Y&CTE=Y&lNotAll=True) from the California Department of Education. "Fine Arts" wasn't used as a subject for this dataset since it included more detailed subjects like "Art", "Art, Media, and Entertainment", "Dance", "Drama/Theater", and "Music". I counted these subjects as falling under the Fine Arts umbrella based on a report by the National Arts Education Association defining 'Fine Arts' for High School graduation requirements as ["consisting of the visual arts, dance, music, and theatre.”](https://www.arteducators.org/advocacy-policy/articles/509-definition-of-fine-arts-for-high-school-graduation-requirements). I filtered the data in descenceding order based on total course enrollment as well as average classes per school in LA County. While enrollment was larger than most other elective subjects, the classes offered wasn't significantly higher.

Courses/School | Total Enrollment
----|----
![A table showing course subjects in ascending order based on average courses per school. Arts subjects are broken up by computer science and health but remain at the lower range.](https://user-images.githubusercontent.com/85646498/183399759-252ad0eb-eebc-4bc9-bf9f-f87a679604f9.png) | ![A table showing course subjects in ascending order based on total enrollment for LA County. Arts subjects are still broken up by computer science and health but have a greater value for enrollment.](https://user-images.githubusercontent.com/85646498/183399829-aa13b1ba-703b-4a08-ad2f-5fb64eb05339.png)

This dataset limits my further research compared to the original broader view because it is not broken down into districts like the first example, but it is useful for seeing a more comprehensive view of arts courses' populatity compared to other electives in LA County.

## Part II: Which districts have the most art classes per school? Which have the fewest? How do they compare to the average?
#### Question 3:
Seeing that the average classes per school in all of LA County is around 15, I wanted to look closer into the districts that fell short of or rose way above that number. I made a pivot table this time taking out the total and using districts as rows with the average classes per school equation as the value to sort by. I excluded districts where there were zero schools teaching any core classes. There were four districts that had no art classes at all, and small number with between one and five. The majority of districts with the fewest art classes were elementary districts.

Districts with Fewest Courses (Ascending)| Districts with Most Courses (Descending)
----|----
![A table showing the five districts with the fewest average arts courses per school in ascending order. The first four values are zero and the fifth school has one course.](https://user-images.githubusercontent.com/85646498/183404981-406bcabe-294d-45fd-9420-a0158a3d2586.png) | ![A table showing the five districts with the most average arts courses per school in descending order. The values are 313, 81.71, 71.22, 38, and 35 respectively.](https://user-images.githubusercontent.com/85646498/183406095-78e26adf-0431-482e-966f-86011b6422bf.png)

#### Question 4:
I wanted to see if there was a geographical relationship to the data from the pivot table. There are no readily available maps of LA County school districts, but I found one from Los Angeles Enterprise Geographic Information Systems which I downloaded and then slightly simplified in mapshaper to get the GeoJSON file small enough to be workable in Datawrapper. Then I downloaded the CSV information and imported it into Google Sheets. I had to adjust the school district names to fit the formatting of the Education Department data so I removed leading spaces, lengthened some cut off words, and made the counties on the subject by district chart in all caps. Once the districts matched, I used VLOOKUP to transpose the Average Arts Columns per School column into my map csv. After I made a copy and restored the original name notations so that the imported csv would connect properly to the district map template in Datawrapper. I broke down the data into seven custom steps to represent the largest groupings of data while highlighting the very low and very high numbers specifically.
<br>

[![A map of school districts in Los Angeles County sorted by which district has the greater number of art courses offered on average per school. Gorman Joint has the most with 313/school, then Acton-Agua Dulce Unified with 82/school. The majority are between 8 and 25.](https://user-images.githubusercontent.com/85646498/183445898-6e941c6c-776c-430a-a2cf-0a6d2bf86457.png)](https://www.datawrapper.de/_/qkeOB/)

Gorman Joint School District had almost three times as many arts classes per school than the second highest district, and looking at the data all of the classes were attached to only one school. I chose to do courses per school to try to equalize the data and look at school investment in arts without the bias of the size of the district. However, the top district had only one school responsible for the arts courses. The public charter offers online enrollment, which is how it has so many teachers and courses, not to mention a student body large enough to support the over three hundred arts courses offered during the 2018-2019 school year. Of the 1,374 students enrolled in the Gorman school district in 2018, only 82 were enrolled in the local K-8 Gorman Elementary according to the [2018-19 Enrollment by Grade report from the California Department of Education](https://dq.cde.ca.gov/dataquest/dqcensus/enrgrdlevels.aspx?cds=1964584&agglevel=District&year=2018-19&ro=y).

## Part III: Are there demographic trends that correlate to courses offered?
#### Question 5:
I didn't see any clear trends geographically based on the level of arts education present on the map. Most of the districts fell within a moderate range, and the districts where numbers dropped or peaked seemed to be clustered together. I wanted to see if there were less visibile distinctions between these areas, so I downloaded the 2018-2019 LA County Free and Reduced Price Lunch data and Enrollment by Ethnicity data. The Reduced Lunch data was written as a number and percent in the same cell so I used a SPLIT formula with the delimiter "()" so I could work with the values as numbers. I was interested in the percent of meals free or reduced and the ethnic demographic for districts, so I used VLOOKUP to join the free and reduced lunch column and average courses per school column into the demographic sheet. Then I sorted by the same ascending and descending patterns for classes as before to see the breakdown for the same highest and lowest districts.

Districts with Fewest Courses (Ascending)| Districts with Most Courses (Descending)
----|----
![A table showing the five districts with the fewest average arts courses per school in ascending order. ](https://user-images.githubusercontent.com/85646498/183471124-f0f14d63-0c37-4602-9ddc-74aadaa9b0f1.png) | ![A table showing the five districts with the most average arts courses per school in descending order. ](https://user-images.githubusercontent.com/85646498/183471868-575dfcda-3b3c-42e7-81b0-6c62ff5b5553.png)

Sorted by Diversity| Sorted by Reduced Lunch
----|----
[![CA chart showing a downward trend comparing the percent of the student body who are not white and the number of arts courses on average offered per school in a district.](https://user-images.githubusercontent.com/85646498/183481432-7b8eda01-dbe6-4a27-b053-7c4508be932c.png)](https://www.datawrapper.de/_/4JryB/)  |  [![A chart showing a downward trend comparing the percent of free and reduced meals and the number of arts courses on average offered per school in a district.](https://user-images.githubusercontent.com/85646498/183481428-21e0fe56-01c3-43a6-b4d2-e6d2ead5b8a1.png)](https://www.datawrapper.de/_/SlSvZ/)

The trend is less obvious just from the last and first five districts in the chart, but looking at the comparisons across the entire data shows a decline in arts classes when the student body is more diverse and more people have reduced or free meals. There's a clearer relation between diveristy and the use of free or reduced meals, but the reduced meals doesn't have as strong of a correlation with arts courses. Depending of the size of the district, there could be a wide variety of differences in demographics for multiple schools that would affect the data without looking at averages. 

## Story Pitch:
For the story I would look more into arts education in LA County. After researching Gorman Joint and how so much of the data is sourced from outside of the district, I'd like to compare public schools with charter or online schools and differing levels of arts education. I'd like to look at the data agian to get a more holistic understanding of the resources available to kids in public schools. Grants for arts education interest me a lot. I'd look at a list of grants given by the [Los Angeles County Arts Education Collective](https://www.lacountyartsedcollective.org/article-sub-categories/grants) and track down where the money went specifically after it was awarded to certain districts. I'd like to talk to local teachers and arts instructors in different parts of LA County about their experiences teaching (probably public school) and what role grants play to supplement funds needed for equipment and resources for their class. The [Average Class Size Report 2018-19](https://dq.cde.ca.gov/dataquest/CourseReports/ClassResults.aspx?Filter=A&TheYear=2018-19&cTopic=Course&cChoice=CrseAvg&cLevel=County&cdscode=19000000000000&Subject=Y&AP=Y&IB=Y&CTE=Y&lNotAll=True) for LA county will only give the data by subjects, not by districts. Part of the setbacks working with this data is that different data sets from the Califronia Department of Education classify data differently. I can't access total enrollment by school district, only schools and classes which is why my focus isn't form a classes per number of students strategy. I'f I'm able to find it, I think possible inequalities about class sizes and the relationship with that to quality of education would be very interesting mapped onto the ascending and descending lists of schools.

## Contacts:
Austin Beutner: 
* Former Superintendent of Los Angeles Unified School District
* is the proponent of the [California Proposition 28, Art and Music K-12 Education Funding Initiative](https://ballotpedia.org/California_Proposition_28,_Art_and_Music_K-12_Education_Funding_Initiative_(2022)#cite_note-text-1) 
* Working to get more money put aside for schools in California specifically for art and music and "distribute a portion of the additional funding based on a local education agency's share of economically disadvantaged students"
* (213) 241-7000 -> probably an old number... so if I can't reach him i'd email info@voteartsandmusic.org which is the group trying to get the prop passed.

Denise Grande: 
* Director of Arts Education for the Los Angeles County Arts Education Collective
* advocates for greater arts education + has a series of grants they award each year to many LA school districts so I'd like to talk more about funding especially outside funding like grants and their role in the arts education system
* (213) 202-5944

Bretton Boyd
* High school film and stage tech theater working in LAUSD who relies a lot on grants that he seeks out himself in order to get equipment for students to learn with.
* (323) 829-0694

