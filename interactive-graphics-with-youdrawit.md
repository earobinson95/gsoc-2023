<!-- https://github.com/rstats-gsoc/gsoc2023 -->

## Background

<!-- 
Explain the motivation for your coding project. What problem would it solve?
-->

<!-- 
Initial studies in the 20th century explored the use of fitting lines by eye through a set
of points. Common methods of fitting trends by eye involved maneuvering a string, black thread, or ruler until the fit was suitable, then drawing the line through the set of points. While psychologists and statisticians have been using eye-fitting techniques to assess our innate perceptual statistical modeling abilities, news organizations have used similar techniques in order to draw readers in and demonstrate the difference between readers’ assumptions and reality. 

In 2015, the New York Times (NYT) introduced an interactive feature, called ‘You Draw It’, where readers input their own assumptions about various metrics of news interest and compare these assumptions to reality. The NYT team used Data Driven Documents (D3), a JavaScript library that allows readers to interact with a chart directly by drawing a line on their computer screen with a mouse. This feature was originally introduced as a tool for interactive reading to inform readers in efforts to reduce misconceptions and aid in storytelling.
-->

‘You Draw It’ is a feature that allows users to interact with a chart directly by drawing a line on their computer screen with a mouse. Originally introduced by the New York Times in 2015 for the purpose of interactive reading, we aimed to adapt and demonstrate the use of the 'You Draw It' method as a tool for interactive testing of graphics.

The following publications provide further background of our prior work with this feature:

