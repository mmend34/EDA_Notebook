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

<!-- ```{r}
nrow(camdata)
ncol(camdata)
# Our data set consists of 130 responses to 258 variables!
``` -->

### Defining Variables

The original data set consists of 130 responses to 258 variables!
Narrowing the focus for a more direct approach, 13 variables were chosen
instead. Three categories were made in order to create a distinction
between these chosen variables. The categories are as follows:
spirituality/religious, health effects, and personal data. For the first
category, the variable *belgdwth* refers to the survey question “I
believe in a God who watches over me”, *prvtpry* refers to “How often do
you pray privately in place?”, *relpersn* refers to “to what extent do
you consider yourself a religious person?”, and *sprtprsn* refers to “to
what extent do you consider yourself a spiritual person?”. The health
effects category contains both physical and psychological effects. These
variables are *DISTRS11*: poor appetite, *DISTRS23*: nausea or upset
stomach, *DISTRS37*: feeling weak in parts of your body, *DISTRS04*:
feelings others are to blame for most of your troubles, *DISTRS16*:
feeling lonely, *DISTRS53*: the idea that something is wrong with your
mind. As for the personal data category, the variables chosen are
*gender*: female or male, *mrtlstus*: marital status (single, married,
divorced, or widowed), and *denom*: denomination. COME BACK TO EXPLAIN
REASONING FOR SELECTING THESE VARIABLES!!

### Cleaning The Data

