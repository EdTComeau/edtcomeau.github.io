---
layout: post
title: Chimerism
---

# Chimerism
 Chimerism analysis is an amazing tool that our Tissue Typing lab is able to offer. 

After a patient receives a hematopoietic stem cell transplantation (HSCT), a major goal of the recovery phase is to predict negative events like relapse, graft rejection, and graft-versus-host disease. Chimerism analysis allows doctors to monitor post HSCT-transplants.

The goal of this post is to quickly describe how we currently do chimerism analysis. An understanding of chimerism analysis should not be needed to read this. 

# What is a Short Tandem Repeat (STR)?
While other technologies rely on sequencing entire portions of a genome, chimerism focuses in on known locations in the genome where DNA has Short Tandem Repeats (STR). An analogy would be if the human genome is the earth, STRs would be like the Great Wall of China, the Eiffel Tower, and Mount Everest: easy to identify markers that everyone has in their DNA. 

STRs are short sequences of DNA, normally two to five base pairs long that are repeated numerous times.

Here is an example of a DNA sequence with an STR. 

> `ATTTTCATTGGCCCCCGGCCA`**`GATAGATAGATAGATAGATAGATAGATAGATAGATA`**`TTTGGC`

The example DNA sequence above can be found at the D7S820 locus, which is on the seventh chromosome. It is comprised of four base pairs **GATA**.

## Classification of STRs
Let's look at that example again:

> `ATTTTCATTGGCCCCCGGCCA`**` GATA GATA GATA GATA GATA GATA GATA GATA GATA `**`TTTGGC`

The base sequence **GATA** repeats nine times. We would define this as allele 9. People can have anywhere between _5 and 16_ repeats!

## Why we use STRs
Consider the following:
- The D7S820 STR is easy to spot because of its repeating nature.
- Depending on a person, they may have anywhere from 5 to 16 repeats of this STR.
- Everyone has 2 of these, one from their mother and one from their father.
- There are 12 different allele possibilities (5 - 16 repeats), and everyone has two of them.

Because of this last point, the single STR marker has 78 possible combinations. They are _somewhat_ random too. This means that if I know how many repeats _your_ two D7S820 loci have, and I have a blood sample with matching repeats, there is a 1 in 78 likelihood of that happening by chance. 

You may now see why these STR's were originally used for forensic evidence. If there is blood at a crime scene and the STR repeats match you, there is a small probability that happened by chance. 

This is what you can do with a single STR and we analyze 21 of them! By analyzing 21 known STR locations we obtain a "genetic fingerprint" that has 10^30 possible combinations. While the _true_ probability is slightly less than that for complicated reasons, it still means that essentially everyone has a unique set of STR alleles that no one else in the world has.

## What does an STR look like to us
Sorry if you a biologist reading this and want to get into the wet work, because I am skipping over all of that. What, only biologists are reading this? Okay, if you really need to know, we do something like:
- Extract DNA
- Amplify DNA
- Attach STR probes
- Amplify those STR markers
- Use something like High Performance Liquid Chromatography (HPLC) to analyze*

*These methods change from lab to lab and from assay to assay.

Some cool math turns the laser intensity from the HPLC into peaks. It looks like this:

![Example 1](/images\STRExamples.png)

In the above example, this patient (Spoiler: it’s my DNA we are analyzing), has 16 repeats from one parent and 17 repeats from the other parent. Pretty neat right? Some things to note:
- The big number under the allele call (i.e. 10027 and 11070) is the area under the peaks.
- The area of these two peaks is about equal.

# What do post-transplant patients look like?
To reiterate, everyone has two copies of their STRs. We test patients _prior to their transplant_ to figure out what their STR alleles look like. We also test the donor _prior to transplant_ to figure out what their STR alleles look like.
After the transplant, we expect to see both the donor **and** the recipient's STRs expressed in the transplant recipient.
Below is an example:
![Example 2](/images\TransplantAlleles.png)
*Amazing photo credit goes to ME and Microsoft Paint

Remember, each peak represents an STR. The patient started with two, one from each parent. The donor has two, one from each parent. After transplant, the patient is expressing four alleles! How cool is that. 

## What we measure
A HSCT transplant recipient will start at 100% recipient alleles (prior to transplant). After the transplant the goal is that their body will replace their STR alleles with the donors STR alleles, or 100% donor. An ideal trend is to see a patient go from 0% donor (on the day of transplant) and over time we test more samples and they get to 100% donor. 

I am not a doctor, and I admit I am oversimplifying here, but here are some charts showing trends in the percent donor versus recipients.

These are the trends doctors look for over time. 

![Example 3](/images\GoodBadUgly.png)

