Unveiling the Spiritual Connection to Health
================
Mariela Mendez, Hannah Huang
2024-07-25

### Complementary and Alternative Medical (CAM) and Spirituality, Religiosity Survey

The CAM and Spirituality, Religiosity survey was given to chronically
ill patients who were randomly chosen from a patient database at a
private medical clinic in Southampton, UK. To be a participant for the
survey, individuals were required to (1) have recent treatment within
the last three years, (2) have a diagnosis of either migraines,
irritable bowel, or chronic fatigue syndrome, and (3) have an age
greater than 18. Six hundred questionnaires were originally mailed to
the patients, yet there was a response rate of 18.5%, with 111
successfully completed questionnaires. The survey aims to explore the
impact of spirituality on health. The spiritual topics range from
spiritual experiences, personal values, to private religious practices
and more. As for the health topics, these range from mindfulness
practices to current health issues. The following data is sourced from
the Association of Religion Data Archives, www.theARDA.com, and was
collected by principal investigators Niko Kohls, Harald Walach, and
George Lewish. The original data set consists of 254 variables and 111
participants, but for better understanding, the ARDA decided to add
variables and responses to include 258 total variables and 130
respondents. However, for the purposes of this analysis, the variable
count has been reduced to 13 variables. While this is a much shorter
data set, the chosen variables create a more direct approach. A concise
data set facilitates clearer interpretation of results without one being
overwhelmed by excessive data.

### Motivation

Understanding the relationship between spirituality and health is an
important aspect in well-being. In medical environments, especially
those dominated by Western medicine, spirituality’s impact on health is
often disregarded. With this data set, investigators are able to explore
how spirituality affects various sectors of health and overall
well-being. Via analysis, patterns or correlations can be linked. One
could uncover whether certain spiritual practices or beliefs are
associated with better mental health, reduced stress, or improved coping
mechanisms. In return, these patterns are relevant to healthcare
providers or therapists looking to integrate effective strategies into
their treatments. Notably, findings could influence policies related to
holistic healthcare approaches that acknowledge the role of spirituality
in patient well-being.

#### Defining our data

Now that we’ve uploaded our data set, we can determine how large our
dataset is and what variables we can narrow our focus to study. \#
`{r} nrow(camdata) ncol(camdata) ## Our dataset consists of 130 responses to 258 variables!`

##### Cleaning our data

