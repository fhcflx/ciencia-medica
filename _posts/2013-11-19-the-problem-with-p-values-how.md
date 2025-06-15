---
layout: post
title: The problem with p values: how significant are they, really? via Geoff Cumming
date: '2013-11-19T18:11:00.000-03:00'
author: Francisco H C Felix
tags:
lang: en-us
ref: p-values-significance
modified_time: '2014-03-19T15:05:26.418-03:00'
blogger_id: tag:blogger.com,1999:blog-2993346515708552092.post-4599161624947558300
blogger_orig_url: https://pharmak.blogspot.com/2013/11/the-problem-with-p-values-how.html
---

# The problem with p values: how significant are they, really?

By [Geoff Cumming](https://theconversation.com/profiles/geoff-cumming-4100), *La Trobe University*

For researchers there’s a lot that turns on the *p* value, the number used to determine whether a result is statistically significant. The current consensus is that if *p* is less than .05, a study has reached the holy grail of being statistically significant, and therefore likely to be published. Over .05 and it’s usually back to the drawing board.

But today, Texas A&M University professor [Valen Johnson](https://www.stat.tamu.edu/directory-details.php?directoryid=321), writing in the prestigious journal Proceedings of the National Academy of Sciences, [argues](https://www.pnas.org/cgi/doi/10.1073/pnas.1313476110) that *p* less than .05 is far too weak a standard.

<!--more-->

Using .05 is, he contends, a key reason why false claims are published and many published results fail to replicate. He advocates requiring .005 or even .001 as the criterion for statistical significance.

## What is a *p* value anyway?

The *p* value is at the heart of the most common approach to data analysis – null hypothesis significance testing (NHST). Think of NHST as a waltz with three steps:

1. State a [null hypothesis](https://www.null-hypothesis.co.uk/science/item/what_is_a_null_hypothesis/): that is, there is no effect.
2. Calculate the *p* value, which is the probability of getting results like ours – *if* the null hypothesis is true.
3. If *p* is sufficiently small, reject the null hypothesis and sound the trumpets: our effect is not zero, it’s statistically significant!

British statistician and geneticist [Sir Ronald Fisher](https://en.wikipedia.org/wiki/Ronald_Fisher) introduced [the *p* value](https://psychclassics.yorku.ca/Fisher/Methods/index.htm) in 1925. He adopted .05 as a reference point for rejecting a null hypothesis. For him it was not a sharp cutoff: a thoughtful researcher should consider the context, and other results as well.

NHST has, however, become deeply entrenched in medicine and numerous other disciplines. The precise value .05 has become a bar to wriggle under to achieve publication in top journals. Generations of students have been inducted into the rituals of .05 meaning “significant”, and .01 “highly significant”.

## Sounds good. What’s the problem?

The trouble is there are [numerous deep flaws](https://www.apastyle.org/manual/related/kline-2004.pdf) in NHST.

There’s [evidence](https://tiny.cc/nhstohdear) that students, researchers and even many teachers of statistics don’t understand NHST properly. More worryingly, there’s [evidence](https://www.nature.com/neuro/journal/v14/n9/full/nn.2886.html) it’s widely misused, even in top journals.

Most researchers don’t appreciate that *p* is highly unreliable. Repeat your experiment and you’ll get a *p* value that could be extremely different. Even more surprisingly, *p* is highly unreliable even for [very large samples](https://tiny.cc/pintervals).

NHST may be a waltz, but the dance of *p* is highly frenetic. Here’s a demonstration of why we simply shouldn’t trust any *p* value:

[YouTube: Why p-values are unreliable](https://www.youtube.com/watch?v=5OL1RqHrZQ8)

Despite all those problems, NHST persists, perhaps because we yearn for certainty. Declaring a result “significant” suggests certainty, even though our results almost always contain considerable uncertainty.

## Should we require stronger evidence?

Johnson makes a cogent argument that .05 provides only weak evidence against the null hypothesis: perhaps only odds of 3 or 4 to 1 against reasonable alternative hypotheses.

He suggests we should require more persuasive odds, say 50 to 1 or even 200 to 1.

To do this, we need to adopt .005 or .001 as our *p* value criterion for statistical significance.

He recognises there’s a price to pay for demanding stronger evidence. In typical cases, we’d need to roughly double our sample sizes to still have a reasonable chance of finding true effects. Using larger samples would indeed be highly desirable, but sometimes that’s simply not possible. And are research grants about to double?

Johnson is correct that .05 corresponds to weak evidence, and .005 or .001 to evidence that’s usefully stronger. Adopting his stricter criterion would, however, mean that the majority of all published research analysed using NHST would fail the new test, and suddenly be statistically non-significant!

![shutupyourface](https://c479107.ssl.cf2.rackcdn.com/files/34853/width237/kzzxq98g-1384132459.jpg)

More fundamentally, merely shifting the criterion does not overcome the unreliability of *p*, or most of the other deep flaws of NHST. The core problem is that NHST panders to our yearning for certainty by presenting the world as black or white — an effect is statistically significant or not; it exists or it doesn’t.

In fact our world is many shades of grey — I won’t pretend to know how many. We need something more nuanced than NHST, and fortunately there are good alternatives.

## A better way: estimation and meta-analysis

[Bayesian techniques](https://www.indiana.edu/~kruschke/DoingBayesianDataAnalysis/) are highly promising and becoming widely used. Most readily available and already widely used is estimation based on [confidence intervals](https://tiny.cc/GeoffConversation).

A confidence interval gives us the best estimate of the true effect, and also indicates the extent of uncertainty in our results. Confidence intervals are also what we need to use [meta-analysis](https://tiny.cc/GeoffConversation), which allows us to integrate results from a number of experiments that investigate the same issue.

We often need to make clear decisions — whether or not to licence the new drug, for example — but NHST provides a poor basis for such decisions. It’s far better to use the integration of all available evidence to guide decisions, and estimation and meta-analysis provides that.

Merely shifting the NHST goal posts simply won’t do.

**Further reading:** [Give p a chance: significance testing is misunderstood](https://theconversation.com/give-p-a-chance-significance-testing-is-misunderstood-20207)

*Geoff Cumming has received funding from the Australian Research Council.*

This article was originally published at [The Conversation](https://theconversation.com). Read the [original article](https://theconversation.com/the-problem-with-p-values-how-significant-are-they-really-20029).

Postagem original em Pharmakon [aqui]({{ page.blogger_orig_url }}).
