# Xamarin.Forms Calendar View Sample

A C# sample of a calendar and date-range selection UI for Android and iOS. It uses Xamarin.Forms `CollectionView` to display months and SkiaSharp to draw each month.

This is a historical Xamarin.Forms sample, useful for studying custom rendering and selection behavior. It is not a packaged calendar library.

## Preview

| iOS | Android |
| --- | --- |
| <img src="ios-gif.gif" width="337" alt="Calendar selection on iOS"> | <img src="android-gif.gif" width="337" alt="Calendar selection on Android"> |

## How it works

- [CalendarView](CalendarViewSample/Calendar/CalendarView.cs) extends `CollectionView` and creates a `SkMonthView` for each month.
- [SkMonthView](CalendarViewSample/Calendar/SkMonthView.cs) draws calendar cells and handles selection.
- [MainPage](CalendarViewSample/MainPage.cs) supplies a list of months through `ItemsSource`.
- `First` and `Last` expose the selected `CalendarObject` values through two-way bindings.
- `FirstAvailableDate` and `LastAvailableDate` constrain the selectable dates.
- Cell rendering and styling can be changed in `SkMonthView`.

## Run the sample

The solution targets the original Xamarin toolchain. The shared project uses .NET Standard 2.0, Xamarin.Forms 4.0.0.425677, and SkiaSharp 1.68.0. Use an environment compatible with these versions and the platform projects.

1. Clone this repository.
2. Open `CalendarViewSample.sln` in a Xamarin-capable development environment.
3. Restore NuGet packages.
4. Select `CalendarViewSample.Android` or `CalendarViewSample.iOS` as the startup project.
5. Build and run on a compatible emulator, simulator, or device. The iOS target requires the corresponding Apple build tools.

The Android startup code enables the original `CollectionView_Experimental` flag. Updating the sample for a newer toolchain or .NET MAUI requires a separate migration; the repository does not include one.
