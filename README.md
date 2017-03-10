# Asp Net Core Web Api
The goal of this project is to serve as a baseline of study for .NetCore by implementing an API and all the tests needed to ensure its ready to ship.

# Before getting started

The project runs under Visual Studio 2015 using `project.json`.
Please don't migrate to VS2017 just yet. VS2017 isn't ready to run with Nunit for .NET Core (or other test suite) as the `dotnet-runner-*` are not supported anymore in .csproj. Be advice, your tests will not be discovered.

# Lessons learnt

To use Nunit you'll need to modify your `project.json` so it looks like this:

```
{
    "version": "1.0.0-*",

    "dependencies": {
        "NUnit": "3.5.0",
        "dotnet-test-nunit": "3.4.0-beta-3"
    },

    "testRunner": "nunit",

    "frameworks": {
        "netcoreapp1.0": {
            "imports": "portable-net45+win8",
            "dependencies": {
                "Microsoft.NETCore.App": {
                    "version": "1.0.0-*",
                    "type": "platform"
                }
            }
        }
    }
}
```
