# g++-11
g++11 - gnu c++ compiler wrapper which enables c++11 standard support

# Why?
My usual setup for code development uses `CMake`-based build system and Eclipse CDT. `CMake` generates Eclipse project files which I subsequently import into my CDT workspace.
For the CDT indexer to properly see my code as well as the `gcc` c++ header files it is crucial to have the builtin `__cplusplus` macro set to a value which matches c++11.
I have made several attempts to force Eclipse's discoverer module to use the `-std=c++11` parameter for retrieval of that macro, but none of that made the settings permanent.
In the end I came up with this idea for the g++ wrapper which calls `c++`/`g++` with the `-std=c++11` option always enabled. Now I run `CMake` with the wrapper set up as the project's c++ compiler. This propagates the compiler setting to Eclipse project files and with that the CDT discoverer has no other way but to always retrieve compiler setup which corresponds to the c++11 standard.

# TODO
c++14? c++17? `.bat` file for `MinGW64`? `c++0x` / `c++11` distinction from the gcc version?
