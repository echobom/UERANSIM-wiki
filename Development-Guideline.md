If you want to contribute to the UERANSIM. Here you can find some development guidelines.

---

### C++ Coding Style

- This UERANSIM-specific coding style guideline shall be used inside of the UERANSIM project.
- Do not use C language, and don't write C-style codes. Use modern and rich C++ features instead.
- Use Microsoft's C++ coding guidelines, with following exceptions:
    - Use `AlwaysBreakTemplateDeclarations: Yes` (for clang tidy)
    - Use `camelCase` for instance methods, `PascalCase` for static functions.

---

### Development Environment

It is recommended to use [Clion](https://www.jetbrains.com/clion/) as an IDE.

1. Start Clion C++ IDE
2. Click `Open`
3. Select the root folder of UERANSIM and hit OK
4. Clion will ask you if you want to import the project as `CMake` or `makefile`. Select **CMake**.
5. Click `Build/Build Project` from the top menu.

---

### Build and Compile

Build instructions written in [Installation Wiki](https://github.com/aligungr/UERANSIM/wiki/Installation) is **not** required for developers. You should be able to build normally inside of Clion C++ IDE. You can also build in Debug mode, and/or utilize the debugger.

If you *add*, *remove* or *rename* a source file, make sure that you click `Reload CMake Project` from the menu, before building the project.

---

### 3GPP Specifications

Here's the list of technical specifications often used by UERANSIM:

- [TS 23.501](https://www.etsi.org/deliver/etsi_ts/123500_123599/123501/15.12.00_60/ts_123501v151200p.pdf) : System architecture for the 5G System
- [TS 23.502](https://www.etsi.org/deliver/etsi_ts/123500_123599/123502/15.12.00_60/ts_123502v151200p.pdf) : Procedures for the 5G System
- [TS 24.007](https://www.etsi.org/deliver/etsi_ts/124000_124099/124007/16.05.00_60/ts_124007v160500p.pdf) : Mobile radio interface signalling layer 3; General Aspects
- [TS 24.501](https://www.etsi.org/deliver/etsi_ts/124500_124599/124501/15.06.00_60/ts_124501v150600p.pdf) : Non-Access-Stratum (NAS) protocol for 5G System
- [TS 31.101](https://www.etsi.org/deliver/etsi_ts/131100_131199/131101/15.03.00_60/ts_131101v150300p.pdf) : UICC-terminal interface; Physical and logical characteristics
- [TS 31.102](https://www.etsi.org/deliver/etsi_ts/131100_131199/131102/15.11.00_60/ts_131102v151100p.pdf) : Characteristics of the USIM Application
- [TS 31.111](https://www.etsi.org/deliver/etsi_ts/131100_131199/131111/15.10.00_60/ts_131111v151000p.pdf) : USIM Application Toolkit (USAT)  
- [TS 33.501](https://www.etsi.org/deliver/etsi_ts/133500_133599/133501/15.11.00_60/ts_133501v151100p.pdf) : Security architecture and procedures for 5G System
- [TS 38.201](https://www.etsi.org/deliver/etsi_ts/138200_138299/138201/15.00.00_60/ts_138201v150000p.pdf) : NR; Physical layer; General description
- [TS 38.202](https://www.etsi.org/deliver/etsi_ts/138200_138299/138202/15.06.00_60/ts_138202v150600p.pdf) : NR; Services provided by the physical layer
- [TS 38.300](https://www.etsi.org/deliver/etsi_ts/138300_138399/138300/15.11.00_60/ts_138300v151100p.pdf) : NR and NG-RAN Overall description; 
- [TS 38.304](https://www.etsi.org/deliver/etsi_ts/138300_138399/138304/15.07.00_60/ts_138304v150700p.pdf) : NR; User Equipment (UE) procedures in idle mode and in RRC Inactive state
- [TS 38.322](https://www.etsi.org/deliver/etsi_ts/138300_138399/138322/16.01.00_60/ts_138322v160100p.pdf) : NR; Radio Link Control (RLC) protocol specification
- [TS 38.323](https://www.etsi.org/deliver/etsi_ts/138300_138399/138323/16.02.00_60/ts_138323v160200p.pdf) : NR; Packet Data Convergence Protocol (PDCP) specification
- [TS 38.331](https://www.etsi.org/deliver/etsi_ts/138300_138399/138331/15.12.00_60/ts_138331v151200p.pdf) : NR; Radio Resource Control (RRC); Protocol specification
- [TS 38.401](https://www.etsi.org/deliver/etsi_ts/138400_138499/138401/16.04.00_60/ts_138401v160400p.pdf) : NG-RAN; Architecture description
- [TS 38.410](https://www.etsi.org/deliver/etsi_ts/138400_138499/138410/16.03.00_60/ts_138410v160300p.pdf) : NG-RAN; NG general aspects and principles
- [TS 38.411](https://www.etsi.org/deliver/etsi_ts/138400_138499/138411/16.00.00_60/ts_138411v160000p.pdf) : NG-RAN; NG layer 1
- [TS 38.412](https://www.etsi.org/deliver/etsi_ts/138400_138499/138412/16.01.00_60/ts_138412v160100p.pdf) : NG-RAN; NG signalling transport
- [TS 38.413](https://www.etsi.org/deliver/etsi_ts/138400_138499/138413/15.06.00_60/ts_138413v150600p.pdf) : NG-RAN; NG Application Protocol (NGAP)
- [TS 38.414](https://www.etsi.org/deliver/etsi_ts/138400_138499/138414/16.00.00_60/ts_138414v160000p.pdf) : NG-RAN; NG data transport
- [TS 38.415](https://www.etsi.org/deliver/etsi_ts/138400_138499/138415/16.03.00_60/ts_138415v160300p.pdf) : NG-RAN; PDU session user plane protocol

We use release **15.6.0** for 3GPP specifications
