---
title: "Density-independent Demography"
date: 2025-06-04 
author: Daniel Borzoo 
#layout: default
---


<script src="https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
<script id="MathJax-script" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js">
</script>
<script>MathJax = {tex: {inlineMath: [["$", "$"]]}}</script>




<p align="justify">

  
In the preceding chapter, we listed Hastings’ (A. Hastings 2011) key principles and assumptions of single species population growth. One of the key assumptions is that “all individuals in a population are identical.” In this chapter, we elucidate an important violation of that assumption, population structure.

</p>

<p align="justify">

Populations have structure. Consider the human populations of Mexico and Sweden in 1990. Mexico had a much larger fraction of their population in child bearing age classes or younger. In addition, the age-specific fertility rate was higher in Mexico, especially for younger women. How did this happen, and why did Mexico have so many young people? What were the consequences of this for their culture, their use of resources, their domestic and foreign policies, and their future population growth? How about Sweden?

</p>

<p align="justify">

Demography is the study of populations with special attention to their structure. Originally, age-based human demography was the provenance of actuaries who helped governments keep track of the number citizens of different ages and thus, for instance, know how many would be available for conscription into the military.

</p>

<p align="justify">

The reason we model the structure of populations is because various demographic rates vary markedly with these stages. Juveniles produce no offspring. Very few seeds survive an entire year, whereas some large adults survive very well. We use structure when that structure is associated with important differences in demographic rates: survival, fecundity, and growth.

</p>

<p align="justify">

The structure to which we refer is simply the organization of populations by some character such as life history stage, age, or size. Sizes and ages are often reduced to categories such as we saw in human populations (e.g., 0–4.9,y, 5–9.9,y,…). Sizes may be based on any reliable and repeatable measure that relates to demographic rates and are similarly binned. Life history stages may include eggs, larvae, metamorphs, juveniles, and adults in amphibians, or seeds, rosettes, and reproductive stems in herbaceous plants. With a variable such as size, we don’t need to use categories, but rather we can use size as a continuous variable; we address this briefly later in the chapter.

</p>

<p align="justify">

Structured population models allow us to intertwine species-specific natural history and quantitative methods. This makes the approach especially appealing for the conservation biology of threatened and endangered species. We use structured population models to improve our understanding of a population or improve predictions of its future dynamics, or guide the management of the population. We might learn a lot about what controls the abundance of a species if we can test ideas related to different stages, ages, or sizes. What limits the population growth of the Western toad – is it egg survival, or overwintering survival of juveniles? Where should we invest our efforts to control garlic mustard (Alliaria petiolata) – killing the first year rosettes, or the second year adults? Why are cacti generally endangered (Goettsch et al. 2015)—is the smallest size or the largest size more important for long-term survival? We can use structured population models to address such questions.


</p>

##  Survivorship
---
<p align="justify">

The construction of a life table begins by gathering information on survivorship by age class. This sounds simple but is easier described than actually done. For example, one method is to study a cohort of individuals all born at the same time and follow the survivorship of these individuals until the last member of the cohort dies. At the beginning of such a study, it would be necessary to locate and mark all newborn individuals. Subsequently, one would need to verify when each individual died. Individuals that simply disappeared could not be assumed to have died; they might have emigrated.

</P>

<p align="justify">

A second approach is to locate and examine all of the dead individuals in a population during some defined period. We would need a method for estimating the age of the animals or plants at death. This approach to the construction of a life table assumes that the rates of survival in the population are fairly constant. If this is not the case, age-specific mortality rates will be confused with year-to-year variation in mortality of the overall population. Data gathered in this manner produce a static, vertical, or time-specific life table.

</p>

<p align="justify">

A third approach is to collect life history data for several cohorts over as long a period as possible. In most populations, there is a large difference between juvenile and adult survivorship. Therefore, although survivorship data on adults are often relatively easy to gather, such data do not apply to the juvenile age classes. Depending on the age when reproduction begins, it is possible to find the growth rate of the population without specific data on juvenile survivorship, as described later in the chapter.

</P>

<p align="justify">

Let $s_x$ be the survival rate, or probability, that an individual in age class $x$ will survive from the beginning of the year to the beginning of the next year and thus reach age $x + 1$. Let $dx$ = the corresponding death rate of age class x. Then 

</P>

$$
  s_x = 1 - d_x
$$

The survivorship from age class 1 to the beginning of age class x is called $l_x$, so 

$$
  l_x = s_1s_2...s_{x-1}
$$

<p align="justify">

In a survivorship curve, age (x), the independent variable, is graphed against survivorship. Pearl (1927) introduced the idea that biological populations routinely fit one of the three “types” of survivorship curves. The type I curve, known as the “death at senescence” curve, is characterized by excellent survivorship at all ages from birth until “old age,” at which time the death rate rapidly accelerates and survivorship plummets. The type II curve is linear and assumes that either a constant number or a constant proportion of the population dies in each age interval.  Finally, the type III curve applies to the majority of biological populations. In this curve, there is very high mortality among the juvenile age classes while adult survivorship is relatively high.

</p>

<p align="justify">

We can make some general comments. The least realistic of the three types is type I. A type I curve applies to laboratory populations of animals such as Drosophila. If provided ample food, the population has a high rate of survivorship until the end of its maximum life span when individuals die more or less simultaneously. In order for an organism to have a type II survivorship curve, all stages of the life history must be more or less equally vulnerable to predation or other causes of death. Birds, especially the adult stages, are most commonly cited as having a type II survivorship curve. The type III survivorship curve, which features heavy mortality among young age classes followed by good to excellent adult survivorship, applies to most bioogical populations from barnacles to sea turtles to plants. 

