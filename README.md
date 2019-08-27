# machinelearningstudies
Journal of my Studies in Machine Learning, Fall 2019

## August 27, 2019

I have made two academic achievements thus far, the first is the completion of Andrew Ng's Machine Learning Coursework, and the second is the completion of the OffSec OSCE Hacking Challenge. The following are my reflections thereon. 

Looking back on the OSCE Challenge, it was worth the effort in that it required me to acquire certain skills that weren't part of my a/A education. I'm referring mainly to the skill in understanding assembly language, compiling it, running it, and debugging it. Specifically, the main skill here is inspecting the registers, and the memory to which they point, as the program runs, which is a little bit of a unique task because each register has its own function, and the values are displayed in hexadecimal.  As such, one needs to know both the purpose of each register, and to be able to read hexadecimal fluently.  Once you can do this, debugging assembly feels as natural as debugging a higher level codebase, and it's quite fun. 

It also reminded me of a few interesting things. The first is that programs can be reverse engineered and modified without changing the functionality of the application. This is done using a program that disassembles the executable, and once you have the disassembled program, you can insert new assembly code and then recomplile it. That's pretty cool, and piggy-backing on top of this, one can also pass code around as text in the form of hexadecimal numbers and "disassemble" the text to inspect it. This was the first time thinking about code at this level of abstraction; that is, a much lower level of abstraction than javascript or ruby, and it made be feel powerful.  

Looking back on the past few days, I probably could have been a little bit more systematic about my studies. I spent most of the time jumping back and forth between a few different approaches to running the assembly code, and I may have been better to just decide to figure out how to run the assembly code and debug it with full visibility into the source. It's just that assembly code can be scripted in a several ways (C wrapper, stand alone), and both of them took a while to grasp because the compilation configurations is specific to the machine I'm using, and because the assembly code itself was buggy, or rather, because the code threw an error that I didn't expect, and I had to spend time understanding it. On top of all of this, I had to learn to think in assembly. So I guess i just did all of those things all at once and emerged with some new knowledge. 

If I learn to pen test, I'll take the OCSP course instead. It could be a lot of fun.

-- 

With regard to the Machine Learning Course, there was definitely a lot of material. We covered real world examples for supervised learning (regression and classification), unsupervised learning (clustering and Principle Component Analysis), and then learned how to debug/evaluate ML algorithms using learning curves, error analysis, ceiling analysis, as well as build a few real world ML systems (anomaly detection, recommender systems. Finally, we learned about large scale ML optimizations and how Image OCR uses the sliding window method and system design of ML pipelines. I feel empowered to implement ML systems after doing a course like this. 

That being said, some questions about the fundamentals remain in my mind. I'm specifically curious about the intuition behind certain ideas in linear algebra and statistics. For example, how did somebody come up with singular value decomposition? At this point, all I know is that it's used in PCA, and how to implement it, but I don't really understand how anyone came up with the idea in the first place. I think the problem is that I'm not even clear on more elementary ideas, such as the proof of the equation for the variance of a Gaussian distribution. If I knew it, I would then know that how idea explains the concept of a covariance matrix, of which I also know the equation, but not the intuition. Then, finally, we reach SVD, which is a series of operations on the corvariance matrix. Like I said, I can implement SVD, and the implementation thereof using the 5000-face dataset was nothing short of astounding, and I could follow the code and high level logic, but when I comes to understanding the deep logic, how someone invented it, I'm not following at this moment.

Similarly, I not sure where the intuition arose of the squared length of a vector in n-dimensions being the sum of the values squared. I can see the extrapolation from pythagorean theorum to n-dimensions, but once again, I feel like I'm missing something in my understanding that allowed someone to make that jump and feel justified in doing it. Perhaps it's because I can't visualize greater than three dimensions, and that's all there is to it. 

There are few more things like the proof for K-means clustering, and just how exactly SVMs were conceived, and just generally the awe that people actually invented these tools at all. In a nutshell, I should dive deeper into the minds of the inventors of these algorithms.

-- 

So, thinking back on my original motivation for doing machine learning, I have to ask myself to what extent I have made progress. The intention for this project was to learn exactly what ML can and can't do, and there is definitely some clarity there. 

In some ways, it's quite simple. Every single ML algorithm is simply minimizing of the sum of the errors between hypothesis and actual by using gradient descent or some optimized version thereof to modified parameters of the hypothesis function. The hypothesis function is a linear equation with a possible transformation, and that's really all there is to it. If the algorithm fails, there is a process for examining whether the algorithm has correctly fit the data (is it biased or highly variant?), and whether the performance is adequate (does it have a good F1 score?).  We learn how to perform these evaluations, as well as what to do about it, whether that means changing the parameters of the algorithm, or acquiring more data, or modifying the dataset.

But in reality, ML is not that simple because modeling the real world is complicated. The real world needs to be described with numbers, and the data needs to be collected, and it needs to be normalized (cleaned). This task is so hard that the ML algorithms are only being applied to very concrete problems. Lets take a look at the examples to understand what I mean:

1. Housing prices (linear regression).
2. College acceptance base on two tests (logistic reg.).
3. 0-9 number classification, and streering wheel self-driving care (NN and one-versus-all logistic regression).
4. Image compression (of the color pallete) (K-means and PCA)
5. Anomaly system for computers base on CPU usage and traffic, and airplane motor quality.
6. Recommender system for movies with 100 features.
7. Image OCR walkthrough (NN, logistic regression).
8. Spam Classification (SVM).
9. Face data analysis, PCA 

This is what we worked on, and you'll see that the examples are only problems that can be easily modeled with numbers and for which there is a strong correlation predictable or visible. Housing prices are already numbers, and college acceptance prediction already has numbers with a visible correlation. Number classification is concrete and requires extremely clean data. Image compression used a easily groupable parameter: the color pallate (RGB). The anomaly detection assumes the data is Gaussian. Movie recommendation is discreet (5 levels) and already representable in numbers. Spam is also easily representable with numbers (count the words). This is all to say that the examples were easily representable in numbers - how could you accurately represent difficult ethical problems with numbers, and come up with a dataset that people agree upon? I certainly am not sure how to do that at this time.

That is not to say that the solutions to these problems aren't creative or amazing. I'm truly amazed that people came up with this, and I don't claim to understand all of the algorithms completely, or how they work. In fact it's amazing that people came up with the algorithsm, and that they figured how to represent the data in such a way that the data actually worked with the algorithsm. That being said, it's important to say that I don't believe that ML algorithms think in any way, and none of these examples are matters of life and death. If ML is doing any kind of thinking, it's doing the kind of thinking that labels and groups concrete entities, and nothing more than that. 


