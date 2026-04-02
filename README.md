# LSAnalyzer2 Repo
LSAnalyzer is my take on a software that enables GUI-driven data analysis for Large-Scale Assessment studies like PISA, PIRLS and so forth. Therefore, it might provide an alternative to IEA IDB Analyzer ([https://www.iea.nl/data-tools/tools](https://www.iea.nl/data-tools/tools)), but relies on a very different tech stack.

Any version is written in C#, uses .NET (>=7.0) and follows the MVVM pattern.

## Version 1 - R-based and Windows-only
The first version uses a fork of [R.NET](https://www.nuget.org/packages/R.NET/) to call into an R.dll and makes calculations via R-package [BIFIEsurvey](https://cran.r-project.org/web/packages/BIFIEsurvey/index.html), which is co-authored by me. In order to access R.dll, a separate R installation is necessary und package BIFIEsurvey has to be installed in its global library.

Version 1 uses WPF as GUI framework and is therefore Windows-only.

Version 1 has [releases](https://github.com/konradoberwimmer/LSAnalyzer/releases) and will be further maintained (bugfixes and minor extensions).

Source code of the first version is in repository [https://github.com/konradoberwimmer/LSAnalyzer/](https://github.com/konradoberwimmer/LSAnalyzer/). Besides the main project, there are projects for the Microsoft installer (powered by the WiX toolset) and a test project with unit and integration tests (xUnit).

## Version 2 - "Stand-alone" and cross-platform
The second version (this repository), that is now my main focus of development, aims at overcoming the limitations version 1 imposes: On the one hand, I try to cut the dependency to an R installation by including my own Rust crate [replicest](https://github.com/konradoberwimmer/replicest) for calculations. On the other hand, [Avalonia](https://www.nuget.org/packages/avalonia) is used as GUI framework, making LSAnalyzer cross-platform with Windows, Linux and MacOS as targets.

Version 2 is very much **work in progress**.