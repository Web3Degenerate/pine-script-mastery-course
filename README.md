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

## [Plot Shape](https://courses.theartoftrading.com/courses/take/pine-script-mastery/lessons/29554564-plot-shape)

- - set shape with `plotshape(_bool_, _title_, style=shape.*)`
