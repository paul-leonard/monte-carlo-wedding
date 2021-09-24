# monte-carlo-wedding
A Monte Carlo Simulation to estimate the distribution of attendants to a wedding using Python, NumPy, and pandas.


## Release Info
**Author**: Paul Leonard
**Version**: 0.1.0


## Overview
This Jupyter Notebook provides a way for users to estimate a distribution of attendees to a wedding or other event.  Using accurate attendance estimates and ranges are key to planning successful events.


## Architecture
Input is provided to the Jupyter Notebook through a user-supplied CSV file containing a list of guest parties invited to a wedding, including their guest count and the probability of each party attending the event.  The CSV is consumed into a pandas dataframe and then Monte Carlo simulations are run for the selected number of simulations.  Each simulation uses NumPy's random method and the user-supplied party's probability to determine if each guest party attends the event or not.  A resulting histogram of total wedding attendance is then displayed showing the distribution of attendees to be expected at the wedding.


## Future Features
- make a guest option where any party size of 1 automatically increases to 2


## Change Log
**0.1.0** 9-22-2021 - Initial creation
**0.2.0** 9-22-2021 - Monte Carlo Analysis runs 1000 simulations and displays histogram


## Sources/References
- [pandas.DataFrame.apply](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.apply.html)
- [apply](https://www.geeksforgeeks.org/create-a-new-column-in-pandas-dataframe-based-on-the-existing-columns/)
- [Monte Carlo Simulation with Python](https://pbpython.com/monte-carlo.html)
- [plotting normal distribution over histogram](https://matplotlib.org/3.1.1/gallery/statistics/histogram_features.html)
- [What does 5-sigma mean in science?](https://www.zmescience.com/science/what-5-sigma-means-0423423/)
- [tabulate](https://stackoverflow.com/questions/9535954/printing-lists-as-tabular-data)
- [tabulate docs](https://pypi.org/project/tabulate/0)
