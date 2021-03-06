---
layout: page
title: R Markdown Tips
description: tips on how to improve r markdown aesthetics
---

Below are a few tips on how to keep the homework reports looking clean.

* **Output html:** If you're using pdf as an output, keep in mind knitr does not automatically wrap your code chunks, and they will run off the page if too long. Be aware of this and add line breaks where appropriate. With this in mind, it may be optimal to knit to html.

* **Minimize R output:** Usually you shouldn't include particular R outputs in your final version of homeworks. You should for sure look at and use the output for yourself, but you can just refer to the important results *in-line* when writing your analyses. 

* **Use inline code chunks:** To reference previously computed statistics outside your code chunks, use inline code chunks. The syntax is like: ``the p-value was `r test$p.val`.``. You can tinker with the round() or formatC() functions to deal with rounding and formatting the numerical value.

* **Format code:** You can also use single back ticks (`` ` ` ``) to reformat a word to look like code. This is mostly for aesthetic purposes, but if I want to tell the reader I'm using the R function, say, Anova, then writing "we will be utilizing the `Anova` function to..." and it will stand out more.

* **Nice tables:** When presenting statistics in a table, try to avoid supplying just the R output. Remember, you are presenting this information to someone that can read statistics, but is not familiar with R. Look into table making packages such as kableExtra.

* **Think about figure widths:** Another aesthetic preference, but figures could be wider to fill up the unused white space in the page, making them larger and easier to read. You can tinker with the fig.width and fig.height code chunk options, and fig.width=10 will make your figures as wide as the page.

* **Squash warnings:** To prevent messages or warnings from showing up in your pdf or html file (for example, after loading a package) you can add message=FALSE and warning=FALSE into your chunk options.

* **Label axes:** Try to avoid letting R set the axis labels, as they could just be R code like `data$variable` when instead you want a nicer looking label.
    It only takes one more line of code and your figures will thank you for it.

* **Set the seed:** If you *set the random seed* in the first (set-up) chunk of your document, by doing something like `set.seed(123)`,
    then any randomness (e.g., simulations) in your report will produce *exactly the same output* every time you knit the document.
