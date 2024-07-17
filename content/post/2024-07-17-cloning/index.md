---
title: "Molecular cloning, or why some biologists become superstitious"
date: 2024-07-17T08:19:07-05:00
draft: false
description: "Molecular cloning is a ubiquitous and essential molecular biology technique, yet it’s the bane of many a scientist's existence. Why does cloning make biologists contemplate career changes? And does it have to be this way?"
categories: 
- molecular biology
- metascience
---

Molecular cloning: it is a ubiquitous and essential molecular biology technique, yet it’s the bane of many a scientist's existence. If you've ever overheard a biologist muttering curses at a petri dish, chances are their cloning has gone wrong.

Don't believe me? Let's take a peek at the [r/labrats](https://www.reddit.com/r/labrats/) subreddit, where desperate researchers bare their souls:

“[For cloning, the most reliable method is a contract with a demon, higher the better.”](https://www.reddit.com/r/labrats/comments/15sow73/comment/jwfj80q/?utm_source=share&utm_medium=web2x&context=3)

"[But of course the gods of cloning have different ideas about my free time. None of the reactions, even the control one, succeed.](https://www.reddit.com/r/labrats/comments/11hwtol/i_just_feel_defeated/)”

“[Cloning, like most of molecular biology is black magic. I've never met more superstitious people then molecular biologists, and seemingly the more superstitious the better they were in the lab.](https://www.reddit.com/r/labrats/comments/pclq17/comment/hajvgst/?utm_source=share&utm_medium=web3x&utm_name=web3xcss&utm_term=1&utm_content=share_button)”

Nothing says "doing science" quite like demonic bargaining, right?

Even when you think you’ve emerged triumphant from your cloning, there’s a good chance you haven’t. In a recent analysis of 2,521 plasmids constructed by researchers and sent to molecular cloning company VectorBuilder, [nearly half contained errors](https://www.biorxiv.org/content/10.1101/2024.06.17.596931v1) compared to the reference sequence. Abysmal. (if you’re reading this and know of other interesting cloning related studies, let me know!)

To be fair, cloning isn’t the only dark art in molecular biology. One study finds human-designed [PCR fails 37-45% of the time](https://www.biorxiv.org/content/10.1101/2021.08.12.455589v1.full). A study investigating how well 2165 recombinant human proteins express in hamster cells found that [41% of human proteins did not have detectable expression](https://www.biorxiv.org/content/10.1101/2022.12.12.520152v1?s=09). Perhaps I will think more extensively about these other methods in the future. But I suspect learning from cloning will provide insight into these others too.

Why does cloning make biologists contemplate career changes? And does it have to be this way?

## Cloning 101

First, a little background. Molecular cloning is the process of assembling pieces of DNA into a circle (a plasmid) that can replicate inside a host organism. It's the first step in many critical tasks, from protein production to gene editing. The process looks like this:.

1. Design your plasmid
2. Assemble DNA fragments
3. Transform host cells with the assembled DNA
4. Identify clonal colonies with the correctly assembled plasmid

End to end, this process should take just a few days. Emphasis on should.

## Plagued by uninformative latent failure

Unfortunately, cloning outcomes can be quite variable, even for experienced practitioners. Sometimes it works flawlessly on the first try, leaving you feeling like a real scientist. Other times, it works once but refuses to cooperate ever again. And then there are those dark times when it stubbornly fails, again and again for weeks, leaving you with no choice but to sacrifice your first-born child. Wait, are we still talking about cloning?

When cloning fails, it's not very forthcoming about why. There are only a few observable failure states:

1. Cells with incorrect plasmids (misassembled, mutated, or containing part/backbone plasmids)
2. No cells growing at all

That's all the feedback you get. Each failure could be the result of any number of different errors. I call this uninformative failure.

Another thing to notice is that failure is observed far after a potential error is made. This is called latent failure. You have to carry out the whole process to see if you did something wrong, making debugging cycles take forever.

{{< figure src="fig1.png" caption="Latent failure of cloning" >}}

## Debugging execution and design errors

So what do you do when your cloning has failed? The typical advice is:

1. Do it again (and add a positive control this time, you rookie)
2. Order new reagents or use a different kit (because clearly, it's the reagents' fault, not yours)
3. Check your fragments and regenerate your input sample (just in case)
4. [Trust nobody](https://bakingbiologist.wordpress.com/2012/10/05/starting-grad-school-trust-nobody/) (not even yourself)

With experience, you become better at catching execution errors, and you can develop intuitions which can help you narrow down what follow up conditions to try.

But even if you execute protocols perfectly, your cloning can still fail. Why? Because sometimes, the very DNA you're trying to clone is the problem.

Cloning involves introducing new DNA sequences into a host organism. But the protein you're trying to clone might be toxic to the host, or the DNA might contain hidden elements that produce unexpected, harmful products (called [cryptic genetic elements](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0136396)), or the plasmid may contain sequences such as repeats that make it unstable. Even for hosts like *E. coli*, we can't always predict whether it will tolerate a particular DNA sequence.

In lieu of perfect predictability, scientists have come up with many "[rules](https://pubmed.ncbi.nlm.nih.gov/16472168/)" for designing plasmids and DNA fragments. Use tightly regulated expression systems! Reduce repetitive regions! Use efficient overhangs! For beginners to cloning, understanding why these rules exist by unintentionally violating them is almost a rite of passage. I know it was for me.

The problem? Not all, but many rules are context- and host-dependent and only become apparent after years of experience. Current plasmid design systems (Benchling, SnapGene) incorporate some basic rule-checking, but they can't account for the diversity of sequences that scientists want to clone. Instead, the state of the art in plasmid design error-checking is to copy and paste your plasmid into various web servers to predict things about your plasmid, and to have your most experienced cloning guru look over your design—bless them.

{{< figure src="fig1.png" caption="Each failure state could have been caused by one of many errors. Note this diagram does not aim to be comprehensive." >}}

## The future of cloning

Faced with these challenges, some biologists are turning to alternative methods. "[Cloning-free](https://genomebiology.biomedcentral.com/articles/10.1186/s13059-015-0653-x)" techniques, outsourcing to companies (Genscript, VectorBuilder, Twist), and "[cell-free cloning](https://fnkprddata.blob.core.windows.net/domestic/data/datasheet/ORC/MS0011-A.pdf)" are all attempts to avoid the dreaded cloning.

But in many cases, cloning simply must be done. What can be done to make it less potentially painful? Here are a few ideas:

1. **Reducing execution variance**: Ideally, you would never have to question whether something went wrong due to human execution error. One development in this vein is [benchtop cloning automation](https://telesisbio.com/products/bioxp-system/bioxp-3250-system/), although at $25,000 I’m not sure how appealing it is to labs. For the price of two of those you could hire a human cloning machine—a grad student.
2. **Predictive modeling**: We need better models to predict how DNA sequences will behave in host organisms. Many already exist, for example [transcription](https://www.nature.com/articles/s41467-022-32829-5) and [translation](https://pubmed.ncbi.nlm.nih.gov/21601672/) prediction in *E. coli*, and we need to use them more. This could help us identify potential issues before we even start cloning.
3. **Better design tools**: DNA design software could incorporate more sophisticated rules and predictive models, helping scientists create sequences that are more likely to work. Large language models still lag quite a bit behind humans on answering questions on cloning related tasks ([LAB-bench](https://arxiv.org/abs/2407.10362)), but I wouldn’t be surprised if that changes soon.
4. **Interpretable intermediate states**: If we could easily check the correctness of each step, debugging cycles could be shortened.

Because of how common it is, I think it is easy to think of cloning as being a procedure with certain success if you don’t mess up (and there are many ways to mess up). But cloning is in part an experiment to see whether a certain host organism will tolerate a certain plasmid.

And hey, if all else fails, there's always that contract with a demon to consider.

## Appendix

Some other cloning-related odds and ends that may be of interest: 

- Your clonal colonies may not actually be clonal. See “[High rates of plasmid cotransformation in E. coli overturn the clonality myth and reveal colony development](https://www.nature.com/articles/s41598-022-14598-9)”
- Sam Rodriques on why cloning is hard to automate ([tweet](https://twitter.com/SGRodriques/status/1785855017137975801)):
    
    > E.g. in cloning, everyone has a design workflow they prefer, but any individual plasmid will usually require some modification in the design process. E.g. maybe the sequence isn’t available on Addgene, maybe the restriction site you want to use is methylated, maybe there are repeats, etc. You can write a script to automate design of any individual plasmid (or maybe any individual backbone), but the same script only rarely works across many plasmids. Everything is an edge case.
    > 
- DNA quantification is different from instrument to instrument, as much as [several fold different](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0305650). Thanks to Niko McCarty for surfacing this paper.
    
    {{< figure src="fig3.png" caption="Qubit is quite different compared to DeNovix and NanoDrop" >}}
    

## Acknowledgements

Thank you to Laura Quinto and Chase Armer for looking over drafts of this piece and providing feedback.

## **Other similar essays I enjoyed**

- [Too much Tacit](https://twitter.com/koeng101/status/1793123441882902798) (Keoni Gandall)
- [Why is machine learning 'hard'?](https://ai.stanford.edu/~zayd/why-is-machine-learning-hard.html) (S. Zayd Enam)