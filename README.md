# mitoSoft.Razor.Spinners
A library providing different spinners for Blazor websites.
It is possible to use with .Net5 as well as .Net6.
It comes with a so-called ModalSpinner and an OverlaySpinner.

## Dependencies

 - Microsoft.AspNetCore.Components.Web (5.0.12)
 - mitoSoft.Razor.Components (6.1.1)

## ModalSpinner

The ModalSpinner is a standard Bootstrap spinner embedded in a Bootstrap modal.
The usage is shown in the following code snippet:

```c#
  
  ...  
  <mitoSoft.Razor.Spinners.ModalSpinner @ref="@_modal" />

  @code {
    private int currentCount = 0;
    private mitoSoft.Razor.Spinners.ModalSpinner _modal = default!;

    private void IncrementCount()
    {
        _modal.Show();

        await Task.Delay(5000);

        currentCount++;
        
	_modal.Hide();
    }
 
    ...

```

### Look and Feel

![Screenshot](ModalSpinnerExample.png)

## OverlaySpinner

The OverlaySpinner pops up as a standard Bootstrap spinner in front of a shaded overlay, which disable all frontend controls and avoid users of breaking their actual session.
The usage is shown in the following code snippet:

```c#
  
  ...  
  <mitoSoft.Razor.Spinners.OverlaySpinner @ref="@_overlay" />

  @code {
    private int currentCount = 0;
    private mitoSoft.Razor.Spinners.OverlaySpinner _overlay = default!;
    
    private void IncrementCount()
    {
        _overlay.Show();

        await Task.Delay(5000);

        currentCount++;
        
	_overlay.Hide();
    }
 
    ...

```

### Look and Feel

![Screenshot](OverlaySpinnerExample.png)

## Default Style

To apply a predefined style for the spinners use the following stylesheet 

./_content/mitoSoft.Razor.Spinners/css/default.css

in 

_Layout.cshtml (.Net6)

or in

_Host.cshtml (.Net5).

```HTML 
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <base href="~/" />
	
    <link rel="stylesheet" href="./_content/mitoSoft.Razor.Spinners/css/default.css" />
    
    <link rel="stylesheet" href="css/bootstrap/bootstrap.min.css" />
    <link href="css/site.css" rel="stylesheet" />
    <link href="mitoSoft.Razor.Spinners.Examples.DotNet6.styles.css" rel="stylesheet" />
    <component type="typeof(HeadOutlet)" render-mode="ServerPrerendered" />
</head>
```