</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/e9727968-b59b-4872-a66b-9727fcf7d677" />
</p>




<p align="justify">

From the $l_x$ column, we can develop two parallel columns, which provide information on how survivorship and mortality rates change with age. The $l_x$ column is based on the probability, at birth, of surviving to a given age class. The $P_x$ column, by contrast, is the age-specific probability of surviving to the next age class.

</P>

$$
 P(x) = \frac {l(x+1)} {l(x)}
$$

<p align="justify">

These px values are critically important when we want to project future population growth as will become clear later in this chapter. The companion value to $P_x$ is $q_x$, which is the proportion of the population that has survived to a given age, $x$, but which will die in the next time or age interval.

</p>

$$
    q_x = 1 - P_x
$$

## Fertility
----------------------
The other half of the life table is the fertility column, $b_x$. Here, each value represents the average number of female offspring produced per female of a given age. Again, gathering accurate data on fertility in the field is problematic for many populations. In order to simplify calculations, we count only the number of females. That is, the values are mean numbers of females by age class. Fertility, similar to survivorship, can be graphed as a function of age, and the resultant fertility curve is usually triangular or rectangular in shape. 

The sum of the $b_x$ column defines the gross reproductive rate (GRR). This number is the average number of female offspring produced by a female that survives at least through the last reproductive age class

$$GRR = \sum {b_x}$$

The net reproductive rate, $R_0$, that bears a loose relationship to $R$:

$$
  R_0 = \sum{(l_xb_x)}
$$

One way to describe $R_0$ in words is: "the average number of female offspring produced per female over her lifetime." That is, if we follow a cohort of newborn females through their entire lives, the average number of (female) offspring each female pro duces is $R_0$. Yet, there is another meaning that can be ascribed to $R_0$: "the per capita growth rate of the population per generation at stable age structure."

At first glance, these two definitions of $R_0$· do not seem to be equivalent. The first deals with a time unit of a lifetime and the second deals with generation times; the first with the number of offspring produced per female and the second with the growth rate of the population (which has units of per time period - e.g., per year). The trick is to define generation time in such a way that these two definitions are equivalent. Moreover, by defining generation time ($G$) more precisely, we can connect $R_0$ with $l$ as follows: 

$$
  e^{rG} = R_0
$$

$$
  r = ln(R_0)/G
$$

The approach we take is to imagine that all the $R_0$ babies born to these mothers over their lifetimes were all born to them at some age G instead.

<p align = 'center'>
  <img src= "https://github.com/user-attachments/assets/7fc79e74-14b4-436a-9ed1-cc17819223cb" /> 
</p> 

There are several possible definitions for generation time. We desire one that is not sensitive to the rate that the population is growing ( or shrinking). The most commonly used is to follow a cohort of females from their births, count up all the daughters that they produce during their lifetimes at each of their ages x, and average them to produce a mean age of reproduction: 

$$
  G = \frac{\sum{(l_xb_xx)}}{\sum{(l_xb_x)}} = \frac{1}{R_0} \sum{(l_xb_xx)}
$$

The numerator of $G$ sums all the lengths of time $x$ between the birth of each mother and the births of each of her own offspring. Mothers give birth only at age $x$ if they survive to age $x$ - hence the $l_x$ terms. The denominator ($R_0$) divides this sum by the total num ber of births produced during the average mother's lifetime.

## Mean Lifetime of Individuals 
---

How long can you expect to live? Another way of asking this question is: What is the mean age of individuals at death in a population? Imagine a cohort of individuals that has no mortality at all until age 10, and then everyone dies. The $l(x)$ curve looks like

<p align = 'center'> 
  <img src="https://github.com/user-attachments/assets/17f0d659-2a2c-4d86-9f32-086c262809c4" />
</p>


The area under the $l(x)$ curve is 10, and all individuals have a lifetime of 10 years. Figure below shows another example, one where the l(x) curve declines linearly with age. Now the average age of individuals in the population would intuitively seem to be one half of 10, or 5, and in fact this is correct.

<p align = 'center'>
  <img src="https://github.com/user-attachments/assets/d6513959-96b9-4f26-9265-4f85f0d1e378" />
</p>

The life expectancy at birth can also be thought of as the mean age of death in the population. Using the definition of a mean age $x$, we get 

<p align = 'center'>
  
  Life Expectancy at birth = Mean age of death = $\sum_{x=0} {x l_x d_x}$

</p> 

Assuming all the mortality takes place immediately at the beginning of the age interval (on the xth birthday), we will find a new expression for $d_x$. 

$$
  d_x = 1 - s_x = \frac {l_x - l_{x+1}}{l_x}
$$

Substituting the above equation into the previous one, we will have

$$
  E_0 = \sum_{x=0}  {x (l_x - l_{x+1})}  = \sum_{x=0} {x (l_x)} - \sum_{x=0} {x (l_{x+1})} 
$$

$$
  E_0 = 0l_0 - 0l_1 + 1l_1 - 1l_2 + 2l_2 - 2l_3 + 3l_3 + ..... - (max - 1)(l_{max}) + max(l_{max}) = \sum_{x=0}  {l_x}
$$