+ [Eye Fitting Straight Lines in the Modern Era](https://www.tandfonline.com/doi/full/10.1080/10618600.2022.2140668) - original validation study of the modern 'You Draw It' tool.
+ [‘You Draw It’: Implementation of visually fitted trends with r2d3](https://earobinson95.github.io/sdss-2022-you-draw-it-manuscript/2022-sdss-you-draw-it-manuscript.pdf) (currently In Press) - provides technical details of the software
development, utilizing interactive graphics in `R`.

Test out the development applet at <https://emily-robinson.shinyapps.io/can-you-draw-it/>.

## Related work

<!-- 
What other R packages with similar functionality already exist? Why
aren't they good enough?
-->

Our initial work implementing the 'You Draw It' feature for user testing was based on the following:

+ In 2015, the [New York Times (NYT)](https://www.nytimes.com/interactive/2015/05/28/upshot/you-draw-it-how-family-income-affects-childrens-college-chances.html) introduced the 'You Draw It' interactive feature where readers input their own assumptions about various metrics of news interest and compare these assumptions to reality.
+ Original code framework can found at <https://github.com/BenoitFuric/you-draw-it-graph>. We adapted and added functionality such as the inclusion of points, visual cues, and storage of user provided data.

Additional pacakges related to user interaction include:

+ Toby Hocking incorporates interactive functionality to ggplot2 through the use of D3 in [animate2](https://github.com/tdhock/animint2). This package currently allows for interaction through clicking, but does not have the capability for users to freely draw their own lines.

The `r2d3` Rpackage easily integrates D3 visuals into existing formats in `R`, such as `shiny`.

## Coding project: interactive graphics with 'You Draw It'

<!-- 
What exactly do you want your contributor to code in the 10 week coding period?
What functions? What do they do? Docs? Tests? Vignettes?
-->

The goal of this GSOC project is to bundle the 'You Draw It' feature into an Rpackage and to add additional functionality to the tool.

An ideal contributor project will also plan to write some tests and documentation (vignette, web page, blog). Some important items from the TODO list:

+ 
+

We encourage contributors to share any other ideas for the improvement of 'You Draw It', as long as they can fit in the 3-month coding time frame. Some additional ideas which are not of high priority:

+ Include the ability to handle more than a one-to-one function (e.g. multiple y-values for a given x-value).
+ Provide an option to show vertical residuals between points and the user's drawn line to demonstrate least squares regression in an educational setting.


## Expected impact

<!-- 
Mentors, please explain how this project will produce a useful package
for the R community.
-->

The development and improvement of this R package will facilitate user experiments and provide an interactive tool for training purposes both within a classroom setting and for those in the workforce, making the 'You Draw It' technique available to other researchers who may not be willing to tinker with JavaScript directly.

## Mentors

<!-- 
MENTORS: fill in this part. each project needs 2 mentors. One should
be an expert R programmer with previous package development
experience, and the other can be a domain expert in some other field
or application area (optimization, bioinformatics, machine learning,
data viz, etc). Ideally one of the two mentors should have previous
experience with GSOC (either as a contributor or mentor). Please provide
contact info for each mentor, along with qualifications.

IMPORTANT: you MUST write "EVALUATING" for one mentor, who will be
required to do the three evaluations of the contributor during the
summer. In previous years we have had issues with mentors who do not
fill in evaluations, and when this happens R project is penalized
(money is taken away), although contributors are not penalized (contributors
are passed by default if no mentor eval is submitted). Therefore one
mentor must take responsibility for doing the evaluations, and you
must indicate that here, and your contributor must indicate that as well
in the application. If it is not clear which mentor will be the
EVALUATING mentor then your project will not be accepted. Example:
-->

Contributors, please contact mentors below after completing at least one
of the tests below.

- EVALUATING MENTOR: Emily Robinson <erobin17@calpoly.edu> is an Assistant Professor at California Polytechnic State University - San Luis Obispo. Her recent research implemented 'You Draw It' as a graphical test to evaluate the choice of scale in data visualizations.

- Susan VanderPlas <svanderplas@unl.edu> is an Assistant Professor at University of Nebraska - Lincoln, an expert in perception of statistical graphics, the author of R packages XXXX and YYY, and has previous GSOC participation experience with RStudio in 2012-2013 and mentoring experience with RStudio in 2014.

- Heike Hofmann <heike.hofmann@gmail.com> is a full professor at Iowa State University, an expert in computing and graphics, is the author of R packages XXX and YYY, and has previous GSOC mentoring experience with RStudio in 20xx-20xx.


## Tests

<!-- 
MENTORS: write several tests that potential contributors can do to
demonstrate their capabilities for this particular project.  Ask some
hard questions that will give you insight about how the contributors write
code to solve problems. You'll see that the harder the questions that
you ask, the easier it will be for you to choose between the contributors
that apply for your project!  Please modify the suggestions below to
make them specific for your project.

- Easy: something that any useR should be able to do, e.g. download
  some existing package listed in the Related Work, and run it on some
  example data.
- Medium: something a bit more complicated. You can encourage contributors
  to write a script or some functions that show their R coding
  abilities.
- Hard: Can the contributor write a package with Rd files, tests, and
  vignettes? If your package interfaces with non-R code, can the
  contributor write in that other language?
-->

Contributors, please clone <https://github.com/earobinson95/you-draw-it-example> and complete one or more of the following tests before contacting the mentors above.

+ **Easy:** Design decisions were made to ease the perceptual and intuitive use of the 'You Draw It' feature. A transparent yellow box is included in the 'You Draw It' feature as a visual cue to inform users of missing inputs and a dashed user line creates the illusion of a continuous line and avoids a jagged appearance. For this test, change the color of the transparent yellow box to orange and the style of the user line to be a long-dash short-dash style.

- **Medium:** Create a bare-bones R package which contains the provided `shiny_drawer()` function. You may find it useful to use the `litr` R package to create your package.

- **Hard:** Create an R package as described in the Medium test and add documentation to the `shiny_drawer()` function. Additionally, add XXX

## Solutions of tests

Contributors, please post a link to your test results here.
- EXAMPLE CONTRIBUTOR 1 NAME, LINK TO GITHUB PROFILE, LINK TO TEST
  RESULTS.
