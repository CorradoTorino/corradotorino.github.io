---
layout: post
title: Cognitive Biases on Estimations
thumbnail-img: /assets/img/2021-10-26-range.jpg
share-img: /assets/img/2021-10-26-range.jpg
tags: [bookreview, Thinking-Fast-and-Slow, learning, estimation, cognitive-biases, WYSIATI]
readtime: true
---
Make no mistake, millions of years of human evolution shaped us to deal better with fight-or-flight choices rather than carefully deal with the complexity of software development. Let’s explore some of our inborn cognitive biases. We’ll understand how these irrationalities can influence our estimations, make us overconfident or too optimistic and make wrong decisions. And why explore them? Because awareness is the first step to any change.

## “Thinking, Fast and Slow” On Estimations

When I started as a software engineer I had the feeling that I was not good at providing reliable estimations. I was not happy with it and I believed that it would become a serious impediment for my growth. However, very soon I had the confirmation that I was not the only one. I realized that it was a common pitfall in our profession. Like a disease written in the DNA of the SW engineers. And I was not so wrong with this perception. Infact, you can imagine my relief when I read from a Nobel prize that this issue has a name: the planning fallacy and it’s embedded in the very nature of the human being. This is only one of the uncountable aha moments that I felt reading the book “Thinking, Fast and Slow” by Daniel Kahnemann. I cannot recommend this reading more. For me it was mind blowing. In its pages I found the explanation to a lot of behaviors and aspects affecting not only my professional context but also my personal sphere. The cognitive bias and the heuristic shown there helps to understand a variety of topics that can span from the relevance of storytelling to the attractiveness of conspiracy theories, from the price of a policy insurance to the motivation of buying a lottery ticket. But, let’s stay focused here on the biases that are more strictiling affecting SW developments and in particular for planning and estimations.
The Two Systems: The Fast & The Slow
I don’t want to go into too much detail, but in order to appreciate our cognitive biases, we need to clarify a couple of key concepts. The first one is the duality of our mind. This is the most important insight to understand the fundamental reasonings of our heuristics. In fact, we can consider ourselves governed by two characters: the Fast and the Slow. Although their effects are real, they cannot be physically mapped to somes places in our brain. We need to think of them metaphorically. For simplicity and avoid confusion we can call it System 1 (the fast) and System 2 (the slow). From on hand, you can think of System 1 like a cache, cheap and fast. On the other hand, System 2 is like a Business Layer, slow and expensive. In fact, System 1 operates automatically, without any effort needed by ourselves and without any voluntary control. It operates mostly using pattern matching. Thanks to System 1 we are able to run when we perceive an immediate danger and we can drive a car on an empty road. On the other hand, System 2 requires our full attention to make decisions. Thanks to System 2 we can perform complex arithmetic operations, write algorithms or drive a tuk tuk in the busy streets of Bangkok. 
The two systems work in synergy and the lazy System2 delegates as much as possible of the work to System 1. From time to time, System 1 needs help from System 2, for example when some new situations happen that are not handled automatically. Then, the most conscious part of ourselves takes control and makes decisions. However, keep in mind that usage of System 2 is expensive, cannot work for too long and handles very bad multi threading.
Most of our cognitive biases boils down to the interaction of these two systems. For example, the pre-work done by System1 influences the decisions of System 2. This is what happens when we are biased by anchoring our estimations and guesses to the wrong facts. Or it can bring us on the Halo effect, where in a job interview we are not able to evaluate a candidate rationally because our first impression changes the very meaning of the traits we observe after.

## WYSIATI: What You See Is All There Is

System 1 excels creating stories with available data and it’s deeply optimized to find coherence in it. It does not take care too much on the quality and quantity of the input information. System 1 works mainly with activated data. An important aspect is that all the information that has not been retrieved (even unconsciously) simply does not exist for it. And it doesn’t wonder to jump to conclusions to create coherence in the story even with missing pieces. This is the essence of WYSIATI: which stands for What You See Is All There Is. At a first glance it appears to me nothing special, but I learned that WYSIATI is a fundamental principle that explains a lot of our cognitive biases. Let’s give the example of overconfidence. It can affect our estimation: due to WYSIATI we are not able to consciously judge the possibilities of the things that can go wrong. System1 is just seeing the best case scenario and the rest simply does not exist. The preprocessed information passed to the System 2 is already biased and you can easily guess 
the consequences.  
Nitpicking Details
I saw the effect of WYSIATI in action too many times in planning and refinement sessions. Too often software engineers don’t ask enough questions in order to challenge assumptions on user stories. Nevertheless, this lack of information does not prevent them from providing estimations and numbers on which they feel comfortable and confident.  
Let's make an example, the product manager asks you to evaluate a simple integration with an external API. You start thinking about the use case scenarios and how you can implement it. But in most of the cases you provide an estimation that considers mainly a solution that fits in your head. Very often this is a best case scenario that does not take in account all the rainy cases. What happen when the external system is down, the network is unreliable, the authentication or authorization fail, the external API has undocumented behavuiors and so on..
But then, what can we do to reduce the negative effects of WYSIATI? Unfortunately simply knowing its existence and consciously trying to avoid it does not work. In fact, it has been proven that  even when people are put in front of the evidence of their cognitive biases, they cannot escape from repeating the same error again and again. My advice is clear and crystal: add more details and make visible the information so you can see it! Did you ever notice that when more information is provided in the user stories then the numbers associated with their estimations growth? 
I invite you to do an experiment. First run an estimation of a user story in your team. Then, run a three amigo BDD sessions and add to the user story all the tests you discover during this work. Then, repeat the estimation showing to the team the user story together with all these tests that need to be implemented. Guess what? The estimation will be bigger. Why? In both the estimation sessions we had the same people, they knew what to do! But in the first session the information was not ready to use in their System 2: What You See Is All There Is…

