If you want to contribute to the UERANSIM. Here you can find some development guidelines.

### C++ Coding Style

- This specific coding style guideline shall be used inside of the UERANSIM project
- Do **not** use C language, and don't write C-style codes. It is obsolete and should not be used. Use modern and rich C++ features instead.
- Use [Microsoft](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/code-style-rule-options?view=vs-2017)'s C++ coding guidelines, with following exceptions:
    - Use `AlwaysBreakTemplateDeclarations: Yes` (for clang tidy)
    - Use `camelCase` for instance methods, `PascalCase` for static functions.

### 3GPP Specifications

All of the 5G with all internals are designed and defined by international 3GPP organization. Our ultimate references for 5G implementation are these documents. Here's the list of technical specifications often used by UERANSIM:

- [TS 23.501]()
- [TS 23.502]()
- [TS 24.501]()
- [TS 38.300]()
- [TS 38.304]()
- [TS 38.322]()
- [TS 38.323]()
- [TS 38.331]()
- [TS 38.401]()
- [TS 38.410]()
- [TS 38.411]()
- [TS 38.412]()
- [TS 38.413]()
- [TS 38.414]()
- [TS 38.415]()

We currently use release-15 for 3GPP specifications, and have a plan to switch to release-16 in the future.