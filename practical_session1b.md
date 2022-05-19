---
title: Session 1, part 2
description: Simple keypress responses
---

## The plan for the rest of this session 

Next we will look at code for a simple grammaticality judgment experiment - this is quite simple, but introduces you to another trial type and gives us a few more things to play with.

## A grammaticality judgment experiment

You need two files for this experiment (`grammaticality_judgments.html` and `grammaticality_judgments.js`), plus a copy of jsPsych to bundle up with them - those are all in this zip file:
<a href="code/grammaticality_judgments.zip" download> Download grammaticality_judgments.zip</a> 

Unzip this in your `online_experiments_practicals` folder, alongside the `cospeech_gesture` folder. Assuming you have the directory structure all right, this code should run on your local computer (just open the `grammaticality_judgments.html` file in your browser) or you can upload it to the tullo.co.uk server and play with it there, using the same sort of directory structure - it needs to be in `public_html`, e.g. if you have exactly the same directory structure on the server then the code would be in `public_html/online_experiments_practicals/grammaticality_judgments/`, and the URL for your experiment would be http://tullo.co.uk/~USERNAME/online_experiments_practicals/grammaticality_judgments/grammaticality_judgments.html. 

First, get the code and run through it so you can check it runs, and you can see what it does. Then take a look at the HTML and js files in your code editor (we are recommending Visual Studio Code).

You will see that `grammaticality_judgments.html` doesn't have much in it - all that does is use the `<script>...</script>` tag to load a couple of plugins plus the file `grammaticality_judgments.js`.

`grammaticality_judgments.js` is probably one of the simplest types of experiments you could build. It has 4 grammaticality judgment trials, where participants provide a keypress response: y or n for "yes, this sentence could be spoken by a native speaker of English" or "no, it could not". Note that is slightly different from what Sprouse (2011) does - he asks people for a numerical response rather than a simple yes-no, we'll come to that later.

As with the co-speech gesture experiment, there is also a little bit of wrapper around those 4 trials - a consent screen where participants click a button to give consent and proceed to the experiment, some information screens before the experiment proper starts, and then a final screen where you can display debrief information, completion codes etc to participants.

The code starts by laying out the grammaticality judgment trials. Each judgment trial involves showing the participant a sentence and getting a single keypress response from them, which we can achieve using the `html-keyboard-response` plugin from jsPsych. Details of the options for that plugin are in the [jsPsych documentation](https://www.jspsych.org/6.3/plugins/jspsych-html-keyboard-response/). We are using the `stimulus` parameter to hold the sentence the participant is judging, `prompt` reminds the participant what they are supposed to be doing, and `choices` shows the list of keyboard responses they are allowed to provide - in this case we only accept y or n keypresses, so everything else is ignored. So the code for one judgment trial looks like this:

```js
var judgment_trial_1 = {
    type: 'html-keyboard-response',
    stimulus: "Where did Blake buy the hat?",
    prompt: "<p><em>Could this sentence be spoken by a native speaker of English? Press y or n</em></p>",
    choices: ['y','n']
};
```

The only slightly fancy thing in there is that in the prompt I am using some HTML tags - the `<p>...</p>` tag to put the prompt in its own paragraph (it vertically separates the prompt from the stimulus a bit, which I think looks better) and also the `<em>...</em>` tag to make the prompt in italics (again, to visually separate it from the stimulus sentence - em stands for *emphasis* I think).

The code defines 4 such trials, inspired by the type of sentences used in Sprouse (2011).

That's basically the only interesting part of the code! The rest is the consent, information and debrief screens that you saw in th ecospeech gesture experiment - they are exactly the same, except that there is a little bit of additional html formatting to get some text in colour (look at the code if you are interested).

Once all the various trials are defined, we can stick them together in a timeline for the experiment. The timeline is very simple and is just a list of all the trials we have created up to this point:
```js
var full_timeline = [consent_screen,instruction_screen_1,instruction_screen_2,
                    judgment_trial_1,judgment_trial_2,judgment_trial_3,judgment_trial_4,
                    final_screen];
```

Then to run the experiment we call `jsPsych.init` with this `full_timeline` variable we have created. We also tell it to show the raw data on-screen at the end of the experiment (using the `on_finish` parameter of `jsPsych.init`). Obviously in a real experiment you would save the data rather than just showing it back to the participant, we'll show you how to do that later in the course!

```js
jsPsych.init({
    timeline: full_timeline,
    on_finish: function(){jsPsych.data.displayData('csv')}
});
```


## Exercises with the grammaticality judgment experiment code

Attempt these problems.

- How would you add extra judgment trials to this code, to ask people about the grammaticality of some additional sentences? Try adding a few new judgment trials.
- As before, have a look at the data that is displayed at the end of the experiment. Can you see where the stimulus and the response for each trial is recorded? Is there anything in the data you weren't expecting or don't understand? 
- Can you change the information screens so that participants progress to the next screen by pressing any key on the keyboard rather than clicking a button? 
- Can you change the judgment trials so participants can provide a single-digit numerical response, e.g. any number between 1 and 9, rather than simply allowing y or n as valid responses? That numerical response could indicate a more continuous scale of grammaticality, a bit more like Sprouse's magnitude estimation task.
- Can you change the judgment trials so the participants provide their responses by clicking yes/no buttons, rather than using the keyboard? 
- How would you use buttons to provide a wider range of responses (e.g. "completely fine", "a little strange", "very strange", ...)?
- [More challenging] Sprouse (2011) actually uses a rather different layout and type of response: he has participants enter a numerical value for each sentence, has multiple judgments presented on a single page, and provides a reference sentence (e.g. an example sentence which should receive a score of 100) at the top of each page. Can you replace our simple yes/no judgment trials with something more like what Sprouse did, using the jsPsych [survey-text plugin](https://www.jspsych.org/plugins/jspsych-survey-text/)?

## Optional: a version of the code using timeline variables

You might have noticed that in `grammaticality_judgments.js` we quite laboriously lay out 4 judgment trials, all of which are identical in structure apart from the `stimulus` parameter. There are a couple of more efficient ways to do this, one of which is by using jsPsych timeline variables. If you'd like to see how that's done, look at the file `grammaticality_judgments_with_timeline_variables.js` (included in the zip), then see if you can get that to run by telling `grammaticality_judgments.html` to load the timeline javascript file rather than the basic one (by editing line 9 of the html file).

You might be wondering what the advantage of using this slightly fancier code is, and/or thinking "I could just copy and paste the judgment trials and edit them directly, isn't that simpler?". It maybe is conceptually simpler to copy and paste simple code, but it's also more error prone, since it relies on you not making any mistakes in copying, pasting and editing the same little block of code over and over again. In general, if you find yourself doing a lot of copying, pasting and editing when writing code it's a sign that you are doing something manually that the computer could do for you automatically, more quickly and with less chance of errors. 


## Re-use

All aspects of this work are licensed under a [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/).
