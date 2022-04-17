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

| AuthorID | FullName      | Email                       | Bio            |
|----------|---------------|-----------------------------|----------------|
| 1        | Eric Fleming  | ericfleming@nimblepros.com  | Long Text Here |
| 2        | Kyle McMaster | kylemcmaster@nimblepros.com | Long Text Here |
| 3        | Steve Smith   | steve@nimblepros.com        | Long Text Here |

### BlogPosts

| Slug                          | Title                                | Body           | AuthorID | Views |
|-------------------------------|--------------------------------------|----------------|----------|-------|
| serilog-structured-logging    | Structured Logging with Serilog      | Long Text Here | 1        | 123   |
| persisting-smart-enum         | Persisting a Smart Enum with EF Core | Long Text Here | 2        | 234   |
| localization-aspnet-core-apis | Localization in ASP.NET Core APIs    | Long Text Here | 3        | 345   |

### Categories

| CategoryID | Category             |
|------------|----------------------|
| 1          | Software Development |
| 2          | Cloud Computing      |
| 3          | Web APIs             |

### Tags

| TagID | Tag          |
|-------|--------------|
| 1     | logging      |
| 2     | serilog      |
| 3     | appinsights  |
| 4     | smartenum    |
| 5     | efcore       |
| 6     | localization |
| 7     | aspnetcore   |
| 8     | web-api      |

### SlugCategories

| Slug                          | CategoryID |
|-------------------------------|------------|
| serilog-structured-logging    | 1          |
| serilog-structured-logging    | 2          |
| persisting-smart-enum         | 1          |
| localization-aspnet-core-apis | 1          |
| localization-aspnet-core-apis | 3          |

### SlugTags

| Slug                          | TagID |
|-------------------------------|-------|
| serilog-structured-logging    | 1     |
| serilog-structured-logging    | 2     |
| serilog-structured-logging    | 3     |
| persisting-smart-enum         | 4     |
| persisting-smart-enum         | 5     |
| localization-aspnet-core-apis | 6     |
| localization-aspnet-core-apis | 7     |
| localization-aspnet-core-apis | 8     |

## Extra Credit

Once you've completed the initial exercise, modify your design to support these additional features:

1. Blog posts can have one or many authors.
2. Users would like to see a report showing views per blog post per day.
3. Blog posts can have Comments. Each Comment should include a Title, Commenter Name, and Body.
