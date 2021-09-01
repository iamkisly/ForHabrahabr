``` ini

BenchmarkDotNet=v0.13.1, OS=ubuntu 21.04
AMD FX(tm)-8120, 1 CPU, 8 logical and 4 physical cores
.NET SDK=6.0.100-preview.7.21379.14
  [Host]     : .NET 6.0.0 (6.0.21.37719), X64 RyuJIT
  DefaultJob : .NET 6.0.0 (6.0.21.37719), X64 RyuJIT


```
|                                 Method | Iterations |      Mean |     Error |    StdDev | Code Size |
|--------------------------------------- |----------- |----------:|----------:|----------:|----------:|
|                 ForWithCustomIncrement |      10000 |  6.147 μs | 0.0387 μs | 0.0343 μs |      30 B |
|             ForeachWithEnumerableRange |      10000 | 64.961 μs | 0.7376 μs | 0.6539 μs |     385 B |
|                 ForeachWithYieldReturn |      10000 | 79.919 μs | 0.7037 μs | 0.5876 μs |     299 B |
|             ForeachWithRangeEnumerator |      10000 |  6.182 μs | 0.0260 μs | 0.0243 μs |     333 B |
|          ForeachWithRangeEnumeratorRaw |      10000 |  6.199 μs | 0.0362 μs | 0.0338 μs |     333 B |
| ForeachWithRangeEnumeratorRawWithLocal |      10000 | 28.486 μs | 0.2395 μs | 0.2000 μs |     368 B |
