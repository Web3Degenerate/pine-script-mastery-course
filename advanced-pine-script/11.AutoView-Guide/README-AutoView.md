# AutoView

## 2. [AutoView Commands](https://courses.theartoftrading.com/courses/take/pine-script-mastery/lessons/30228743-autoview-commands)

- - Full List of Commands from [AutoView Docs](chrome-extension://okdhadoplaoehmeldlpakhpekjcpljmb/options.html#alert-syntax)
  - Main Commands:
  - ![AutoView Main Command List](https://i.imgur.com/Uv8fID0.png)

  - Does not recommend **sl=** and **tp=**
  - Recommends instead using **fsl=** _fixed stop loss_ and **ftp=** _fixed take profit_ (~11:00)

  - Secondary Commands:

    - ![AutoView Secondary Command List](https://i.imgur.com/bAPQmMt.png)

  - Some Example AutoView Commands:

    - ![AutoView Sample Commands](https://i.imgur.com/Ttz9Qmp.png)

    - [Oanda Rest-Live-v20 Docs](https://developer.oanda.com/rest-live-v20/order-df/)

## [Alert Syntax Examples](https://courses.theartoftrading.com/courses/take/pine-script-mastery/lessons/30228748-alert-syntax-examples)

- - Example alert buy:
    - Set the exchange: `e=oanda` || `e=oandapractice`
    - Set the symbol: `s=aud/usd` || `s=aud_usd`
    - Set the book: `b=long` || `b=short`
    - Set the quanity: `q=1`
    - Set the type: `t=market` || `t=limit`
    - Set disabled: `d=1`
      - _disabled means it won't get sent to the exchange. Just for testing._
    - Optional Delay: `delay=5` \_delays sending for 5 seconds
  -
  - Close (all?) positions with **c**
    - `e=oandapractice s=aud/usd c=position t=market`
  -
  - Example stop loss and take profit **with PIPS**
    - No idea: `e=oandapractice s=aud/usd b=long t=market q=1 sl=-0.01226 tp=0.00056`
  - **BETTER WAY** - Set Stop Loss and Take Profit based on **PRICE**
    - `e=oan-dapractice s=aud/usd b=long t=market q=1 fsl=-0.65582 ftp=0.65487`
