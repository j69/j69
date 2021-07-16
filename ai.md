# AI notes
---
we'll highlight three applications of AI that illustrate different aspects of AI. We'll return to each of them throughout the course, to deepen our understanding.

AI is a scientific discipline, like mathematics or biology. This means that AI is a collection of concepts, problems, and methods for solving them.

AI systems will typically demonstrate at least some of the following behaviors associated with human intelligence: planning, learning, reasoning, problem-solving, knowledge representation, perception, motion, and manipulation and, to a lesser extent, social intelligence and creativity.

# AI charachteristics0:

    1 Autonomy
    The ability to perform tasks in complex environments without constant guidance by a user.

    2 Adaptivity
    The ability to improve performance by learning from experience.



# Machine learning
Systems that improve their performance in a given task with more and more experience or data.

contains:

    1 Deep Learining: increase this complexity
    2 Data science :
    3 Robotics: building and programming robots so that they can operate in complex, real-world scenarios

Computer vision and speech recognition for sensing the environment
Natural language processing, information retrieval, and reasoning under uncertainty for processing instructions and predicting consequences of potential actions
Cognitive modeling and affective computing for interacting and working together with humans
Many of the robotics-related AI problems are best approached by machine learning, which makes machine learning a central branch of AI for robotics.


What is a robot?
In brief, a robot is a machine comprising sensors (which sense the environment) and actuators (which act on the environment) that can be programmed to perform sequences of actions. People used to science-fictional depictions of robots will usually think of humanoid machines walking with an awkward gait and speaking in a metallic monotone. Most real-world robots currently in use look very different as they are designed according to the application. Most applications would not benefit from the robot having human shape, just like we dont have humanoid robots to do our dishwashing but machines in which we place the dishes to be washed by jets of water.

