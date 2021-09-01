``` ini

BenchmarkDotNet=v0.13.1, OS=ubuntu 21.04
AMD FX(tm)-8120, 1 CPU, 8 logical and 4 physical cores
.NET SDK=5.0.400
  [Host]     : .NET 5.0.9 (5.0.921.35908), X64 RyuJIT
  DefaultJob : .NET 5.0.9 (5.0.921.35908), X64 RyuJIT


```
|                                 Method | Iterations |      Mean |     Error |    StdDev | Code Size |
|--------------------------------------- |----------- |----------:|----------:|----------:|----------:|
|                 ForWithCustomIncrement |      10000 |  6.125 μs | 0.0586 μs | 0.0549 μs |      30 B |
|             ForeachWithEnumerableRange |      10000 | 69.712 μs | 1.1155 μs | 1.2399 μs |     433 B |
|                 ForeachWithYieldReturn |      10000 | 77.253 μs | 1.4753 μs | 2.0681 μs |     365 B |
|             ForeachWithRangeEnumerator |      10000 |  6.171 μs | 0.0640 μs | 0.0567 μs |     340 B |
|          ForeachWithRangeEnumeratorRaw |      10000 |  6.228 μs | 0.0513 μs | 0.0480 μs |     340 B |
| ForeachWithRangeEnumeratorRawWithLocal |      10000 | 27.767 μs | 0.1562 μs | 0.1461 μs |     370 B |
