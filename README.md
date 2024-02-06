# Brilliant Reversals Alert

This code is a sample implementation of the Brilliant Reversals Alert indicator for the MQL5 platform. It is designed to detect potential trend reversals in the market and send alert notifications when a reversal is detected.

## Input Parameters

- `ReversalPeriod`: The period for reversal detection. This parameter determines the number of previous bars to consider when calculating the average high and low prices for detecting reversals.
- `AlertThreshold`: The threshold for reversal detection. This parameter sets the minimum difference between the current high and the average high, as well as the minimum difference between the current low and the average low, for a reversal to be considered.
- `AlertTimeout`: The timeout for alert notifications in minutes. This parameter controls the minimum time interval between consecutive alert notifications.

## Global Variables

- `lastAlertTime`: The last time an alert was sent. This variable is used to track the time of the last alert notification to avoid sending consecutive alerts within a short time interval.
- `prevHigh[]`: An array to store the previous high prices. This array is used to calculate the average high price for detecting reversals.
- `prevLow[]`: An array to store the previous low prices. This array is used to calculate the average low price for detecting reversals.

## Initialization Function

The `OnInit()` function is called during the initialization of the expert advisor. In this function, the global variables and arrays are initialized. The `ArrayResize()` function is used to resize the `prevHigh[]` and `prevLow[]` arrays based on the specified `ReversalPeriod`. The `lastAlertTime` variable is set to 0 to indicate that no alerts have been sent yet.

## Deinitialization Function

The `OnDeinit()` function is called during the deinitialization of the expert advisor. This function can be used to perform any necessary cleanup operations.

## Tick Function

The `OnTick()` function is called on every tick of the price data. In this function, the current high and low prices are obtained. The `IsTrendReversal()` function is then called to check if a potential trend reversal has occurred. If a reversal is detected and enough time has passed since the last alert, an alert notification is sent using the `Alert()` function. The `lastAlertTime` variable is updated to the current time.

## Trend Reversal Detection Function

The `IsTrendReversal()` function is used to check for trend reversals based on the current high and low prices and the average high and low prices calculated from the previous bars. The function calculates the average high and low prices by summing up the values in the `prevHigh[]` and `prevLow[]` arrays and dividing them by the `ReversalPeriod`. If the current high is lower than the average high minus the `AlertThreshold` multiplied by the point value, and the current low is higher than the average low plus the `AlertThreshold` multiplied by the point value, a precise reversal is detected and the function returns true.

## Product Description

This code is a sample implementation of the Brilliant Reversals Alert indicator. It is designed to help traders identify potential trend reversals in the forex market. When a reversal is detected, the indicator sends an alert notification, allowing traders to take appropriate action.

The indicator works by calculating the average high and low prices based on a specified period. It then compares the current high and low prices with the average prices to determine if a reversal has occurred. The threshold parameter allows traders to set the minimum difference required for a reversal to be considered.

Please note that ForexRobotEasy is not the official developer of this product. We are only showcasing a sample code that can work based on the description provided. To find the official developer of this product, please refer to the MQL5 platform.

For detailed reviews and trading results of this product, please visit [forexroboteasy.com](https://forexroboteasy.com/forex-robot-review/brilliant-reversals-alert-review-unleash-forex-trading-success/).
