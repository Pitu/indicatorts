### Momentum Indicators

Momentum indicators measure the speed of movement.

- [Awesome Oscillator](#awesome-oscillator)
- [Chaikin Oscillator](#chaikin-oscillator)
- [Ichimoku Cloud](#ichimoku-cloud)
- [Relative Strength Index (RSI)](#relative-strength-index-rsi)
- [Stochastic Oscillator](#stochastic-oscillator)
- [Williams R](#williams-r)

#### Awesome Oscillator

The [awesomeOscillator](./awesomeOscillator.ts) function calculates the awesome oscillator based on low and high daily prices for a given stock. It is an indicator used to measure market momentum.

```
Median Price = ((Low + High) / 2)
AO = 5-Period SMA - 34-Period SMA.
```

```TypeScript
import {awesomeOscillator} from 'indicatorts';

const result = awesomeOscillator(highs, lows);
```

#### Chaikin Oscillator

The [chaikinOscillator](./chaikinOscillator.ts) function measures the momentum of the [Accumulation/Distribution (A/D)](../volume/index.md#accumulationdistribution-ad) using the [Moving Average Convergence Divergence (MACD)](../trend/index.md#moving-average-convergence-divergence-macd) formula. It takes the difference between fast and slow periods EMA of the A/D. Cross above the A/D line indicates bullish.

```
CO = Ema(fastPeriod, AD) - Ema(slowPeriod, AD)
```

```TypeScript
import {chaikinOscillator} from 'indicatorts';

const result = chaikinOscillator(fastPeriod, slowPeriod, highs, lows, closings);
```

Most frequently used fast and short periods are 3 and 10. The [defaultChaikinOscillator](./chaikinOscillator.ts) function calculates Chaikin Oscillator with those periods.

#### Ichimoku Cloud

The [ichimokuCloud](./ichimokuCloud.ts), also known as Ichimoku Kinko Hyo, calculates a versatile indicator that defines support and resistence, identifies tred direction, gauges momentum, and provides trading signals.

```
Tenkan-sen (Conversion Line) = (9-Period High + 9-Period Low) / 2
Kijun-sen (Base Line) = (26-Period High + 26-Period Low) / 2
Senkou Span A (Leading Span A) = (Conversion Line + Base Line) / 2
Senkou Span B (Leading Span B) = (52-Period High + 52-Period Low) / 2
Chikou Span (Lagging Span) = Closing plotted 26 days in the past.
```

```TypeScript
import {ichimokuCloud} from 'indicatorts';

const result = ichimokuCloud(highs, lows, closings);
```

#### Relative Strength Index (RSI)

The [rsi](./rsi.ts) function calculates a momentum indicator that measures the magnitude of recent price changes to evaluate overbought and oversold conditions.

```
RS = Average Gain / Average Loss
RSI = 100 - (100 / (1 + RS))
```

```TypeScript
import {rsi} from 'indicatorts';

const result = rsi(closings);
```

#### Stochastic Oscillator

The [stochasticOscillator](./stochasticOscillator.ts) function calculates a momentum indicator that shows the location of the closing relative to high-low range over a set number of periods.

```
K = (Closing - Lowest Low) / (Highest High - Lowest Low) * 100
D = 3-Period SMA of K
```

```TypeScript
import {stochasticOscillator} from 'indicatorts';

const result = stochasticOscillator(highs, lows, closings);
```

#### Williams R

The [williamsR](./williamsR.ts) function calculates the Williams R based on low, high, and closing prices. It is a type of momentum indicator that moves between 0 and -100 and measures overbought and oversold levels.

```
WR = (Highest High - Closing) / (Highest High - Lowest Low)
```

```TypeScript
import {williamsR} from 'indicatorts';

const result = williamsR(highs, lows, closings);
```

## Disclaimer

The information provided on this project is strictly for informational purposes and is not to be construed as advice or solicitation to buy or sell any security.

## License

Copyright (c) 2022 Onur Cinar. All Rights Reserved.

The source code is provided under MIT License.
