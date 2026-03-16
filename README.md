# PlSql-Parser-Antlr4-Csharp
A generated C# PlSql parser, from the [PlSqlLexer.g4](https://github.com/antlr/grammars-v4/blob/master/sql/plsql/PlSqlLexer.g4) and [PlSqlParser.g4](https://github.com/antlr/grammars-v4/blob/master/sql/plsql/PlSqlParser.g4) grammars using [ANTLR4](https://github.com/antlr/antlr4) 4.13.2 tool

## Content
Files are in the `src` folder and can be copied to any C# project to parse Pl Sql.

You must also add the `Antlr4.Runtime.Standard` NuGet package to your project to use the generated parser.

## Usage
Inherit from the `PlSqlParserBaseVisitor` class to create a visitor that can traverse the parse tree and extract information or perform actions based on the parsed Pl Sql code.
Or If you prefer, you can use the `PlSqlParserBaseListener` class to create a listener that responds to events during the parsing process.

```csharp
var input = """
    [PL/SQL code to parse]  
    """;
var lexer = new PlSqlLexer(new AntlrInputStream(input));
var tokens = new CommonTokenStream(lexer);
var parser = new PlSqlParser(tokens);
var tree = parser.sql_script();
tree.Accept(new YourCustomVisitor(input));
```
