# monte-carlo-wedding
A Monte Carlo Simulation to estimate the attendance to a wedding using Python, NumPy, and pandas.


## Release Info
**Author**: Paul Leonard
**Version**: 1.0.0

# Wedding Attendance Estimator

## Overview
This Jupyter Notebook uses a Monte Carlo Simulation to estimate the distribution of attendance to a wedding using Python, NumPy, Matplotlib, and pandas.  The analysis returns potential ranges of people to expect at your wedding with associated levels of confidence.  Using accurate attendance estimates and ranges are key to planning successful events.


## Architecture
Input is provided to the Jupyter Notebook through a user-supplied CSV file containing a list of guest parties invited to a wedding, including their guest count and the probability of each party attending the event.  The CSV is consumed into a pandas dataframe and then Monte Carlo simulations are run for the selected number of simulations.  Each simulation uses NumPy's random method and the user-supplied party's probability to determine if each guest party attends the event or not.  A resulting histogram of total wedding attendance is then displayed showing the distribution of attendees to be expected at the wedding.


## Input
Input is provided by the user in the form of a CSV file with the headers ("Chance_of_Attendance,Party_Size") on the first line.  Each subsequent line then contains two values separated by a comma describing that *guest party*.  A guest party should be considered a close and collected group of guests such as a single person, a couple, or a family.  The first value is the chance of that guest party attending the wedding.  The second number is the total number of people in that guest party (single, couple, family).

### Input Modifications
A Notebook variable `include_plus_ones` can be set to True or False.  A True setting adds a plus-one invite to any *guest party* that had an original total size of 1 person in the CSV file.  The plus-one invite may go used or unused.  A random draw with a stated probability distribution is used to decide if each plus-one is used in each simulation or not.  The uniform probability of a plus-one attending is common to all guest parties and can be set using the variable `chance_of_plus_ones`.  A False setting of `include_plus_ones` leaves each guest party at the size defined in the CSV input file.


## Output
The results of the analysis are provided in textual, tabular, and graphical representations to help the user better understand the likely event attendance.


## Change Log
**0.1.0** 9-22-2021 - Initial creation
**0.2.0** 9-22-2021 - Monte Carlo Analysis runs 1000 simulations and displays histogram
**0.3.0** 9-24-2021 - Added normal distribution curve, plot formatting, and results summary
**1.0.0** 9-27-2021 - Added option to automatically account for plus-one guests, expanded assumptions and documentation section


## Assumptions
1. Either the whole *guest party* attends, or none of the CSV listed guest party attends.  (Exception for plus-one invites.)
1. Each *guest party's* decision to attend the wedding or not is independent of the decision of another *guest party's* decision to attend or not.  For example, the simulation does not take into account dependent situations such as  "I'm only going if my brother also attends." or "I'm only going if my ex isn't attending."
1. The user did a fantastic job predicting the chances of each *guest party* attending in the CSV file.  The user should try to reflect influencing circumstances such as local/out-of-town guest, financial ability, calendar availability, and strength of relationship when estimating the chance of a guest party attending.
1. When using the plus-one invite function, all plus-one invites have the same probability of attending.


## Sources/References
- [pandas.DataFrame.apply](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.apply.html)
- [apply](https://www.geeksforgeeks.org/create-a-new-column-in-pandas-dataframe-based-on-the-existing-columns/)
- [Monte Carlo Simulation with Python](https://pbpython.com/monte-carlo.html)
- [plotting normal distribution over histogram](https://matplotlib.org/3.1.1/gallery/statistics/histogram_features.html)
- [What does 5-sigma mean in science?](https://www.zmescience.com/science/what-5-sigma-means-0423423/)
- [counting subsets](https://stackoverflow.com/questions/35277075/python-pandas-counting-the-occurrences-of-a-specific-value)
- [multiple conditionals](https://stackoverflow.com/questions/20995196/pandas-counting-and-summing-specific-conditions)
- [tabulate](https://stackoverflow.com/questions/9535954/printing-lists-as-tabular-data)
- [tabulate docs](https://pypi.org/project/tabulate/0)