We will create a new dataframe incorporating our variables of interest.

    ## tibble [130 × 13] (S3: tbl_df/tbl/data.frame)
    ##  $ belgdwth: hvn_lbll [1:130]  1,  1,  3,  4,  3,  3,  4,  3,  3,  3,  4,  4,  4,  ...
    ##    ..@ label       : chr "I believe in a God who watches over me."
    ##    ..@ format.stata: chr "%8.0g"
    ##    ..@ labels      : Named num [1:4] 1 2 3 4
    ##    .. ..- attr(*, "names")= chr [1:4] "Strongly disagree" "Disagree" "Agree" "Strongly agree"
    ##  $ prvtpry : hvn_lbll [1:130] 1, 2, 4, 5, 8, 8, 5, 8, 1, 7, 8, 7, 8, 6, 1, 8, 4, 4,...
    ##    ..@ label       : chr "How often do you pray privately in places other than a church or synagogue?"
    ##    ..@ format.stata: chr "%8.0g"
    ##    ..@ labels      : Named num [1:8] 1 2 3 4 5 6 7 8
    ##    .. ..- attr(*, "names")= chr [1:8] "Never" "Less than once a month" "Once a month" "A few times a month" ...
    ##  $ relpersn: hvn_lbll [1:130] 1, 2, 1, 2, 1, 2, 3, 1, 2, 2, 4, 2, 1, 1, 1, 1, 2, 4,...
    ##    ..@ label       : chr "To what extent do you consider yourself a religious person?"
    ##    ..@ format.stata: chr "%8.0g"
    ##    ..@ labels      : Named num [1:4] 1 2 3 4
    ##    .. ..- attr(*, "names")= chr [1:4] "Not religious at all" "Slightly religious" "Moderately religious" "Very religious"
    ##  $ sprtprsn: hvn_lbll [1:130] 2, 1, 2, 3, 3, 4, 4, 4, 2, 4, 4, 3, 4, 4, 4, 4, 3, 4,...
    ##    ..@ label       : chr "To what extent do you consider yourself a spiritual person?"
    ##    ..@ format.stata: chr "%8.0g"
    ##    ..@ labels      : Named num [1:4] 1 2 3 4
    ##    .. ..- attr(*, "names")= chr [1:4] "Not spiritual at all" "Slightly spiritual" "Moderately spiritual" "Very spiritual"
    ##  $ DISTRS04: hvn_lbll [1:130] 2, 0, 0, 0, 0, 0, 3, 1, 2, 3, 0, 1, 2, 0, 0, 0, 1, 1,...
    ##    ..@ label       : chr "This test consists of a list of problems people sometimes have.  Read each quest"
    ##    ..@ format.stata: chr "%8.0g"
    ##    ..@ labels      : Named num [1:5] 0 1 2 3 4
    ##    .. ..- attr(*, "names")= chr [1:5] "Not at all" "A little bit" "Moderately" "Quite a bit" ...
    ##  $ DISTRS11: hvn_lbll [1:130] 1, 0, 0, 0, 3, 3, 2, 0, 2, 1, 1, 0, 3, 2, 0, 0, 1, 1,...
    ##    ..@ label       : chr "This test consists of a list of problems people sometimes have.  Read each quest"
    ##    ..@ format.stata: chr "%8.0g"
    ##    ..@ labels      : Named num [1:5] 0 1 2 3 4
    ##    .. ..- attr(*, "names")= chr [1:5] "Not at all" "A little bit" "Moderately" "Quite a bit" ...
    ##  $ DISTRS16: hvn_lbll [1:130] 0, 0, 1, 4, 4, 2, 0, 1, 3, 4, 0, 1, 1, 0, 1, 1, 1, 3,...
    ##    ..@ label       : chr "This test consists of a list of problems people sometimes have.  Read each quest"
    ##    ..@ format.stata: chr "%8.0g"
    ##    ..@ labels      : Named num [1:5] 0 1 2 3 4
    ##    .. ..- attr(*, "names")= chr [1:5] "Not at all" "A little bit" "Moderately" "Quite a bit" ...
    ##  $ DISTRS23: hvn_lbll [1:130]  4,  0,  0,  4,  3,  4,  1,  0,  2,  1,  1,  0,  2,  ...
    ##    ..@ label       : chr "This test consists of a list of problems people sometimes have.  Read each quest"
    ##    ..@ format.stata: chr "%8.0g"
    ##    ..@ labels      : Named num [1:5] 0 1 2 3 4
    ##    .. ..- attr(*, "names")= chr [1:5] "Not at all" "A little bit" "Moderately" "Quite a bit" ...
    ##  $ DISTRS37: hvn_lbll [1:130] 2, 0, 0, 4, 3, 4, 3, 4, 1, 4, 2, 3, 3, 2, 2, 3, 4, 3,...
    ##    ..@ label       : chr "This test consists of a list of problems people sometimes have.  Read each quest"
    ##    ..@ format.stata: chr "%8.0g"
    ##    ..@ labels      : Named num [1:5] 0 1 2 3 4
    ##    .. ..- attr(*, "names")= chr [1:5] "Not at all" "A little bit" "Moderately" "Quite a bit" ...
    ##  $ DISTRS53: hvn_lbll [1:130]  0,  0,  0,  2,  1,  2,  1,  1, NA,  0,  1,  0,  0,  ...
    ##    ..@ label       : chr "This test consists of a list of problems people sometimes have.  Read each quest"
    ##    ..@ format.stata: chr "%8.0g"
    ##    ..@ labels      : Named num [1:4] 0 1 2 4
    ##    .. ..- attr(*, "names")= chr [1:4] "Not at all" "A little bit" "Moderately" "Extremely"
    ##  $ gender  : hvn_lbll [1:130]  2,  2,  2,  2,  2,  2,  2,  2, NA,  2,  2,  2,  2,  ...
    ##    ..@ label       : chr "Sex"
    ##    ..@ format.stata: chr "%8.0g"
    ##    ..@ labels      : Named num [1:2] 1 2
    ##    .. ..- attr(*, "names")= chr [1:2] "Male" "Female"
    ##  $ mrtlstus: hvn_lbll [1:130] 2, 2, 2, 1, 1, 3, 1, 1, 2, 3, 2, 2, 3, 1, 2, 1, 3, 2,...
    ##    ..@ label       : chr "Marital status"
    ##    ..@ format.stata: chr "%8.0g"
    ##    ..@ labels      : Named num [1:4] 1 2 3 4
    ##    .. ..- attr(*, "names")= chr [1:4] "Single" "Married" "Divorced" "Widowed"
    ##  $ denom   : hvn_lbll [1:130]  7,  2,  2, 11,  2,  2,  7, 30, NA,  3, 24,  5, 21, 1...
    ##    ..@ label       : chr "Denomination"
    ##    ..@ format.stata: chr "%8.0g"
    ##    ..@ labels      : Named num [1:24] 1 2 3 4 5 7 8 10 11 12 ...
    ##    .. ..- attr(*, "names")= chr [1:24] "None" "Protestant" "Baptist" "Free Evangelical" ...

#### Analysis
