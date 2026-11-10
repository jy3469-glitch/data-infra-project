# Lab 2 · Reflection

**Name:** June Yoon
**Due:** Sunday, November 8 at 11:59 PM

Answer in a few sentences each. Specific beats long.

**1. Your join.** Which column connected your two tables? How many rows went in, how many came out, and what did you do about anything that didn't match?
I used BBL column to join two tables. 392 rows went in and 385 rows were joined. I tried to use adress column to match, but some condominium buildings had multiple BBL in one building, so I need another data to join those 7 POPS.
**2. The reading.** Kleppmann describes tables (relational), documents (nested, like JSON) and graphs as different ways to model data. Would any of your two tables have been easier to work with as a document or a graph? Why or why not?
I think the relational model works best for my POPS and PLUTO datasets because both are structured as tables and can be joined using BBL. A document model would not offer much advantage for this analysis, but a graph model could be useful for exploring more complex relationships among POPS, buildings, and property owners.
---

**Checklist before you submit**

- [ ] `notebooks/lab2_joins.ipynb`: Part A run in class, Part B completed with your own tables
- [ ] Every Part B text cell filled in (grain, unmatched rows, what the result tells you)
- [ ] This file answered
- [ ] Notebook saved (Cmd+S), then committed and pushed
- [ ] Repo URL submitted on CourseWorks
