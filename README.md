### Indexing columns that used in WHERE, ORDER BY AND GROUP clause:
Indexing makes the query faster because it stores values of indexed columns in separate 
location in certain order with record pointer on it. Now instead of search through every
record of specified column in actual table, MySQL will search to the indexed table which is already
sorted and therefore easy to identify the matched value. The columns in this case are 
the ff:

JobCategories.name\
JobTypes.name\
Jobs.name\
Jobs.description\
Jobs.detail\
Jobs.business_skill\
Jobs.knowledge\
Jobs.location\
Jobs.activity\
Jobs.salary_statistic_group\
Jobs.salary_range_remarks\
Jobs.restriction\
Jobs.remarks\
Personalities.name\
PracticalSkills.name\
BasicAbilities.name\
Tools.name\
CareerPaths.name\
RecQualifications.name\
ReqQualifications.name\
publish_status\
Jobs.deleted\
Jobs.id\
Jobs.sort_order

### LIKE condition with leading wildcard or %
Leading wildcard forces MySQL to run full table scan which defeat the purpose of
indexing. On the other hand we should consider placing the wildcard to the end of
searching value in that sense you can use both wildcard and indexes. The way of search
may differ a little because instead of matching value in any position, it will only match
record with starting search value.

### Full Text instead of LIKE wildcard
Full text search can replace **LIKE "wildcard%"** statement if you are searching against large number of columns.
