---
title: 'The First (and Namesake) Post: Is It Cake?'
author: Ariel Zane
date: '2018-02-06'
tags:
  - classification
  - clustering
  - supervised learning
  - unsupervised learning
slug: the-first-and-namesake-post-is-it-cake
---
# Hello, world

After all of the inspiring excitement of RStudio::conf 2018, I decided that I should start a blog. I'm not a statistician (I've never taken a formal statistics class, and for some unknown reason I confessed that to [Charlotte Wickham] (http://cwick.co.nz) at lunch during the conference, but she was very lovely about it, because she's very lovely), and I'm not a computer scientist, but it **is** part of my day job to explain our team's analysis methods to people who are _also_ not statisticians or programmers - by and large, most of my presentations are to scientists who are experts in biology, immunology, virology, biochemistry...you get the idea.

My background is in physical chemistry, so many of these data science and/or machine learning concepts are new to me, too, and I find it helpful to consider analogies when I present these methods. The math is helpful (and I appreciate now all of those statistical mechanics and quantum mechanics classes in graduate school), but sometimes a concrete example can help lay the foundation for complicated concepts. 

What I'm going to try to do here is produce simple examples that can tackle some of those ideas. I'll aim to link to more in-depth, potentially math-heavier explanations where I can, as well as to more tutorial-type example code and vignettes (I'd like to add my own code in the future, but...baby steps!). Most likely these examples will be gross oversimplications, but sufficient to get the idea across. If you have anything to add, please feel free to get in touch! The easiest way is to leave a comment, or tweet me [**@lariebyrd**](https://twitter.com/lariebyrd).

Anyway, I figured I'd start with the common question: what is the difference between **unsupervised** and **supervised** learning?

## Unsupervised vs. supervised learning

### Unsupervised learning

So let's start with this. With unsupervised learning, you're typically trying to find structure in your data. Take this raw dataset, for example, where every data element is an emoji (no, the data set is _not_ [tidy](http://vita.had.co.nz/papers/tidy-data.html)):

![Foooood](/img/cake_raw_20180206.png)

Now, if I asked you to sort this into **two** bins, based on some criteria that you determine, what would you do?

\*Jeopardy song\*

\
\
\
(Just kidding, we're stress-free here)

\
\
\

![](/img/cake_clustered_20180206.png)

If you sorted them into NOT CAKE and CAKE, then:

1. We are definitely friends.

2. You just clustered the data! 

\
Right, so now you probably have questions. 

1. **In real scenarios, how would you determine how many clusters there are?** There are great tutorials and explanations for methods (this is a good one from [**UC Business Analytics**](https://uc-r.github.io/kmeans_clustering)), but good 'ole trial and error or educated guessing can sometimes work, as well.

2. **What if I chose some other criteria? Like, for example, savory vs. sweet?** That's legitimate, and a common problem with clustering and unsupervised methods. You may have a guess as to the underlying structure in the data, but there may be several possibilities, depending on the characteristics of the data.

3. **Are pancakes cake?** This is deep. I don't know. And this is another issue you may face - the clusters you create will usually be exclusive (i.e., an item or observation can only belong to one or the other), but that doesn't mean that the items won't have qualities characteristic of both clusters.

### Supervised learning

Now you have your clusters, or your _classes_. This is usually why, if you don't have labeled data, you start with unsupervised learning and then move to supervised - the latter requires a training set (the output of your clustering), or something to train your algorithm on. We're tackling classification here - specifically _binary_ classification, since we have two classes. 

Based on our classes above (1. NOT CAKE, 2. CAKE), if I hand you a new set of raw data, can you sort them based on the criteria: IS IT CAKE?

![](/img/cake_class_20180206.png)

In this case, you're going by image - is this image a cake, or not? If we broke that down, we'd be talking about some organization of pixels that make up this cake emoji. If you had actual food as your data, you'd be thinking: is this sweet? Is it fluffy? Does it have frosting? Likewise, if you were only given descriptors (text data): "moist" (sorry), "frosted," "chocolate," that might help you sort that line of description into the "cake" pile, vs. descriptors like "spicy", "crispy," "salty" - that would (hopefully) be "not cake."

So we've classified this element - it's 1. NOT CAKE.

And finally, if we wanted to drill down in the data, we could also just take the CAKE group, and say now that we would like to sort new cake data into WHOLE CAKES and CAKE SLICES, based on our breaking down the CAKE cluster and labeling each element as either a WHOLE CAKE, or a CAKE SLICE. That would create a new training set, and we can get further specificity.

## Need conclusion here