## Divide Et Impera

In my previous post about [Why Nurturing Broad Interests and Skills Instead of Rushing to Specialize](https://corradocalzoni.com/2021-10-26-why-nurturing-broad-interests-and-skills-instead-of-rushing-to-specialize/)[^1] I explained the difference between kind learning environments and wicked learning environments. Here, I want to stress that System 1 is working very well in kind environments where you get immediate feedback and you can train often. However, a large software project is a clear example of a wicked environment, hard to predict and estimate. You do it not so often and you have feedback with weeks of delays and sometimes this feedback is misleading. On the other hand, tasks that are achievable in 2 to 8 hours can be done very often and you get quick feedback. In these cases you are training your System 1 and after a while you are able to provide reliable estimates by instinct.
Then, you can figure out why experienced senior sw engineers play with advantages in estimating small tasks, more than estimating big projects. Infact, the pattern matching of their System 1 had a lot of chances to be trained during their careers. They can provide guesses with their guts and you can trust them. But be aware: to not rely on them when estimating complex projects simply by their instincts.  
So, now you can agree with me that a good technique to debias overconfidence is to break complex features in small tasks. My personal preference is to have tasks smaller than a day (2 to 8 hours). 

## Come Back For More..

These were just some of the thoughts triggered by reading “Thinking, Fast and Slow” by Daniel Kahnemann. It’s by far not a comprehensive list. In fact if we want to focus just on cognitive bias affecting the estimation process I think we should take in account at least: 
- ***Anchoring bias***, where our estimates are influenced by an initial value called an anchor.
- ***Confirmation Bias***, where we focus too much attention to details confirming our existing beliefs and ignoring the challenging ones
- ***Optimistic bias***, where we tend to be unrealistically optimistic for events happening during the implementation,
- ***Overconfidence Bias***, where we tend to be too optimistic in our own skills and talents to solve the task,
- ***Wishful Thinking***, where we push our understanding of the user story to what might be pleasing to us, rather than on evidences
- ***Bandwagon Effect***, where we tend to align our opinions with the majority’s opinion, or what we perceive as the majority
- ***Cargo Cult***, where we follow blindly what the others do without without a real understanding
- ***Fixation and framing effect***, where we focus disproportionately on one aspect (i.e. some requirements) while ignoring others

I want to cover the implication of some of these biases in the next post. Stay tuned..

In the meanwhile, I would be very happy to hear from you how these cognitive biases impacted your developer experience. Just drop me a message, you know where you can find me. 

## References & Useful Readings

[^1]: [Why Nurturing Broad Interests and Skills Instead of Rushing to Specialize:<br>](https://corradocalzoni.com/2021-10-26-why-nurturing-broad-interests-and-skills-instead-of-rushing-to-specialize/) {:target="_blank"} https://corradocalzoni.com/2021-10-26-why-nurturing-broad-interests-and-skills-instead-of-rushing-to-specialize/
[^2]: [Cognitive Biases in Software Engineering: A Systematic Mapping Study] (https://www.researchgate.net/publication/328410759_Cognitive_Biases_in_Software_Engineering_A_Systematic_Mapping_Study
[^3]: [8 Cognitive Biases in Software Development https://thevaluable.dev/cognitive-bias-software-development/
[^4]: [Thinking, fast and slow for Software Development https://blog.migsar.com/thinking-fast-and-slow-for-software-development-8ea13e6ab4c6
[^1]: [Coding, Fast and Slow: Developers and the Psychology of Overconfidence https://betterprogramming.pub/coding-fast-and-slow-developers-and-the-psychology-of-overconfidence-433388e7aec0
[^1]: [Software Development: Fast and Slow. https://mdubakov.medium.com/software-development-fast-and-slow-3621b9cc396
[^1]: [How cognitive biases influence software development https://www.atlassian.com/blog/add-ons/how-cognitive-biases-influence-software-development
[^1]: [4 Ways To Combat Personal Biases In Design https://medium.com/paloit/4-ways-to-combat-personal-bias-in-design-3db5312e54
[^1]: [Decision Frames: How Cognitive Biases Affect UX Practitioners https://www.nngroup.com/articles/decision-framing-cognitive-bias-ux-pros/
[^1]: [Mapping Biases to Testing – The Framing Effect https://www.maaikebrinkhof.nl/2017/12/mapping-biases-to-testing-the-framing-effect/

