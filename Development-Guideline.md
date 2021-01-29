If you want to contribute to the UERANSIM. Here you can find some development guidelines.

### C++ Coding Style

- This specific coding style guideline shall be used inside of the UERANSIM project
- Do not use C language, and don't write C-style codes. It is obsolete and should not be used. Use modern and rich C++ features instead.
- Use [Microsoft](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/code-style-rule-options?view=vs-2017)'s C++ coding guidelines, with following exceptions:
    - Use `AlwaysBreakTemplateDeclarations: Yes` (for clang tidy)
    - Use `camelCase` for instance methods, `PascalCase` for static functions.