We will create a new data frame incorporating our variables of interest.

    ##   [1] "strdream" "disworld" "IGNROVR1" "sprtwrk"  "drmfutr"  "hibnghlp"
    ##   [7] "inenvrmt" "outspntm" "hrnvoice" "cntraln"  "spclite"  "consbody"
    ##  [13] "mysmean"  "heatbdy"  "antdstny" "enrgysp"  "extrpow"  "thnkhpn" 
    ##  [19] "prtdie"   "thnkslw"  "expndbdy" "mnfldrms" "readmnd"  "othrctrl"
    ##  [25] "vivdrms"  "mntlsprt" "vibskin"  "peace"    "ineyevis" "trnsfrm" 
    ##  [31] "intouch"  "atrctloc" "nothnk"   "unvrsrel" "knwclng"  "dilinvce"
    ##  [37] "enrgypls" "cursed"   "sndhrmen" "supntbng" "lfeineye" "blrenvrt"
    ##  [43] "vewaprt"  "notrivl"  "felsprtb" "posstho"  "hrvochlp" "inspinst"
    ##  [49] "senrad"   "discenv"  "disself"  "strgtho"  "nofocus"  "sinbdy"  
    ##  [55] "ildivne"  "benlght"  "incrund"  "pecdrm"   "exgwrld"  "IGNROVR2"
    ##  [61] "spowork"  "dremfut"  "hibnhlp"  "inenvrnt" "outsptm"  "scldvoc" 
    ##  [67] "ctstrfor" "imsplit"  "consep"   "depmyst"  "hetbdy"   "antdest" 
    ##  [73] "enrgyspn" "extnpow"  "mothnkhp" "prtdies"  "slwthk"   "bdyexpnd"
    ##  [79] "mnfldrm"  "otplrdmd" "wilacton" "vivdrems" "mentsup"  "tngskin" 
    ##  [85] "atpeace"  "visineye" "bngtrans" "intochev" "locatrct" "bngthot" 
    ##  [91] "unvrel"   "knocal"   "dilinvoc" "enrgybdy" "crsed"    "mentlhrm"
    ##  [97] "contsubn" "lifeiney" "blrenvr"  "wrldvew"  "notrvil"  "felexbng"
    ## [103] "thoinmnd" "voichlp"  "insinst"  "spradsns" "discenvr" "selfwrld"
    ## [109] "nomythot" "notfocus" "strngsin" "ildivstr" "benlite"  "inrundst"
    ## [115] "extrexp"  "evokslf"  "altrslf"  "relatexp" "meditech" "whtech"  
    ## [121] "lngprct"  "oftprct"  "teahinst" "MNDFUL01" "MNDFUL02" "MNDFUL03"
    ## [127] "MNDFUL04" "MNDFUL05" "MNDFUL06" "MNDFUL07" "MNDFUL08" "MNDFUL09"
    ## [133] "MNDFUL10" "MNDFUL11" "MNDFUL12" "MNDFUL13" "MNDFUL14" "SPTEXP01"
    ## [139] "SPTEXP02" "SPTEXP03" "SPTEXP04" "SPTEXP05" "SPTEXP06" "SPTEXP07"
    ## [145] "SPTEXP08" "SPTEXP09" "SPTEXP10" "SPTEXP11" "SPTEXP12" "SPTEXP13"
    ## [151] "SPTEXP14" "SPTEXP15" "SPTEXP16" "belgdwth" "redpnwld" "frgwrng" 
    ## [157] "frgothrt" "gdfrgv"   "prvtpry"  "oftmed"   "relprgm"  "rdbblit" 
    ## [163] "PRYB4MEL" "lgsprtfc" "prtnrwgd" "suptgod"  "punshsin" "gdabndon"
    ## [169] "norelygd" "relgstrs" "conghlp"  "congcmft" "condemnd" "concrit" 
    ## [175] "lifechng" "agexp"    "fathgain" "agegain"  "losfaith" "ageloss" 
    ## [181] "belinlif" "cntrbch"  "hrschrh"  "atendrel" "wrshpact" "relpref" 
    ## [187] "DENOM_SP" "relpersn" "sprtprsn" "lifediv"  "lifecal"  "DISTRS01"
    ## [193] "DISTRS02" "DISTRS03" "DISTRS04" "DISTRS05" "DISTRS06" "DISTRS07"
    ## [199] "DISTRS08" "DISTRS09" "DISTRS10" "DISTRS11" "DISTRS12" "DISTRS13"
    ## [205] "DISTRS14" "DISTRS15" "DISTRS16" "DISTRS17" "DISTRS18" "DISTRS19"
    ## [211] "DISTRS20" "DISTRS21" "DISTRS22" "DISTRS23" "DISTRS24" "DISTRS25"
    ## [217] "DISTRS26" "DISTRS27" "DISTRS28" "DISTRS29" "DISTRS30" "DISTRS31"
    ## [223] "DISTRS32" "DISTRS33" "DISTRS34" "DISTRS35" "DISTRS36" "DISTRS37"
    ## [229] "DISTRS38" "DISTRS39" "DISTRS40" "DISTRS41" "DISTRS42" "DISTRS43"
    ## [235] "DISTRS44" "DISTRS45" "DISTRS46" "DISTRS47" "DISTRS48" "DISTRS49"
    ## [241] "DISTRS50" "DISTRS51" "DISTRS52" "DISTRS53" "age"      "gender"  
    ## [247] "mrtlstus" "chldrn"   "lfesitu"  "denom"    "eductn"   "prsntoc" 
    ## [253] "sample"   "grouppe"  "I_AGE"    "I_ATTEND" "I_EDUC"   "I_GENDER"

    ##               belgdwth                    prvtpry                   relpersn 
    ##  Strongly disagree:25   Never                 :39   Not religious at all:50  
    ##  Disagree         :18   More than once a day  :22   Slightly religious  :37  
    ##  Agree            :41   Less than once a month:21   Moderately religious:26  
    ##  Strongly agree   :43   A few times a week    :17   Very religious      :15  
    ##  NA's             : 3   Once a day            :14   NA's                : 2  
    ##                         (Other)               :15                            
    ##                         NA's                  : 2                            
    ##                  sprtprsn          DISTRS04          DISTRS11 
    ##  Not spiritual at all:16   Not at all  :76   Not at all  :90  
    ##  Slightly spiritual  :22   A little bit:33   A little bit:25  
    ##  Moderately spiritual:45   Moderately  : 9   Moderately  : 6  
    ##  Very spiritual      :45   Quite a bit : 9   Quite a bit : 5  
    ##  NA's                : 2   Extremely   : 1   Extremely   : 2  
    ##                            NA's        : 2   NA's        : 2  
    ##                                                               
    ##          DISTRS16          DISTRS23          DISTRS37          DISTRS53 
    ##  Not at all  :59   Not at all  :69   Not at all  :47   Not at all  :90  
    ##  A little bit:46   A little bit:34   A little bit:33   A little bit:24  
    ##  Moderately  : 9   Moderately  :10   Moderately  :17   Moderately  : 8  
    ##  Quite a bit : 7   Quite a bit : 4   Quite a bit :20   Extremely   : 5  
    ##  Extremely   : 7   Extremely   : 9   Extremely   :11   NA's        : 3  
    ##  NA's        : 2   NA's        : 4   NA's        : 2                    
    ##                                                                         
    ##     gender        mrtlstus              denom   
    ##  Male  : 17   Single  :35   Protestant     :50  
    ##  Female:112   Married :69   No denomination:29  
    ##  NA's  :  1   Divorced:25   Other          : 8  
    ##               Widowed : 1   Christian      : 5  
    ##                             Catholic       : 5  
    ##                             (Other)        :28  
    ##                             NA's           : 5

### Graphs/ Tabular…

#### Gender

![](EDA_Notebook_files/figure-gfm/unnamed-chunk-4-1.png)<!-- -->

### Analysis

Plans: huge difference in gender (women 112\> men 17) most are not
religious (50) but very spiritual (45) 90 nothing is wrong with mind 50
protestant most are married most never have private practice

want to create and analyze charts/graphs (maybe more) spiritual person
w/ psychological problems vs religious spiritual person w/ physical
problems vs religious mrtstus effect on health problems belgdwth effect
on health problems
