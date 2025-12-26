### run "zig build benchmark", and you'll get this:
```

╔══════════════════════════════════════════════════════════════════════════════╗
║                           u32 Integer Keys                                  ║
╚══════════════════════════════════════════════════════════════════════════════╝

════════════════════════════════════════════════════════════════════════════════
  u32 key → void (set) value
════════════════════════════════════════════════════════════════════════════════

  100 elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    26 ns │    50 ns │    31 ns │    25 ns │    23 ns │
  │ Seq. Insert    │    18 ns │    25 ns │    32 ns │    18 ns │    20 ns │
  │ Reserved Ins.  │    11 ns │    31 ns │    26 ns │    18 ns │    12 ns │
  │ Update         │     7 ns │     9 ns │     6 ns │    12 ns │    13 ns │
  │ Rand. Lookup   │     8 ns │    12 ns │     5 ns │     7 ns │    32 ns │
  │ High Load      │     5 ns │    10 ns │     4 ns │     6 ns │    28 ns │
  │ Lookup Miss    │     5 ns │    12 ns │     5 ns │     7 ns │    35 ns │
  │ Tombstone      │     9 ns │    33 ns │    13 ns │    16 ns │    26 ns │
  │ Delete         │     5 ns │    26 ns │    12 ns │    14 ns │     9 ns │
  │ Iteration      │     4 ns │     4 ns │     2 ns │     0 ns │     1 ns │
  │ Churn          │    16 ns │    40 ns │    44 ns │    21 ns │    21 ns │
  │ Mixed          │    10 ns │    19 ns │    10 ns │    16 ns │    18 ns │
  │ Read-Heavy     │     5 ns │     6 ns │     5 ns │     9 ns │    13 ns │
  │ Write-Heavy    │    24 ns │    27 ns │    26 ns │    17 ns │    20 ns │
  │ Update-Heavy   │     9 ns │    12 ns │     7 ns │    14 ns │    17 ns │
  │ Zipfian        │     9 ns │    18 ns │    11 ns │    17 ns │    13 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

  3K elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    29 ns │    21 ns │    26 ns │    23 ns │    30 ns │
  │ Seq. Insert    │    29 ns │    21 ns │    25 ns │    20 ns │    28 ns │
  │ Reserved Ins.  │    11 ns │    21 ns │    24 ns │    19 ns │    12 ns │
  │ Update         │    10 ns │     8 ns │     5 ns │    19 ns │    17 ns │
  │ Rand. Lookup   │    13 ns │    13 ns │     5 ns │     9 ns │    34 ns │
  │ High Load      │     7 ns │    14 ns │     5 ns │    10 ns │    28 ns │
  │ Lookup Miss    │     5 ns │     9 ns │     4 ns │     7 ns │    24 ns │
  │ Tombstone      │    16 ns │    23 ns │     9 ns │    28 ns │    34 ns │
  │ Delete         │     7 ns │    20 ns │     8 ns │    16 ns │    13 ns │
  │ Iteration      │     5 ns │     4 ns │     2 ns │     0 ns │     2 ns │
  │ Churn          │    18 ns │    39 ns │    14 ns │    26 ns │    52 ns │
  │ Mixed          │    16 ns │    19 ns │    14 ns │    22 ns │    22 ns │
  │ Read-Heavy     │     9 ns │     8 ns │     6 ns │    13 ns │    17 ns │
  │ Write-Heavy    │    42 ns │    32 ns │    28 ns │    31 ns │    37 ns │
  │ Update-Heavy   │    13 ns │    11 ns │     6 ns │    25 ns │    21 ns │
  │ Zipfian        │    12 ns │    19 ns │    13 ns │    21 ns │    15 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

  100K elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    62 ns │    24 ns │    31 ns │    52 ns │    50 ns │
  │ Seq. Insert    │    59 ns │    24 ns │    31 ns │    52 ns │    50 ns │
  │ Reserved Ins.  │    30 ns │    24 ns │    31 ns │    52 ns │    26 ns │
  │ Update         │    17 ns │    11 ns │     9 ns │    37 ns │    25 ns │
  │ Rand. Lookup   │    17 ns │    11 ns │    13 ns │    39 ns │    28 ns │
  │ High Load      │    17 ns │    13 ns │    14 ns │    35 ns │    27 ns │
  │ Lookup Miss    │    16 ns │    13 ns │     7 ns │    17 ns │    35 ns │
  │ Tombstone      │    31 ns │    31 ns │    16 ns │    55 ns │    51 ns │
  │ Delete         │    14 ns │    28 ns │    13 ns │    43 ns │    20 ns │
  │ Iteration      │     4 ns │     4 ns │     2 ns │     0 ns │     5 ns │
  │ Churn          │    52 ns │    53 ns │    51 ns │    79 ns │    84 ns │
  │ Mixed          │    33 ns │    31 ns │    24 ns │    62 ns │    47 ns │
  │ Read-Heavy     │    22 ns │    15 ns │    14 ns │    41 ns │    35 ns │
  │ Write-Heavy    │    59 ns │    37 ns │    34 ns │    45 ns │    53 ns │
  │ Update-Heavy   │    17 ns │    10 ns │    10 ns │    26 ns │    21 ns │
  │ Zipfian        │    13 ns │    11 ns │    10 ns │    28 ns │    14 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

════════════════════════════════════════════════════════════════════════════════
  u32 key → 4B value
════════════════════════════════════════════════════════════════════════════════

  100 elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    13 ns │    14 ns │    18 ns │    12 ns │    12 ns │
  │ Seq. Insert    │    10 ns │    13 ns │    15 ns │    11 ns │    11 ns │
  │ Reserved Ins.  │     5 ns │    12 ns │    15 ns │    10 ns │     6 ns │
  │ Update         │     3 ns │     4 ns │     5 ns │     3 ns │     6 ns │
  │ Rand. Lookup   │     2 ns │     6 ns │     2 ns │     3 ns │    16 ns │
  │ High Load      │     3 ns │     5 ns │     2 ns │     3 ns │    14 ns │
  │ Lookup Miss    │     1 ns │     6 ns │     2 ns │     3 ns │    12 ns │
  │ Tombstone      │     5 ns │    15 ns │     7 ns │     8 ns │    14 ns │
  │ Delete         │     2 ns │    12 ns │     6 ns │     6 ns │     5 ns │
  │ Iteration      │     2 ns │     2 ns │     1 ns │     0 ns │     1 ns │
  │ Churn          │     8 ns │    19 ns │    23 ns │    10 ns │    11 ns │
  │ Mixed          │     5 ns │     9 ns │     5 ns │     7 ns │    10 ns │
  │ Read-Heavy     │     2 ns │     3 ns │     3 ns │     4 ns │     6 ns │
  │ Write-Heavy    │    11 ns │    13 ns │    15 ns │     9 ns │    13 ns │
  │ Update-Heavy   │     5 ns │     6 ns │     7 ns │     6 ns │     9 ns │
  │ Zipfian        │     4 ns │     8 ns │     5 ns │     8 ns │     5 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

  3K elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    15 ns │    11 ns │    14 ns │    12 ns │    17 ns │
  │ Seq. Insert    │    15 ns │    11 ns │    15 ns │    11 ns │    16 ns │
  │ Reserved Ins.  │     5 ns │    11 ns │    15 ns │    11 ns │     6 ns │
  │ Update         │     5 ns │     4 ns │     4 ns │     7 ns │    10 ns │
  │ Rand. Lookup   │     4 ns │     5 ns │     2 ns │     5 ns │    16 ns │
  │ High Load      │     3 ns │     5 ns │     2 ns │     4 ns │    13 ns │
  │ Lookup Miss    │     2 ns │     4 ns │     2 ns │     4 ns │    12 ns │
  │ Tombstone      │     7 ns │    12 ns │     5 ns │    15 ns │    17 ns │
  │ Delete         │     3 ns │     9 ns │     4 ns │     9 ns │     7 ns │
  │ Iteration      │     2 ns │     2 ns │     1 ns │     0 ns │     1 ns │
  │ Churn          │     9 ns │    20 ns │     7 ns │    14 ns │    28 ns │
  │ Mixed          │     8 ns │    10 ns │     7 ns │    11 ns │    12 ns │
  │ Read-Heavy     │     4 ns │     3 ns │     3 ns │     8 ns │     8 ns │
  │ Write-Heavy    │    22 ns │    18 ns │    16 ns │    17 ns │    20 ns │
  │ Update-Heavy   │     7 ns │     6 ns │     7 ns │    11 ns │    12 ns │
  │ Zipfian        │     6 ns │     9 ns │     6 ns │    12 ns │     8 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

  100K elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    33 ns │    14 ns │    18 ns │    26 ns │    25 ns │
  │ Seq. Insert    │    30 ns │    14 ns │    19 ns │    28 ns │    26 ns │
  │ Reserved Ins.  │    15 ns │    14 ns │    18 ns │    26 ns │    14 ns │
  │ Update         │     9 ns │     6 ns │    10 ns │    14 ns │    14 ns │
  │ Rand. Lookup   │     8 ns │     6 ns │     7 ns │    18 ns │    13 ns │
  │ High Load      │     8 ns │     7 ns │     7 ns │    17 ns │    13 ns │
  │ Lookup Miss    │     8 ns │     6 ns │     4 ns │     8 ns │    18 ns │
  │ Tombstone      │    16 ns │    17 ns │     8 ns │    26 ns │    27 ns │
  │ Delete         │     6 ns │    13 ns │     6 ns │    20 ns │    10 ns │
  │ Iteration      │     2 ns │     2 ns │     1 ns │     0 ns │     2 ns │
  │ Churn          │    28 ns │    27 ns │    28 ns │    40 ns │    43 ns │
  │ Mixed          │    16 ns │    14 ns │    13 ns │    28 ns │    22 ns │
  │ Read-Heavy     │    10 ns │     7 ns │     8 ns │    28 ns │    15 ns │
  │ Write-Heavy    │    85 ns │    53 ns │    28 ns │    37 ns │    72 ns │
  │ Update-Heavy   │    16 ns │    11 ns │    14 ns │    27 ns │    19 ns │
  │ Zipfian        │    14 ns │    12 ns │    10 ns │    26 ns │    14 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

════════════════════════════════════════════════════════════════════════════════
  u32 key → 64B value
════════════════════════════════════════════════════════════════════════════════

  100 elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    20 ns │    26 ns │    25 ns │    21 ns │    18 ns │
  │ Seq. Insert    │    17 ns │    18 ns │    21 ns │    17 ns │    17 ns │
  │ Reserved Ins.  │    12 ns │    21 ns │    23 ns │    19 ns │    12 ns │
  │ Update         │    15 ns │    17 ns │    16 ns │    15 ns │    14 ns │
  │ Rand. Lookup   │    11 ns │     6 ns │     2 ns │     3 ns │    16 ns │
  │ High Load      │     3 ns │     5 ns │     2 ns │     3 ns │    13 ns │
  │ Lookup Miss    │     1 ns │     5 ns │     2 ns │     3 ns │    13 ns │
  │ Tombstone      │     9 ns │    18 ns │    10 ns │    12 ns │    15 ns │
  │ Delete         │     3 ns │    13 ns │     6 ns │     6 ns │     4 ns │
  │ Iteration      │     2 ns │     2 ns │     1 ns │     0 ns │     1 ns │
  │ Churn          │    11 ns │    22 ns │    30 ns │    14 ns │    19 ns │
  │ Mixed          │     6 ns │    11 ns │     7 ns │     7 ns │    10 ns │
  │ Read-Heavy     │     2 ns │     4 ns │     3 ns │     4 ns │     6 ns │
  │ Write-Heavy    │    16 ns │    19 ns │    23 ns │    15 ns │    15 ns │
  │ Update-Heavy   │    13 ns │    21 ns │    17 ns │    16 ns │    18 ns │
  │ Zipfian        │     5 ns │    10 ns │     7 ns │     8 ns │    10 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

  3K elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    24 ns │    30 ns │    27 ns │    22 ns │    24 ns │
  │ Seq. Insert    │    25 ns │    20 ns │    27 ns │    19 ns │    22 ns │
  │ Reserved Ins.  │    13 ns │    28 ns │    27 ns │    20 ns │    12 ns │
  │ Update         │    15 ns │    17 ns │    17 ns │    16 ns │    15 ns │
  │ Rand. Lookup   │    14 ns │     8 ns │     4 ns │     6 ns │    19 ns │
  │ High Load      │     4 ns │     6 ns │     3 ns │     5 ns │    15 ns │
  │ Lookup Miss    │     3 ns │     4 ns │     2 ns │     4 ns │    12 ns │
  │ Tombstone      │    11 ns │    14 ns │    10 ns │    18 ns │    18 ns │
  │ Delete         │     4 ns │    10 ns │     4 ns │     8 ns │     7 ns │
  │ Iteration      │     2 ns │     2 ns │     1 ns │     0 ns │     1 ns │
  │ Churn          │    13 ns │    22 ns │    12 ns │    18 ns │    29 ns │
  │ Mixed          │    10 ns │    11 ns │     9 ns │    12 ns │    13 ns │
  │ Read-Heavy     │     5 ns │     5 ns │     4 ns │     9 ns │     9 ns │
  │ Write-Heavy    │    39 ns │    23 ns │    27 ns │    26 ns │    26 ns │
  │ Update-Heavy   │    18 ns │    21 ns │    18 ns │    17 ns │    18 ns │
  │ Zipfian        │     7 ns │    11 ns │     9 ns │    13 ns │    10 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

  100K elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │   122 ns │    45 ns │    53 ns │    37 ns │    53 ns │
  │ Seq. Insert    │    96 ns │    50 ns │    51 ns │    37 ns │    55 ns │
  │ Reserved Ins.  │    37 ns │    46 ns │    56 ns │    37 ns │    24 ns │
  │ Update         │    35 ns │    63 ns │    49 ns │    27 ns │    32 ns │
  │ Rand. Lookup   │    16 ns │    23 ns │    24 ns │    29 ns │    15 ns │
  │ High Load      │    14 ns │    13 ns │    13 ns │    22 ns │    14 ns │
  │ Lookup Miss    │     8 ns │     6 ns │     4 ns │     8 ns │    17 ns │
  │ Tombstone      │    28 ns │    48 ns │    36 ns │    33 ns │    41 ns │
  │ Delete         │    15 ns │    23 ns │    15 ns │    20 ns │    10 ns │
  │ Iteration      │     2 ns │     2 ns │     1 ns │     0 ns │     2 ns │
  │ Churn          │    38 ns │    41 ns │    44 ns │    50 ns │    51 ns │
  │ Mixed          │    30 ns │    34 ns │    35 ns │    46 ns │    30 ns │
  │ Read-Heavy     │    20 ns │    20 ns │    18 ns │    32 ns │    17 ns │
  │ Write-Heavy    │   112 ns │   101 ns │   102 ns │    91 ns │    84 ns │
  │ Update-Heavy   │    64 ns │    54 ns │    65 ns │    69 ns │    51 ns │
  │ Zipfian        │    31 ns │    29 ns │    19 ns │    32 ns │    30 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

╔══════════════════════════════════════════════════════════════════════════════╗
║                           u64 Integer Keys                                  ║
╚══════════════════════════════════════════════════════════════════════════════╝

════════════════════════════════════════════════════════════════════════════════
  u64 key → void (set) value
════════════════════════════════════════════════════════════════════════════════

  100 elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    19 ns │    15 ns │    16 ns │    12 ns │     9 ns │
  │ Seq. Insert    │     7 ns │    12 ns │    12 ns │    10 ns │     9 ns │
  │ Reserved Ins.  │     5 ns │    13 ns │    14 ns │    11 ns │     4 ns │
  │ Update         │     3 ns │     4 ns │     3 ns │     5 ns │     4 ns │
  │ Rand. Lookup   │     2 ns │     6 ns │     2 ns │     2 ns │     7 ns │
  │ High Load      │     2 ns │     4 ns │     2 ns │     3 ns │     6 ns │
  │ Lookup Miss    │     2 ns │     6 ns │     2 ns │     3 ns │     5 ns │
  │ Tombstone      │     4 ns │    16 ns │     6 ns │     6 ns │     9 ns │
  │ Delete         │     2 ns │    12 ns │     6 ns │     6 ns │     3 ns │
  │ Iteration      │     2 ns │     1 ns │     1 ns │     0 ns │     1 ns │
  │ Churn          │     9 ns │    19 ns │    16 ns │    11 ns │    10 ns │
  │ Mixed          │     4 ns │     9 ns │     5 ns │     7 ns │     6 ns │
  │ Read-Heavy     │     2 ns │     3 ns │     3 ns │     3 ns │     4 ns │
  │ Write-Heavy    │    11 ns │    15 ns │    15 ns │    12 ns │     8 ns │
  │ Update-Heavy   │     4 ns │     5 ns │     3 ns │     9 ns │     7 ns │
  │ Zipfian        │     4 ns │     9 ns │     5 ns │     7 ns │     5 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

  3K elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    13 ns │    11 ns │    15 ns │    14 ns │    15 ns │
  │ Seq. Insert    │    13 ns │    10 ns │    13 ns │     9 ns │    13 ns │
  │ Reserved Ins.  │     5 ns │    11 ns │    15 ns │    13 ns │     6 ns │
  │ Update         │     4 ns │     4 ns │     3 ns │     9 ns │     9 ns │
  │ Rand. Lookup   │     4 ns │     5 ns │     3 ns │     5 ns │    17 ns │
  │ High Load      │     3 ns │     5 ns │     3 ns │     4 ns │    14 ns │
  │ Lookup Miss    │     3 ns │     4 ns │     2 ns │     4 ns │    12 ns │
  │ Tombstone      │     8 ns │    12 ns │     5 ns │    11 ns │    15 ns │
  │ Delete         │     3 ns │    10 ns │     4 ns │     9 ns │     7 ns │
  │ Iteration      │     2 ns │     2 ns │     1 ns │     0 ns │     1 ns │
  │ Churn          │     9 ns │    20 ns │     7 ns │    14 ns │    25 ns │
  │ Mixed          │     7 ns │    10 ns │     7 ns │    11 ns │    11 ns │
  │ Read-Heavy     │     5 ns │     3 ns │     3 ns │     7 ns │     8 ns │
  │ Write-Heavy    │    22 ns │    18 ns │    17 ns │    19 ns │    19 ns │
  │ Update-Heavy   │     7 ns │     5 ns │     4 ns │    14 ns │    11 ns │
  │ Zipfian        │     7 ns │    10 ns │     7 ns │    12 ns │     9 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

  100K elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    33 ns │    13 ns │    17 ns │    29 ns │    24 ns │
  │ Seq. Insert    │    30 ns │    12 ns │    13 ns │    10 ns │    23 ns │
  │ Reserved Ins.  │    15 ns │    13 ns │    17 ns │    28 ns │    13 ns │
  │ Update         │     8 ns │     6 ns │     5 ns │    17 ns │    12 ns │
  │ Rand. Lookup   │     8 ns │     5 ns │     6 ns │    18 ns │    13 ns │
  │ High Load      │     8 ns │     6 ns │     6 ns │    17 ns │    13 ns │
  │ Lookup Miss    │     8 ns │     6 ns │     3 ns │     8 ns │    16 ns │
  │ Tombstone      │    15 ns │    17 ns │     7 ns │    25 ns │    24 ns │
  │ Delete         │     7 ns │    14 ns │     6 ns │    19 ns │    10 ns │
  │ Iteration      │     2 ns │     2 ns │     1 ns │     0 ns │     2 ns │
  │ Churn          │    28 ns │    28 ns │    25 ns │    38 ns │    42 ns │
  │ Mixed          │    19 ns │    13 ns │    11 ns │    28 ns │    23 ns │
  │ Read-Heavy     │    13 ns │     7 ns │     7 ns │    22 ns │    14 ns │
  │ Write-Heavy    │    44 ns │    28 ns │    26 ns │    36 ns │    32 ns │
  │ Update-Heavy   │    18 ns │    10 ns │     9 ns │    25 ns │    18 ns │
  │ Zipfian        │    13 ns │    12 ns │    10 ns │    29 ns │    15 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

════════════════════════════════════════════════════════════════════════════════
  u64 key → 4B value
════════════════════════════════════════════════════════════════════════════════

  100 elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    15 ns │    14 ns │    16 ns │    14 ns │    10 ns │
  │ Seq. Insert    │     9 ns │    12 ns │    15 ns │    12 ns │     9 ns │
  │ Reserved Ins.  │     5 ns │    13 ns │    15 ns │    12 ns │     5 ns │
  │ Update         │     3 ns │     4 ns │     6 ns │     3 ns │     5 ns │
  │ Rand. Lookup   │     2 ns │     6 ns │     2 ns │     3 ns │     7 ns │
  │ High Load      │     3 ns │     5 ns │     2 ns │     3 ns │     7 ns │
  │ Lookup Miss    │     2 ns │     6 ns │     2 ns │     3 ns │     5 ns │
  │ Tombstone      │     5 ns │    16 ns │     7 ns │     7 ns │    10 ns │
  │ Delete         │     2 ns │    13 ns │     6 ns │     6 ns │     3 ns │
  │ Iteration      │     2 ns │     2 ns │     1 ns │     0 ns │     0 ns │
  │ Churn          │     9 ns │    21 ns │    18 ns │    10 ns │    11 ns │
  │ Mixed          │     5 ns │    11 ns │     6 ns │     7 ns │     6 ns │
  │ Read-Heavy     │     2 ns │     4 ns │     3 ns │     4 ns │     4 ns │
  │ Write-Heavy    │    13 ns │    15 ns │    18 ns │    12 ns │     9 ns │
  │ Update-Heavy   │     5 ns │     8 ns │     8 ns │     9 ns │     8 ns │
  │ Zipfian        │     5 ns │    10 ns │     6 ns │     6 ns │     5 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

  3K elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    14 ns │    11 ns │    17 ns │    15 ns │    17 ns │
  │ Seq. Insert    │    14 ns │     9 ns │    17 ns │    10 ns │    15 ns │
  │ Reserved Ins.  │     5 ns │    11 ns │    17 ns │    15 ns │     6 ns │
  │ Update         │     5 ns │     4 ns │     7 ns │     7 ns │    10 ns │
  │ Rand. Lookup   │     5 ns │     6 ns │     3 ns │     7 ns │    16 ns │
  │ High Load      │     3 ns │     6 ns │     3 ns │     4 ns │    16 ns │
  │ Lookup Miss    │     2 ns │     4 ns │     2 ns │     4 ns │    12 ns │
  │ Tombstone      │     9 ns │    12 ns │     7 ns │    13 ns │    18 ns │
  │ Delete         │     4 ns │    10 ns │     4 ns │     8 ns │     6 ns │
  │ Iteration      │     2 ns │     2 ns │     1 ns │     0 ns │     1 ns │
  │ Churn          │    10 ns │    21 ns │     8 ns │    14 ns │    25 ns │
  │ Mixed          │     8 ns │    10 ns │     8 ns │    12 ns │    12 ns │
  │ Read-Heavy     │     5 ns │     4 ns │     4 ns │     7 ns │     9 ns │
  │ Write-Heavy    │    25 ns │    21 ns │    22 ns │    19 ns │    20 ns │
  │ Update-Heavy   │     8 ns │     7 ns │     9 ns │    11 ns │    12 ns │
  │ Zipfian        │     7 ns │    10 ns │     7 ns │    12 ns │     9 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

  100K elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    32 ns │    14 ns │    21 ns │    30 ns │    27 ns │
  │ Seq. Insert    │    32 ns │    12 ns │    17 ns │    13 ns │    25 ns │
  │ Reserved Ins.  │    16 ns │    15 ns │    20 ns │    29 ns │    15 ns │
  │ Update         │    10 ns │     6 ns │    10 ns │    14 ns │    14 ns │
  │ Rand. Lookup   │     9 ns │     6 ns │     7 ns │    17 ns │    13 ns │
  │ High Load      │    12 ns │     7 ns │     8 ns │    17 ns │    12 ns │
  │ Lookup Miss    │     8 ns │     6 ns │     4 ns │     9 ns │    16 ns │
  │ Tombstone      │    18 ns │    16 ns │     9 ns │    27 ns │    26 ns │
  │ Delete         │     7 ns │    13 ns │     7 ns │    19 ns │     9 ns │
  │ Iteration      │     2 ns │     2 ns │     1 ns │     0 ns │     2 ns │
  │ Churn          │    37 ns │    28 ns │    28 ns │    39 ns │    49 ns │
  │ Mixed          │    23 ns │    20 ns │    19 ns │    31 ns │    33 ns │
  │ Read-Heavy     │    15 ns │     8 ns │     9 ns │    21 ns │    16 ns │
  │ Write-Heavy    │    53 ns │    31 ns │    32 ns │    37 ns │    34 ns │
  │ Update-Heavy   │    17 ns │    12 ns │    16 ns │    24 ns │    21 ns │
  │ Zipfian        │    15 ns │    12 ns │    12 ns │    28 ns │    15 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

════════════════════════════════════════════════════════════════════════════════
  u64 key → 64B value
════════════════════════════════════════════════════════════════════════════════

  100 elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    17 ns │    17 ns │    20 ns │    17 ns │    13 ns │
  │ Seq. Insert    │    12 ns │    16 ns │    20 ns │    18 ns │    15 ns │
  │ Reserved Ins.  │     8 ns │    15 ns │    19 ns │    16 ns │     7 ns │
  │ Update         │     6 ns │     7 ns │     8 ns │     6 ns │     7 ns │
  │ Rand. Lookup   │     5 ns │     6 ns │     2 ns │     3 ns │     7 ns │
  │ High Load      │     3 ns │     6 ns │     2 ns │     3 ns │     6 ns │
  │ Lookup Miss    │     2 ns │     5 ns │     2 ns │     3 ns │     5 ns │
  │ Tombstone      │     6 ns │    22 ns │     8 ns │     9 ns │    10 ns │
  │ Delete         │     2 ns │    13 ns │     6 ns │     6 ns │     3 ns │
  │ Iteration      │     2 ns │     2 ns │     1 ns │     0 ns │     1 ns │
  │ Churn          │    10 ns │    24 ns │    22 ns │    13 ns │    13 ns │
  │ Mixed          │     5 ns │    11 ns │     5 ns │     7 ns │     6 ns │
  │ Read-Heavy     │     2 ns │     3 ns │     3 ns │     3 ns │     4 ns │
  │ Write-Heavy    │    14 ns │    17 ns │    19 ns │    15 ns │    11 ns │
  │ Update-Heavy   │     7 ns │     8 ns │     9 ns │    13 ns │    13 ns │
  │ Zipfian        │     4 ns │     9 ns │     5 ns │     6 ns │     5 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

  3K elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    18 ns │    14 ns │    24 ns │    19 ns │    19 ns │
  │ Seq. Insert    │    20 ns │    20 ns │    24 ns │    19 ns │    21 ns │
  │ Reserved Ins.  │     8 ns │    15 ns │    23 ns │    20 ns │     9 ns │
  │ Update         │    10 ns │     7 ns │     8 ns │    11 ns │    15 ns │
  │ Rand. Lookup   │     5 ns │     8 ns │     4 ns │     7 ns │    21 ns │
  │ High Load      │     4 ns │     7 ns │     5 ns │     5 ns │    17 ns │
  │ Lookup Miss    │     2 ns │     5 ns │     2 ns │     4 ns │    12 ns │
  │ Tombstone      │    11 ns │    13 ns │     7 ns │    14 ns │    17 ns │
  │ Delete         │     4 ns │    11 ns │     4 ns │     9 ns │     6 ns │
  │ Iteration      │     2 ns │     2 ns │     1 ns │     0 ns │     1 ns │
  │ Churn          │    12 ns │    23 ns │    10 ns │    17 ns │    27 ns │
  │ Mixed          │     9 ns │    10 ns │     9 ns │    15 ns │    13 ns │
  │ Read-Heavy     │     5 ns │     5 ns │     4 ns │     8 ns │     9 ns │
  │ Write-Heavy    │    36 ns │    24 ns │    28 ns │    29 ns │    25 ns │
  │ Update-Heavy   │    12 ns │    10 ns │    12 ns │    15 ns │    15 ns │
  │ Zipfian        │     8 ns │    10 ns │    10 ns │    11 ns │    10 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

  100K elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    65 ns │    37 ns │    46 ns │    40 ns │    41 ns │
  │ Seq. Insert    │    69 ns │    51 ns │    54 ns │    25 ns │    50 ns │
  │ Reserved Ins.  │    28 ns │    38 ns │    45 ns │    38 ns │    20 ns │
  │ Update         │    24 ns │    17 ns │    22 ns │    19 ns │    20 ns │
  │ Rand. Lookup   │    13 ns │    16 ns │    16 ns │    23 ns │    14 ns │
  │ High Load      │    15 ns │    17 ns │    18 ns │    23 ns │    14 ns │
  │ Lookup Miss    │     9 ns │     8 ns │     4 ns │     8 ns │    17 ns │
  │ Tombstone      │    21 ns │    24 ns │    20 ns │    27 ns │    27 ns │
  │ Delete         │    11 ns │    20 ns │    14 ns │    19 ns │    10 ns │
  │ Iteration      │     2 ns │     2 ns │     1 ns │     0 ns │     2 ns │
  │ Churn          │    35 ns │    32 ns │    37 ns │    41 ns │    48 ns │
  │ Mixed          │    24 ns │    24 ns │    26 ns │    37 ns │    31 ns │
  │ Read-Heavy     │    18 ns │    20 ns │    19 ns │    28 ns │    18 ns │
  │ Write-Heavy    │   143 ns │    82 ns │    87 ns │    74 ns │    93 ns │
  │ Update-Heavy   │    39 ns │    25 ns │    34 ns │    39 ns │    31 ns │
  │ Zipfian        │    19 ns │    19 ns │    17 ns │    31 ns │    20 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

╔══════════════════════════════════════════════════════════════════════════════╗
║                    String Keys (Random Length 8-64 chars)                   ║
╚══════════════════════════════════════════════════════════════════════════════╝

════════════════════════════════════════════════════════════════════════════════
  string key → void (set) value
════════════════════════════════════════════════════════════════════════════════

  100 elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    29 ns │    26 ns │    17 ns │    26 ns │    24 ns │
  │ Seq. Insert    │    20 ns │    23 ns │    17 ns │    24 ns │    20 ns │
  │ Reserved Ins.  │    11 ns │    23 ns │    17 ns │    23 ns │     8 ns │
  │ Update         │     9 ns │    24 ns │    23 ns │    30 ns │    10 ns │
  │ Rand. Lookup   │    18 ns │    13 ns │     8 ns │    10 ns │    15 ns │
  │ High Load      │     8 ns │    11 ns │     7 ns │     9 ns │    14 ns │
  │ Lookup Miss    │     7 ns │    10 ns │     5 ns │     8 ns │    13 ns │
  │ Tombstone      │    11 ns │    31 ns │    17 ns │    27 ns │    16 ns │
  │ Delete         │     9 ns │    34 ns │    24 ns │    30 ns │    10 ns │
  │ Iteration      │     2 ns │     2 ns │     1 ns │     0 ns │     0 ns │
  │ Churn          │    16 ns │    37 ns │    26 ns │    31 ns │    22 ns │
  │ Mixed          │    10 ns │    37 ns │    33 ns │    35 ns │    12 ns │
  │ Read-Heavy     │     8 ns │    26 ns │    26 ns │    25 ns │    11 ns │
  │ Write-Heavy    │    24 ns │    35 ns │    28 ns │    30 ns │    25 ns │
  │ Update-Heavy   │    11 ns │    28 ns │    26 ns │    37 ns │    23 ns │
  │ Zipfian        │    11 ns │    36 ns │    32 ns │    34 ns │    11 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

  3K elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    45 ns │    29 ns │    20 ns │    35 ns │    39 ns │
  │ Seq. Insert    │    43 ns │    29 ns │    20 ns │    35 ns │    39 ns │
  │ Reserved Ins.  │    13 ns │    29 ns │    19 ns │    35 ns │    15 ns │
  │ Update         │    16 ns │    31 ns │    30 ns │    41 ns │    19 ns │
  │ Rand. Lookup   │    28 ns │    21 ns │    15 ns │    23 ns │    45 ns │
  │ High Load      │    23 ns │    20 ns │    16 ns │    25 ns │    46 ns │
  │ Lookup Miss    │    15 ns │    12 ns │     8 ns │    15 ns │    22 ns │
  │ Tombstone      │    22 ns │    31 ns │    20 ns │    45 ns │    24 ns │
  │ Delete         │    16 ns │    36 ns │    30 ns │    48 ns │    19 ns │
  │ Iteration      │     2 ns │     2 ns │     1 ns │     0 ns │     2 ns │
  │ Churn          │    28 ns │    41 ns │    32 ns │    51 ns │    35 ns │
  │ Mixed          │    28 ns │    53 ns │    54 ns │    67 ns │    33 ns │
  │ Read-Heavy     │    20 ns │    40 ns │    39 ns │    48 ns │    25 ns │
  │ Write-Heavy    │    67 ns │    69 ns │    52 ns │    67 ns │    58 ns │
  │ Update-Heavy   │    28 ns │    44 ns │    41 ns │    59 ns │    28 ns │
  │ Zipfian        │    25 ns │    53 ns │    48 ns │    61 ns │    27 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

  100K elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    85 ns │    39 ns │    32 ns │    54 ns │    56 ns │
  │ Seq. Insert    │    78 ns │    44 ns │    32 ns │    53 ns │    52 ns │
  │ Reserved Ins.  │    33 ns │    45 ns │    34 ns │    53 ns │    22 ns │
  │ Update         │    25 ns │    40 ns │    40 ns │    51 ns │    23 ns │
  │ Rand. Lookup   │    56 ns │    87 ns │    89 ns │   107 ns │    46 ns │
  │ High Load      │    57 ns │    87 ns │    99 ns │   112 ns │    45 ns │
  │ Lookup Miss    │    20 ns │    15 ns │    12 ns │    19 ns │    28 ns │
  │ Tombstone      │    36 ns │    39 ns │    30 ns │    59 ns │    30 ns │
  │ Delete         │    28 ns │    47 ns │    39 ns │    58 ns │    22 ns │
  │ Iteration      │     2 ns │     2 ns │     1 ns │     0 ns │     2 ns │
  │ Churn          │    77 ns │    71 ns │    78 ns │    90 ns │    77 ns │
  │ Mixed          │    69 ns │    99 ns │   101 ns │   127 ns │    67 ns │
  │ Read-Heavy     │    54 ns │    85 ns │    85 ns │   110 ns │    53 ns │
  │ Write-Heavy    │   216 ns │   210 ns │   165 ns │   180 ns │   167 ns │
  │ Update-Heavy   │    64 ns │    90 ns │    89 ns │   121 ns │    58 ns │
  │ Zipfian        │    54 ns │    82 ns │    83 ns │   107 ns │    49 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

════════════════════════════════════════════════════════════════════════════════
  string key → 4B value
════════════════════════════════════════════════════════════════════════════════

  100 elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    23 ns │    27 ns │    19 ns │    20 ns │    25 ns │
  │ Seq. Insert    │    20 ns │    25 ns │    18 ns │    19 ns │    21 ns │
  │ Reserved Ins.  │    11 ns │    25 ns │    18 ns │    18 ns │     9 ns │
  │ Update         │     9 ns │    30 ns │    29 ns │    26 ns │    10 ns │
  │ Rand. Lookup   │    11 ns │    13 ns │     7 ns │    10 ns │    16 ns │
  │ High Load      │     8 ns │    11 ns │     7 ns │    10 ns │    14 ns │
  │ Lookup Miss    │     7 ns │     9 ns │     5 ns │     8 ns │    13 ns │
  │ Tombstone      │    11 ns │    30 ns │    19 ns │    24 ns │    15 ns │
  │ Delete         │    10 ns │    35 ns │    27 ns │    33 ns │    10 ns │
  │ Iteration      │     2 ns │     2 ns │     1 ns │     0 ns │     1 ns │
  │ Churn          │    16 ns │    38 ns │    28 ns │    29 ns │    22 ns │
  │ Mixed          │    10 ns │    40 ns │    37 ns │    38 ns │    13 ns │
  │ Read-Heavy     │     9 ns │    29 ns │    28 ns │    28 ns │    11 ns │
  │ Write-Heavy    │    23 ns │    38 ns │    30 ns │    28 ns │    25 ns │
  │ Update-Heavy   │    11 ns │    33 ns │    32 ns │    34 ns │    23 ns │
  │ Zipfian        │    10 ns │    39 ns │    35 ns │    36 ns │    12 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

  3K elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    43 ns │    30 ns │    29 ns │    33 ns │    40 ns │
  │ Seq. Insert    │    41 ns │    28 ns │    27 ns │    32 ns │    39 ns │
  │ Reserved Ins.  │    15 ns │    29 ns │    28 ns │    34 ns │    15 ns │
  │ Update         │    18 ns │    35 ns │    36 ns │    37 ns │    20 ns │
  │ Rand. Lookup   │    29 ns │    21 ns │    15 ns │    29 ns │    47 ns │
  │ High Load      │    25 ns │    20 ns │    15 ns │    23 ns │    42 ns │
  │ Lookup Miss    │    16 ns │    13 ns │     8 ns │    14 ns │    23 ns │
  │ Tombstone      │    21 ns │    33 ns │    25 ns │    46 ns │    25 ns │
  │ Delete         │    16 ns │    41 ns │    32 ns │    54 ns │    19 ns │
  │ Iteration      │     2 ns │     2 ns │     1 ns │     0 ns │     2 ns │
  │ Churn          │    30 ns │    43 ns │    32 ns │    45 ns │    36 ns │
  │ Mixed          │    28 ns │    52 ns │    50 ns │    59 ns │    33 ns │
  │ Read-Heavy     │    20 ns │    41 ns │    39 ns │    49 ns │    24 ns │
  │ Write-Heavy    │    74 ns │    64 ns │    53 ns │    63 ns │    54 ns │
  │ Update-Heavy   │    24 ns │    44 ns │    46 ns │    49 ns │    27 ns │
  │ Zipfian        │    24 ns │    48 ns │    47 ns │    57 ns │    25 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

  100K elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    85 ns │    54 ns │    37 ns │    50 ns │    58 ns │
  │ Seq. Insert    │    84 ns │    49 ns │    35 ns │    49 ns │    57 ns │
  │ Reserved Ins.  │    42 ns │    54 ns │    37 ns │    50 ns │    23 ns │
  │ Update         │    30 ns │    43 ns │    43 ns │    45 ns │    25 ns │
  │ Rand. Lookup   │    62 ns │   114 ns │   108 ns │   125 ns │    54 ns │
  │ High Load      │    63 ns │    98 ns │   103 ns │   122 ns │    52 ns │
  │ Lookup Miss    │    24 ns │    15 ns │    12 ns │    19 ns │    28 ns │
  │ Tombstone      │    36 ns │    40 ns │    30 ns │    57 ns │    31 ns │
  │ Delete         │    26 ns │    46 ns │    42 ns │    59 ns │    23 ns │
  │ Iteration      │     2 ns │     2 ns │     1 ns │     0 ns │     2 ns │
  │ Churn          │    86 ns │    77 ns │    86 ns │    93 ns │    79 ns │
  │ Mixed          │    77 ns │   156 ns │   126 ns │   143 ns │    68 ns │
  │ Read-Heavy     │    63 ns │   100 ns │    88 ns │   122 ns │    55 ns │
  │ Write-Heavy    │   238 ns │   309 ns │   199 ns │   164 ns │   187 ns │
  │ Update-Heavy   │    77 ns │   108 ns │    97 ns │   126 ns │    63 ns │
  │ Zipfian        │    67 ns │    92 ns │    86 ns │   113 ns │    49 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

════════════════════════════════════════════════════════════════════════════════
  string key → 64B value
════════════════════════════════════════════════════════════════════════════════

  100 elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    33 ns │    31 ns │    22 ns │    24 ns │    27 ns │
  │ Seq. Insert    │    25 ns │    30 ns │    25 ns │    25 ns │    25 ns │
  │ Reserved Ins.  │    11 ns │    27 ns │    20 ns │    21 ns │     9 ns │
  │ Update         │    14 ns │    33 ns │    31 ns │    28 ns │    12 ns │
  │ Rand. Lookup   │    13 ns │    17 ns │     8 ns │    10 ns │    16 ns │
  │ High Load      │     9 ns │    11 ns │     7 ns │    10 ns │    14 ns │
  │ Lookup Miss    │     7 ns │    11 ns │     5 ns │     7 ns │    13 ns │
  │ Tombstone      │    13 ns │    32 ns │    19 ns │    25 ns │    16 ns │
  │ Delete         │    10 ns │    36 ns │    27 ns │    32 ns │    10 ns │
  │ Iteration      │     2 ns │     2 ns │     1 ns │     0 ns │     1 ns │
  │ Churn          │    16 ns │    38 ns │    29 ns │    30 ns │    23 ns │
  │ Mixed          │    11 ns │    41 ns │    38 ns │    37 ns │    12 ns │
  │ Read-Heavy     │     9 ns │    29 ns │    28 ns │    28 ns │    11 ns │
  │ Write-Heavy    │    25 ns │    43 ns │    33 ns │    31 ns │    27 ns │
  │ Update-Heavy   │    14 ns │    35 ns │    33 ns │    36 ns │    27 ns │
  │ Zipfian        │    11 ns │    40 ns │    36 ns │    41 ns │    11 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

  3K elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    52 ns │    35 ns │    32 ns │    39 ns │    45 ns │
  │ Seq. Insert    │    50 ns │    38 ns │    34 ns │    41 ns │    48 ns │
  │ Reserved Ins.  │    19 ns │    34 ns │    28 ns │    38 ns │    18 ns │
  │ Update         │    24 ns │    41 ns │    38 ns │    41 ns │    24 ns │
  │ Rand. Lookup   │    49 ns │    23 ns │    16 ns │    24 ns │    46 ns │
  │ High Load      │    27 ns │    22 ns │    15 ns │    24 ns │    44 ns │
  │ Lookup Miss    │    16 ns │    14 ns │     8 ns │    14 ns │    25 ns │
  │ Tombstone      │    23 ns │    36 ns │    26 ns │    47 ns │    28 ns │
  │ Delete         │    17 ns │    43 ns │    35 ns │    50 ns │    20 ns │
  │ Iteration      │     2 ns │     2 ns │     1 ns │     0 ns │     2 ns │
  │ Churn          │    33 ns │    47 ns │    34 ns │    54 ns │    41 ns │
  │ Mixed          │    30 ns │    78 ns │    63 ns │    67 ns │    41 ns │
  │ Read-Heavy     │    23 ns │    48 ns │    52 ns │    53 ns │    26 ns │
  │ Write-Heavy    │    80 ns │    75 ns │    63 ns │    74 ns │    65 ns │
  │ Update-Heavy   │    29 ns │    53 ns │    49 ns │    57 ns │    30 ns │
  │ Zipfian        │    25 ns │    58 ns │    50 ns │    60 ns │    26 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

  100K elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │   143 ns │    83 ns │    88 ns │    61 ns │   103 ns │
  │ Seq. Insert    │   171 ns │   100 ns │    96 ns │    64 ns │   104 ns │
  │ Reserved Ins.  │    63 ns │   101 ns │   103 ns │    69 ns │    34 ns │
  │ Update         │    69 ns │   159 ns │    86 ns │    48 ns │    65 ns │
  │ Rand. Lookup   │    94 ns │   186 ns │   187 ns │   226 ns │    73 ns │
  │ High Load      │    92 ns │   180 ns │   187 ns │   215 ns │    70 ns │
  │ Lookup Miss    │    33 ns │    19 ns │    13 ns │    19 ns │    28 ns │
  │ Tombstone      │    57 ns │    70 ns │    68 ns │    58 ns │    44 ns │
  │ Delete         │    37 ns │    75 ns │    81 ns │    60 ns │    24 ns │
  │ Iteration      │     2 ns │     2 ns │     1 ns │     0 ns │     2 ns │
  │ Churn          │   104 ns │   143 ns │   125 ns │   134 ns │   114 ns │
  │ Mixed          │   103 ns │   167 ns │   169 ns │   237 ns │    94 ns │
  │ Read-Heavy     │    92 ns │   246 ns │   181 ns │   226 ns │    76 ns │
  │ Write-Heavy    │   321 ns │   272 ns │   213 ns │   207 ns │   230 ns │
  │ Update-Heavy   │   131 ns │   223 ns │   174 ns │   205 ns │   133 ns │
  │ Zipfian        │    82 ns │   125 ns │   112 ns │   159 ns │    70 ns │
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
