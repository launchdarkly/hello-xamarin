# LaunchDarkly Sample Xamarin Application s

We've built a simple demo that demonstrates how LaunchDarkly's SDK works. Since the Xamarin SDK can be used either on Xamarin-compatible mobile devices or in portable .NET code, there are three versions of the demo: an Android app, an iOS app, and a .NET Core console app.

Below, you'll find the basic build procedures, but for more comprehensive instructions, you can visit your [Quickstart page](https://app.launchdarkly.com/quickstart#/) or the [Xamarin SDK reference guide](https://docs.launchdarkly.com/sdk/client-side/xamarin).

## Instructions for Android and iOS

The Android and iOS demos require Visual Studio to build and run. For iOS, besides Visual Studio you must also have [Xcode](https://developer.apple.com/xcode/). You can run either on a real device or a simulator.

These demo apps use Android- and iOS-specific user interface components, rather than Xamarin Forms. The LaunchDarkly Xamarin SDK in itself has no UI functionality, so in a Xamarin Forms app there would be no difference in how you would use the SDK.

1. Open `LaunchDarkly.HelloXamarin.sln` in Visual Studio.

2. Edit `Shared/DemoParameters.cs` and set the value of `MobileKey` to your LaunchDarkly SDK key. If there is an existing boolean feature flag in your LaunchDarkly project that you want to evaluate, set `FeatureFlagKey` to the flag key.

```csharp
    public const string MobileKey = "1234567890abcdef";

    public const string FeatureFlagKey = "my-flag";
```

3. Build and run the `XamarinAndroidApp` or `XamarinIOsApp` project.

You should see the message `"Feature flag '<flag key>' is <true/false> for this user"`.

If you leave the app running and use your LaunchDarkly dashboard to turn the flag off or on, you should see the message change to show the new value, showing how an app can receive live updates.

## Instructions for .NET Core (console)

1. Edit `Shared/DemoParameters` as described above.

2. If you are using Visual Studio, open `LaunchDarkly.HelloXamarin.sln` and run the `XamarinConsoleApp` project. Or, to run from the command line, type the following command:

```
    dotnet run --project XamarinConsoleApp
```

You should see the message `"Feature flag '<flag key>' is <true/false> for this user"`.

Unlike the Android and iOS demos, the console demo exits immediately, so it does not demonstrate receiving live updates of flags. However, the same streaming update functionality can be used in a long-running .NET Core application just as it would in a mobile app.
