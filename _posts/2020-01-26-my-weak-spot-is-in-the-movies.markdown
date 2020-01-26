---
layout: post
title:  "My weak spot is in the movies"
date:   2020-01-26 11:40:00 -0300
categories: [math, movies]
---

For some time, I have had the impression that I tend to like movies better when I watch them in the theaters.

So what have I decided to do? Test this with data!

I used my [Letterboxd diary][letbd], which has ratings for each movie, and tags indicating where I watched them. I downloaded my data files from their website, and manually did some simplifications to the `diary.csv` file.

In the diary file, each movie may have several tags, so I deleted all irrelevant tags and left only one for each movie, indicating whether it was seen at home or in the theaters. This change was done to simplify my code, if you don't want to manually alter the diary file, some minor changes in the code will be needed.

The Letterboxd profile pages already show a histogram of ratings for each user. With 275 films in total, my histogram looks like this:

{:refdef: style="text-align: center;"}
![Histogram of all my movie ratings]({{ "/assets/movies_hist.png" | absolute_url }})
{: refdef}

I also calculated the distributions for movies seen in theaters (65 in total) and at home (210 in total), separately: 

{:refdef: style="text-align: center;"}
![Histograms of ratings for movies in theaters and movies at home]({{ "/assets/movies_compare_hist.png" | absolute_url }})
{: refdef}

In this figure, I noticed that both distributions look different, supporting my initial hypothesis. Five star ratings are more frequent in theaters, and three star ratings are less common.

The mean rating of movies in theaters is also larger: 3.86, against a mean of 3.61 for movies at home.

I also measured the frequency of movies with a rating ($R$) of four stars or more, which can be interpreted as the probability of a movie having this rating. In the theaters, this probability is

$$
\mathrm{Pr}[R \geq 4 | \mathrm{cinema}] =  68\% \ ,
$$

and at home, the same probability is

$$
\mathrm{Pr}[R \geq 4 | \mathrm{home}] =  58\% \ .
$$

Again, I observed a difference between ratings at home and ratings in the theaters. This probability can also be calculated for the histogram of all movies:

$$
\mathrm{Pr}[R \geq 4] =  60\% \ ,
$$

which is a value very close to the probability at home.

But this is not enough, I still had to calculate $p$ values.

The $p$ value is used as a measure of the _statistical significance_ of a result. It estimates the probability that the observed phenomenom is a source of random fluctuations, instead of a genuine effect.

In my case, the phenomenom I observed is: Movies I saw in the theaters have consistently higher ratings than movies seen at home. The _null hypothesis_, $H_0$, in this case corresponds to: There is no such difference, and all of my movie ratings stem from the same probability distribution.

To test this, I will consider each movie rating as a binary distribution. So, each movie is categorized as _good_ (four stars or more), or _bad_ (three stars or less).

Under the null hypothesis, the probability of a movie being _good_ is $x=0.60$, thus the probability of it being _bad_ is $x=0.40$.

Considering the movies I watched in theaters, 44 out of 65 were _good_. This is my observation, in quantitative terms.

The $p$ value is the probability, under the null hypothesis, that I would obtain a result equal or more extreme than the one I observed. That is:

$$
p = \mathrm{Pr}[N_1 \geq 44|N=65,H_0] \ .
$$

The probability of watching $N_1$ _good_ movies out of $N$ total movies is a binomial random variable, and its probability is

$$
\mathrm{Pr}[N_1|N,H_0] = \binom{N}{N_1} \ x^{N_1} \ (1-x)^{N-N_1} \ ,
$$

hence the $p$ value is

$$
\mathrm{Pr}[N_1 \geq 44|N=65,H_0] = \sum_{N_1 = 44}^{65} \mathrm{Pr}[N_1|N=65,H_0] \ ,
$$

with a numerical result of:

$$
p = 0.13 \ .
$$

The smaller the $p$ value, the higher the significance of the result, because it shows that this result is unlikely to come from the null hypothesis. In scientific research, the effect is said to be _significant_ if $p$ is below some threshold, usually one of these values: 0.05, 0.01, 0.005, or 0.001.

My $p$ value is not below any of these thresholds, but this is not rigorous scientific research and I consider myself convinced that this effect isn't just a random fluctuation (maybe this is an instance of confirmation bias?)

One more interesting observation is: If I had taken $x=0.58$, with the null hypothesis that movies in theaters follow the same distribution as movies at home, the $p$ value would be different. In this case

$$p=0.07 \ ,$$

which is quite smaller than the previous value for $p$. 
This is an instance of $p$ hacking, a topic which is under a lot of discussion nowadays. Some popular discussions are available at [Wired][wired] and [FiveThirtyEight][538].
Also, let's not forget that the statistical sample is not large, there are less than 300 movies in total, thus statistical fluctuations of the averages and a large variation in the $p$ value are expected.

In the end, I consider this a positive result, but still no explanation has been given to the effect. Is it because I choose movies better when I go to the theater? Is it because I pay more attention? Is it because the theater screen has a hypnotizing effect on me?

I don't know. All I can conclude is that I like the theaters.

The code for this analysis is available on [my github][code].

[letbd]: https://www.letterboxd.com/
[code]: https://github.com/gapolinario/cinema-weak-spot
[538]: https://fivethirtyeight.com/features/science-isnt-broken/#part1
[wired]: https://www.wired.com/story/were-all-p-hacking-now/