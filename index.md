This is the webpage for the 2-day version of the course Online Experiments for Language Scientists, set up for the Deparment of English Language and Linguistics at the University of Birmingham, May 2022. 

The course is taught by [Kenny Smith](http://www.lel.ed.ac.uk/~kenny/). The best way to get in touch with me before/after the course is by email to [kenny.smith@ed.ac.uk](mailto:kenny.smith@ed.ac.uk). My colleague in Edinburgh, our tech guru and javascript whizz [Alisdair Tullo](https://tullo.co.uk/alisdair/), also set up the server we'll be using on the course, and normally teaches this stuff with me.

For a longer version of the course, see e.g. [our Autumn 2021 semester-long course at Edinburgh](https://kennysmithed.github.io/oels2021/).

## Course summary

Many areas in the language sciences rely on collecting data from human participants, from grammaticality judgments to behavioural responses (key presses, mouse clicks, spoken responses). While data collection traditionally takes place face-to-face, recent years have seen an explosion in the use of online data collection: participants take part remotely, providing responses through a survey tool or custom experimental software running in their web browser, with surveys or experiments often being advertised on crowdsourcing websites like Amazon Mechanical Turk (MTurk) or Prolific. Online methods potentially allow rapid and low-effort collection of large samples, and are particularly useful in situations where face-to-face data collection is not possible (e.g. during a pandemic); however, building and running these experiments poses challenges that differ from lab-based methods.

This course will provide a rapid tour of online experimental methods in the language sciences, covering a range of paradigms, from simple text stimuli and keyboard responses (e.g. as required for grammaticality judgments) through more standard psycholinguistic methods (images, sounds and video stimuli, mouse-click responses) up to more ambitious and challenging techniques (we'll cover voice recording, which is often useful for linguists). We'll split the two days into a morning and afternoon session; each session will start by a short lecture/Q&A, then we'll look at code (written in javascript using jsPsych) to implement a similar experiment. I'll aim to cover at least one experimental paradigm per session, with optional add-ons for people who are making rapid progress; the techniques are fairly general so hopefully we will cover something close-ish to what you need - and if not, ask for advice! We’ll also look at the main platforms for reaching paid participants, e.g. Prolific and MTurk, and discuss some of the challenges around data quality and the ethics of running on those platforms.

No prior experience in coding is assumed, but you have to be prepared to dive in and try things out!

## Class times

Thursday and Friday 26th-27th May 2022, 9.30am-12.30pm and 1.30pm-4.30pm.


## Course Materials

Prior to the course starting, you'll need to do some preparatory work - reading a couple of short blog-type summaries I think will be useful to help set the scene and then (more important), working through some basic preparation by working through some of the [Online Experiments with jsPsych](https://softdev.ppls.ed.ac.uk/online_experiments/index.html) tutorial written by my colleague at Edinburgh, [Alisdair Tullo](https://tullo.co.uk/alisdair/). Get as far as you can with this - and don't worry if you get stuck, I can help you get unstuck in the practicals when the course starts! If you get through this I'd also encourage you to work through as much of the Day 1 materials as you can, since it'll mean we can make the most of the face-to-face time we have during the course proper.

Once the course starts, each session will start with a short lecture/Q&A and a programming practical.

Each lecture comes with an associated reading (a paper plus some accompanying notes of mine) - you don't have to read the papers (and that is definitely less important than doing the practical preparation), I'll summarise the content in the lecture.

The programming assignment involves looking at (and editing) some code which implements a language-related experiment; we'll use most of our time as lab time to work on the programming task and get help with programming difficulties or questions you have.

There are also some post-course materials intended to give you some additional tips on getting your experiment online, managing your participants, and so on.

### Preparatory materials

Do your best to work through the following preparatory materials.

- *Scientific content:* lab vs online data collection
- *Technical content:* jspsych basics, intro to crowdsourcing platforms
- [Reading](reading_pre.md)
- [Programming task](practical_pre.md)

### Thursday morning: Co-speech gesture, grammaticality judgments

Slightly ambitiously the plan is to cram a couple of basic experimental paradigms into the first session - hopefully the paradigms and the code are simple enough that we can manage this, but if not we can just bleed over into the afternoon and compress later stuff.

- *Scientific content:* co-speech gesture and mental timelines; lab vs online grammaticality judgments
- *Technical content:* video and text stimuli; simple button-press, key-press and text responses; collecting reaction time data
- [Reading part 1](reading_session1a.md)
- [Programming task part 1](practical_session1a.md)
- [Reading part 2](reading_session1b.md)
- [Programming task part 2](practical_session1b.md)


### Thursday afternoon: Word learning / frequency learning

- *Scientific content:* probability matching and regularisation
- *Technical content:* randomisation within and across trials; using trial data for contingent trials; filtering and saving data 
- [Reading](reading_session2.md)
- [Programming task](practical_session2.md)

### Friday morning: Audio stimuli

- *Scientific content:* speech perception, social influences on phonetic adaptation
- *Technical content:* Audio, trial data again, saving data trial by trial
- [Reading](reading_session3.md)
- [Programming task](practical_session3.md)

### Friday afternoon: Confederate priming

- *Scientific content:* syntactic priming and alignment
- *Technical content:*  Audio recording, more randomisation stuff, custom preload lists, reading trial lists from CSV
- [Reading](reading_session4.md)
- [Programming task](practical_session4.md)*not ready yet*

### Post-course materials: Getting your experiment online

- *Scientific content:* None!
- *Technical content:* How to set up a server, launch and pay participants, manage qualifications, etc
- [Reading: how to get your experiment online](reading_post.md)*not ready yet*


## Re-use

All aspects of this work are licensed under a [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/).