## How we measure
So, we have received a blood sample from a patient who recently had a transplant. Let's recap what information we already have:
- Before the transplant, we obtained a list of RECIPIENT alleles by testing them.
- Before the transplant, we obtained a list of DONOR alleles by testing them.

We now have a sample that has a mix of DONOR and RECIPIENT alleles. We just need to compare _quantitatively_ how much donor and how much recipient is present. 

Here is another picture example:
![Example 4](/images\PossibilitiesAlleles.png)

Our goal is to report out the percentage donor that is expressed. To do this we must compare the peak areas. NOTE: Peak areas are proportional to peak heights. I may use the terms interchangeably because in this case they are interchangeable.

So we must look at the peak areas and compare. Here is an example: 
![Example 5](/images\DonorRecipAlleles.png)

You can _almost_ estimate by looking at the chart. Looking at the pre-transplant testing I can tell you that the 10 and 12 peaks are donor, and the 13 and 14 peaks are the recipient. Looks like the recipient peaks are about half the size of the donor peaks -- we should actually do the math though.

We just sum up the DONOR peak areas and divide it by the total peak areas (donor + recipient).
![Math](/images\MathyStuffcHIM.png)

79% donor chimerism, yayy!

This is great. We love to see high donor percentages because it usually means things are trending well.

# Complications
Everything above is a high level overview. It is amazing how we are seeing patients who are expressing two people’s DNA! We can look at the ratio and determine how well the graft is going. 

There are some complications I purposely left for the end. I honestly think the complications are what makes it so interesting so keep reading, we are almost done!

## Hope you like math!
So the above is the math for one locus, but remember I said we test for 21 loci? So we need to do this 21 times over. Also, we run a couple dozen of these patients a day (as of 2022). Break out your TI-82 calculator, that is a lot of math!

## I lied to you about having two alleles
I lied to you about having two alleles. To quote former me, "Everyone has  two alleles, one from their mother and one from their father."

Well, that actually was a lie. Remember how I said there are around 12 different allele possibilities for a single allele? This means 1 in 12 times you may get the same alleles from your mother as your father. That’s okay, it means that you have one allele expressed sometimes, not two. It changes the math, but let’s not get into that. 

## Sometimes alleles overlap in post-analysis
Sometimes a donor and recipient share an allele, or maybe two! Let’s say a recipient has a 12 and 13 allele, but the donor has a 13 and 14 allele. They share the 13 allele! This means that in post-chimerism analysis, we really can’t use the 13 allele to figure out whether the donor or recipient is present. That's totally fine, we can still use the other alleles to estimate the percentage; it just changes the math equation. 

## Stutter
This is the most complicated part of the assay in my opinion. If you don’t quite understand stutter after this, it is because of my failure to explain it in two paragraphs.

We use a PCR reaction to amplify the DNA. A by-product of that PCR amplification is called _slippage_, where sometimes alleles appear where they should not be. In fact for every one _real_ allele, there is one _fake_ stutter peak. For example: if I have a 12 and 14 allele, running my DNA into the machine will show peaks at 11, 12, 13, and 14. The stutter always causes a peak at: {number of repeats} minus 1. So a 12 peak will have a stutter (or fake peak) at 11.

Our own lab keeps track of every allele and how much fake peak we expect. So before doing any math, we need to subtract the fake peaks. I excluded all of this in the above examples.

## Some loci do not work
Because of the above complications, often some of the 21 loci just are not useful. Sometimes there aren’t enough loci, other times they just aren’t accurate enough. Before the transplant we identify _informative_ and _uninformative_ loci and only use the informative ones. 

# Chimerism Calculator
Would you believe me if I told you that everything leading up to this was so that I could talk about *the chimerism calculator*? Everything above this is just relevant background info. I'll be brief. We have a chimerism calculator. I created it a few years ago and it does everything we just talked about and its unique to our Tissue Typing lab. 

You can upload an entire batch of patients (up to 96 patients at a time) and it does ALL THE MATH! It:
- Imports pre-transplant testing from recipient
- Imports pre-transplant testing from donor
- Automatically classifies informative loci
- Adjusts every peak for stutter
- Decides the correct equation based off the number of alleles
- calculates percent donor
- Creates summary sheets for every patient

This makes life so much easier: no need to do the math anymore and no more calculators on our desk. 

# Conclusion
I hope everyone gets a chance to see the chimerism assay in action. The wet work is straight-forward but exciting. We get a crazy number of samples through this assay in a day. The analysis is fun and it puts a smile on your face to see patients chimerism rise to 100% donor. I don’t know what it looks like to the patient when they get to 100% donor, but in my head, I imagine balloons and confetti. 

I hope reading this sparked some questions. We have a lot of technologists and directors that have enough combined experience to answer just about any question you may have. Bring it up! In case you can’t tell, we love talking about chimerism!

