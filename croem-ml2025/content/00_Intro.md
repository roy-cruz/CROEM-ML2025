# Introduction

## How ML is shaping our world

Machine learning is a powerful tool that has become ubiquotous in our day to day life. From the algorithms in Instagram determining what to show you based on your interests, to the image recognition software your phone uses to organize pictures, to the very popular ChatGPT which has started to rival Google's search engine (which also uses ML!), ML is everywhere in our modern age. Its influence has not been restricted to the tools we use every day. It has also been key to the many scientific breakthrough shaping our world today. Here are some of the more noticeable examples:

- Biology and medicine: AlphaFold2 predicted the 3D structure of ~200 million proteins (nearly every known protein!), which solved a 50-year-old challenge in structural biology. This will speed up drug discovery, enzyme design, and understanding disease mechanisms.
    <iframe 
        width="560" 
        height="315" 
        src="https://www.youtube.com/embed/P_fHJIYENdI?si=pfYASrubrLsECICF" 
        title="YouTube video player" 
        frameborder="0" 
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" 
        referrerpolicy="strict-origin-when-cross-origin" 
        allowfullscreen
    ></iframe>

- High energy physics: Numerous ML models have been key for the search of new physics in experiments such as the CMS and ATLAS in the LHC at CERN.
    <iframe 
        width="560" 
        height="315" 
        src="https://www.youtube.com/embed/nvYpPf-Gyjk?si=XOhqgB4Vbe4PbKfz" 
        title="YouTube video player" 
        align="center"
        frameborder="0" 
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" 
        referrerpolicy="strict-origin-when-cross-origin" 
        allowfullscreen
    ></iframe>

- Chemistry and material science: GNoME model by Google allowed for the discovery of 2.2 million crystals which could have applications in a plethora of technologies such as computer chips and batteries. More information: [link](https://deepmind.google/discover/blog/millions-of-new-materials-discovered-with-deep-learning/)
    ```{figure} images/ggnome.png
    ---
    height: 250px
    name:   ggnome
    align:  center
    ---
    "About 20,000 of the crystals experimentally identified in the ICSD database are computationally stable. Computational approaches drawing from the Materials Project, Open Quantum Materials Database and WBM database boosted this number to 48,000 stable crystals. GNoME expands the number of stable materials known to humanity to 421,000. - A. Merchant & E. Dogus"
    ```
- And many, many more!

With how useful ML has been, its no wonder why its worth learning!

## Why is ML so powerful?

Suppose that you are receiving a lot of spam in your email and you want to find a way to automatically flag emails as spam. The conventional approach would go something like this:

1. Identify what typical spam looks like. You could write down all of the typical words and phrases used in these emails (i.e. "free", "act now", "winner" and "rich").
2. Write an algorithm which looks for these words and phrases in an email and, if any are found, that email would be flagged.

```{figure} images/traditional.png
---
height: 150px
name:   traditional
align:  right
---
Problem solving with traditional programming
```

This approach presents some immediate difficulty. For instance, how are you supposed to make a comprehensive list of words and phrases? And what if, after you're done with your list, scammers notice that their emails are getting flagged if they used a particular phrase, so they change it slightly so that it is no longer captured by your algorithm. You'd need endlessly tweak and fine-tune your list and spam-detecting algorithm, continuously updating it to capture all cases. This is not a good approach!

```python
flag_words = ["free", "winner", "rich"]
email = """
Hello! We are reaching out to you to let you know that you are the winner of a free car! Act now, because another person might claim it before you do!
"""
email_words = email.split()

for flag_word in flag_words:
    if flag_word in email_words:
        print("Potential spam found!")
```

An alternate approach to solve this problem would be to ditch the list of words and instead teach your computer how to identify spam emails without programming a strict set of rules. This is what machine learning (ML) allows us to do. A potential approach would be as follows:
1. Have a bunch of example emails, some of which are known spam and other which are not.
2. Train your ML algorithm with a portion of this example data.
3. Evaluate the trained algorithm by running it on the rest of the data and seeing how it performs.
4. If needed, re-train or tweak model until you reach the desired performance.

```{figure} images/mlapproach.png
---
height: 250px
name:   ml-approach
---
Machine learning approach
```

This approach is particularly powerful because the re-training fo the ML algorithm can be automated and keeping it up to date is feasible.

```{figure} images/mlapproachauto.png
---
height: 250px
name:   ml-approachauto
---
Automation of machine learning approach
```

As can be seen from this simple example, ML turns traditional problem-solving on its head. In classical programming, we define a set of rules or functions that map inputs to outputs.

```{mermaid}
---
align:  center
---
flowchart LR
    A["Data ($$x$$)"] --> C
    C{"$$f(x)$$"} --> D["Output"]
```

However, with ML, we can ask: "what is the *function* that maps the inputs to the output?" This involves two steps:
1. Training the model: Teach the model how to correctly map inputs to outputs.
    ```{mermaid}
    ---
    align:  center
    ---
    flowchart TB
        A["Input $$\;x_i$$"] --> B{"ML Model ($$f(x;h)$$)"}
        B --> C["Predicted output $$\;\hat{y}_i$$"]
        C --> D["Compare actual output to predicted $$\;E(\hat{y}_i, y_i)$$"]
        D --> |"Update model to reduce $$\;E$$"|B
    ```
2. Testing the model: Show data to the model that it has never seen before. Make sure that the model is still performing well.
3. Deploy model: With the generalizability of the model ensured, we can now go ahead and use it!

## What will we be learning?

At the end of this workshop you should:

1. Understand the fundamental principles behind ML.
2. Be familiar with some basic ML models that are commonly used and serve as basis for other, more advanced models.
3. Be able to solve simple problems with ML.

The material provided in the following chapters are actually Jupyter Notebooks that you can open in Google Colab, modify and run by clicking the [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://youtu.be/5LB_y-nudGU?si=MYDYvubUH8qLpm89). Go ahead and click on any on the links below to more ahead in the material! 

```{tableofcontents}
```
