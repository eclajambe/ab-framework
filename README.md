# A/B Framework

This repository contains HTML/CSS for the A/B framework. Content used in this repository is used for demonstration purposes only and should not be considered final.

Below are a few things I felt needed a bit more context:

## CSS

For the sake of clarity, I've separated styling that should be globally accessible for all tools (regardless of framework) from styling specific to the A/B framework.

* [/css/tools-global.css](https://github.com/eclajambe/ab-framework/blob/master/css/tools-global.css) - Styling across all tools on concur.com
* [/css/tools-framework-ab.css](https://github.com/eclajambe/ab-framework/blob/master/css/tools-framework-ab.css) - Styling specific to A/B framework tools

## Progress Bar

### #ab__progress_bar

User progress should be calculated as such: One less than the index of the current question, divided by the total number of question screens in the tool (including both question and question-content screens), multiplied by 100. Or, as a formula:  

```
([Current screen] – 1) / [Total screens] * 100 = [Completion %]
```
The completion % should be displayed to the user as a whole number, with no decimal places. 

Ex: A user is on question 8 of a tool with 16 total question screens, is 43% complete: 

```
([8] – 1) / [16] * 100 = [43%] 
```

## Segment List

### #ab__segment_list 

Each list item in the #ab__segment_list should have only *one* of the following status classes applied at any given time, to give users an indication of which segment they're currently on: 

* **Future** (.future) - Use this class to indicate any segments that have not yet been visited.
* **Current** (.current) - Use this class to indicate the segment the user is currently viewing.
* **Completed** (.completed) - Use this class to indicate any segemnts that users have already completed.

Classes should be added/removed dynamically, as users progress through the test.


## Question Input

### #ab__user_input

The only bit of JS used in this code is found here, and is used only to demonstrate how it should look when a user clicks on a choice to make their selection.  

For this type of input (.boolean), making a choice of either "Yes" or "No" should automatically advance the user to the next screen, after a slight delay (explained below). Other inputs in the future - text input, for instance - might require users to click a button after their input is complete. 

A delay of 500ms should be applied after a user makes a selection in order to briefly show the .selected state of the input before taking them to the next screen. 
