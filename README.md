# Silent Enum.map Failure in Elixir

This repository demonstrates a subtle bug in Elixir related to the silent failure of `String.to_integer/1` within `Enum.map/2` when processing lists containing non-numeric strings.

The original code (`bug.exs`) uses `Enum.map/2` to convert a list of strings to integers. However, if the list contains non-numeric strings, `String.to_integer/1` returns `:error` without raising an exception, leading to unexpected results.  This makes debugging difficult because the error isn't immediately apparent.

The solution (`bugSolution.exs`) addresses this by explicitly handling the `:error` case using pattern matching.