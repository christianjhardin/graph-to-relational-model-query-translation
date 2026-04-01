# Graph to Relational Model Query Translation
## Objectives
- Translate graph traversal problems into SQL queries
- Model many-to-many relationships using relational schemas
- Analyze performance and scalability differences between approaches
- Demonstrate advanced SQL techniques for relationship-based data
## Dataset & Schema
The dataset represents relationships between:
- Persons (actors, directors, reviewers)
- Movies
- All relationships are M:N (many to many)
## Key Problems & SQL Solutions
### 1. Actors Who Directed Movies They Acted In
- Identifies individuals who both acted in and directed the same movie
- Uses joins across actor and director tables
Concepts used:
- Multi-table joins
- Filtering on shared keys
### 2. Reviewer Pairs Who Reviewed the Same Movie
Finds pairs of reviewers connected through shared movie reviews
- Concepts used:
  - Self-joins
  - Pairwise combinations
  - Aliasing
- Scalability Note:
  - Results grow at a rate of n(n-1)/2, making this computationally expensive as data increases.
### 3. Actor Pairs in Multiple Movies Together
- Identifies actor pairs who have collaborated more than once
- Concepts used:
  - Self-joins
  - Aggregation (COUNT)
  - GROUP BY and HAVING
### 4. Multi-Hop Graph Traversal (Limitations of SQL)
Example: finding all nodes reachable within 4 hops
- Key Insight:
  - Difficult to implement efficiently in SQL
  - Requires recursion (WITH RECURSIVE in newer SQL versions)
  - Significantly slower compared to graph databases
## Key Takeaways
### Relational Databases (SQL)
- Strengths:
  - Efficient for structured data and well-defined relationships
  - Strong performance for standard queries and joins
  - Widely used in industry
- Limitations:
  - Complex queries require multiple joins
  - Poor performance for deep relationship traversal
  - Relationships are implicit (via foreign keys)
## Performance Considerations
- Query complexity increases significantly with:
  - Self-joins
  - Pairwise comparisons
  - Large datasets
- Graph databases outperform SQL in:
  - Multi-hop traversal
  - Network-based queries
