This UERANSIM specific coding style guideline should be used inside of UERANSIM project.

### JAVA Guidelines

- Do **not** use Java-style getter and setter methods. Use **public** fields instead. Use getters and setters if and only if there is a business logic behind it.
- Do **not** use Java 8 concurrent programming procedures. Use NTS architecture instead.
- Prefix all interfaces with `"I"`.
    - **✖** `public interface MyInterface`
    - **✓**    `public interface IMyInterface`
- Use **static** and **final** wherever possible.
- Always use **immutable types** except you can't.
- Use package-private whenever possible.
- Use **PascalCase** for acronyms.
    - **✖** `getUEAssociatedPDU`
    - **✓** `getUeAssociatedPdu`