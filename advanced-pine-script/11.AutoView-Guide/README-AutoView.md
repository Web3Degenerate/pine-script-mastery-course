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
    - `e=oandapractice s=aud/usd b=long t=market q=1 fsl=-0.65582 ftp=0.65487`
  -
  - **Fixed Price** fp and t=limit
  - ## `e=oandapractice s=aud/usd b=short t=limit q=1 fp=0.65584 fsl=0.65632 ftp=0.65502` - enter short at fixed price at swing high (entry) - fixed stop loss (fsl) at higher candles a ways back (1m) - fixed take profit (ftp) at swing low
  - Set datetime expiration

    - use `dt=12-15-2023` day
    - or specify date and time: `dt=12-15-2023 14:00:00`
    - or use **unix time**

    - Commands tested in this lesson:

```js
    e= BROKER
    s= SYMBOL
    b= LONG/SHORT
    q= QUANTITY
    t= ORDER TYPE (limit/market/stop)
    fp= PRICE FOR LIMIT ORDERS
    dt= DATE/TIME
    fsl= STOP LOSS PRICE
    sl= STOP LOSS PIPS
    ftp= PROFIT TARGET PRICE
    tp= PROFIT TARGET PIPS
    fgsl= FIXED GUARANTEED SL PRICE
    ts= TRAILING STOP PIPS
    ro=1 REDUCE ONLY
    delay= PAUSE IN SECONDS BETWEEN ORDERS
    d=1 DISABLES COMMAND EXECUTION
    c= POSITION/ORDER
    a= ACCOUNT ALIAS
```
