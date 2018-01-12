# Log4Net ASP .NET Core Logger Provider

[![Build status](https://ci.appveyor.com/api/projects/status/qd1ofsdky7anj2nk?svg=true)](https://ci.appveyor.com/project/iwillspeak/log4netprovider)

This repository contains a simple `ILoggerProvider` implementation which sends all log messages to [Log4Net][log4net].

## Getting Started

This logging provider can be used from anywhere which supports .NET Standard 2.0 or above. To get started just install the NuGet package:

    > Install-Package Jmw.Log4netProviderFork

To add the Log4Net provider to your logging repository add the following to your `Configure` method:

```c#
loggerRepository.AddLog4Net();
```

This will configure Log4Net using a file called `log4net.config` in your application's output directory. If the file does not exist then the `BasicConfigurator` will be used to set up console logging only.

## Custom Configuration

To specify a different location for the config file, or to tell log4net to watch for changes there are a few overloads:

```c#
lr.AddLog4Net("logging.config")
  .AddLog4Net("logging.config", true)
  .AddLog4Net(new FileInfo("log.conf"))
  .AddLog4Net(new FileInfo("log.conf"), true));
```

## Bleeding Edge Builds

The latest builds are available as pre-release packages from `https://ci.appveyor.com/nuget/log4netprovider-91kex3llaig0`. Only use these if you _really_ know what you're doing though. No guarantees are made.

 [log4net]: https://logging.apache.org/log4net/
