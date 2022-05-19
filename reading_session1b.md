---
title: Session 1, part 2
description: Grammaticality judgements
---

## The plan for the rest of this session 

Next up we'll look at grammaticality judgments - not because I am especially interested in syntax, but because this is a very simple sort of data to collect (in its simplest form, simple yes/no responses on whether or not a particular sentence could be produced by a native speaker), so coding it up is going to be easy and gives us the opportunity to look at some slightly longer experiments. We'll look at a paper published in 2011, in the early days of widespread use of online data collection, which verifies that 'traditional' in-lab judgments match those collected online from MTurk. Then in [the accompanying practical](practical_session1b.md) you'll get a chance to look at some very simple jsPsych code for a grammaticality judgment experiment.

## The paper

- [Sprouse, J. (2011). A validation of Amazon Mechanical Turk for the collection of acceptability judgments in linguistic theory.
*Behavior Research Methods, 43,* 155-167.](https://doi.org/10.3758/s13428-010-0039-7)

A couple of things to note if you work through the paper:
- Sprouse uses text boxes for a magnitude estimation task - participants are asked to numerically score sentences for grammaticality. In the practical we'll start by looking at a simpler task where you simply give a yes/no decision, purely because that's an easier place to start with the code.
- Note that Sprouse reports paying his online participants less than his lab participants - see comments in [the preparatory reading](reading_pre.md) and the my remarks in the initial lecture about variation in pay on MTurk and generally low rates.
- Sprouse's technique for dealing with repeat participants is not ideal - he allows participants to take the experiment multiple times, but then rejects repeat entries. This is bad because it potentially results in people inadvertently participating repeatedly and yet not being paid; also, rejections affect workers' ratings on MTurk which restricts the tasks they can access, so people tend to get quite upset if you reject their submission. I'm not sure what the situation was when Sprouse was conducting this study, but nowadays there are actually straightforward ways to prevent people from participating repeatedly. On MTurk you can use the qualifications system, awarding a qualification to people who complete your study and requiring that people *not* have this qualification to participate; on Prolific repeat participation in a single study is blocked automatically and there's a simple exclusion option to block people who have already taken a related study in the prescreener. Using one of these options means that nobody wastes their time and participates repeatedly for no pay, you don't have to filter out repeat participants and deal with upset people - in short, don't use the allow-then-reject procedure that Sprouse reports.
- Sprouse gives a long list of limitations of online data collection at the end of the paper, including technical limitations around audio, reaction times, randomisation. The technology has moved on since Sprouse wrote the paper, and jsPsych is going to handle all these problems for us. His other remarks on e.g. verifying that participants understand the task still stand of course.


## Re-use

All aspects of this work are licensed under a [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/).
