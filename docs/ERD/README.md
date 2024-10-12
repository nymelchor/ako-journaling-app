# Entity-Relationship Diagrams

**ERD**s are a graphical representation of the entities in a system and the relationships between those entities.

## Pre-Development ERDs

![First Pass ERD](Akó-ERD-v0.1.png "First Pass ERD")

While this design effectively addresses the core requirements of the journaling app, several areas warrant improvement for enhanced scalability, performance, and user experience. First, this implementation restricts flexibility with regards to moods - there's no support for associating multiple moods to a single entry or capturing mood intensity (i.e slightly happy vs extremely happy). Data retrieval may slow down over time when querying for heavily tagged entries and searching through multiple entries. Additionally, the absence of role-based access prevents collaborative features, such as two people contributing to one entry. Furthermore, there is no mechanism to track revisions that may come later, similar to git, which could enlighten users to see how their thoughts evolved. Data-related issues could arise without soft deletes, which should be integrated to facilitate recovery of deleted entries. In this iteration, a deleted journal entry cannot be recovered.

| **Pros**                                                     | **Cons**                                                    |
|--------------------------------------------------------------|-------------------------------------------------------------|
| Custom named journals                                        | Absence of a role-based access control for shared journals  |
| Users can create multiple journals                           | No soft delete functionality                                |
| User-defined tags for entries                                | Costly queries on tag and mood usage trends                 |
| Supports mood tracking for entries                           | Inadequate options for multi-mood entries or intensity      |
| Suitable for basic journaling needs                          | Lacks version control for entries                           |