It may not be obvious at first sight, but any kind of vehicles that have at least some level of autonomy and include sensors and actuators are also counted as robotics. On the other hand, only software based solutions such as customer service chatbot, even if they are sometimes called `software robots´ aren´t counted as (real) robotics.



General vs narrow AI
When reading the news, you might see the terms “general” and “narrow” AI. So what do these mean? Narrow AI refers to AI that handles one task. General AI, or Artificial General Intelligence (AGI) refers to a machine that can handle any intellectual task. All the AI methods we use today fall under narrow AI, with general AI being in the realm of science fiction. In fact, the ideal of AGI has been all but abandoned by the AI researchers because of lack of progress towards it in more than 50 years despite all the effort. In contrast, narrow AI makes progress in leaps and bounds.

Strong vs weak AI
A related dichotomy is “strong” and “weak” AI. This boils down to the above philosophical distinction between being intelligent and acting intelligently, which was emhpasized by Searle. Strong AI would amount to a “mind” that is genuinely intelligent and self-conscious. Weak AI is what we actually have, namely systems that exhibit intelligent behaviors despite being “mere“ computers.



Search and problem solving

Many problems can be phrased as search problems. This requires that we start by formulating the alternative choices and their consequences.
Search in practice: getting from A to B



The state space
means the set of possible situations. In the chicken-crossing puzzle, the state space consisted of ten allowed states NNNN through to FFFF (but not for example NFFF, which the puzzle rules don´t allow). If the task is to navigate from place A to place B, the state space could be the set of locations defined by their (x,y) coordinates that can be reached from the starting point A. Or we could use a constrained set of locations, for example, different street addresses so that the number of possible states is limited.

Transitions
are possible moves between one state and another, such as NNNN to FNFN. It is important to note that we only count direct transitions between neighboring states as transitions. A sequence of multiple transitions, for example, from A to C, from C to D, and from D to B (the goal), is a path rather than a single transition.

Costs
refer to the fact that, oftentimes the different transitions aren´t all alike. They can differ in ways that make some transitions more preferable or cheaper (in a not necessarily monetary sense of the word), and others most costly. We can express this by associating with each transition a certain cost. If the goal is to minimize the total distance traveled, then a natural cost is the geographical distance between states. On the other hand, the goal could actually be to minimize the time instead of the distance, in which case the natural cost would obviously be the time. If all the transitions are equal, then we can ignore the costs.


II

Interlude on the history of AI: Starting from Search
AI is arguably as old as computer science. Long before we had computers, people thought of the possibility of automatic reasoning and intelligence. As we already mentioned in Chapter 1, one of the great thinkers who considered this question was Alan Turing. In addition to the Turing test, his contributions to AI, and more generally to computer science, include the insight that anything that can be computed (= calculated using either numbers or other symbols) can be automated.

Note

Helping win WWII
Turing designed a very simple device that can compute anything that is computable. His device is known as the Turing machine. While it is a theoretical model that isn’t practically useful, it lead Turing to the invention of programmable computers: computers that can be used to carry out different tasks depending on what they were programmed to do.

So instead of having to build a different device for each task, we use the same computer for many tasks. This is the idea of programming. Today this invention sounds trivial but in Turing’s days it was far from it. Some of the early programmable computers were used during World War II to crack German secret codes, a project where Turing was also personally involved.

The term Artificial Intelligence is often attributed to John McCarthy (1927-2011) – who is often also referred to as the Father of AI – but in fact he denies coming up with the term. He was nevertheless influential in its adoption for the emerging field. The term became established when it was chosen as the topic of a summer seminar, known as the Dartmouth conference, which was organized by McCarthy and held in 1956 at Dartmouth College in New Hampshire. In the proposal to organize the seminar, McCarthy continued with Turings argument about automated computation. The proposal contains the following crucial statement:

Note

John McCarthy’s key statement about AI
'The study is to proceed on the basis of the conjecture that every aspect of learning or any other feature of intelligence can in principle be so precisely described that a machine can be made to simulate it.'

In other words, any element of intelligence can be broken down into small steps so that each of the steps is as such so simple and “mechanical” that it can be written down as a computer program. This statement was, and is still today, a conjecture, which means that we can’t really prove it to be true. Nevertheless, the idea is absolutely fundamental when it comes to the way we think about AI. We’ll return to this point of view in a little while when we talk about the philosophy of AI.

Why search and games became central in AI research
As computers developed to the level where it was feasible to experiment with practical AI algorithms in the 1950s, the most distinctive AI problems (besides cracking Nazi codes) were games. Games provided a convenient restricted domain that could be formalized easily. Board games such as checkers, chess, and recently quite prominently Go (an extremely complex strategy board game originating from China at least 2500 years ago), have inspired countless researchers, and continue to do so.

Closely related to games, search and planning techniques were an area where AI lead to great advances in the 1960s: algorithms with names such as the Minimax algorithm or Alpha-Beta Pruning, which were developed then are still the basis for game playing AI, although of course more advanced variants have been proposed over the years. In this Chapter, we will study games and planning problems on a conceptual level.



Game trees
To solve games using AI, we will introduce the concept of a game tree. The different states of the game are represented by nodes in the game tree,

In the game tree, the nodes are arranged in levels that correspond to each players turns in the game so that the “root” node of the tree (usually depicted at the top of the diagram) is the beginning position in the game.
Under root, on the second level, there are the possible states that can result from the first player’s moves We call these nodes the “children” of the root node.

Minimizing and maximizing value
In order to be able to create game AI that attempts to win the game, we attach a numerical value to each possible end result. To the board positions where X has a line of three so that Max wins, we attach the value +1, and likewise, to the positions where Min wins with three Os in a row we attach the value -1. For the positions where the board is full and neither player wins, we use the neutral value 0.

It doesn’t really matter what the values are as long as they in this order
Player 1 tries to maximize the value, and PÅlayer2 tries to minimize it.

The value of the root node = who wins
The value of the root node, which is said to be the value of the game, tells us who wins (and how much, if the outcome is not just plain win or lose): Max wins if the value of the game is +1, Min if the value is –1, and if the value is 0, then the game will end in a draw. In other games, the value may also take other values (such as the monetary value of the chips in front of you in poker for example).

This all is based on the assumption that both players choose what is best for them and that what is best for one is the worst for the other (so called "zero-sum game").

'Finding the optimal moves
Having determined the values of all the nodes in the game tree, the optimal moves can be deduced: at any Min node (where it is Min’s turn), the optimal choice is given by the child node whose value is minimal, and conversely, at any Max node (where it is Max’s turn), the optimal choice is given by the child node whose value is maximal. Sometimes there are many equally good choices that are, well, equally good, and the outcome will be the same no matter which one of them is picked.'

The Minimax algorithm
We can exploit the above concept of the value of the game to obtain an algorithm called the Minimax algorithm. It guarantees optimal game play in, theoretically speaking, any deterministic, two-person, perfect-information zero-sum game. Given a state of the game, the algorithm simply computes the values of the children of the given state and chooses the one that has the maximum value if it is Max’s turn, and the one that has the minimum value if it is Min’s turn.

The algorithm can be implemented using a few lines of code. However, we will be satisfied with having grasped the main idea. If you are interested in taking a look at the actual algorithm (alert: programming required) feel check out, for example, Wikipedia: Minimax.

The problem of massive game trees
In many games, the game tree is simply way too big to traverse in full.
If we can afford to explore only a small part of the game tree, we need a way to stop the minimax recursion before reaching an end-node, i.e., a node where the game is over and the winner is known. This is achieved by using a so called heuristic evaluation function that takes as input a board position, including the information about which player’s turn is next, and returns a score that should be an estimate of the likely outcome of the game continuing from the given board position.

'Good heuristics
Good heuristics for chess, for example, typically count the amount of material (pieces) weighted by their type: the queen is usually considered worth about two times as much as a rook, three times a knight or a bishop, and nine times as much as a pawn. The king is of course worth more than all other things combined since losing it amounts to losing the game. Further, occupying the strategically important positions near the middle of the board is considered an advantage and the heuristic assign higher value to such positions.'


The minimax algorithm presented above requires minimal changes to obtain a depth-limited version where the heuristic is returned at all nodes at a given depth limit: the depth simply refers to the number of steps that the game tree is expanded before applying a heuristic evaluation function.

the value of the game
value 0 = draw
value -1 = Min won
value +1 = Max won

Your task:
Look at the game tree starting from the below board position. Using a pencil and paper, fill in the values of the bottom-level nodes where the game is over. Note that this time some of the games end in a draw, which means that the values of the nodes is 0 (instead of –1 or 1).

Next continue filling the values of the nodes in the next level up. Since there is no branching at that level, the values on the second lowest level are the same as at the bottom level.

On the second highest level, fill in the values by choosing for each node the maximum of the values of the child nodes – as you notice, this is a MAX level. Finally, fill in the root node's value by choosing the minimum of the root node's child nodes' values. This is the value of the game.


The limitations of plain search
It may look like we have a method to solve any problem by specifying the states and transitions between them, and finding a path from the current state to our goal. Alas, things get more complicated when we want to apply AI in real world problems. Basically, the number of states in even a moderately complex real-world scenario grows out of hand, and we can’t find a solution by exhaustive search (brute force) or even by using clever heuristics.

Moreover, the transitions which take us from one state to the next when we choose an action are not deterministic. This means that whatever we choose to do will not always completely determine the outcome because there are factors that are beyond our control, and that are often unknown to us.

The algorithms we have discussed above can be adapted to handle some randomness, for example randomness in choosing cards from a shuffled deck or throwing dice. This means that we will need to introduce the concept of uncertainty and probability. Only thus we can begin to approach real-world AI instead of simple puzzles and games. This is the topic of Chapter 3.'


Odds and probability


Instead of perfect information, there is a host of 'unknown' possibilities, ranging from missing information to deliberate deception.

'Note

The history of dealing with uncertainty
The history of AI has seen various competing paradigms for handling uncertain and imprecise information. For example, you may have heard of fuzzy logic. Fuzzy logic was for a while a contender for the best approach to handle uncertain and imprecise information and used in many customer-applications such as washing machines where the machine could detect the dirtiness (a matter of degrees, not only dirty or clean) and adjust the program accordingly.

However, probability has turned out to be the best approach for reasoning under uncertainty, and almost all current AI applications are based, in at least some degree, on probabilities.'

fuzzy nechetkiy
probability can also be used to quantify and compare risks in everyday life


'
The key lesson about probability
The most important lesson about probability that we’d like you to take away is not probability calculus. Instead, it is the ability to think of uncertainty as a thing that can be quantified at least in principle. This means that we can talk about uncertainty as if it were a number: numbers can be compared (“is this thing more probable than that thing”), and they can often be measured. The numbers in probability will sometimes be somewhat subjective, but we can nevertheless critically evaluate them, and our numbers can sometimes be found to be right or wrong. In other words, the lesson is that uncertainty is not something that is beyond the scope of rational thinking and discussion.'

Note

Why quantifying uncertainty matters
If we think of uncertainty as something that can't be quantified or measured, the uncertainty aspect may become an obstacle for rational discussion. We may for example argue that since we don’t know exactly whether a vaccine may cause a harmful side-effect, it is too dangerous to use. However, this may lead us to ignore a life-threatening disease that the vaccine will eradicate. In most cases, the benefits and risks are known to sufficient precision to clearly see that one is more significant than the other.ä'


Odds - шансы



By odds, we mean for example 3:1 (three to one), which means that we expect that for every three cases of an outcome, for example winning a bet, there is one case of the opposite outcome, not winning the bet. The other way to express the same would be to say that the chances of winning are 3/4 (three in four). These are called natural frequencies since they involve only whole numbers. With whole numbers, it is easy to imagine, for example, four people out of whom, three have brown eyes. Or four days out of which it rains on three (if you’re in Helsinki).

Note

Why we use odds and not percentages
Three out of four is of course the same as 75%. (Mathematicians prefer to use fractions like 0.75 instead of percentages.) It has been found that people get confused and make mistakes more easily when dealing with fractions and percentages than with natural frequencies or odds. This is why we use natural frequencies and odds whenever convenient.

But be careful: the odds 1:5, even if it can be expressed as the number 0.2, is different from 20% probability (or probability 0.2 using the mathematicians notation). For odds that are greater than one, such as 5:1, it is easy to remember that we are not dealing with probabilities because no probability can be greater than 1 (or greater than 100%), but for odds that are less than one such as 1:5, the danger of confusion lurks around the corner. The correspondence between odds and probabilities is further demonstrated in the following exercise.

In general, if the odds in favor of an event are x:y, the probability of the event is given by x / (x+y).




As we already mentioned above, the odds 3:1 – for example three rainy days for each rainless day – corresponds to probability 0.75 (or in percentages 75%).

In general, if the odds in favor of an event are x:y, the probability of the event is given by x / (x+y).

As we also pointed out, the odds 6:2 corresponds to exactly the same probability as the odds 3:1 because for x=6 and y=2, we also get the same result: x / (x+y) = 6/(6+2) = 6/8 = 3/4 = 0.75.

Your task:

For the first three items 1–3, convert from odds to ratios of natural integers; for example from 1:1 to 1/2. Give your answer as a fraction, for example 2/3.

For the last three items 4–6, convert the probabilities into percentages (e.g. 4.2%.) Give your answer in percentages using a single decimal, for example 12.2%.




Hint: the calculations are to be calculated with a simple calculator and the formulas can be found above.

The chances of getting three of a kind in poker are about 1:46.
The chances of rain in Helsinki are 206:159.
The chances of rain in San Diego are 23:342.


Answer:

Part A is 1/47 of the whole
Part B is 46/47 of the whole

Solution:
Assuming there are no other parts,
the Whole = A + B is the denominator:
Whole = 1 + 46 = 47

Part A = 1 and Part B = 46 are numerators for each fraction.

The fractions are then:
1/47 and 46/47

Meaning:
Part A is 1/47 of the whole
Part B is 46/47 of the whole


The formula is called the Bayes rule (or the Bayes formula).

Key terminology

Prior and posterior odds
The Bayes rule can be expressed in many forms. The simplest one is in terms of odds. The idea is to take the odds for something happening (against it not happening), which we´ll write as prior odds. The word prior refers to our assessment of the odds before obtaining some new information that may be relevant. The purpose of the formula is to update the prior odds when new information becomes available, to obtain the posterior odds, or the odds after obtaining the information. (The dictionary meaning of posterior is “something that comes after, later.“)


Likelihood ratio
The above ratio (nine times higher chance of clouds on a rainy day than on a rainless day) is called the likelihood ratio. More generally, the likelihood ratio is the probability of the observation in case the event of interest (in the above, rain), divided by the probability of the observation in case of no event (in the above, no rain). Please read the previous sentence a few times. It may look a little intimidating, but it´s not impossible to digest if you just focus carefully. We will walk you through the steps in detail, just don´t lose your nerve. We´re almost there.


 В более общем плане, отношение правдоподобия - это вероятность наблюдения в случае интереса (в приведенном выше дожде), деленного на вероятность наблюдения в случае отсутствия события (в приведенном выше, без дождя).

likelihood ratio = (9/10) / (1/10) = 9

The mighty Bayes rule for converting prior odds into posterior odds is — ta-daa! — as follows:
posterior odds = likelihood ratio × prior odds (only x, not y)


Many forms of Bayes
In case you have any trouble with the following exercises, you may need to read the above material a few times and give it some time, and if that doesn´t do it, you can look for more material online. Just a word of advice: there are many different forms in which the Bayes rule can be written, and the odds form that we use isn´t the most common one. Here are a couple links that you may find useful.
Maths Doctor: Bayes' Theorem and medical testing
Better Explained: Understanding Bayes Theorem With Ratios





One of the most useful applications of the Bayes rule is the so-called naive Bayes classifier.
The Bayes classifier is a machine learning technique that can be used to classify objects such as text documents into two or more classes. The classifier is trained by analysing a set of training data, for which the correct classes are given.'

spam email filter as a running example for illustrating the idea of the naive Bayes classifier.

Why we call it “naive”
Using spam filters as an example, the idea is to think of the words as being produced by choosing one word after the other so that the choice of the word depends only on whether the message is spam or ham. This is a crude simplification of the process because it means that there is no dependency between adjacent words, and the order of the words has no significance. This is in fact why the method is called naive.
,


Zero means trouble
One problem with estimating the probabilities directly from the counts is that the zero counts lead to zero estimates. This can be quite harmful for the performance of the classifier - it easily leads to situations where the posterior odds is 0/0, which is nonsense. The simplest solution is to use a small lower bound for all probability estimates. The value 1/100000, for instance, does the job.


We will use a spam email filter as a running example for illustrating the idea of the naive Bayes classifier. Thus, the class variable indicates whether a message is spam (or “junk email”) or whether it is a legitimate message (also called “ham”). T



Machine learning

“It has been long understood that learning is a key element of intelligence. This holds both for natural intelligence - we all get smarter by learning - and artificial intelligence.”

Note

MNIST – Whats that?
Every machine learning student knows about the MNIST dataset. Fewer know what the acronym stands for. In fact, we had to look it up to be able to tell you that the M stands for Modified, and NIST stands for National Institute of Standards and Technology. Now you probably know something that an average machine learning expert doesn’t!


How not to solve the problem
An automatic digit recognizer could in principle be built manually by writing down rules such as:
if the black pixels are mostly in the form of a single loop then the label is 0
if the black pixels form two intersecting loops then the label is 8
if the black pixels are mostly in a straight vertical line in the middle of the figure then the label is 1
and so on...

This was how AI methods were mostly developed in the 1980s (so called “expert systems”). However, even for such a simple task as digit recognition, the task of writing such rules is very laborious. In fact, the above example rules wouldn’t be specific enough to be implemented by programming – we’d have to define precisely what we mean by “mostly”, “loop”, “line”, “middle”, and so on.

And even if we did all this work, the result would likely be a bad AI method because as you can see, the handwritten digits are often a bit so-and-so, and every rule would need a dozen exceptions.



Three types of machine learning
The roots of machine learning are in statistics, which can also be thought of as the art of extracting knowledge from data. Especially methods such as linear regression and Bayesian statistics, which are both already more than two centuries old (!), are even today at the heart of machine learning. For more examples and a brief history, see the timeline of machine learning (Wikipedia).

The area of machine learning is often divided in subareas according to the kinds of problems being attacked. A rough categorisation is as follows:

'Supervised learning:' We are given an input, for example a photograph with a traffic sign, and the task is to predict the correct output or label, for example which traffic sign is in the picture (speed limit, stop sign, ...). In the simplest cases, the answers are of the form yes/no. (We call these binary classification problems.)

'Unsupervised learning': There are no labels or correct outputs. The task is to discover the structure of the data: for example, grouping similar items to form “clusters”, or reducing the data to a small number of important “dimensions”. Data visualization can also be considered unsupervised learning.

'Reinforcement learning': Commonly used in situations where an AI agent like a self-driving car must operate in an environment and where feedback about good or bad choices is available with some delay. Also used in games where the outcome may be decided only at the end of the game.

The categories are somewhat overlapping and fuzzy, so a particular method can sometimes be hard to place in one category. For example, as the name suggests, so called semisupervised learning is partly supervised and partly unsupervised.



Note

Classification
When it comes to machine learning, we will focus primarily on supervised learning, and in particular, classification tasks. In classification, we observe in input, such as a photograph of a traffic sign, and try to infer its “class”, such as the type of sign (speed limit 80 km/h, pedestrian crossing, stop sign, ...). Other examples of classification tasks include: identification of fake Twitter accounts (input includes the list of followers, and the rate at which they have started following the account, and the class is either fake or real account) and handwritten digit recognition (input is an image, class is 0,...,9).



Humans teaching machines: supervised learning
Instead of manually writing down exact rules to do the classification, the point in supervised machine learning is to take a number of examples, label each one by the correct label, and use them to “train” an AI method to automatically recognize the correct label for the training examples as well as (at least hopefully) any other images. This of course requires that the correct labels are provided, which is why we talk about supervised learning. The user who provides the correct labels is a supervisor who guides the learning algorithm towards correct answers so that eventually, the algorithm can independently produce them.

In addition to learning how to predict the correct label in a classification problem, supervised learning can also be used in situations where the predicted outcome is a number. Examples include predicting the number of people who will click a Google ad based on the ad content and data about the user’s prior online behavior, predicting the number of traffic accidents based on road conditions and speed limit, or predicting the selling price of real estate based on its location, size, and condition. These problems are called regression. You probably recognize the term linear regression, which is a classical, still very popular technique for regression.

Example
Suppose we have a data set consisting of apartment sales data. For each purchase, we would obviously have the price that was paid, together with the size of the apartment in square meters (or square feet, if you like), and the number of bedrooms, the year of construction, the condition (on a scale from “disaster“ to “spick and span”). We could then use machine learning to train a regression model that predicts the selling price based on these features. See a real-life example here

The first thing to keep in mind in order to avoid big mistakes, is to split your data set into two parts: the training data and the test data. We first train the algorithm using only the training data. This gives us a model or a rule that predicts the output based on the input variables.

To assess how well we can actually predict the outputs, we cant count on the training data. While a model may be a very good predictor in the training data, it is no proof that it can generalize to any other data. This is where the test data comes in handy: we can apply the trained model to predict the outputs for the test data and compare the predictions to the actual outputs (for example, future apartment sale prices).

Too fit to be true! Overfitting alert
It is very important to keep in mind that the accuracy of a predictor learned by machine learning can be quite different in the training data and in separate test data. This is the so called overfitting phenomenon, and a lot of machine learning research is focused on avoiding it one way or another. Intuitively, overfitting means trying to be too smart. When predicting the success of a new song by a known artist, you can look at the track record of the artist's earlier songs, and come up with a rule like “if the song is about love, and includes a catchy chorus, it will be top-20“. However, maybe there are two love songs with catchy choruses that didn't make the top-20, so you decide to continue the rule “...except if Sweden or yoga are mentioned“ to improve your rule. This could make your rule fit the past data perfectly, but it could in fact make it work worse on future test data.

Machine learning methods are especially prone to overfitting because they can try a huge number of different “rules“ until one that fits the training data perfectly is found. Especially methods that are very flexible and can adapt to almost any pattern in the data can overfit unless the amount of data is enormous. For example, compared to quite restricted linear models obtained by linear regression, neural networks can require massive amounts of data before they produce reliable prediction.

Learning without a teacher: unsupervised learning
Above we discussed supervised learning where the correct answers are available, and the taks of the machine learning algorithm is to find a model that predicts them based on the input data.

In unsupervised learning, the correct answers are not provided. This makes the situation quite different since we can't build the model by making it fit the correct answers on training data. It also makes the evaluation of performance more complicated since we can't check whether the learned model is doing well or not.

Typical unsupervised learning methods attempt to learn some kind of “structure” underlying the data. This can mean, for example, visualization where similar items are placed near each other and dissimilar items further away from each other. It can also mean clustering where we use the data to identify groups or “clusters” of items that are similar to each other but dissimilar from data in other clusters.

Example
As a concrete example, grocery store chains collect data about their customers' shopping behavior (that's why you have all those loyalty cards). To better understand their customers, the store can either visualize the data using a graph where each customer is represented by a dot and customers who tend to buy the same products are placed nearer each other than customers who buy different products. Or, the store could apply clustering to obtain a set of customer groups such as ‘low-budget health food enthusiasts’, ‘high-end fish lovers’, ‘soda and pizza 6 days a week’, and so on. Note that the machine learning method would only group the customers into clusters, but it wouldnt automatically generate the cluster labels (‘fish lovers’ and so on). This task would be left for the user.



Yet another example of unsupervised learning can be termed generative modeling. This has become a prominent approach since the last few years as a deep learning technique called /generative adversarial networks/ (GANs) has lead to great advances. Given some data, for example, photographs of people's faces, a generative model can generate more of the same: more real-looking but artificial images of people's faces.


Defining ‘nearest’
Using the geometric distance to decide which is the nearest item may not always be reasonable or even possible: the type of the input may, for example, be text, where it is not clear how the items are drawn in a geometric representation and how distances should be measured. You should therefore choose the distance metric on a case-by-case basis.





recommending news of social media content that a user is likely to click or like, may lead to filter bubbles where the users only see content that is in line with their own values and views.



The difference between classification and regression
There is a small but important difference in the kind of predictions that we should produce in different scenarios. While for example the nearest neighbor classifier chooses a class label for any item out of a given set of alternatives (like spam/ham, or 0,1,2,...,9), linear regression produces a numerical prediction that is not constrained to be an integer (a whole number as opposed to something like 3.14). So linear regression is better suited in situations where the output variable can be any number like the price of a product, the distance to an obstacle, the box-office revenue of the next Star Wars movie, and so on.


linear regression is to add up the effects of each of the feature variables to produce the predicted value. The technical term for the adding up process is linear combination. The idea is very straightforward, and it can be illustrated by your shopping bill.



Thinking of linear regression as a shopping bill
Suppose you go to the grocery store and buy 2.5kg potatoes, 1.0kg carrots, and two bottles of milk. If the price of potatoes is 2€ per kg, the price of carrots is 4€ per kg, and a bottle of milk costs 3€, then the bill, calculated by the cashier, totals 2.5 × 2€ + 1.0 × 4€ + 2 × 3€ = 15€. In linear regression, the amount of potatoes, carrots, and milk are the inputs in the data. The output is the cost of your shopping, which clearly depends on both the price and how much of each product you buy.

The word linear means that the increase in the output when one input feature is increased by some fixed amount is always the same. In other words, whenever you add, say, two kilos of carrots into your shopping basket, the bill goes up 8€. When you add another two kilos, the bill goes up another 8€, and if you add half as much, 1kg, the bill goes up exactly half as much, 4€.


'Key terminology

Coefficients or weights
In linear regression terminology, the prices of the different products would be called coefficients or weights. (This may appear confusing since we measured the amount of potatoes and carrots by weight, but not let yourself be tricked by this!) One of the main advantages of linear regression is its easy interpretability: the learned weights may in fact be more interesting than the predictions of the outputs.

For example, when we use linear regression to predict the life expectancy, the weight of smoking (cigarettes per day) is about minus half a year, meaning that smoking one cigarette more per day takes you on the average half a year closer to termination. Likewise, the weight of vegetable consumption (handful of vegetables per day) has weight plus one year, so eating a handful of greens gives every day gives you on the average one more year.'


In the above exercise, the life expectancy of non-smoking, veggie-hating women, 80 years, was the starting point for the calculation. The technical term for the starting point is the intercept.



Example
Continuing the shopping analogy, suppose we were given the contents of a number of shopping baskets and the total bill for each of them, and we were asked to figure out the price of each of the products (potatoes, carrots, and so on). From one basket, say 1kg of sirloin steak, 2kg of carrots, and a bottle of Chianti, even if we knew that the total bill is 35€, we couldnt determine the prices because there are many sets of prices that will yield the same total bill. With many baskets, however, we will usually be able to solve the problem.




Machine learning applications of linear regression
Linear regression is truly the workhorse of many AI and data science applications. It has its limits but they are often compensated by its simplicity, interpretability and efficiency. Linear regression has been successfully used in the following problems to give a few examples:

prediction of click rates in online advertising
prediction of retail demand for products
prediction of box-office revenue of Hollywood movies
prediction of software cost
prediction of insurance cost
prediction of crime rates
prediction of real estate prices


Could we use regression to predict labels?
As we discussed above, linear regression and the nearest neighbor method produce different kinds of predictions. Linear regression outputs numerical outputs while the nearest neighbor method produces labels from a fixed set of alternatives (“classes”).

Where linear regression excels compared to nearest neighbors, is interpretability. What do we mean by this? You could say that in a way, the nearest neighbor method and any single prediction that it produces are easy to interpret: it’s just the nearest training data element! This is true, but when it comes to the interpretability of the learned model, there is a clear difference. Interpreting the trained model in nearest neighbors in a similar fashion as the weights in linear regression is impossible: the learned model is basically the whole data, and it is usually way too big and complex to provide us with much insight. So what if we’d like to have a method that produces the same kind of outputs as the nearest neighbor, labels, but is interpretable like linear regression?


Logistic regression to the rescue
Well there are good news for you: we can turn the linear regression method’s outputs into predictions about labels. The technique for doing this is called logistic regression. We will not go into the technicalities, suffice to say that in the simplest case, we take the output from linear regression, which is a number, and predict one label A if the label is more than zero, and another label B if the label is less than or equal to zero. Actually, instead of just predicting one class or another, logistic regression can also give us a measure of uncertainty of the prediction. So if we are predicting whether a customer will buy a new smartphone this year, we can get a prediction that customer A will buy a phone with probability 90%, but for another, less predictable customer, we can get a prediction that they will not buy a phone with 55% probability (or in other words, that they will buy one with 45% probability).

It is also possible to use the same trick to obtain predictions over more than two possible labels, so instead of always predicting either yes or no (buy a new phone or not, fake news or real news, and so forth), we can use logistic regression to identify, for example, handwritten digits, in which case there are ten possible labels.


The limits of machine learning
To summarize, machine learning is a very powerful tool for building AI applications. In addition to the nearest neighbor method, linear regression, and logistic regression, there are literally hundreds, if not thousands, different machine learning techniques, but they all boil down to the same thing: trying to extract patterns and dependencies from data and using them either to gain understanding of a phenomenon or to predict future outcomes.

Machine learning can be a very hard problem and we can’t usually achieve a perfect method that would always produce the correct label. However, in most cases, a good but not perfect prediction is still better than none. Sometimes we may be able to produce better predictions by ourselves but we may still prefer to use machine learning because the machine will make its predictions faster and it will also keep churning out predictions without getting tired. Good examples are recommendation systems that need to predict what music, what videos, or what ads are more likely to be of interest to you.

The factors that affect how good a result we can achieve include:

The hardness of the task: in handwritten digit recognition, if the digits are written very sloppily, even a human can’t always guess correctly what the writer intended
The machine learning method: some methods are far better for a particular task than others
The amount of training data: from only a few examples, it is impossible to obtain a good classifier
The quality of the data



Data quality matters
In the beginning of this Chapter, we emphasized the importance of having enough data and the risks of overfitting. Another equally important factor is the quality of the data. In order to build a model that generalises well to data outside of the training data, the training data needs to contain enough information that is relevant to the problem at hand. For example, if you create an image classifier that tells you what the image given to the algorithm is about, and you have trained it only on pictures of dogs and cats, it will assign everything it sees as either a dog or a cat. This would make sense if the algorithm is used in an environment where it will only see cats and dogs, but not if it is expected to see boats, cars, and flowers as well.

Well return to potential problems caused by ”biased” data.


It is also important to emphasize that different machine learning methods are suitable for different tasks. Thus, there is no single best method for all problems (“one algorithm to rule them all...”). Fortunately, one can try out a large number of different methods and see which one of them works best in the problem at hand.

This leads us to a point that is very important but often overlooked in practice: what it means to work better. In the digit recognition task, a good method would of course produce the correct label most of the time. We can measure this by the classification error: the fraction of cases where our classifier outputs the wrong class. In predicting apartment prices, the quality measure is typically something like the difference between the predicted price and the final price for which the apartment is sold. In many real-life applications, it is also worse to err in one direction than in another: setting the price too high may delay the process by months, but setting the price too low will mean less money for the seller. And to take yet another example, failing to detect a pedestrian in front of a car is a far worse error than falsely detecting one when there is none.

As mentioned above, we can’t usually achieve zero error, but perhaps we will be happy with error less than 1 in 100 (or 1%). This too depends on the application: you wouldn’t be happy to have only 99% safe cars on the streets, but being able to predict whether you’ll like a new song with that accuracy may be more than enough for a pleasant listening experience. Keeping the actual goal in mind at all times helps us make sure that we create actual added value.


What are neural networks?
To better understand the whole, we will start by discussing the individual units that make it up. A neural network can mean either a “real” biological neural network such as the one in your brain, or an artificial neural network simulated in a computer.


Key terminology

Deep learning
Deep learning refers to certain kinds of machine learning techniques where several “layers” of simple processing units are connected in a network so that the input to the system is passed through each one of them in turn. This architecture has been inspired by the processing of visual information in the brain coming through the eyes and the captured by the retina. This depth allows the network to learn more complex structures without requiring unrealistically large amounts of data.

Neurons, cell bodies, and signals
A neural network, either biological and artificial, consists of a large number simple units, neurons, that receive and transmit signals to each other. The neurons are very very simple processors of information, consisting of a cell body and wires that connect the neurons to each other. Most of the time, they do nothing but sit still and watch for signals coming in through the wires.

Dendrites, axons, and synapses
In the biological lingo, we call the wires that provide the input to the neurons dendrites. Sometimes, depending on the incoming signals, the neuron may fire and send a signal out for the other neurons to receive. The wire that transmits the outgoing signal is called an axon. Each axon may be connected to one or more dendrites at intersections that are called synapses.


Isolated from its fellow-neurons, a single neuron is quite unimpressive, and capable of only a very restricted set of behaviors. When connected to each other, however, the system resulting from their concerted action can become extremely complex. (Exhibit A: your brain.) The behavior of the system is determined by the ways in which the neurons are wired together. Each neuron reacts to the incoming signals in a specific way that can also adapt over time. This adaptation is known to be the key to functions such as memory and learning.

Dendrite (input) -  wires that provide the input to the neurons
Synapse (connection) -  intersections of Each axon may be connected to one or more dendrites
Axon (output) -  wire that transmits the outgoing signal


The case for neural networks in general as an approach to AI is based on a similar argument as that for logic-based approaches

Compared to how computers traditionally work, neural networks have certain special features:

For one, in a traditional computer, information is processed in a central processor (aptly named the central processing unit, or CPU for short) which can only focus on doing one thing at a time. The CPU can retrieve data to be processed from the computer’s memory, and store the result in the memory. Thus, data storage and processing are handled by two separate components of the computer: the memory and the CPU. In neural networks, the system consists of a large number of neurons, each of which can process information on its own so that instead of having a CPU process each piece of information one after the other, the neurons process vast amounts of information simultaneously.


The second difference is that data storage (memory) and processing isn’t separated like in traditional computers. The neurons both store and process information so that there is no need to retrieve data from the memory for processing. The data can be stored short term in the neurons themselves (they either fire or not at any given time) or for longer term storage, in the connections between the neurons — their so called weights, which we will discuss below.

Because of these two differences, neural networks and traditional computers are suited for somewhat different tasks. Even though it is entirely possible to simulate neural networks in traditional computers, which was the way they were used for a long time, their maximum capacity is achieved only when we use special hardware (computer devices) that can process many pieces of information at the same time. This is called parallel processing. Incidentally, graphics processors (or graphics processing units, GPUs) have this capability and they have become a cost-effective solution for running massive deep learning methods.


How neural networks are built

Weights and inputs
The basic artificial neuron model involves a set of adaptive parameters, called weights like in linear and logistic regression. Just like in regression, these weights are used as multipliers on the inputs of the neuron, which are added up. The sum of the weights times the inputs is called the linear combination of the inputs. You can probably recall the shopping bill analogy: you multiply the amount of each item by its price per unit and add up to get the total.


If we have a neuron with six inputs (analogous to the amounts of the six shopping items: potatoes, carrots, and so on), input1, input2, input3, input4, input5, and input6, we also need six weights. The weights are analogous to the prices of the items. We’ll call them weight1, weight2, weight3, weight4, weight5, and weight6. In addition, we’ll usually want to include an intercept term like we did in linear regression. This can be thought of as a fixed additional charge due to processing a credit card payment, for example.


We can then calculate the linear combination like this: linear combination = intercept + weight1 × input1 + ... + weight6 × input6 (where the ... is a shorthand notation meaning that the sum include all the terms from 1 to 6).

With some example numbers we could then get:

10.0 + 5.4 × 8 + (-10.2) × 5 + (-0.1) × 22 + 101.4 × (-5) + 0.0 × 2 + 12.0 × (-3) = -543.0


Activations and outputs
Once the linear combination has been computed, the neuron does one more operation. It takes the linear combination and puts it through a so called activation function. Typical examples of the activation function include:

identity function: do nothing and just output the linear combination

step function: if the value of the linear combination is greater than zero, send a pulse (ON), otherwise do nothing (OFF)

sigmoid function: a “soft” version of the step function

Note that with the first activation function, the identity function, the neuron is exactly the same as linear regression. This is why the identity function is rarely used in neural networks: it leads to nothing new and interesting.


How neurons activate

Real, biological neurons communicate by sending out sharp, electrical pulses called “spikes”, so that at any given time, their outgoing signal is either on or off (1 or 0). The step function imitates this behavior. However, artificial neural networks tend to use the second kind of activation functions so that they output a continuous numerical activation level at all times. Thus, to use a somewhat awkward figure of speech, real neurons communicate by something similar to the Morse code, whereas artificial neurons communicate by adjusting the pitch of their voice as if yodeling.


Perceptron: the mother of all ANNs
The perceptron is simply a fancy name for the simple neuron model with the step activation function we discussed above. It was among the very first formal models of neural computation and because of its fundamental role in the history of neural networks, it wouldn’t be unfair to call it the “Mother of all Artificial Neural Networks”.

It can be used as a simple classifier in binary classification tasks. A method for learning the weights of the perceptron from data, called the Perceptron algorithm, was introduced by the psychologist Frank Rosenblatt in 1957. We will not study the Perceptron algorithm in detail. Suffice to say that it is just about as simple as the nearest neighbor classifier. The basic principle is to feed the network training data one example at a time. Each misclassification leads to an update in the weight.


AI hyperbole
After its discovery, the Perceptron algorithm received a lot of attention, not least because of optimistic statements made by its inventor, Frank Rosenblatt. A classic example of AI hyperbole is a New York Times article published on July 8th, 1958:
“The Navy revealed the embryo of an electronic computer today that it expects will be able to walk, talk, see, reproduce itself and be conscious of its existence.”

Please note that neural network enthusiasts are not at all the only ones inclined towards optimism. The rise and fall of the logic-based expert systems approach to AI had all the same hallmark features of an AI-hype and people claimed that the final breakthrough is just a short while away. The outcome both in the early 1960s and late 1980s was a collapse in the research funding called an AI Winter.


The history of the debate that eventually lead to almost complete abandoning of the neural network approach in the 1960s for more than two decades is extremely fascinating. The article A Sociological Study of the Official History of the Perceptrons Controversy by Mikel Olazaran (published in Social Studies of Science, 1996) reviews the events from a sociology of science point of view. Reading it today is quite thought provoking. Reading stories about celebrated AI heroes who had developed neural networks algorithms that would soon reach the level of human intelligence and become self-conscious can be compared to some statements made during the current hype. If you take a look at the above article, even if you wouldn't read all of it, it will provide an interesting background to today's news. Consider for example an article in the MIT Technology Review published in September 2017, where Jordan Jacobs, co-founder of a multimillion dollar Vector institute for AI compares Geoffrey Hinton (a figure-head of the current deep learning boom) to Einstein because of his contributions to development of neural network algorithms in the 1980s and later. Also recall the Human Brain project mentioned in the previous section.

According to Hinton, “the fact that it doesn’t work is just a temporary annoyance.” (Although according to the article, Hinton is laughing about the above statement, so it's hard to tell how serious he is about it.) The Human Brain project claims to be “close to a profound leap in our understanding of consciousness“. Doesn't that sound familiar?

No-one really knows the future with certainty, but knowing the track record of earlier annoucements of imminent breakthroughs, some critical thinking is advised. We'll return to the future of AI in the final Chapter, but for now, let's see how artificial neural networks are built.



Putting neurons together: networks
A single neuron would be way too simple to make decisions and prediction reliably in most real-life applications. To unleash the full potential of neural networks, we can use the the output of one neuron as the input of other neurons, whose outputs can be the input to yet other neurons, and so on. The output of the whole network is obtained as the output of a certain subset of the neurons, which are called the output layer. We’ll return to this in a bit, after we discussed the way neural networks adapt to produce different behaviors by learning their parameters from data.


Layers
Often the network architecture is composed of layers. The input layer consists of neurons that get their inputs directly from the data. So for example, in an image recognition task, the input layer would use the pixel values of the input image as the inputs of the input layer. The network typically also has hidden layers that use the other neurons´ outputs as their input, and whose output is used as the input to other layers of neurons. Finally, the output layer produces the output of the whole network. All the neurons on a given layer get inputs from neurons on the previous layer and feed their output to the next.




Advanced neural network techniques

In the previous section, we have discussed the basic ideas behind most neural network methods: multilayer networks, non-linear activation functions, and learning rules such as the backpropagation algorithm.

Convolutional neural networks (CNNs)
One area where deep learning has achieved spectacular success is image processing. The simple classifier that we studied in detail in the previous section is severely limited – as you noticed it wasnt even possible to classify all the smiley faces correctly. By adding more layers in the network and using backpropagation to learn the weights does in principle solve the problem, but another one emerges: the number of weights becomes extremely large and consequently, the amount of training data required to achieve satisfactory accuracy can become too large to be realistic.

Fortunately, a very elegant solution to the problem of too many weights exists: a special kind of neural networks, or rather, a special kind of layer that can be included in a deep neural network. This special kind of layer is a so called convolutional layer. Networks including convolutional layers are called convolutional neural networks (CNNs). Their key property is that they can detect image features such as bright or dark (or specific color) spots, edges in various orientations, patterns, and so on. These form the basis for detecting more abstract features such as a cat’s ears, a dog’s snout, a person’s eye, or the octagonal shape of a stop sign.

It would normally be hard to train a neural network to detect such features based on the pixels of the input image, because the features can appear in different positions, different orientations, and in different sizes in the image: moving the object or the camera angle will change the pixel values dramatically even if the object itself looks just the same to us. In order to learn to detect a stop sign in all these different conditions would require vast of amounts of training data because the network would only detect the sign in conditions where it has appeared in the training data. So, for example, a stop sign in the top right corner of the image would be detected only if the training data included an image with the stop sign in the top right corner. CNNs can recognize the object anywhere in the image no matter where it has been observed in the training images.


Why we need CNNs
CNNs use a clever trick to reduce the amount of training data required to detect objects in different conditions. The trick basically amounts to using the same input weights for many neurons — so that all of these neurons are activated by the same pattern — but with different input pixels. We can for example have a set of neurons that are activated by a cat’s pointy ear. When the input is a photo of a cat, two neurons are activated, one for the left ear and another for the right. We can also let the neuron’s input pixels be taken from a smaller or a larger area, so that different neurons are activated by the ear appearing in different scales (sizes), so that we can detect a small cats ears even if the training data only included images of big cats.



The convolutional neurons are typically placed in the bottom layers of the network, which processes the raw input pixels. Basic neurons (like the perceptron neuron discussed above) are placed in the higher layers, which process the output of the bottom layers. The bottom layers can usually be trained using unsupervised learning, without a particular prediction task in mind. Their weights will be tuned to detect features that appear frequently in the input data. Thus, with photos of animals, typical features will be ears and snouts, whereas in images of buildings, the features are architectural components such as walls, roofs, windows, and so on. If a mix of various objects and scenes is used as the input data, then the features learned by the bottom layers will be more or less generic. This means that pre-trained convolutional layers can be reused in many different image processing tasks. This is extremely important since it is easy to get virtually unlimited amounts of unlabeled training data - images without labels - which can be used to train the bottom layers. The top layers are always trained by supervised machine learning techniques such as backpropagation.


Having learned a neural network from data, it can be used for prediction. Since the top layers of the network have been trained in a supervised manner to perform a particular classification or prediction task, the top layers are really useful only for that task. A network trained to detect stop signs is useless for detecting handwritten digits or cats.

A fascinating result is obtained by taking the pre-trained bottom layers and studying what the features they have learned look like. This can be achieved by generating images that activate a certain set neurons in the bottom layers. Looking at the generated images, we can see what the neural network “thinks” a particular feature looks like, or what an image with a select set of features in it would look like.


The neural network doesn’t really dream, and it doesn’t have a concept of a cat that it would understand in a similar sense as a human understands. It is simply trained to recognize objects and it can generate images that are similar to the input data that it is trained on.

To actually generate real looking cats, human faces, or other objects (you’ll get whatever you used as the training data), Ian Goodfellow who currently works at Google Brain, proposed a clever combination of two neural networks. The idea is to let the two networks compete against each other. One of the networks is trained to generate images like the ones in the training data. The other network’s task is to separate images generated by the first network from real images from the training data — it is called the adversarial network, and the whole system is called generative adversarial network or a GAN.

The system trains the two models side by side. In the beginning of the training, the adversarial model has an easy task to tell apart the real images from the training data and the clumsy attempts by the generative model. However, as the generative network slowly gets better and better, the adversarial model has to improve as well, and the cycle continues until eventually the generated images are almost indistinguishable from real ones. The GAN tries to not only reproduce the images in the training data: that would be a way too simple strategy to beat the adversarial network. Rather, the system is trained so that it has to be able to generate new, real-looking images too.




Part 6/6

Implications



About predicting the future

You may be disappointed to hear this, but we dont have a crystal ball that would show us what the world will be like in the future and how AI will transform our lives.

The reality distortion field
Not everyone is quite as conservative about their forecasts, however. In the modern world where big headlines sell, and where you have to dissect news into 280 characters, reserved (boring?) messaged are lost, and simple and dramatic messages are magnified. In the public perception of AI, this is clearly true.


From utopian visions to grim predictions
The media sphere is dominated by the extremes. We are beginning to see AI celebrities, standing for one big idea and making oracle-like forecasts about the future of AI. The media love their clear messages. Some promise us a utopian future with exponential growth and trillion-dollar industries emerging out of nowhere, true AI that will solve all problems we cannot solve by ourselves, and where humans don’t need to work at all.

It has also been claimed that AI is a path to world domination. Others make even more extraordinary statements according to which AI marks the end of humanity (in about 20-30 years from now), life itself will be transformed in the “Age of AI“, and that AI is a threat to our existence.


AI winters
The history of AI, just like many other fields of science, has witnessed the coming and going of various different trends. In philosophy of science, the term used for a trend is paradigm. Typically, a particular paradigm is adopted by most of the research community and optimistic predictions about progress in the near-future are provided. For example, in the 1960s neural networks were widely believed to solve all AI problems by imitating the learning mechanisms in the nature, the human brain in particular. The next big thing was expert systems based on logic and human-coded rules, which was the dominant paradigm in the 1980s.


The societal implications of AI
In the very beginning of this course, we briefly discussed the importance of AI in today’s and tomorrow’s society but at that time, we could do so only to a limited extent because we hadn’t introduced enough of the technical concepts and methods to ground the discussion on concrete terms.
