---
layout: default
---
# Data Science Portfolio

This is the most up-to-date location for personal and school projects that I want to display. I do have projects that I do not display (either because they are incomplete, in progress, or for my personal use). I hope it gives a good sense of what I can do and where my skills are at. I aim for them to be concise snips of presentations - quick and easy-to-digest. If you have any criticism, feel free to message me on LinkedIn, which is linked on the sidebar, or my email, which is on my resume at the very bottom.

## Wordle Game AI

This project was done as part of my foundations of artificial intelligence class. Our motivation came from one of my teammates being a New York Times reader who saw their acquisition of the Wordle game and the surge in automated solvers. There are plenty of methods applied to the game with repos online. My team used existing methods as well as some which we wrote up from our class textbook - 'Artificial Intelligence: A Modern Approach' by Russel & Norvig.

### What is Wordle?

Wordle is a word guessing game. The most common variant has a word-of-the-day. This word is usually five letters long. The game allows six guesses. After each guess, the letters are shaded by the game to give the player information. A green letter means that the letter is correct and in the right position. A yellow letter means the word contains that letter but it is not positioned correctly. Lastly, an uncolored letter is not in the word.

![](/images/game_example.png)

For this project, my team built out the game, a simple UI, and four solvers/solving agents. The whole project was done in python and the repository is linked below. I focused on two types of solvers that I found interesting - a genetic algorithm based solver and a Q-learning agent.

### An Explanation of My Methods

- The genetic algorithm is based on genetics and how genes combine and mutate. There are five main parts to this method - initialization, evaluation, selection, crossover, and mutation. We initialize by picking the first two guesses randomly. From here we loop the following steps. Each word is given a fitness based on how many correct letters are guessed. For each uncolored letter, 1 fitness point is removed. For each yellow letter, 1 fitness point is added. For each green letter, 2 fitness points are added. Each new guess word has its fitness calculated. Then we select the 2 fittest, randomly combine them, and mutate each letter with some small probability.

- Q-learning was also attempted to decide optimal policy and make decisions. Our state is the previously guessed word. The reward for a correct word is 10 and for an incorrect word is -1. Our actions will be picking which word to guess next. This gives a Q-value matrix of size n-squared where n is the size of the word list. We used the Q-learning update policy:

  Q(s,a) ← Q(s,a) + α(R(s) + λ(max_a′_(Q(s′,a′)) − Q(s,a)))

  Our approach was to learn a policy once then quickly make guesses by reusing the learned policy. We also sped up the process and reduced the Q-matrix size by only calculating the values of the state-action pairs that were seen during training rather than for all pairs. Since a single policy with this idea of state would align with only a single answer word, the idea is to update the policy with multiple target words. This means the policy will not converge, but our goal is to find the words that have the highest possible utility for the most answers. Many reinforcement learning(RL) agents rely on the problem being a Markov decision process(MDP) however this description of the problem is not and thus this could have ended very badly. It worked however the results were very poor.

### Our Results  
![](/images/cmp_word_length.jpg)  
![](/images/wordle_cmp_algos.jpg)  
1. Max Entropy either performs really well or really poorly. Though this algorithm has the lowest win rate, it also takes the least amount of guesses if the algorithm wins that round. This accuracy variation is unique to this algorithm.
2. Aggregated Frequency is the top performer. This algorithm performs well across the board while maintaining one of the lowest average run times so it is determined to be efficient. It also has the highest win rate.
3. The Genetic algorithm performs second best. The metrics for Genetic algorithm performance are in line with Aggregated Frequency except slightly lower. It is a good alternative solver and still much better than human performance.
4. The "Human" performs decently. This is consistent with what most of us experience in a given game of Wordle when solving it ourselves. We win most games after 4-5 guesses.
5. Q Learning has suboptimal run time performance. This makes Q Learning not a viable option for solving the game as it takes significantly more time to run than all other algorithms to the extent that we are barely able to visual all other average run times for the algorithms. Additionally, we note that Q Learning is only 3rd best in terms of win rate and takes the most number of guesses whether the game is won or lost. Hence, Q Learning is the least ideal to apply to the game of Wordle.

### Repo & Report
<a href="/pdfs/Priyank_Shelat_Team8_Project_Report.pdf" target="_blank">Project Report</a>  
<a href="https://github.com/emilyjcosta5/AI-Final-Project" target="_blank">Github Repo</a>

## Computer Vision Micro-Projects
These are a series of smaller projects done as part of my computer vision class. I will give a brief description of each and link my repo for them at the end.

### Motion Detection Using Simple Image Filtering

### Image Mosaicking

### Stereo Vision Dense Disparity Mapping

## Air Quality Analysis

## Mars Rover Classification

## Audio Source Separation






--------------------------------------------------------------------------
Text can be **bold**, _italic_, or ~~strikethrough~~.

[Link to another page](./another-page.html).

There should be whitespace between paragraphs.

There should be whitespace between paragraphs. We recommend including a README, or a file with information about your project.

# Header 1

This is a normal paragraph following a header. GitHub is a code hosting platform for version control and collaboration. It lets you and others work together on projects from anywhere.

## Header 2

> This is a blockquote following a header.
>
> When something is important enough, you do it even if the odds are not in your favor.

### Header 3

```js
// Javascript code with syntax highlighting.
var fun = function lang(l) {
  dateformat.i18n = require('./lang/' + l)
  return true;
}
```

```ruby
# Ruby code with syntax highlighting
GitHubPages::Dependencies.gems.each do |gem, version|
  s.add_dependency(gem, "= #{version}")
end
```

#### Header 4

*   This is an unordered list following a header.
*   This is an unordered list following a header.
*   This is an unordered list following a header.

##### Header 5

1.  This is an ordered list following a header.
2.  This is an ordered list following a header.
3.  This is an ordered list following a header.

###### Header 6

| head1        | head two          | three |
|:-------------|:------------------|:------|
| ok           | good swedish fish | nice  |
| out of stock | good and plenty   | nice  |
| ok           | good `oreos`      | hmm   |
| ok           | good `zoute` drop | yumm  |

### There's a horizontal rule below this.

* * *

### Here is an unordered list:

*   Item foo
*   Item bar
*   Item baz
*   Item zip

### And an ordered list:

1.  Item one
1.  Item two
1.  Item three
1.  Item four

### And a nested list:

- level 1 item
  - level 2 item
  - level 2 item
    - level 3 item
    - level 3 item
- level 1 item
  - level 2 item
  - level 2 item
  - level 2 item
- level 1 item
  - level 2 item
  - level 2 item
- level 1 item

### Small image

![Octocat](https://github.githubassets.com/images/icons/emoji/octocat.png)

### Large image

![Branching](https://guides.github.com/activities/hello-world/branching.png)


### Definition lists can be used with HTML syntax.

<dl>
<dt>Name</dt>
<dd>Godzilla</dd>
<dt>Born</dt>
<dd>1952</dd>
<dt>Birthplace</dt>
<dd>Japan</dd>
<dt>Color</dt>
<dd>Green</dd>
</dl>

```
Long, single-line code blocks should not wrap. They should horizontally scroll if they are too long. This line should be long enough to demonstrate this.
```

```
The final element.
```
