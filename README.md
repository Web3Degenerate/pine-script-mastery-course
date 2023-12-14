# pine-script-mastery-course

Pine Script Tutorial

## [Intro to Pine Script](https://courses.theartoftrading.com/courses/take/pine-script-mastery/lessons/29525739-intro-to-pine-script)

- - **library** - like modules in JS.
  - Otherwise using either **indicator()** or **strategy()**
  - Example of powerful built-in functions:

    - _The Average True Range (ATR) Formula_

      - ![ATR Formula](https://i.imgur.com/cHR4tZ6.png)

      - Simply call with _atrValue_ = **ta.atr(14)** bilt in function.

  - **indicator Pine Script** - designed for creating indicators & alerts. Oscillator or MA, etc.

    - Has access to alert functionality.
    - Shares all the same inbuilt functions & variables as **strategy** scripts.
      - But can not execute buy / sell like strategy.

  - **strategy Pine Script** - A specialized Pine Script type for backtesting strategies.

    - Does NOT have access to some indicator functions.
    - Limited alert functionality compared to indicators.
    - Better to use indicators for alerts/
    - Has access to **strategy.\*** functions for placing and managing mock trades.
      - type `strategy.` + CTRL + SPACE (_see full list of commands_)

  - **library** - re-usable code of libraries, like modules in JS.
    - (~16:30).

---

## [Finding Reference Scripts](https://courses.theartoftrading.com/courses/take/pine-script-mastery/lessons/29550971-finding-reference-scripts)

- - User **HPotter** mentioned in tutorial.
  - Search **People** or **Scripts** to find useful indicators/strategies.

---

## [Plot Shape](https://courses.theartoftrading.com/courses/take/pine-script-mastery/lessons/29554564-plot-shape)

- - set shape with `plotshape(_bool_, _title_, style=shape.*)`

---

## Swing High or Swing Low

- From [VWAP & VWMA](https://courses.theartoftrading.com/courses/take/pine-script-mastery/lessons/29955382-vwap-vwma)

```js
// Prepare filters
// Is the current bar the lowest of the last 4  || was the last bar the lowest bar of the last four?
swingLow  = low == ta.lowest(low, 4) or low[1] == ta.lowest(low, 4)
// Is the current bar the highest of the last 4 || was the last bar the highest bar of the last four?
swingHigh = high == ta.highest(high, 4) or high[1] == ta.highest(high, 4)
```

## His Main Indicators

- - (1) ATR, (2) RSI and (3) EMA
  - mentioned in [Ichimoku Cloud](https://courses.theartoftrading.com/courses/take/pine-script-mastery/lessons/29955385-ichimoku-cloud)

## Using Libraries to get Candles

- Using the zen library, we can tap into candle types like `hammer` or `star`
- Example from [Ichimoku Cloud](https://courses.theartoftrading.com/courses/take/pine-script-mastery/lessons/29955385-ichimoku-cloud)

```js
// Import zen library
import ZenAndTheArtOfTrading/ZenLibrary/2 as zen

// Get candle patterns from zen library:
hammer = zen.isHammer()
star   = zen.isStar()

// Then combine with trade setups
longSignal = aboveIchy and hammer
shortSignal = belowIchy and star

```

- Clear up clutter with user input and ternary operator on indicators to turn off

```js
// user input:
displayFullCloud    = input.bool(title="Show Full Cloud?", defval=true)

// ================== Clear up clutter with ternary operator on displayFullCloud == false =========================== //
plot(displayFullCloud ? conversionLine : na, color=#2962FF, title="Conversion Line")
plot(displayFullCloud ? baseLine : na, color=#B71C1C, title="Base Line")
plot(displayFullCloud ? close : na, offset=-displacement + 1, color=#43A047, title="Lagging Span")
// ================== Clear up clutter with ternary operator on displayFullCloud == false =========================== //

```

## [Session Candles](https://courses.theartoftrading.com/courses/take/pine-script-mastery/lessons/29483619-session-candles)

- - get the current timeframe (15m, 4h, 1D, etc) of the user's choice with `timeframe.period`
  - use the `time(_timeframe, _period-to-check)` function to see if a the current bar is within the defined time range. Here it's used in our custom function `isInSession()`
    - `isInSession(_session) => not na( time(timeframe.period, _session) )`
    -
- - **array_shift()** type method in pine. We get (_potentially_) a collection of bars and we want the FIRST bar in our _"array"_ as follows:

    - ``

  - **array_shift()** type method in pine. We get (_potentially_) a collection of bars and we want the FIRST bar in our _"array"_ as follows:

    - ``

  - How to Start and Stop a period to get the **high** and **low** in the desired period (8:05)
    - X
