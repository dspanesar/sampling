# ASSIGNMENT: Sampling and Reproducibility in Python

Read the blog post [Contact tracing can give a biased sample of COVID-19 cases](https://andrewwhitby.com/2020/11/24/contact-tracing-biased/) by Andrew Whitby to understand the context and motivation behind the simulation model we will be examining.

Examine the code in `whitby_covid_tracing.py`. Identify all stages at which sampling is occurring in the model. Describe in words the sampling procedure, referencing the functions used, sample size, sampling frame, any underlying distributions involved, and how these relate to the procedure outlined in the blog post.

Run the Python script file called whitby_covid_tracing.py as is and compare the results to the graphs in the original blog post. Does this code appear to reproduce the graphs from the original blog post?

Modify the number of repetitions in the simulation to 100 (from the original 1000). Run the script multiple times and observe the outputted graphs. Comment on the reproducibility of the results.

Alter the code so that it is reproducible. Describe the changes you made to the code and how they affected the reproducibility of the script file. The output does not need to match Whitby’s original blogpost/graphs, it just needs to produce the same output when run multiple times

# Author: Darshan Panesar

```
I have numbered each component of this assignment above. 

1. Here  are the details for the code in `whitby_covid_tracing.py`.
   a. Identify all stages at which sampling is occurring in the model:
   There are 3 stages in which sampling occurs:

FIRST: The random sample of individuals who are infected at a random rate of 10% this is done to the entire population of 1000 (200 at the wedding event and 800 at brunch).
a.	Where the rate of infection or ATTACK_RATE is specified at the beginning of the code as 0.10 or 10%
b.	The code for this is listed as:
# Infect a random subset of people
infected_indices = np.random.choice(ppl.index, size=int(len(ppl) * ATTACK_RATE), replace=False)
ppl.loc[infected_indices, 'infected'] = True

c.	The size of the infected sample would be 10% of the original population which was 200 for the wedding event and 800 for the brunch event therefore would be 20 and 80 respectively or 100 individuals total. 

d.	The sampling frame is the original population of 1000 individuals: made up of 200 for the wedding event and 800 for the brunch event.

e.	Underlying distribution involved is binomial because there are 2 options either infected or not infected (1 or 0). Here the probability of success or infection is 10%. 

f.	This relates to the procedure outlined in the blog post as this is the simple modelling step highlighted. Specifically, modelling that each person has a 10% chance of being infected. But it also speaks to the fact that this is a controlled, simple, (even though random) distribution and population. Imagine if we were to infer the entire world or a country’s population’s infection rate or other stats from this small sample. This raises an important point about generalizability and estimation.

SECOND: The second is the primary contact tracing. Specifically, the 20% random sample of individuals who are traced from the population of those that are infected.
a.	Where the trace success rate or TRACE_SUCCESS is specified at the beginning of the code as 0.20 or 20%

b.	The code for this is listed as:
  # Primary contact tracing: randomly decide which infected people get traced
ppl.loc[ppl['infected'], 'traced'] = np.random.rand(sum(ppl['infected'])) < TRACE_SUCCESS

c.	The size of the infected sample would be 10% of the population of individuals infected which was 100 (20 and 80 respectively) therefore this sample would be 20% of that which would be 20 individuals who are marked with ‘traced’ (4 and 16 respectively from the wedding and brunch events). 

d.	The sampling frame is the population of individuals infected which was 100 individuals (20 and 80 respectively from each event). 

e.	Underlying distribution involved is binomial because the contact tracing is essentially seeing if there is a trace success or failure (1 or 0). The probability of success in this case or trace success is 20%.

f.	This relates to the procedure outlined in the blog post as it speaks to the point “those that are being traced are very unlikely to be a random sample of all cases.” Here, is a realistic example that we often only sample a small subset of the entire population and from that a smaller sample of infected individuals. It exemplifies the limitations and imperfections in sampling and primary sampling more so. Again, this speaks to the limited generalizability and our ability to infer or make any accurate larger estimations.


THIRD: The third is the secondary contact tracing. Specifically, examining the 20% random sample of individuals who were successfully traced from the population of those that were infected.
a.	The sampling procedure is all the infected individuals who were traced successfully in the primary trace. Where the trace success rate or TRACE_SUCCESS is specified at the beginning of the code as 0.20 or 20%. A secondary evaluation is conducted here which evaluates whether at least 2 individuals can be traced back to an event. If there are a min of 2 then all the individuals at that event are evaluated and all infected individuals here are labelled as traced. 

b.	The code for this is listed as:

  # Secondary contact tracing based on event attendance
  	event_trace_counts = ppl[ppl['traced'] == True]['event'].value_counts()
  
events_traced = event_trace_counts[event_trace_counts >= SECONDARY_TRACE_THRESHOLD].index
 
ppl.loc[ppl['event'].isin(events_traced) & ppl['infected'], 'traced'] = True

c.	The sample size here would be in 2 parts, 1. Is all the 20 infected individuals who were traced (frame), then 2. The events which had a minimum of 2 infected people (this would be from all of those individuals derived from the total population which is the infected which is 100) 

d.	The sampling frame is the population of individuals infected who were successfully traced in the primary trace (20%) therefore would be 20 individuals  (4 and 16 respectively from the wedding and brunch events).

e.	I think the underlying distribution involved is again a binomial because there is a true and false here. If there are 2 infected at an event it is a success, if not it is a failure and it doesn’t move forward with the secondary tracing. The threshold here represents the probability which is a minimum of 2 infected individuals.

f.	This relates to the procedure outlined in the blog post in which a secondary contact tracing is done (which the author suggests is a realistic public health agency action). This would be a critical more effective way to 1. Trace individuals who are infected and ideally the infection trajectories 2. Get a more generalizable estimate or better representation of infection versus the entire population. 

Note: we do set a population sample at the start of 1000 (200 and 800 for each event respectively). In addition the last portion of the code also separates the wedding event as another sampling event.  



2. Upon running the code, it produced the following graph: (see uploaded Figure1_1000.png)
 
The Infections from wedding (blue) shows a similar distribution to the one in the blog post. Where each person had a 10% chance of being infected with some variability. This results in approximately 20% of all cases from the wedding (as you can see the center or mean of the graph is at approximately 0.2 or 20%). This graph generated by the code shows exactly that.
The second graph overlayed on top is the cases that were traced. In a perfect world of sampling this would be 100%. Here, our observed from primary and secondary tracing we can see it is a relatively good match to the original or true infected distribution from the wedding event. Here we are pretty good at estimating the infected cases between the 2 tracing methods. Out mean is close to 0.2 or the true mean (perhaps around 0.17) but it does seem to show variability in estimation as the proportion moves away from the mean.
In comparison, the blog post’s prediction graph looks different even though they use the same strategy. They note that their tracing method/strategy overestimates the proportion of cases that result from weddings. They note that “mean observed proportion is around double the true proportion, and the observed value is even higher”.


3. I changed the code here:
# Run the simulation 1000 times to # Run the simulation 100 times
results = [simulate_event(m) for m in range(1000)] to results = [simulate_event(m) for m in range(100)]
Then I reran the code 10 times, below are the graphs generated. (see uploaded Figure2_100.png)
These graphs are all different each showing variations not only from one another but from the original graph from the blog and the 1000 simulations version above. 
The mean value also seems to be variable; it is close to 0.20 (i.e., the 20% proportion of cases) but deviates with each instance. The random sampling (i.e., the 10% infection rate) coupled with the lower 100 simulations creates less variation. But in doing so we also create less accurate of a representation of the real-world scenario. More simulation would create more variation but a better representation overall. The distribution would be closer to a bell-shaped normal distribution while the 100 would deviate more.


 
4. To make the graph reproducible I set a manual random seed in the global function before the 100 simulations were run. I added the following line (which uses the numpy function random.seed) np.random.seed(63)
In doing so the code will now generate the same reproducible results/graph every time. This prevents the variations between instances in which the code runs. From our previous modules we learned that the random seed function though it generates a random sequence of numbers it does so the same way every time allowing random but reproducible results every time the code is run. 


```


## Criteria

|Criteria|Complete|Incomplete|
|--------|----|----|
|Altercation of the code|The code changes made, made it reproducible.|The code is still not reproducible.|
|Description of changes|The author explained the reasonings for the changes made well.|The author did not explain the reasonings for the changes made well.|

## Submission Information

🚨 **Please review our [Assignment Submission Guide](https://github.com/UofT-DSI/onboarding/blob/main/onboarding_documents/submissions.md)** 🚨 for detailed instructions on how to format, branch, and submit your work. Following these guidelines is crucial for your submissions to be evaluated correctly.

### Submission Parameters:
* Submission Due Date: `23:59 - 09/04/2025`
* The branch name for your repo should be: `assignment-1`
* What to submit for this assignment:
    * This markdown file (a1_sampling_and_reproducibility.md) should be populated.
    * The `whitby_covid_tracing.py` should be changed.
* What the pull request link should look like for this assignment: `https://github.com/<your_github_username>/sampling/pull/<pr_id>`
    * Open a private window in your browser. Copy and paste the link to your pull request into the address bar. Make sure you can see your pull request properly. This helps the technical facilitator and learning support staff review your submission easily.

Checklist:
- [x] Create a branch called `assignment-1`.
- [x] Ensure that the repository is public.
- [x] Review [the PR description guidelines](https://github.com/UofT-DSI/onboarding/blob/main/onboarding_documents/submissions.md#guidelines-for-pull-request-descriptions) and adhere to them.
- [x] Verify that the link is accessible in a private browser window.

If you encounter any difficulties or have questions, please don't hesitate to reach out to our team via the help channel in Slack. Our Technical Facilitators and Learning Support staff are here to help you navigate any challenges.
