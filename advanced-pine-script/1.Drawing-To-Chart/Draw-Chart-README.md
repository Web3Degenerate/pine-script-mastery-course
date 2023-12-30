## Notes

## Draw Line When Event Occurs

- - Use `bgcolor()` to draw the line on the chart.
  - Set condition to boolean.

```python

movingAverage1 = ta.ema(close, 50)
movingAverage2 = ta.ema(close, 100)

maCrossOver = ta.crossover(movingAverage1, movingAverage2)
maCrossUnder - ta.crossunder(movingAverage1, movingAverage2)

# Draw Line to chart when cross over/under occurs:
bgcolor(maCrossOver ? color.green : na)
bgcolor(maCrossUnder ? color.red : na)

```
