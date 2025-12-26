### run "zig build benchmark", and you'll get this:
```
╔══════════════════════════════════════════════════════════════════════════════╗
║                           u32 Integer Keys                                   ║
╚══════════════════════════════════════════════════════════════════════════════╝

════════════════════════════════════════════════════════════════════════════════
  u32 key → void (set) value
════════════════════════════════════════════════════════════════════════════════

  100 elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    14 ns │    22 ns │    16 ns │    11 ns │    12 ns │
  │ Seq. Insert    │     9 ns │    13 ns │    14 ns │     9 ns │    10 ns │
  │ Reserved Ins.  │     5 ns │    13 ns │    14 ns │     9 ns │     6 ns │
  │ Update         │     3 ns │     4 ns │     3 ns │     5 ns │     6 ns │
  │ Rand. Lookup   │     3 ns │     6 ns │     2 ns │     3 ns │    16 ns │
  │ High Load      │     3 ns │     5 ns │     2 ns │     3 ns │    14 ns │
  │ Lookup Miss    │     1 ns │     5 ns │     2 ns │     3 ns │    13 ns │
  │ Tombstone      │     5 ns │    16 ns │     6 ns │     8 ns │    13 ns │
  │ Delete         │     4 ns │    13 ns │     6 ns │     6 ns │     4 ns │
  │ Iteration      │     2 ns │     2 ns │     1 ns │     0 ns │     1 ns │
  │ Churn          │     8 ns │    22 ns │    21 ns │    10 ns │    11 ns │
  │ Mixed          │     4 ns │     9 ns │     6 ns │     8 ns │     9 ns │
  │ Read-Heavy     │     3 ns │     3 ns │     3 ns │     4 ns │     6 ns │
  │ Write-Heavy    │    12 ns │    14 ns │    14 ns │     8 ns │    10 ns │
  │ Update-Heavy   │     4 ns │     6 ns │     3 ns │     6 ns │     8 ns │
  │ Zipfian        │     4 ns │    10 ns │     5 ns │     8 ns │     5 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

  3K elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    15 ns │    12 ns │    13 ns │    12 ns │    15 ns │
  │ Seq. Insert    │    15 ns │    12 ns │    13 ns │    16 ns │    15 ns │
  │ Reserved Ins.  │     9 ns │    12 ns │    13 ns │    13 ns │     7 ns │
  │ Update         │     5 ns │     4 ns │     3 ns │    10 ns │     8 ns │
  │ Rand. Lookup   │     4 ns │     6 ns │     2 ns │     4 ns │    15 ns │
  │ High Load      │     3 ns │     5 ns │     2 ns │     3 ns │    14 ns │
  │ Lookup Miss    │     3 ns │     4 ns │     2 ns │     4 ns │    12 ns │
  │ Tombstone      │     7 ns │    12 ns │     4 ns │    13 ns │    17 ns │
  │ Delete         │     4 ns │    11 ns │     4 ns │    10 ns │     7 ns │
  │ Iteration      │     2 ns │     2 ns │     1 ns │     0 ns │     1 ns │
  │ Churn          │    10 ns │    21 ns │     7 ns │    13 ns │    28 ns │
  │ Mixed          │     8 ns │    11 ns │     7 ns │    14 ns │    12 ns │
  │ Read-Heavy     │     5 ns │     4 ns │     3 ns │     7 ns │     9 ns │
  │ Write-Heavy    │    24 ns │    19 ns │    15 ns │    17 ns │    20 ns │
  │ Update-Heavy   │     7 ns │     5 ns │     3 ns │    13 ns │    12 ns │
  │ Zipfian        │     7 ns │    10 ns │     7 ns │    11 ns │     9 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

  100K elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    31 ns │    13 ns │    15 ns │    25 ns │    25 ns │
  │ Seq. Insert    │    31 ns │    13 ns │    15 ns │    26 ns │    25 ns │
  │ Reserved Ins.  │    15 ns │    13 ns │    15 ns │    26 ns │    13 ns │
  │ Update         │     8 ns │     6 ns │     4 ns │    17 ns │    12 ns │
  │ Rand. Lookup   │     9 ns │     5 ns │     6 ns │    17 ns │    13 ns │
  │ High Load      │     8 ns │     6 ns │     6 ns │    17 ns │    13 ns │
  │ Lookup Miss    │     9 ns │     6 ns │     3 ns │     8 ns │    18 ns │
  │ Tombstone      │    15 ns │    16 ns │     7 ns │    26 ns │    25 ns │
  │ Delete         │     7 ns │    14 ns │     6 ns │    20 ns │    10 ns │
  │ Iteration      │     2 ns │     2 ns │     1 ns │     0 ns │     2 ns │
  │ Churn          │    26 ns │    27 ns │    24 ns │    39 ns │    41 ns │
  │ Mixed          │    17 ns │    12 ns │    11 ns │    27 ns │    22 ns │
  │ Read-Heavy     │    11 ns │     7 ns │     7 ns │    21 ns │    15 ns │
  │ Write-Heavy    │    38 ns │    26 ns │    24 ns │    36 ns │    33 ns │
  │ Update-Heavy   │    15 ns │     9 ns │     9 ns │    25 ns │    18 ns │
  │ Zipfian        │    13 ns │    12 ns │     9 ns │    26 ns │    14 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

════════════════════════════════════════════════════════════════════════════════
  u32 key → 4B value
════════════════════════════════════════════════════════════════════════════════

  100 elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    14 ns │    15 ns │    16 ns │    13 ns │    12 ns │
  │ Seq. Insert    │    11 ns │    13 ns │    15 ns │    11 ns │    11 ns │
  │ Reserved Ins.  │     5 ns │    13 ns │    14 ns │    10 ns │     7 ns │
  │ Update         │     4 ns │     4 ns │     5 ns │     3 ns │     7 ns │
  │ Rand. Lookup   │     4 ns │     6 ns │     2 ns │     3 ns │    16 ns │
  │ High Load      │     3 ns │     4 ns │     2 ns │     3 ns │    14 ns │
  │ Lookup Miss    │     2 ns │     6 ns │     2 ns │     3 ns │    13 ns │
  │ Tombstone      │     5 ns │    16 ns │     7 ns │     8 ns │    15 ns │
  │ Delete         │     2 ns │    13 ns │     6 ns │     6 ns │     5 ns │
  │ Iteration      │     2 ns │     1 ns │     1 ns │     0 ns │     1 ns │
  │ Churn          │     8 ns │    21 ns │    24 ns │    11 ns │    11 ns │
  │ Mixed          │     5 ns │    10 ns │     5 ns │     7 ns │    10 ns │
  │ Read-Heavy     │     2 ns │     3 ns │     3 ns │     4 ns │     6 ns │
  │ Write-Heavy    │    10 ns │    14 ns │    15 ns │     9 ns │    11 ns │
  │ Update-Heavy   │     5 ns │     6 ns │     7 ns │     7 ns │     9 ns │
  │ Zipfian        │     4 ns │     9 ns │     5 ns │     8 ns │     6 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

  3K elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    14 ns │    11 ns │    15 ns │    11 ns │    15 ns │
  │ Seq. Insert    │    14 ns │    11 ns │    15 ns │    11 ns │    16 ns │
  │ Reserved Ins.  │     6 ns │    11 ns │    16 ns │    14 ns │     6 ns │
  │ Update         │     5 ns │     4 ns │     5 ns │     8 ns │     9 ns │
  │ Rand. Lookup   │     5 ns │     6 ns │     3 ns │     5 ns │    15 ns │
  │ High Load      │     3 ns │     7 ns │     3 ns │     6 ns │    13 ns │
  │ Lookup Miss    │     2 ns │     5 ns │     2 ns │     4 ns │    12 ns │
  │ Tombstone      │     7 ns │    13 ns │     5 ns │    13 ns │    17 ns │
  │ Delete         │     3 ns │    10 ns │     4 ns │     8 ns │     7 ns │
  │ Iteration      │     2 ns │     2 ns │     1 ns │     0 ns │     1 ns │
  │ Churn          │    10 ns │    20 ns │    11 ns │    27 ns │    30 ns │
  │ Mixed          │     9 ns │    10 ns │     7 ns │    11 ns │    12 ns │
  │ Read-Heavy     │     4 ns │     4 ns │     3 ns │     7 ns │     9 ns │
  │ Write-Heavy    │    23 ns │    17 ns │    17 ns │    16 ns │    20 ns │
  │ Update-Heavy   │     8 ns │     6 ns │     7 ns │    11 ns │    12 ns │
  │ Zipfian        │     7 ns │     9 ns │     8 ns │    12 ns │     9 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

  100K elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    34 ns │    15 ns │    19 ns │    28 ns │    26 ns │
  │ Seq. Insert    │    32 ns │    14 ns │    19 ns │    27 ns │    27 ns │
  │ Reserved Ins.  │    15 ns │    14 ns │    18 ns │    27 ns │    14 ns │
  │ Update         │     9 ns │     7 ns │    10 ns │    15 ns │    14 ns │
  │ Rand. Lookup   │     8 ns │     6 ns │     7 ns │    18 ns │    13 ns │
  │ High Load      │     8 ns │     7 ns │     7 ns │    17 ns │    13 ns │
  │ Lookup Miss    │     9 ns │     6 ns │     4 ns │     8 ns │    18 ns │
  │ Tombstone      │    15 ns │    17 ns │     9 ns │    26 ns │    26 ns │
  │ Delete         │     7 ns │    14 ns │     6 ns │    19 ns │    10 ns │
  │ Iteration      │     2 ns │     2 ns │     1 ns │     0 ns │     2 ns │
  │ Churn          │    27 ns │    29 ns │    27 ns │    38 ns │    43 ns │
  │ Mixed          │    17 ns │    15 ns │    13 ns │    28 ns │    22 ns │
  │ Read-Heavy     │    11 ns │     8 ns │     8 ns │    21 ns │    15 ns │
  │ Write-Heavy    │    53 ns │    28 ns │    28 ns │    41 ns │    35 ns │
  │ Update-Heavy   │    17 ns │    11 ns │    15 ns │    25 ns │    20 ns │
  │ Zipfian        │    15 ns │    13 ns │    11 ns │    25 ns │    15 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

════════════════════════════════════════════════════════════════════════════════
  u32 key → 64B value
════════════════════════════════════════════════════════════════════════════════

  100 elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    21 ns │    22 ns │    27 ns │    23 ns │    19 ns │
  │ Seq. Insert    │    15 ns │    18 ns │    21 ns │    18 ns │    17 ns │
  │ Reserved Ins.  │    11 ns │    19 ns │    23 ns │    20 ns │    12 ns │
  │ Update         │    13 ns │    15 ns │    16 ns │    15 ns │    14 ns │
  │ Rand. Lookup   │     4 ns │     6 ns │     2 ns │     3 ns │    17 ns │
  │ High Load      │     3 ns │     5 ns │     2 ns │     3 ns │    15 ns │
  │ Lookup Miss    │     1 ns │     7 ns │     2 ns │     4 ns │    14 ns │
  │ Tombstone      │     9 ns │    17 ns │    11 ns │    13 ns │    15 ns │
  │ Delete         │     3 ns │    13 ns │     6 ns │     8 ns │     5 ns │
  │ Iteration      │     2 ns │     2 ns │     1 ns │     0 ns │     1 ns │
  │ Churn          │    11 ns │    26 ns │    30 ns │    16 ns │    15 ns │
  │ Mixed          │     6 ns │    14 ns │     8 ns │    10 ns │    11 ns │
  │ Read-Heavy     │     4 ns │     4 ns │     3 ns │    11 ns │     7 ns │
  │ Write-Heavy    │    16 ns │    19 ns │    22 ns │    16 ns │    15 ns │
  │ Update-Heavy   │    12 ns │    15 ns │    16 ns │    17 ns │    18 ns │
  │ Zipfian        │     6 ns │    13 ns │     8 ns │    11 ns │     8 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

  3K elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    30 ns │    27 ns │    27 ns │    22 ns │    23 ns │
  │ Seq. Insert    │    24 ns │    22 ns │    27 ns │    20 ns │    24 ns │
  │ Reserved Ins.  │    14 ns │    25 ns │    29 ns │    22 ns │    13 ns │
  │ Update         │    16 ns │    18 ns │    18 ns │    15 ns │    18 ns │
  │ Rand. Lookup   │     5 ns │     8 ns │     4 ns │     7 ns │    24 ns │
  │ High Load      │     4 ns │     6 ns │     3 ns │     5 ns │    18 ns │
  │ Lookup Miss    │     2 ns │     4 ns │     2 ns │     5 ns │    13 ns │
  │ Tombstone      │    11 ns │    16 ns │    10 ns │    18 ns │    19 ns │
  │ Delete         │     4 ns │    11 ns │     4 ns │    10 ns │     7 ns │
  │ Iteration      │     2 ns │     2 ns │     1 ns │     0 ns │     1 ns │
  │ Churn          │    13 ns │    22 ns │    12 ns │    18 ns │    30 ns │
  │ Mixed          │    10 ns │    12 ns │     9 ns │    14 ns │    14 ns │
  │ Read-Heavy     │     6 ns │     5 ns │     4 ns │    10 ns │     9 ns │
  │ Write-Heavy    │    40 ns │    24 ns │    29 ns │    24 ns │    26 ns │
  │ Update-Heavy   │    19 ns │    19 ns │    18 ns │    17 ns │    19 ns │
  │ Zipfian        │     8 ns │    11 ns │     9 ns │    14 ns │    10 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

  100K elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │   125 ns │    75 ns │    82 ns │    40 ns │    64 ns │
  │ Seq. Insert    │   118 ns │    71 ns │    54 ns │    37 ns │    68 ns │
  │ Reserved Ins.  │    30 ns │    43 ns │    51 ns │    40 ns │    23 ns │
  │ Update         │    31 ns │    32 ns │    37 ns │    26 ns │    27 ns │
  │ Rand. Lookup   │    11 ns │    13 ns │    13 ns │    22 ns │    13 ns │
  │ High Load      │    12 ns │    14 ns │    16 ns │    22 ns │    14 ns │
  │ Lookup Miss    │     8 ns │     7 ns │     4 ns │     8 ns │    17 ns │
  │ Tombstone      │    23 ns │    29 ns │    26 ns │    29 ns │    31 ns │
  │ Delete         │     9 ns │    19 ns │    13 ns │    20 ns │    10 ns │
  │ Iteration      │     2 ns │     2 ns │     1 ns │     0 ns │     2 ns │
  │ Churn          │    32 ns │    31 ns │    34 ns │    41 ns │    46 ns │
  │ Mixed          │    23 ns │    22 ns │    22 ns │    37 ns │    25 ns │
  │ Read-Heavy     │    15 ns │    16 ns │    14 ns │    25 ns │    17 ns │
  │ Write-Heavy    │    99 ns │    84 ns │    97 ns │    66 ns │    77 ns │
  │ Update-Heavy   │    42 ns │    38 ns │    44 ns │    47 ns │    34 ns │
  │ Zipfian        │    17 ns │    22 ns │    18 ns │    30 ns │    18 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

╔══════════════════════════════════════════════════════════════════════════════╗
║                           u64 Integer Keys                                   ║
╚══════════════════════════════════════════════════════════════════════════════╝

════════════════════════════════════════════════════════════════════════════════
  u64 key → void (set) value
════════════════════════════════════════════════════════════════════════════════

  100 elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    14 ns │    15 ns │    15 ns │    13 ns │    10 ns │
  │ Seq. Insert    │     7 ns │    12 ns │    12 ns │    10 ns │     9 ns │
  │ Reserved Ins.  │     5 ns │    13 ns │    14 ns │    11 ns │     4 ns │
  │ Update         │     3 ns │     4 ns │     3 ns │     5 ns │     4 ns │
  │ Rand. Lookup   │     2 ns │     5 ns │     2 ns │     3 ns │     7 ns │
  │ High Load      │     3 ns │     4 ns │     2 ns │     3 ns │     6 ns │
  │ Lookup Miss    │     2 ns │     6 ns │     2 ns │     3 ns │     5 ns │
  │ Tombstone      │     5 ns │    16 ns │     6 ns │     7 ns │     9 ns │
  │ Delete         │     2 ns │    14 ns │     6 ns │     6 ns │     3 ns │
  │ Iteration      │     2 ns │     2 ns │     1 ns │     0 ns │     1 ns │
  │ Churn          │     9 ns │    19 ns │    16 ns │    10 ns │    10 ns │
  │ Mixed          │     4 ns │     9 ns │     5 ns │     7 ns │     6 ns │
  │ Read-Heavy     │     2 ns │     3 ns │     3 ns │     4 ns │     4 ns │
  │ Write-Heavy    │    11 ns │    14 ns │    15 ns │    12 ns │     9 ns │
  │ Update-Heavy   │     4 ns │     5 ns │     3 ns │     9 ns │     7 ns │
  │ Zipfian        │     4 ns │    10 ns │     5 ns │     6 ns │     5 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

  3K elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    13 ns │    12 ns │    14 ns │    13 ns │    16 ns │
  │ Seq. Insert    │    13 ns │    10 ns │    13 ns │     9 ns │    15 ns │
  │ Reserved Ins.  │     5 ns │    11 ns │    14 ns │    13 ns │     6 ns │
  │ Update         │     4 ns │     4 ns │     3 ns │     9 ns │     9 ns │
  │ Rand. Lookup   │     4 ns │     6 ns │     3 ns │     5 ns │    18 ns │
  │ High Load      │     4 ns │     5 ns │     2 ns │     4 ns │    14 ns │
  │ Lookup Miss    │     2 ns │     4 ns │     2 ns │     4 ns │    12 ns │
  │ Tombstone      │     8 ns │    12 ns │     5 ns │    12 ns │    16 ns │
  │ Delete         │     4 ns │    10 ns │     4 ns │     8 ns │     7 ns │
  │ Iteration      │     2 ns │     2 ns │     1 ns │     0 ns │     1 ns │
  │ Churn          │     9 ns │    23 ns │     7 ns │    14 ns │    24 ns │
  │ Mixed          │     8 ns │    10 ns │     7 ns │    12 ns │    12 ns │
  │ Read-Heavy     │     5 ns │     3 ns │     3 ns │     7 ns │     9 ns │
  │ Write-Heavy    │    24 ns │    19 ns │    15 ns │    18 ns │    20 ns │
  │ Update-Heavy   │     7 ns │     5 ns │     3 ns │    12 ns │    11 ns │
  │ Zipfian        │     6 ns │     9 ns │     7 ns │    12 ns │     9 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

  100K elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    31 ns │    14 ns │    17 ns │    28 ns │    25 ns │
  │ Seq. Insert    │    30 ns │    13 ns │    14 ns │    11 ns │    23 ns │
  │ Reserved Ins.  │    15 ns │    14 ns │    17 ns │    28 ns │    13 ns │
  │ Update         │     8 ns │     6 ns │     5 ns │    16 ns │    12 ns │
  │ Rand. Lookup   │     8 ns │     5 ns │     6 ns │    19 ns │    13 ns │
  │ High Load      │     9 ns │     6 ns │     7 ns │    18 ns │    13 ns │
  │ Lookup Miss    │     9 ns │     6 ns │     4 ns │     9 ns │    17 ns │
  │ Tombstone      │    15 ns │    16 ns │     8 ns │    26 ns │    24 ns │
  │ Delete         │     7 ns │    14 ns │     6 ns │    19 ns │     9 ns │
  │ Iteration      │     2 ns │     2 ns │     1 ns │     0 ns │     2 ns │
  │ Churn          │    28 ns │    28 ns │    26 ns │    38 ns │    43 ns │
  │ Mixed          │    18 ns │    14 ns │    12 ns │    28 ns │    23 ns │
  │ Read-Heavy     │    12 ns │     7 ns │     7 ns │    22 ns │    15 ns │
  │ Write-Heavy    │    42 ns │    31 ns │    27 ns │    38 ns │    34 ns │
  │ Update-Heavy   │    17 ns │    10 ns │     9 ns │    27 ns │    18 ns │
  │ Zipfian        │    14 ns │    12 ns │    10 ns │    27 ns │    15 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

════════════════════════════════════════════════════════════════════════════════
  u64 key → 4B value
════════════════════════════════════════════════════════════════════════════════

  100 elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    15 ns │    17 ns │    16 ns │    14 ns │    11 ns │
  │ Seq. Insert    │     8 ns │    12 ns │    14 ns │    11 ns │    10 ns │
  │ Reserved Ins.  │     5 ns │    13 ns │    15 ns │    12 ns │     5 ns │
  │ Update         │     3 ns │     4 ns │     6 ns │     3 ns │     5 ns │
  │ Rand. Lookup   │     2 ns │     6 ns │     2 ns │     3 ns │     8 ns │
  │ High Load      │     3 ns │     5 ns │     2 ns │     3 ns │     6 ns │
  │ Lookup Miss    │     2 ns │     5 ns │     2 ns │     3 ns │     6 ns │
  │ Tombstone      │     5 ns │    18 ns │     6 ns │     7 ns │     9 ns │
  │ Delete         │     2 ns │    13 ns │     6 ns │     6 ns │     4 ns │
  │ Iteration      │     2 ns │     2 ns │     1 ns │     0 ns │     1 ns │
  │ Churn          │     9 ns │    22 ns │    19 ns │    12 ns │    11 ns │
  │ Mixed          │     5 ns │    11 ns │     5 ns │     6 ns │     6 ns │
  │ Read-Heavy     │     2 ns │     3 ns │     3 ns │     3 ns │     4 ns │
  │ Write-Heavy    │    13 ns │    14 ns │    17 ns │    12 ns │     9 ns │
  │ Update-Heavy   │     5 ns │     8 ns │     8 ns │     9 ns │     8 ns │
  │ Zipfian        │     4 ns │    10 ns │     6 ns │     6 ns │     5 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

  3K elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    16 ns │    12 ns │    17 ns │    17 ns │    18 ns │
  │ Seq. Insert    │    16 ns │    10 ns │    15 ns │    10 ns │    17 ns │
  │ Reserved Ins.  │     6 ns │    12 ns │    17 ns │    16 ns │     7 ns │
  │ Update         │     5 ns │     4 ns │     7 ns │     8 ns │    11 ns │
  │ Rand. Lookup   │     5 ns │     6 ns │     4 ns │     6 ns │    17 ns │
  │ High Load      │     3 ns │     6 ns │     3 ns │     5 ns │    18 ns │
  │ Lookup Miss    │     2 ns │     4 ns │     2 ns │     4 ns │    12 ns │
  │ Tombstone      │     9 ns │    12 ns │     7 ns │    13 ns │    17 ns │
  │ Delete         │     4 ns │    10 ns │     4 ns │     9 ns │     6 ns │
  │ Iteration      │     2 ns │     2 ns │     1 ns │     0 ns │     1 ns │
  │ Churn          │    10 ns │    21 ns │     9 ns │    14 ns │    27 ns │
  │ Mixed          │     8 ns │    11 ns │     8 ns │    11 ns │    12 ns │
  │ Read-Heavy     │     5 ns │     4 ns │     4 ns │     7 ns │     9 ns │
  │ Write-Heavy    │    25 ns │    19 ns │    19 ns │    20 ns │    22 ns │
  │ Update-Heavy   │     8 ns │     7 ns │     9 ns │    10 ns │    12 ns │
  │ Zipfian        │     7 ns │    12 ns │     7 ns │    11 ns │    10 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

  100K elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    33 ns │    14 ns │    20 ns │    30 ns │    27 ns │
  │ Seq. Insert    │    32 ns │    13 ns │    16 ns │    13 ns │    24 ns │
  │ Reserved Ins.  │    16 ns │    14 ns │    20 ns │    30 ns │    14 ns │
  │ Update         │    10 ns │     6 ns │    10 ns │    14 ns │    14 ns │
  │ Rand. Lookup   │     9 ns │     7 ns │     8 ns │    18 ns │    13 ns │
  │ High Load      │    10 ns │     7 ns │     8 ns │    17 ns │    13 ns │
  │ Lookup Miss    │     9 ns │     6 ns │     4 ns │     8 ns │    17 ns │
  │ Tombstone      │    16 ns │    16 ns │     9 ns │    27 ns │    25 ns │
  │ Delete         │     7 ns │    17 ns │     9 ns │    25 ns │    11 ns │
  │ Iteration      │     2 ns │     2 ns │     1 ns │     0 ns │     3 ns │
  │ Churn          │    35 ns │    29 ns │    29 ns │    41 ns │    45 ns │
  │ Mixed          │    22 ns │    16 ns │    14 ns │    28 ns │    24 ns │
  │ Read-Heavy     │    14 ns │     8 ns │     9 ns │    22 ns │    15 ns │
  │ Write-Heavy    │    49 ns │    36 ns │    37 ns │    44 ns │    37 ns │
  │ Update-Heavy   │    20 ns │    12 ns │    17 ns │    25 ns │    20 ns │
  │ Zipfian        │    14 ns │    13 ns │    13 ns │    27 ns │    16 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

════════════════════════════════════════════════════════════════════════════════
  u64 key → 64B value
════════════════════════════════════════════════════════════════════════════════

  100 elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    20 ns │    17 ns │    20 ns │    17 ns │    14 ns │
  │ Seq. Insert    │    13 ns │    15 ns │    19 ns │    18 ns │    14 ns │
  │ Reserved Ins.  │     7 ns │    15 ns │    19 ns │    16 ns │     6 ns │
  │ Update         │     6 ns │     7 ns │     9 ns │     6 ns │     8 ns │
  │ Rand. Lookup   │     3 ns │     6 ns │     2 ns │     3 ns │     7 ns │
  │ High Load      │     3 ns │     5 ns │     2 ns │     3 ns │     6 ns │
  │ Lookup Miss    │     2 ns │     5 ns │     2 ns │     3 ns │     5 ns │
  │ Tombstone      │     6 ns │    15 ns │     8 ns │     9 ns │     9 ns │
  │ Delete         │     2 ns │    13 ns │     6 ns │     6 ns │     3 ns │
  │ Iteration      │     2 ns │     2 ns │     1 ns │     0 ns │     1 ns │
  │ Churn          │    10 ns │    22 ns │    21 ns │    12 ns │    13 ns │
  │ Mixed          │     5 ns │    11 ns │    10 ns │     7 ns │     6 ns │
  │ Read-Heavy     │     2 ns │     4 ns │     3 ns │     4 ns │     4 ns │
  │ Write-Heavy    │    16 ns │    16 ns │    20 ns │    15 ns │    11 ns │
  │ Update-Heavy   │     7 ns │     9 ns │     9 ns │    12 ns │    14 ns │
  │ Zipfian        │     4 ns │     9 ns │     6 ns │     6 ns │     5 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

  3K elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    20 ns │    14 ns │    23 ns │    20 ns │    20 ns │
  │ Seq. Insert    │    21 ns │    17 ns │    25 ns │    19 ns │    22 ns │
  │ Reserved Ins.  │     8 ns │    17 ns │    26 ns │    21 ns │     9 ns │
  │ Update         │    10 ns │     7 ns │    10 ns │    11 ns │    13 ns │
  │ Rand. Lookup   │     6 ns │     9 ns │     5 ns │     7 ns │    22 ns │
  │ High Load      │     4 ns │     6 ns │     4 ns │     5 ns │    21 ns │
  │ Lookup Miss    │     2 ns │     5 ns │     2 ns │     5 ns │    12 ns │
  │ Tombstone      │    11 ns │    13 ns │     8 ns │    15 ns │    17 ns │
  │ Delete         │     4 ns │    10 ns │     5 ns │    10 ns │     7 ns │
  │ Iteration      │     2 ns │     2 ns │     1 ns │     0 ns │     1 ns │
  │ Churn          │    12 ns │    22 ns │    11 ns │    17 ns │    26 ns │
  │ Mixed          │     9 ns │    12 ns │     9 ns │    14 ns │    14 ns │
  │ Read-Heavy     │     5 ns │     5 ns │     4 ns │     8 ns │     9 ns │
  │ Write-Heavy    │    33 ns │    28 ns │    30 ns │    25 ns │    28 ns │
  │ Update-Heavy   │    12 ns │    10 ns │    11 ns │    17 ns │    14 ns │
  │ Zipfian        │     9 ns │    10 ns │     9 ns │    12 ns │    10 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

  100K elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    92 ns │    59 ns │    49 ns │    39 ns │    62 ns │
  │ Seq. Insert    │    71 ns │    51 ns │    57 ns │    26 ns │    48 ns │
  │ Reserved Ins.  │    27 ns │    37 ns │    52 ns │    38 ns │    20 ns │
  │ Update         │    22 ns │    15 ns │    24 ns │    19 ns │    19 ns │
  │ Rand. Lookup   │    14 ns │    14 ns │    19 ns │    23 ns │    13 ns │
  │ High Load      │    13 ns │    16 ns │    19 ns │    23 ns │    14 ns │
  │ Lookup Miss    │     9 ns │     7 ns │     4 ns │     8 ns │    17 ns │
  │ Tombstone      │    23 ns │    27 ns │    21 ns │    28 ns │    27 ns │
  │ Delete         │    11 ns │    24 ns │    17 ns │    20 ns │     9 ns │
  │ Iteration      │     2 ns │     2 ns │     1 ns │     0 ns │     2 ns │
  │ Churn          │    34 ns │    33 ns │    35 ns │    42 ns │    47 ns │
  │ Mixed          │    25 ns │    24 ns │    23 ns │    35 ns │    31 ns │
  │ Read-Heavy     │    18 ns │    18 ns │    18 ns │    27 ns │    18 ns │
  │ Write-Heavy    │   106 ns │    78 ns │    88 ns │    71 ns │    74 ns │
  │ Update-Heavy   │    30 ns │    25 ns │    34 ns │    37 ns │    32 ns │
  │ Zipfian        │    21 ns │    22 ns │    19 ns │    32 ns │    21 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

╔══════════════════════════════════════════════════════════════════════════════╗
║                    String Keys (Random Length 8-64 chars)                    ║
╚══════════════════════════════════════════════════════════════════════════════╝

════════════════════════════════════════════════════════════════════════════════
  string key → void (set) value
════════════════════════════════════════════════════════════════════════════════

  100 elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    28 ns │    25 ns │    19 ns │    26 ns │    23 ns │
  │ Seq. Insert    │    20 ns │    23 ns │    17 ns │    23 ns │    21 ns │
  │ Reserved Ins.  │    11 ns │    22 ns │    16 ns │    23 ns │     8 ns │
  │ Update         │     9 ns │    29 ns │    26 ns │    33 ns │    10 ns │
  │ Rand. Lookup   │    15 ns │    13 ns │     7 ns │     9 ns │    15 ns │
  │ High Load      │     8 ns │    11 ns │     7 ns │     9 ns │    13 ns │
  │ Lookup Miss    │     6 ns │    11 ns │     5 ns │     8 ns │    13 ns │
  │ Tombstone      │    11 ns │    33 ns │    18 ns │    29 ns │    15 ns │
  │ Delete         │     9 ns │    37 ns │    28 ns │    35 ns │     9 ns │
  │ Iteration      │     2 ns │     2 ns │     1 ns │     0 ns │     1 ns │
  │ Churn          │    16 ns │    38 ns │    27 ns │    33 ns │    22 ns │
  │ Mixed          │    10 ns │    41 ns │    37 ns │    42 ns │    12 ns │
  │ Read-Heavy     │     8 ns │    30 ns │    29 ns │    31 ns │    11 ns │
  │ Write-Heavy    │    32 ns │    36 ns │    29 ns │    32 ns │    24 ns │
  │ Update-Heavy   │    10 ns │    32 ns │    30 ns │    42 ns │    22 ns │
  │ Zipfian        │    11 ns │    40 ns │    35 ns │    41 ns │    11 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

  3K elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    43 ns │    27 ns │    19 ns │    34 ns │    40 ns │
  │ Seq. Insert    │    44 ns │    29 ns │    21 ns │    35 ns │    40 ns │
  │ Reserved Ins.  │    14 ns │    29 ns │    20 ns │    35 ns │    12 ns │
  │ Update         │    16 ns │    36 ns │    34 ns │    50 ns │    19 ns │
  │ Rand. Lookup   │    27 ns │    21 ns │    18 ns │    26 ns │    43 ns │
  │ High Load      │    22 ns │    21 ns │    15 ns │    24 ns │    41 ns │
  │ Lookup Miss    │    15 ns │    13 ns │     7 ns │    15 ns │    23 ns │
  │ Tombstone      │    21 ns │    33 ns │    23 ns │    49 ns │    27 ns │
  │ Delete         │    16 ns │    41 ns │    36 ns │    55 ns │    18 ns │
  │ Iteration      │     2 ns │     2 ns │     1 ns │     0 ns │     2 ns │
  │ Churn          │    28 ns │    43 ns │    33 ns │    51 ns │    35 ns │
  │ Mixed          │    28 ns │    54 ns │    50 ns │    68 ns │    30 ns │
  │ Read-Heavy     │    20 ns │    40 ns │    39 ns │    52 ns │    23 ns │
  │ Write-Heavy    │    74 ns │    61 ns │    54 ns │    70 ns │    54 ns │
  │ Update-Heavy   │    22 ns │    43 ns │    43 ns │    59 ns │    24 ns │
  │ Zipfian        │    22 ns │    52 ns │    49 ns │    63 ns │    24 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

  100K elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    73 ns │    42 ns │    34 ns │    54 ns │    53 ns │
  │ Seq. Insert    │    74 ns │    41 ns │    33 ns │    53 ns │    53 ns │
  │ Reserved Ins.  │    35 ns │    41 ns │    34 ns │    54 ns │    22 ns │
  │ Update         │    22 ns │    43 ns │    43 ns │    59 ns │    23 ns │
  │ Rand. Lookup   │    47 ns │    94 ns │    90 ns │   124 ns │    48 ns │
  │ High Load      │    52 ns │    90 ns │    90 ns │   113 ns │    49 ns │
  │ Lookup Miss    │    21 ns │    15 ns │    12 ns │    19 ns │    28 ns │
  │ Tombstone      │    36 ns │    40 ns │    32 ns │    60 ns │    31 ns │
  │ Delete         │    26 ns │    48 ns │    43 ns │    62 ns │    23 ns │
  │ Iteration      │     2 ns │     2 ns │     1 ns │     0 ns │     2 ns │
  │ Churn          │    85 ns │    83 ns │    78 ns │    91 ns │    75 ns │
  │ Mixed          │    67 ns │   116 ns │   104 ns │   142 ns │    67 ns │
  │ Read-Heavy     │    57 ns │    91 ns │    85 ns │   113 ns │    48 ns │
  │ Write-Heavy    │   220 ns │   195 ns │   166 ns │   183 ns │   163 ns │
  │ Update-Heavy   │    63 ns │    89 ns │   104 ns │   127 ns │    55 ns │
  │ Zipfian        │    55 ns │    88 ns │    84 ns │   110 ns │    47 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

════════════════════════════════════════════════════════════════════════════════
  string key → 4B value
════════════════════════════════════════════════════════════════════════════════

  100 elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    24 ns │    27 ns │    19 ns │    20 ns │    25 ns │
  │ Seq. Insert    │    20 ns │    24 ns │    17 ns │    17 ns │    21 ns │
  │ Reserved Ins.  │    10 ns │    24 ns │    17 ns │    17 ns │     8 ns │
  │ Update         │     9 ns │    34 ns │    32 ns │    31 ns │     9 ns │
  │ Rand. Lookup   │    12 ns │    12 ns │     8 ns │    10 ns │    15 ns │
  │ High Load      │     8 ns │    10 ns │     7 ns │     9 ns │    13 ns │
  │ Lookup Miss    │     7 ns │    10 ns │     5 ns │     8 ns │    13 ns │
  │ Tombstone      │    11 ns │    32 ns │    20 ns │    26 ns │    15 ns │
  │ Delete         │     9 ns │    39 ns │    30 ns │    37 ns │     9 ns │
  │ Iteration      │     2 ns │     2 ns │     1 ns │     0 ns │     1 ns │
  │ Churn          │    16 ns │    40 ns │    30 ns │    31 ns │    22 ns │
  │ Mixed          │    10 ns │    44 ns │    41 ns │    42 ns │    13 ns │
  │ Read-Heavy     │     9 ns │    33 ns │    32 ns │    33 ns │    10 ns │
  │ Write-Heavy    │    23 ns │    40 ns │    36 ns │    30 ns │    25 ns │
  │ Update-Heavy   │    11 ns │    37 ns │    35 ns │    39 ns │    23 ns │
  │ Zipfian        │    10 ns │    43 ns │    39 ns │    41 ns │    12 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

  3K elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    42 ns │    30 ns │    23 ns │    33 ns │    41 ns │
  │ Seq. Insert    │    44 ns │    30 ns │    23 ns │    33 ns │    40 ns │
  │ Reserved Ins.  │    13 ns │    30 ns │    23 ns │    35 ns │    15 ns │
  │ Update         │    16 ns │    38 ns │    37 ns │    44 ns │    19 ns │
  │ Rand. Lookup   │    40 ns │    22 ns │    15 ns │    23 ns │    49 ns │
  │ High Load      │    22 ns │    23 ns │    20 ns │    24 ns │    42 ns │
  │ Lookup Miss    │    15 ns │    12 ns │     9 ns │    15 ns │    23 ns │
  │ Tombstone      │    22 ns │    33 ns │    23 ns │    47 ns │    23 ns │
  │ Delete         │    19 ns │    41 ns │    35 ns │    54 ns │    18 ns │
  │ Iteration      │     2 ns │     2 ns │     1 ns │     0 ns │     2 ns │
  │ Churn          │    28 ns │    44 ns │    34 ns │    48 ns │    35 ns │
  │ Mixed          │    26 ns │    56 ns │    55 ns │    66 ns │    31 ns │
  │ Read-Heavy     │    21 ns │    43 ns │    45 ns │    50 ns │    23 ns │
  │ Write-Heavy    │    63 ns │    72 ns │    51 ns │    61 ns │    60 ns │
  │ Update-Heavy   │    23 ns │    45 ns │    43 ns │    52 ns │    25 ns │
  │ Zipfian        │    26 ns │    53 ns │    49 ns │    63 ns │    26 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

  100K elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    84 ns │    54 ns │    40 ns │    48 ns │    57 ns │
  │ Seq. Insert    │    90 ns │    56 ns │    34 ns │    49 ns │    59 ns │
  │ Reserved Ins.  │    36 ns │    57 ns │    44 ns │    48 ns │    23 ns │
  │ Update         │    29 ns │    45 ns │    45 ns │    53 ns │    24 ns │
  │ Rand. Lookup   │    56 ns │   106 ns │   103 ns │   135 ns │    49 ns │
  │ High Load      │    58 ns │   116 ns │    94 ns │   121 ns │    51 ns │
  │ Lookup Miss    │    22 ns │    16 ns │    12 ns │    19 ns │    28 ns │
  │ Tombstone      │    35 ns │    42 ns │    32 ns │    58 ns │    31 ns │
  │ Delete         │    29 ns │    52 ns │    46 ns │    63 ns │    23 ns │
  │ Iteration      │     2 ns │     2 ns │     1 ns │     0 ns │     2 ns │
  │ Churn          │    77 ns │    92 ns │    85 ns │    99 ns │    81 ns │
  │ Mixed          │    72 ns │   116 ns │   122 ns │   140 ns │    72 ns │
  │ Read-Heavy     │    67 ns │   102 ns │    96 ns │   114 ns │    55 ns │
  │ Write-Heavy    │   238 ns │   264 ns │   166 ns │   167 ns │   175 ns │
  │ Update-Heavy   │    72 ns │   109 ns │   105 ns │   124 ns │    65 ns │
  │ Zipfian        │    55 ns │   102 ns │    85 ns │   112 ns │    50 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

════════════════════════════════════════════════════════════════════════════════
  string key → 64B value
════════════════════════════════════════════════════════════════════════════════

  100 elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    27 ns │    33 ns │    21 ns │    23 ns │    26 ns │
  │ Seq. Insert    │    25 ns │    31 ns │    25 ns │    24 ns │    25 ns │
  │ Reserved Ins.  │    11 ns │    28 ns │    20 ns │    20 ns │     9 ns │
  │ Update         │    12 ns │    37 ns │    33 ns │    34 ns │    12 ns │
  │ Rand. Lookup   │    14 ns │    14 ns │     8 ns │    11 ns │    16 ns │
  │ High Load      │     9 ns │    11 ns │     7 ns │    10 ns │    14 ns │
  │ Lookup Miss    │     7 ns │    11 ns │     5 ns │     8 ns │    13 ns │
  │ Tombstone      │    11 ns │    35 ns │    21 ns │    28 ns │    15 ns │
  │ Delete         │     9 ns │    39 ns │    31 ns │    38 ns │    10 ns │
  │ Iteration      │     2 ns │     2 ns │     1 ns │     0 ns │     1 ns │
  │ Churn          │    16 ns │    41 ns │    31 ns │    33 ns │    23 ns │
  │ Mixed          │    11 ns │    47 ns │    42 ns │    43 ns │    13 ns │
  │ Read-Heavy     │    10 ns │    34 ns │    33 ns │    33 ns │    11 ns │
  │ Write-Heavy    │    24 ns │    43 ns │    35 ns │    33 ns │    26 ns │
  │ Update-Heavy   │    13 ns │    39 ns │    36 ns │    41 ns │    26 ns │
  │ Zipfian        │    11 ns │    44 ns │    39 ns │    41 ns │    11 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

  3K elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    50 ns │    37 ns │    29 ns │    38 ns │    47 ns │
  │ Seq. Insert    │    53 ns │    40 ns │    33 ns │    38 ns │    46 ns │
  │ Reserved Ins.  │    16 ns │    32 ns │    27 ns │    38 ns │    16 ns │
  │ Update         │    24 ns │    43 ns │    39 ns │    46 ns │    26 ns │
  │ Rand. Lookup   │    49 ns │    22 ns │    15 ns │    23 ns │    45 ns │
  │ High Load      │    25 ns │    21 ns │    15 ns │    22 ns │    44 ns │
  │ Lookup Miss    │    15 ns │    15 ns │     7 ns │    14 ns │    23 ns │
  │ Tombstone      │    23 ns │    41 ns │    28 ns │    47 ns │    25 ns │
  │ Delete         │    17 ns │    48 ns │    38 ns │    53 ns │    18 ns │
  │ Iteration      │     2 ns │     2 ns │     1 ns │     0 ns │     2 ns │
  │ Churn          │    31 ns │    49 ns │    36 ns │    52 ns │    38 ns │
  │ Mixed          │    33 ns │    62 ns │    56 ns │    78 ns │    32 ns │
  │ Read-Heavy     │    25 ns │    46 ns │    50 ns │    56 ns │    25 ns │
  │ Write-Heavy    │    80 ns │    73 ns │    64 ns │    71 ns │    66 ns │
  │ Update-Heavy   │    28 ns │    55 ns │    49 ns │    60 ns │    31 ns │
  │ Zipfian        │    26 ns │    56 ns │    54 ns │    68 ns │    25 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

  100K elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │   134 ns │    82 ns │    81 ns │    58 ns │   100 ns │
  │ Seq. Insert    │   155 ns │    95 ns │    95 ns │    64 ns │   106 ns │
  │ Reserved Ins.  │    53 ns │    96 ns │    81 ns │    58 ns │    32 ns │
  │ Update         │    59 ns │    72 ns │    77 ns │    54 ns │    47 ns │
  │ Rand. Lookup   │    90 ns │   183 ns │   183 ns │   214 ns │    70 ns │
  │ High Load      │    85 ns │   177 ns │   172 ns │   206 ns │    66 ns │
  │ Lookup Miss    │    30 ns │    19 ns │    14 ns │    19 ns │    27 ns │
  │ Tombstone      │    51 ns │    69 ns │    65 ns │    58 ns │    45 ns │
  │ Delete         │    38 ns │    85 ns │    80 ns │    63 ns │    24 ns │
  │ Iteration      │     2 ns │     2 ns │     1 ns │     0 ns │     2 ns │
  │ Churn          │   112 ns │   112 ns │   119 ns │   149 ns │   107 ns │
  │ Mixed          │   107 ns │   176 ns │   158 ns │   201 ns │    91 ns │
  │ Read-Heavy     │    87 ns │   175 ns │   150 ns │   198 ns │    75 ns │
  │ Write-Heavy    │   278 ns │   272 ns │   213 ns │   204 ns │   229 ns │
  │ Update-Heavy   │   112 ns │   171 ns │   161 ns │   207 ns │    99 ns │
  │ Zipfian        │    80 ns │   149 ns │   145 ns │   222 ns │    61 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

╔══════════════════════════════════════════════════════════════════════════════╗
║                    OVERALL AVERAGE (All Key/Value/Size Combinations)         ║
╚══════════════════════════════════════════════════════════════════════════════╝

════════════════════════════════════════════════════════════════════════════════
  Average of all 27 configurations (3 key types × 3 value types × 3 sizes)
════════════════════════════════════════════════════════════════════════════════

  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    39 ns │    27 ns │    26 ns │    26 ns │    30 ns │
  │ Seq. Insert    │    37 ns │    26 ns │    25 ns │    23 ns │    29 ns │
  │ Reserved Ins.  │    14 ns │    24 ns │    24 ns │    25 ns │    12 ns │
  │ Update         │    13 ns │    19 ns │    20 ns │    22 ns │    14 ns │
  │ Rand. Lookup   │    16 ns │    22 ns │    19 ns │    27 ns │    22 ns │
  │ High Load      │    14 ns │    22 ns │    19 ns │    25 ns │    21 ns │
  │ Lookup Miss    │     7 ns │     8 ns │     4 ns │     8 ns │    15 ns │
  │ Tombstone      │    15 ns │    24 ns │    15 ns │    25 ns │    20 ns │
  │ Delete         │     9 ns │    24 ns │    17 ns │    25 ns │    10 ns │
  │ Iteration      │     2 ns │     1 ns │     1 ns │     0 ns │     1 ns │
  │ Churn          │    26 ns │    36 ns │    30 ns │    37 ns │    34 ns │
  │ Mixed          │    21 ns │    35 ns │    31 ns │    41 ns │    23 ns │
  │ Read-Heavy     │    15 ns │    26 ns │    24 ns │    33 ns │    17 ns │
  │ Write-Heavy    │    61 ns │    57 ns │    49 ns │    49 ns │    48 ns │
  │ Update-Heavy   │    21 ns │    30 ns │    30 ns │    39 ns │    24 ns │
  │ Zipfian        │    17 ns │    31 ns │    27 ns │    38 ns │    16 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

╔══════════════════════════════════════════════════════════════════════════════╗
║                         Memory Usage Comparison                              ║
╚══════════════════════════════════════════════════════════════════════════════╝

════════════════════════════════════════════════════════════════════════════════
  u32 key → void (set)
════════════════════════════════════════════════════════════════════════════════
  ┌──────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Size         │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├──────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ 1K           │  12.0 KB │   8.0 KB │   7.5 KB │   8.1 KB │  10.0 KB │
  │ 100K         │ 768.0 KB │ 512.0 KB │ 480.0 KB │ 512.1 KB │ 640.0 KB │
  │ 1M           │  12.0 MB │   8.0 MB │   7.5 MB │   8.0 MB │  10.0 MB │
  └──────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

════════════════════════════════════════════════════════════════════════════════
  u32 key → 4B value
════════════════════════════════════════════════════════════════════════════════
  ┌──────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Size         │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├──────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ 1K           │  20.0 KB │  16.0 KB │  15.0 KB │  16.1 KB │  18.0 KB │
  │ 100K         │   1.3 MB │   1.0 MB │ 960.0 KB │   1.0 MB │   1.1 MB │
  │ 1M           │  20.0 MB │  16.0 MB │  15.0 MB │  16.0 MB │  18.0 MB │
  └──────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

════════════════════════════════════════════════════════════════════════════════
  u64 key → void (set)
════════════════════════════════════════════════════════════════════════════════
  ┌──────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Size         │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├──────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ 1K           │  20.0 KB │  16.0 KB │  15.0 KB │  16.1 KB │  18.0 KB │
  │ 100K         │   1.3 MB │   1.0 MB │ 960.0 KB │   1.0 MB │   1.1 MB │
  │ 1M           │  20.0 MB │  16.0 MB │  15.0 MB │  16.0 MB │  18.0 MB │
  └──────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

════════════════════════════════════════════════════════════════════════════════
  u64 key → 4B value
════════════════════════════════════════════════════════════════════════════════
  ┌──────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Size         │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├──────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ 1K           │  36.0 KB │  32.0 KB │  30.0 KB │  32.1 KB │  26.0 KB │
  │ 100K         │   2.3 MB │   2.0 MB │   1.9 MB │   2.0 MB │   1.6 MB │
  │ 1M           │  36.0 MB │  32.0 MB │  30.0 MB │  32.0 MB │  26.0 MB │
  └──────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

════════════════════════════════════════════════════════════════════════════════
  u64 key → 64B value
════════════════════════════════════════════════════════════════════════════════
  ┌──────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Size         │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├──────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ 1K           │ 148.0 KB │ 144.0 KB │ 135.0 KB │ 144.1 KB │ 146.0 KB │
  │ 100K         │   9.3 MB │   9.0 MB │   8.4 MB │   9.0 MB │   9.1 MB │
  │ 1M           │ 148.0 MB │ 144.0 MB │ 135.0 MB │ 144.0 MB │ 146.0 MB │
  └──────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

════════════════════════════════════════════════════════════════════════════════
  string key → void (set)
════════════════════════════════════════════════════════════════════════════════
  ┌──────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Size         │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├──────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ 1K           │  52.0 KB │  32.0 KB │  30.0 KB │  32.1 KB │  34.0 KB │
  │ 100K         │   3.3 MB │   2.0 MB │   1.9 MB │   2.0 MB │   2.1 MB │
  └──────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

════════════════════════════════════════════════════════════════════════════════
  string key → 4B value
════════════════════════════════════════════════════════════════════════════════
  ┌──────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Size         │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├──────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ 1K           │  68.0 KB │  48.0 KB │  45.0 KB │  48.1 KB │  42.0 KB │
  │ 100K         │   4.3 MB │   3.0 MB │   2.8 MB │   3.0 MB │   2.6 MB │
  └──────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

```
