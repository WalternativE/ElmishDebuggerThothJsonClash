# Repro for Elmish Debugger Thoth Json version clash

Currently `Thoth.Fetch` v1 needs a minimal `Thoth.Json` version of >=3.1.0.
The Elmish Debugger states that it is ok with `Thoth.Json` >= 3.0.0. As long as this configuration
is present everything works fine.

If we introduce the `Thoth.Fetch` v2 beta into the mix we lift the minimal needed version of
`Thoth.Json` to >= 3.4.1 (the newest stable version). Theoretically the Elmish Debugger _should_ be
fine with that. In practice failures can occur. Using the Fable Compiler things will most likely work
(at least there are no obvious errors) - using the .NET Core SDK via `dotnet build` on the client project
the compilation will fail.
