# Data Design Exercise

Designing a database schema using normalization techniques.

## Instructions

Using the non-normalized data in the **BlogPost** table below, create a database schema that will represent the same data in 3rd Normal Form. When you're done, make a pull request to the upstream repo ([this one](https://github.com/DevBetterCom/DataDesignExercise)) so we can discuss in the PR comments.

### Blog Posts

| Slug                          | Title                                | Body           | AuthorName    | AuthorEmail                 | AuthorBio      | Category1            | Category2       | Tags                            | Views |
|-------------------------------|--------------------------------------|----------------|---------------|-----------------------------|----------------|----------------------|-----------------|---------------------------------|-------|
| serilog-structured-logging    | Structured Logging with Serilog      | Long Text Here | Eric Fleming  | ericfleming@nimblepros.com  | Long Text Here | Software Development | Cloud Computing | logging,serilog,appinsights     | 123   |
| persisting-smart-enum         | Persisting a Smart Enum with EF Core | Long Text Here | Kyle McMaster | kylemcmaster@nimblepros.com | Long Text Here | Software Development | null            | smartenum,efcore                | 234   |
| localization-aspnet-core-apis | Localization in ASP.NET Core APIs    | Long Text Here | Steve Smith   | steve@nimblepros.com        | Long Text Here | Software Development | Web APIs        | localization,aspnetcore,web-api | 345   |

[Table Generated with TableGenerator.com](https://www.tablesgenerator.com/markdown_tables#)

Fork this repository and add your tables here:

(your tables go here - you can use TableGenerator to create them. Include the data from the sample above in your tables)

### Authors

| Id       | FullName      | Email                       | Bio            |
|----------|---------------|-----------------------------|----------------|
| 1        | Eric Fleming  | ericfleming@nimblepros.com  | Long Text Here |
| 2        | Kyle McMaster | kylemcmaster@nimblepros.com | Long Text Here |
| 3        | Steve Smith   | steve@nimblepros.com        | Long Text Here |

### BlogPosts

| Id | Slug                          | Title                                | Body           | Authors.Id | Views |
|----|-------------------------------|--------------------------------------|----------------|------------|-------|
| 1  | serilog-structured-logging    | Structured Logging with Serilog      | Long Text Here | 1          | 123   |
| 2  | persisting-smart-enum         | Persisting a Smart Enum with EF Core | Long Text Here | 2          | 234   |
| 3  | localization-aspnet-core-apis | Localization in ASP.NET Core APIs    | Long Text Here | 3          | 345   |

### Categories

| Id | Category             |
|----|----------------------|
| 1  | Software Development |
| 2  | Cloud Computing      |
| 3  | Web APIs             |

### Tags

| Id | Tag          |
|----|--------------|
| 1  | logging      |
| 2  | serilog      |
| 3  | appinsights  |
| 4  | smartenum    |
| 5  | efcore       |
| 6  | localization |
| 7  | aspnetcore   |
| 8  | web-api      |

### BlogPostsCategories

| BlogPosts.Id | Categories.Id |
|--------------|---------------|
| 1            | 1             |
| 1            | 2             |
| 2            | 1             |
| 3            | 1             |
| 3            | 3             |

## BlogPostsTags

| BlogPosts.Id | Tags.Id |
|--------------|---------|
| 1            | 1       |
| 1            | 2       |
| 1            | 3       |
| 2            | 4       |
| 2            | 5       |
| 3            | 6       |
| 3            | 7       |
| 3            | 8       |

## Extra Credit 1: More Schema Additions

Once you've completed the initial exercise, modify your design to support these additional features:

1. Blog posts can have one or many authors.
2. Users would like to see a report showing views per blog post per day.
3. Blog posts can have Comments. Each Comment should include a Title, Commenter Name, and Body.

## Extra Credit 2: The Queries

You're building a blog based on the data that's been modeled above. The home page of the blog lists the following:

1. The last 10 blog posts published by an author, ordered by most recent first.
1. Each blog post listing includes the title and author name(s).
1. Each blog post listing includes the categories that article is in. (tags are not shown on the home page with articles)
1. A sidebar widget lists all authors with their article count.
1. A sidebar widget lists all categories with their article count.

Write the SQL queries required **using the original schema** to support these features. Assume the total number of authors is < 100 and the total number of articles is less than 1000 if that matters in your decision-making process.

- How many queries were required?
- What kind of performance characteristics does the page have with regard to its data queries and data schema?

## Extra Credit 3: Return of the Custom Schema

See Extra Credit 2. The home page of the blog site has the exact same features.

Write the SQL queries required **using your new schema** to support these features. Same assumptions regarding total data size.

- How many queries were required?
- What kind of performance characteristics does the page have with regard to its data queries and data schema?
## Extra Credit 1: More Schema Additions

### BlogPosts

| Id | Slug                          | Title                                | Body           |
|----|-------------------------------|--------------------------------------|----------------|
| 1  | serilog-structured-logging    | Structured Logging with Serilog      | Long Text Here |
| 2  | persisting-smart-enum         | Persisting a Smart Enum with EF Core | Long Text Here |
| 3  | localization-aspnet-core-apis | Localization in ASP.NET Core APIs    | Long Text Here |

### BlogPostsAuthors

| BlogPosts.Id | Authors.Id |
|--------------|------------|
| 1            | 1          |
| 2            | 2          |
| 3            | 3          |

### ViewsPerDay

| Id | BlogPosts.Id | Date       | Views |
|----|--------------|------------|-------|
| 1  | 1            | 2022-04-29 | 89    |
| 2  | 1            | 2022-04-30 | 123   |
| 3  | 2            | 2022-04-29 | 204   |
| 4  | 2            | 2022-04-30 | 234   |
| 5  | 3            | 2022-04-29 | 320   |
| 6  | 3            | 2022-04-30 | 345   |

### Comments

| Id | BlogPosts.Id | Title                         | DateTime            | CommenterName | Body                                    |
|----|--------------|-------------------------------|---------------------|---------------|-----------------------------------------|
| 1  | 1            | Inspiring article!            | 2022-05-07 13:23:44 | Elaine Ng     | This one made my day!                   |
| 2  | 3            | That's what I was looking for | 2022-05-02 15:24:54 | Jason Stone   | Glad I read it! Clear and to the point. |
