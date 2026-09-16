# visual-state-manager-xamarin-forms

This Xamarin.Forms sample demonstrates how to use the **Visual State Manager (VSM)** with **Syncfusion SfButton** controls to define and manage different visual states in a clean and maintainable way. Visual State Manager enables developers to change control properties automatically when the control transitions between states, eliminating the need for additional code-behind logic and making UI customization easier.

The sample showcases how button text can be updated dynamically based on the current state of the button. States such as **Normal**, **Pressed**, **Checked**, and **Disabled** are defined using Visual State Manager and configured with property setters that update the button text. This provides clear visual feedback to the user while keeping the implementation entirely within XAML.

The sample contains two sections. The first section displays regular disabled `SfButton` controls that use the default button behavior without any Visual State Manager configuration. The second section demonstrates buttons that are configured with Visual State Manager. These buttons automatically update their text when state transitions occur.

An `SfCheckBox` is included to control the button's `IsCheckable` property. When toggle mode is enabled, the button can enter the **Checked** state. This allows developers to observe how button-specific states work alongside the standard common states supported by Visual State Manager.

## Features

- Demonstrates Visual State Manager integration with Syncfusion `SfButton`.
- Defines states entirely in XAML.
- Updates button text automatically based on state transitions.
- Supports Normal, Disabled, Pressed, and Checked states.
- Demonstrates toggle button behavior using `SfCheckBox`.
- Provides a comparison between standard buttons and VSM-enabled buttons.
- Requires minimal code-behind implementation.

## States Demonstrated

### CommonStates

| State | Text |
|---------|---------|
| Normal | Enabled |
| Disabled | Disabled |

### ButtonStates

| State | Text |
|---------|---------|
| Pressed | Clicked |
| Checked | Checked |

## Sample Workflow

1. The application loads and displays multiple Syncfusion buttons.
2. Buttons configured with Visual State Manager display **Enabled** in their Normal state.
3. When the user presses the button, the text changes to **Clicked**.
4. Enabling the checkbox allows the button to enter toggle mode.
5. When the button is checked, the displayed text changes to **Checked**.
6. Disabled buttons automatically display **Disabled** when the control enters the Disabled state.

## Sample

```xml
<button:SfButton Grid.Row="2"
                 IsCheckable="{Binding Source={x:Reference ToggleCheck}, Path=IsChecked}"
                 Grid.Column="1"
                 Text="Enabled">
    <VisualStateManager.VisualStateGroups>
        <VisualStateGroup x:Name="CommonStates">
            <VisualState x:Name="Normal">
                <VisualState.Setters>
                    <Setter Property="Text" Value="Enabled"/>
                </VisualState.Setters>
            </VisualState>

            <VisualState x:Name="Disabled">
                <VisualState.Setters>
                    <Setter Property="Text" Value="Disabled"/>
                </VisualState.Setters>
            </VisualState>
        </VisualStateGroup>

        <VisualStateGroup x:Name="ButtonStates">
            <VisualState x:Name="Pressed">
                <VisualState.Setters>
                    <Setter Property="Text" Value="Clicked"/>
                </VisualState.Setters>
            </VisualState>

            <VisualState x:Name="Checked">
                <VisualState.Setters>
                    <Setter Property="Text" Value="Checked"/>
                </VisualState.Setters>
            </VisualState>
        </VisualStateGroup>
    </VisualStateManager.VisualStateGroups>
</button:SfButton>
```

## Toggle Mode Configuration

The checkbox enables the button's checkable behavior through data binding.

```xml
<button:SfCheckBox
    x:Name="ToggleCheck"
    Text="Enable Toggle Mode"/>
```

```xml
IsCheckable="{Binding Source={x:Reference ToggleCheck}, Path=IsChecked}"
```

## Requirements

- Visual Studio 2019 or later
- Xamarin.Forms
- Syncfusion Xamarin Button controls

## NuGet Package

```text
Syncfusion.Xamarin.Buttons
```

## Running the Sample

1. Clone or download the sample repository.
2. Restore all NuGet packages.
3. Build the application.
4. Deploy and run on Android, iOS, or UWP.
5. Interact with the buttons and toggle checkbox to observe Visual State Manager transitions.

## Conclusion

This sample demonstrates how to use Visual State Manager with Syncfusion `SfButton` controls in Xamarin.Forms applications. By defining visual states directly in XAML, developers can easily customize control behavior, improve maintainability, and provide meaningful visual feedback for user interactions without writing complex state-management logic in code-behind.