# Thomas's thoughts on his portion of the project

Dave merging the datasets for us saved me a lot of time since all I really needed to do afterwards was focus in on a few
columns.  Sentiment and Price were the first two things I wanted to analyze, so I dropped a bunch of columns, dropped
any rows with NaN in the Polarity value (meaning the person submitted a review with either no words or no words that the
sentiment polarity program could recognize), and did a little formatting of the Price column to change the values back to
integers since the $ makes them strings.

Originally I had wanted to graph the average sentiment polarity of the apps compared to their price, but I realized looking
through my narrowed data that I ended up with a total of like 8 unique paid apps compared to hundreds or thousands of free
ones.  At this point I realized my narrowed dataset didn't include every single app in the store, but I assumed that it was
still reasonably representative sample of the overall.

After learning that, instead of one dot per app on the scatterplot, I plotted every review I access to.  On it you can see
the sentiment polarity for every review and what the price was for the app it was written about.  It's tough to make out the
spread along the $0 line, but that can be seen in the pie chart in the Sentiment-Type section.  For everything that has an
actual cost, however, you can easily see that sentiment polarity is largely positive.  Especially so for the comments left
on apps that cost $10 or more.

With the number of free apps so heavily outnumbering the paid ones, I wouldn't trust the regression line that was produced
one bit in making future predictions.  Seriously the r2 value was like .03 rounded up.  Maybe if I took a new sample of
paid apps only I could get a decent one, but that wasn't my objective this time.

Moving on to the Sentiment-Type analysis, I again took Dave's combined dataset and cut out columns until I only had the app,
its type, and the review sentiment remaining.  This time instead of the actual sentiment score, the cell contained only a
"Negative" for negative scores, "Neutral" for scores of 0, and "Positive" for positive scores.

With those columns, I used a groupby function to check out each unique app in my sample and its distribution of review scores.
While cool to see and have if I wanted it in the future, I decided what I actually wanted was the same distribution but for
"Free" and "Paid" apps all lumped into those groupings.  So after gathering that data grouping, I made pie charts of them.  I
would have preferred bars but as said before, the free apps so heavily outnumber the paid apps that you wouldn't have been able
to see the tiny Paid bars at all beneath the Free mountain.

Looking at the pies, you can see that most reviews tend to be positive regardless of app type.  By type grouping, however, you
can see that paid apps have a higher percentage of positive reviews than free ones do.  Why this may be is up for debate and
can't be answered with the info I have here.  Maybe the quality is actually better?  Maybe there's some sunk cost fallacy at
play where people feel better about the paid apps just because they had to actually spend money on them?  It takes time and
effort to leave a review, so maybe the free ones get held down by pestering users to leave reviews they don't want to make in
return for some sort of in-app benefit?  I've got no clue.  The data says what it says but I can't tell you the "why" with
absolute certainty with it.

That's all for my sections.  Paid stuff is more positively reviewed than free stuff based on my sample.
