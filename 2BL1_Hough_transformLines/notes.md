### Notes:
- In real world, we have real image I(x,y) and we want to find some useful data from it.
- A Parametric model, is a class of instances where each is defined by a value of parameters.  
    For example, Lines, Circles, parametric templates etc
- Things to remember while fitting a Parametric model:
	- Choose a parametric model to represent set of features.
	- Membership criterion is not local that means we cannot tell just by looking at particular point/pixel, if that point/pixel belongs to certain model or not. We have to see bigger picture (multipe points/pixels)
	- Think about computational complexity. It is not possible and feasible to check all combinations of parametric models.
- Consider the case of searching for line. Even though we already have edges, there are still issues remaining:
	- Extra edge point (clutter), multiple lines/edges at same point.
	- Only some part of each line is detected while remaining part still missing.
	- Noise in measured edge points, orientation
- Voting:
	- Voting is general technique where we let the features vote for all modesl that are compatible with it.
	- Steps are:
		1. Cycle through features, each casting votes for model parametersor set of model parameters.
		2. Look for model parameters/ set of model parameters that receive more number of votes.
	- Why it work:
		- Even thoughnoise and clutter features also cast their votes, in general, these votes are inconsistent with majority of good features voting.
		- Even though some fragments of model are not observed (that means, they don't get enough votes) , as other fragments are observed (got enough votes to be considered), the model itself gets identified.
- In case of fitting lines, model questions can be:
	- Given points that belong to a line, what is the line? (what is parametric model)
	- How many lines are there? (number of parametric models.)
	- Which point belong to which line? (observing and choosing parametric model out of multiple models.)
- Hough transform:
	- Each edge point votes for compatible lines.
	- Lines which get more number of votes are selected.
	