### run "zig build benchmark", and you'll get this:
```
╔══════════════════════════════════════════════════════════════════════════════╗
║                           u32 Integer Keys                                   ║
╚══════════════════════════════════════════════════════════════════════════════╝

════════════════════════════════════════════════════════════════════════════════
  u32 key → void (set) value
════════════════════════════════════════════════════════════════════════════════

  10 elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    47 ns │   249 ns │    33 ns │    43 ns │    35 ns │
  │ Seq. Insert    │    16 ns │    30 ns │    25 ns │    32 ns │    24 ns │
  │ Reserved Ins.  │    12 ns │    30 ns │    25 ns │    33 ns │    15 ns │
  │ Update         │    10 ns │    13 ns │    11 ns │    12 ns │    16 ns │
  │ Rand. Lookup   │     9 ns │    13 ns │     9 ns │     9 ns │    19 ns │
  │ High Load      │     9 ns │     9 ns │     7 ns │    10 ns │    17 ns │
  │ Lookup Miss    │     9 ns │     9 ns │     8 ns │    12 ns │    14 ns │
  │ Tombstone      │    12 ns │    29 ns │    21 ns │    16 ns │    15 ns │
  │ Delete         │     9 ns │    24 ns │    23 ns │    15 ns │    14 ns │
  │ Iteration      │     8 ns │     8 ns │     8 ns │     4 ns │     6 ns │
  │ Churn          │    13 ns │    16 ns │    11 ns │    12 ns │    18 ns │
  │ Mixed          │    21 ns │    27 ns │    23 ns │    27 ns │    33 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

  1K elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    29 ns │    27 ns │    33 ns │    22 ns │    24 ns │
  │ Seq. Insert    │    23 ns │    25 ns │    33 ns │    20 ns │    22 ns │
  │ Reserved Ins.  │     8 ns │    25 ns │    38 ns │    19 ns │     8 ns │
  │ Update         │     5 ns │     7 ns │     5 ns │     8 ns │     9 ns │
  │ Rand. Lookup   │     5 ns │     6 ns │     4 ns │     5 ns │     8 ns │
  │ High Load      │     4 ns │     5 ns │     5 ns │     5 ns │     7 ns │
  │ Lookup Miss    │     3 ns │     6 ns │     4 ns │     6 ns │     6 ns │
  │ Tombstone      │     8 ns │    15 ns │     9 ns │    10 ns │     8 ns │
  │ Delete         │     4 ns │    12 ns │     8 ns │     9 ns │     6 ns │
  │ Iteration      │     5 ns │    10 ns │     2 ns │     0 ns │     3 ns │
  │ Churn          │    13 ns │    26 ns │    12 ns │    16 ns │    16 ns │
  │ Mixed          │     9 ns │    15 ns │    11 ns │    12 ns │    13 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

  100K elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    60 ns │    24 ns │    30 ns │    49 ns │    48 ns │
  │ Seq. Insert    │    57 ns │    24 ns │    30 ns │    48 ns │    49 ns │
  │ Reserved Ins.  │    30 ns │    24 ns │    30 ns │    48 ns │    26 ns │
  │ Update         │    16 ns │    12 ns │    10 ns │    42 ns │    25 ns │
  │ Rand. Lookup   │    17 ns │    10 ns │    12 ns │    40 ns │    25 ns │
  │ High Load      │    18 ns │    11 ns │    13 ns │    37 ns │    26 ns │
  │ Lookup Miss    │    19 ns │    12 ns │     7 ns │    16 ns │    36 ns │
  │ Tombstone      │    29 ns │    31 ns │    15 ns │    50 ns │    50 ns │
  │ Delete         │    13 ns │    26 ns │    12 ns │    38 ns │    19 ns │
  │ Iteration      │     4 ns │     4 ns │     2 ns │     0 ns │     5 ns │
  │ Churn          │    52 ns │    53 ns │    49 ns │    75 ns │    80 ns │
  │ Mixed          │    30 ns │    24 ns │    22 ns │    54 ns │    43 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

════════════════════════════════════════════════════════════════════════════════
  u32 key → 4B value
════════════════════════════════════════════════════════════════════════════════

  10 elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    24 ns │    45 ns │    34 ns │    45 ns │    29 ns │
  │ Seq. Insert    │    16 ns │    29 ns │    25 ns │    35 ns │    25 ns │
  │ Reserved Ins.  │    12 ns │    27 ns │    26 ns │    35 ns │    15 ns │
  │ Update         │    10 ns │    16 ns │    13 ns │     9 ns │    17 ns │
  │ Rand. Lookup   │    15 ns │    11 ns │     8 ns │     9 ns │    18 ns │
  │ High Load      │     9 ns │    10 ns │     8 ns │     8 ns │    18 ns │
  │ Lookup Miss    │    10 ns │    11 ns │     8 ns │    10 ns │    12 ns │
  │ Tombstone      │    12 ns │    28 ns │    21 ns │    16 ns │    15 ns │
  │ Delete         │     9 ns │    26 ns │    23 ns │    15 ns │    14 ns │
  │ Iteration      │     8 ns │     8 ns │    10 ns │     4 ns │     6 ns │
  │ Churn          │    13 ns │    19 ns │    12 ns │    11 ns │    17 ns │
  │ Mixed          │    16 ns │    21 ns │    16 ns │    18 ns │    32 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

  1K elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    27 ns │    26 ns │    40 ns │    23 ns │    26 ns │
  │ Seq. Insert    │    25 ns │    25 ns │    39 ns │    22 ns │    25 ns │
  │ Reserved Ins.  │     8 ns │    25 ns │    40 ns │    22 ns │     8 ns │
  │ Update         │     7 ns │     8 ns │    10 ns │     5 ns │    10 ns │
  │ Rand. Lookup   │     4 ns │     6 ns │     5 ns │     6 ns │     9 ns │
  │ High Load      │     4 ns │     6 ns │     5 ns │     6 ns │     7 ns │
  │ Lookup Miss    │     3 ns │     6 ns │     4 ns │     6 ns │     7 ns │
  │ Tombstone      │     8 ns │    16 ns │    11 ns │    12 ns │     9 ns │
  │ Delete         │     5 ns │    12 ns │     8 ns │    10 ns │     6 ns │
  │ Iteration      │     5 ns │    10 ns │     3 ns │     0 ns │     2 ns │
  │ Churn          │    13 ns │    28 ns │    15 ns │    15 ns │    17 ns │
  │ Mixed          │     9 ns │    17 ns │    14 ns │    14 ns │    14 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

  100K elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    63 ns │    26 ns │    36 ns │    54 ns │    51 ns │
  │ Seq. Insert    │    58 ns │    26 ns │    35 ns │    52 ns │    50 ns │
  │ Reserved Ins.  │    30 ns │    26 ns │    35 ns │    52 ns │    29 ns │
  │ Update         │    19 ns │    13 ns │    19 ns │    27 ns │    27 ns │
  │ Rand. Lookup   │    17 ns │    12 ns │    13 ns │    33 ns │    25 ns │
  │ High Load      │    18 ns │    13 ns │    14 ns │    32 ns │    26 ns │
  │ Lookup Miss    │    17 ns │    12 ns │     7 ns │    16 ns │    35 ns │
  │ Tombstone      │    31 ns │    32 ns │    16 ns │    49 ns │    50 ns │
  │ Delete         │    12 ns │    21 ns │     9 ns │    27 ns │    16 ns │
  │ Iteration      │     3 ns │     2 ns │     1 ns │     0 ns │     3 ns │
  │ Churn          │    33 ns │    31 ns │    29 ns │    41 ns │    49 ns │
  │ Mixed          │    18 ns │    14 ns │    12 ns │    26 ns │    21 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

════════════════════════════════════════════════════════════════════════════════
  u32 key → 64B value
════════════════════════════════════════════════════════════════════════════════

  10 elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    25 ns │    28 ns │    23 ns │    31 ns │    23 ns │
  │ Seq. Insert    │    14 ns │    20 ns │    18 ns │    24 ns │    18 ns │
  │ Reserved Ins.  │    12 ns │    22 ns │    20 ns │    26 ns │    13 ns │
  │ Update         │    14 ns │    17 ns │    17 ns │    16 ns │    15 ns │
  │ Rand. Lookup   │     7 ns │     6 ns │     4 ns │     5 ns │    10 ns │
  │ High Load      │     4 ns │     5 ns │     4 ns │     4 ns │     8 ns │
  │ Lookup Miss    │     4 ns │     5 ns │     4 ns │     5 ns │     6 ns │
  │ Tombstone      │    10 ns │    15 ns │    14 ns │    13 ns │    13 ns │
  │ Delete         │    72 ns │    12 ns │    11 ns │     7 ns │     8 ns │
  │ Iteration      │     4 ns │     4 ns │     4 ns │     2 ns │     3 ns │
  │ Churn          │     9 ns │    12 ns │    11 ns │    12 ns │    11 ns │
  │ Mixed          │     9 ns │    10 ns │     8 ns │     9 ns │    13 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

  1K elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    22 ns │    22 ns │    32 ns │    21 ns │    21 ns │
  │ Seq. Insert    │    18 ns │    22 ns │    29 ns │    18 ns │    18 ns │
  │ Reserved Ins.  │    11 ns │    21 ns │    30 ns │    19 ns │    10 ns │
  │ Update         │    14 ns │    17 ns │    18 ns │    14 ns │    13 ns │
  │ Rand. Lookup   │     3 ns │     4 ns │     3 ns │     3 ns │     4 ns │
  │ High Load      │     4 ns │     4 ns │     3 ns │     3 ns │     4 ns │
  │ Lookup Miss    │     1 ns │     3 ns │     2 ns │     3 ns │     3 ns │
  │ Tombstone      │     7 ns │    11 ns │     9 ns │    11 ns │     7 ns │
  │ Delete         │     4 ns │     6 ns │     5 ns │     6 ns │     3 ns │
  │ Iteration      │     2 ns │     5 ns │     1 ns │     0 ns │     1 ns │
  │ Churn          │     9 ns │    16 ns │    10 ns │    11 ns │    10 ns │
  │ Mixed          │     5 ns │     9 ns │     8 ns │     8 ns │     8 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

  100K elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │   119 ns │    58 ns │    52 ns │    37 ns │    55 ns │
  │ Seq. Insert    │   105 ns │    57 ns │    55 ns │    38 ns │    56 ns │
  │ Reserved Ins.  │    50 ns │    84 ns │    92 ns │    39 ns │    37 ns │
  │ Update         │    66 ns │    68 ns │    46 ns │    28 ns │    36 ns │
  │ Rand. Lookup   │    12 ns │    12 ns │    13 ns │    20 ns │    13 ns │
  │ High Load      │    11 ns │    13 ns │    12 ns │    21 ns │    13 ns │
  │ Lookup Miss    │     9 ns │     7 ns │     3 ns │     8 ns │    18 ns │
  │ Tombstone      │    20 ns │    23 ns │    20 ns │    28 ns │    31 ns │
  │ Delete         │    10 ns │    24 ns │    11 ns │    19 ns │    10 ns │
  │ Iteration      │     2 ns │     2 ns │     1 ns │     0 ns │     2 ns │
  │ Churn          │    33 ns │    30 ns │    33 ns │    40 ns │    47 ns │
  │ Mixed          │    21 ns │    21 ns │    21 ns │    32 ns │    27 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

╔══════════════════════════════════════════════════════════════════════════════╗
║                           u64 Integer Keys                                   ║
╚══════════════════════════════════════════════════════════════════════════════╝

════════════════════════════════════════════════════════════════════════════════
  u64 key → void (set) value
════════════════════════════════════════════════════════════════════════════════

  10 elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    12 ns │    27 ns │    15 ns │    23 ns │    13 ns │
  │ Seq. Insert    │     8 ns │    15 ns │    12 ns │    19 ns │    12 ns │
  │ Reserved Ins.  │     7 ns │    15 ns │    13 ns │    19 ns │     6 ns │
  │ Update         │     5 ns │     7 ns │     5 ns │     6 ns │     6 ns │
  │ Rand. Lookup   │     5 ns │     7 ns │     4 ns │     4 ns │     7 ns │
  │ High Load      │     4 ns │     5 ns │     3 ns │     4 ns │     7 ns │
  │ Lookup Miss    │     4 ns │     5 ns │     4 ns │     4 ns │     7 ns │
  │ Tombstone      │     6 ns │    15 ns │    10 ns │     7 ns │    10 ns │
  │ Delete         │     5 ns │    13 ns │    10 ns │     7 ns │     6 ns │
  │ Iteration      │     4 ns │     4 ns │     5 ns │     2 ns │     3 ns │
  │ Churn          │     7 ns │     9 ns │     8 ns │     7 ns │     9 ns │
  │ Mixed          │    56 ns │     9 ns │     8 ns │     8 ns │    11 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

  1K elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    14 ns │    13 ns │    19 ns │    15 ns │    13 ns │
  │ Seq. Insert    │    11 ns │    11 ns │    17 ns │    11 ns │    11 ns │
  │ Reserved Ins.  │     4 ns │    13 ns │    19 ns │    14 ns │     4 ns │
  │ Update         │     3 ns │     3 ns │     3 ns │     4 ns │     4 ns │
  │ Rand. Lookup   │     2 ns │     3 ns │     2 ns │     3 ns │     4 ns │
  │ High Load      │     1 ns │     3 ns │     2 ns │     3 ns │     3 ns │
  │ Lookup Miss    │     1 ns │     2 ns │     2 ns │     3 ns │     3 ns │
  │ Tombstone      │     3 ns │     8 ns │     5 ns │     5 ns │     3 ns │
  │ Delete         │     2 ns │     6 ns │     4 ns │     5 ns │     2 ns │
  │ Iteration      │     2 ns │     5 ns │     1 ns │     0 ns │     1 ns │
  │ Churn          │     7 ns │    13 ns │     6 ns │     8 ns │     8 ns │
  │ Mixed          │     5 ns │     9 ns │    10 ns │    11 ns │     6 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

  100K elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    32 ns │    14 ns │    17 ns │    28 ns │    26 ns │
  │ Seq. Insert    │    27 ns │    12 ns │    14 ns │    10 ns │    23 ns │
  │ Reserved Ins.  │    15 ns │    13 ns │    17 ns │    27 ns │    12 ns │
  │ Update         │     8 ns │     6 ns │     5 ns │    16 ns │    12 ns │
  │ Rand. Lookup   │     8 ns │     5 ns │     6 ns │    17 ns │    13 ns │
  │ High Load      │     9 ns │     6 ns │     6 ns │    17 ns │    13 ns │
  │ Lookup Miss    │    10 ns │     6 ns │     3 ns │     7 ns │    17 ns │
  │ Tombstone      │    15 ns │    16 ns │     7 ns │    24 ns │    24 ns │
  │ Delete         │     7 ns │    13 ns │     6 ns │    19 ns │     9 ns │
  │ Iteration      │     2 ns │     2 ns │     1 ns │     0 ns │     2 ns │
  │ Churn          │    28 ns │    27 ns │    26 ns │    39 ns │    43 ns │
  │ Mixed          │    17 ns │    13 ns │    11 ns │    28 ns │    21 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

════════════════════════════════════════════════════════════════════════════════
  u64 key → 4B value
════════════════════════════════════════════════════════════════════════════════

  10 elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    15 ns │    33 ns │    18 ns │    26 ns │    14 ns │
  │ Seq. Insert    │     8 ns │    14 ns │    11 ns │    21 ns │    13 ns │
  │ Reserved Ins.  │     7 ns │    14 ns │    12 ns │    21 ns │     6 ns │
  │ Update         │     5 ns │     8 ns │     8 ns │     5 ns │     6 ns │
  │ Rand. Lookup   │     5 ns │     6 ns │     4 ns │     4 ns │     7 ns │
  │ High Load      │     4 ns │     5 ns │     4 ns │     4 ns │     6 ns │
  │ Lookup Miss    │     4 ns │     6 ns │     4 ns │     4 ns │     7 ns │
  │ Tombstone      │     6 ns │    15 ns │    10 ns │     8 ns │     9 ns │
  │ Delete         │     5 ns │    13 ns │    10 ns │     7 ns │     6 ns │
  │ Iteration      │     4 ns │     4 ns │     4 ns │     2 ns │     3 ns │
  │ Churn          │     7 ns │    10 ns │     9 ns │     6 ns │     9 ns │
  │ Mixed          │     8 ns │    11 ns │     8 ns │     9 ns │    13 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

  1K elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    14 ns │    13 ns │    21 ns │    16 ns │    13 ns │
  │ Seq. Insert    │    12 ns │    12 ns │    20 ns │    13 ns │    10 ns │
  │ Reserved Ins.  │     4 ns │    14 ns │    21 ns │    14 ns │     4 ns │
  │ Update         │     3 ns │     4 ns │     6 ns │     3 ns │     4 ns │
  │ Rand. Lookup   │     2 ns │     3 ns │     2 ns │     3 ns │     4 ns │
  │ High Load      │     2 ns │     3 ns │     2 ns │     3 ns │     3 ns │
  │ Lookup Miss    │     1 ns │     3 ns │     2 ns │     3 ns │     3 ns │
  │ Tombstone      │     3 ns │     7 ns │     6 ns │     5 ns │     4 ns │
  │ Delete         │     2 ns │     6 ns │     4 ns │     4 ns │     2 ns │
  │ Iteration      │     2 ns │     5 ns │     1 ns │     0 ns │     1 ns │
  │ Churn          │     7 ns │    13 ns │     8 ns │     8 ns │     8 ns │
  │ Mixed          │     5 ns │     8 ns │     7 ns │     7 ns │     6 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

  100K elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    35 ns │    14 ns │    20 ns │    31 ns │    26 ns │
  │ Seq. Insert    │    29 ns │    13 ns │    19 ns │    12 ns │    24 ns │
  │ Reserved Ins.  │    15 ns │    15 ns │    20 ns │    29 ns │    14 ns │
  │ Update         │    10 ns │     6 ns │    10 ns │    14 ns │    13 ns │
  │ Rand. Lookup   │    10 ns │     7 ns │     7 ns │    18 ns │    12 ns │
  │ High Load      │    11 ns │     7 ns │     8 ns │    17 ns │    13 ns │
  │ Lookup Miss    │     9 ns │     6 ns │     3 ns │     8 ns │    17 ns │
  │ Tombstone      │    17 ns │    16 ns │     9 ns │    26 ns │    25 ns │
  │ Delete         │     7 ns │    14 ns │     6 ns │    19 ns │    10 ns │
  │ Iteration      │     2 ns │     2 ns │     1 ns │     0 ns │     2 ns │
  │ Churn          │    30 ns │    28 ns │    32 ns │    39 ns │    44 ns │
  │ Mixed          │    18 ns │    15 ns │    13 ns │    28 ns │    22 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

════════════════════════════════════════════════════════════════════════════════
  u64 key → 64B value
════════════════════════════════════════════════════════════════════════════════

  10 elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    22 ns │    25 ns │    17 ns │    36 ns │    19 ns │
  │ Seq. Insert    │    13 ns │    19 ns │    16 ns │    31 ns │    17 ns │
  │ Reserved Ins.  │     9 ns │    18 ns │    14 ns │    29 ns │     8 ns │
  │ Update         │     9 ns │     9 ns │     9 ns │    15 ns │     9 ns │
  │ Rand. Lookup   │     4 ns │     7 ns │     4 ns │     5 ns │     7 ns │
  │ High Load      │     4 ns │     6 ns │     4 ns │     4 ns │     7 ns │
  │ Lookup Miss    │     4 ns │     5 ns │     4 ns │     4 ns │     7 ns │
  │ Tombstone      │    10 ns │    13 ns │    11 ns │    12 ns │     9 ns │
  │ Delete         │     5 ns │    12 ns │    10 ns │     6 ns │     7 ns │
  │ Iteration      │     4 ns │     4 ns │     5 ns │     2 ns │     3 ns │
  │ Churn          │    11 ns │    12 ns │    11 ns │    12 ns │    10 ns │
  │ Mixed          │     9 ns │    13 ns │     9 ns │     8 ns │    11 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

  1K elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    22 ns │    17 ns │    27 ns │    20 ns │    19 ns │
  │ Seq. Insert    │    20 ns │    22 ns │    27 ns │    19 ns │    19 ns │
  │ Reserved Ins.  │     6 ns │    17 ns │    29 ns │    18 ns │     6 ns │
  │ Update         │     7 ns │     7 ns │     8 ns │     6 ns │     7 ns │
  │ Rand. Lookup   │     3 ns │     4 ns │     3 ns │     3 ns │     6 ns │
  │ High Load      │     2 ns │     4 ns │     3 ns │     3 ns │     5 ns │
  │ Lookup Miss    │     1 ns │     3 ns │     3 ns │     3 ns │     3 ns │
  │ Tombstone      │     6 ns │     9 ns │     7 ns │     7 ns │     6 ns │
  │ Delete         │     3 ns │     6 ns │     4 ns │     5 ns │     3 ns │
  │ Iteration      │     2 ns │     5 ns │     1 ns │     0 ns │     1 ns │
  │ Churn          │     9 ns │    17 ns │     9 ns │    10 ns │    11 ns │
  │ Mixed          │     6 ns │     9 ns │     8 ns │     6 ns │     7 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

  100K elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │   110 ns │    54 ns │    57 ns │    40 ns │    58 ns │
  │ Seq. Insert    │   107 ns │    63 ns │    59 ns │    27 ns │    58 ns │
  │ Reserved Ins.  │    38 ns │    52 ns │    58 ns │    41 ns │    17 ns │
  │ Update         │    19 ns │    16 ns │    18 ns │    19 ns │    21 ns │
  │ Rand. Lookup   │    12 ns │    14 ns │    13 ns │    23 ns │    13 ns │
  │ High Load      │    13 ns │    13 ns │    14 ns │    22 ns │    14 ns │
  │ Lookup Miss    │     9 ns │     7 ns │     4 ns │     8 ns │    17 ns │
  │ Tombstone      │    21 ns │    24 ns │    16 ns │    28 ns │    27 ns │
  │ Delete         │    10 ns │    20 ns │    12 ns │    19 ns │     9 ns │
  │ Iteration      │     2 ns │     2 ns │     1 ns │     0 ns │     2 ns │
  │ Churn          │    32 ns │    30 ns │    32 ns │    41 ns │    47 ns │
  │ Mixed          │    21 ns │    22 ns │    21 ns │    33 ns │    27 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

╔══════════════════════════════════════════════════════════════════════════════╗
║                    String Keys (Random Length 8-64 chars)                    ║
╚══════════════════════════════════════════════════════════════════════════════╝

════════════════════════════════════════════════════════════════════════════════
  string key → void (set) value
════════════════════════════════════════════════════════════════════════════════

  10 elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    59 ns │    49 ns │    26 ns │    52 ns │    43 ns │
  │ Seq. Insert    │    22 ns │    27 ns │    17 ns │    42 ns │    31 ns │
  │ Reserved Ins.  │    18 ns │    28 ns │    17 ns │    42 ns │    14 ns │
  │ Update         │    18 ns │    41 ns │    35 ns │    43 ns │    17 ns │
  │ Rand. Lookup   │    30 ns │    18 ns │    13 ns │    19 ns │    16 ns │
  │ High Load      │    14 ns │    13 ns │     7 ns │     9 ns │    14 ns │
  │ Lookup Miss    │    47 ns │     9 ns │     8 ns │    10 ns │    11 ns │
  │ Tombstone      │    12 ns │    23 ns │    16 ns │    26 ns │    12 ns │
  │ Delete         │    10 ns │    26 ns │    22 ns │    27 ns │    10 ns │
  │ Iteration      │     4 ns │     4 ns │     5 ns │     2 ns │     4 ns │
  │ Churn          │    14 ns │    22 ns │    20 ns │    25 ns │    15 ns │
  │ Mixed          │    16 ns │    43 ns │    42 ns │    40 ns │    16 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

  1K elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    44 ns │    32 ns │    23 ns │    30 ns │    33 ns │
  │ Seq. Insert    │    40 ns │    32 ns │    23 ns │    28 ns │    33 ns │
  │ Reserved Ins.  │     9 ns │    32 ns │    23 ns │    27 ns │     8 ns │
  │ Update         │     9 ns │    28 ns │    26 ns │    34 ns │    10 ns │
  │ Rand. Lookup   │    26 ns │    15 ns │    11 ns │    13 ns │    15 ns │
  │ High Load      │    16 ns │    16 ns │     9 ns │    11 ns │    16 ns │
  │ Lookup Miss    │     8 ns │     9 ns │     6 ns │     8 ns │    10 ns │
  │ Tombstone      │    10 ns │    25 ns │    17 ns │    28 ns │    11 ns │
  │ Delete         │     9 ns │    31 ns │    27 ns │    34 ns │    11 ns │
  │ Iteration      │     2 ns │     5 ns │     1 ns │     0 ns │     1 ns │
  │ Churn          │    15 ns │    30 ns │    22 ns │    29 ns │    15 ns │
  │ Mixed          │    14 ns │    46 ns │    38 ns │    40 ns │    15 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

  100K elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    79 ns │    41 ns │    34 ns │    52 ns │    52 ns │
  │ Seq. Insert    │    76 ns │    42 ns │    33 ns │    52 ns │    53 ns │
  │ Reserved Ins.  │    33 ns │    41 ns │    33 ns │    52 ns │    23 ns │
  │ Update         │    24 ns │    39 ns │    39 ns │    50 ns │    22 ns │
  │ Rand. Lookup   │    51 ns │    66 ns │    75 ns │    99 ns │    39 ns │
  │ High Load      │    45 ns │    74 ns │    69 ns │    90 ns │    42 ns │
  │ Lookup Miss    │    22 ns │    15 ns │    11 ns │    19 ns │    27 ns │
  │ Tombstone      │    32 ns │    37 ns │    30 ns │    57 ns │    29 ns │
  │ Delete         │    31 ns │    45 ns │    38 ns │    58 ns │    23 ns │
  │ Iteration      │     2 ns │     2 ns │     1 ns │     0 ns │     2 ns │
  │ Churn          │    63 ns │    63 ns │   121 ns │    83 ns │    64 ns │
  │ Mixed          │    67 ns │    85 ns │    90 ns │   109 ns │    80 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

════════════════════════════════════════════════════════════════════════════════
  string key → 4B value
════════════════════════════════════════════════════════════════════════════════

  10 elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    20 ns │    33 ns │    22 ns │    34 ns │    33 ns │
  │ Seq. Insert    │    12 ns │    21 ns │    16 ns │    27 ns │    19 ns │
  │ Reserved Ins.  │    11 ns │    22 ns │    15 ns │    27 ns │     9 ns │
  │ Update         │    11 ns │    29 ns │    28 ns │    25 ns │    10 ns │
  │ Rand. Lookup   │    13 ns │    10 ns │     7 ns │    10 ns │     9 ns │
  │ High Load      │     9 ns │     8 ns │     7 ns │     9 ns │     8 ns │
  │ Lookup Miss    │    10 ns │     9 ns │     8 ns │    10 ns │    11 ns │
  │ Tombstone      │    11 ns │    23 ns │    18 ns │    25 ns │    12 ns │
  │ Delete         │    10 ns │    27 ns │    24 ns │    29 ns │    10 ns │
  │ Iteration      │     4 ns │     4 ns │     4 ns │     2 ns │     3 ns │
  │ Churn          │    14 ns │    22 ns │    20 ns │    22 ns │    15 ns │
  │ Mixed          │    13 ns │    45 ns │    44 ns │    43 ns │    14 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

  1K elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    32 ns │    35 ns │    26 ns │    24 ns │    40 ns │
  │ Seq. Insert    │    30 ns │    34 ns │    26 ns │    23 ns │    35 ns │
  │ Reserved Ins.  │    10 ns │    36 ns │    27 ns │    22 ns │     8 ns │
  │ Update         │    10 ns │    32 ns │    31 ns │    28 ns │    11 ns │
  │ Rand. Lookup   │    23 ns │    16 ns │    14 ns │    31 ns │    14 ns │
  │ High Load      │    26 ns │    23 ns │    20 ns │    25 ns │    23 ns │
  │ Lookup Miss    │    13 ns │    10 ns │     5 ns │     8 ns │    11 ns │
  │ Tombstone      │    12 ns │    26 ns │    19 ns │    26 ns │    12 ns │
  │ Delete         │    10 ns │    34 ns │    29 ns │    67 ns │    13 ns │
  │ Iteration      │     3 ns │     5 ns │     1 ns │     0 ns │     3 ns │
  │ Churn          │    16 ns │    32 ns │    24 ns │    26 ns │    17 ns │
  │ Mixed          │    16 ns │    40 ns │    38 ns │    41 ns │    17 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

  100K elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    84 ns │    50 ns │    37 ns │    48 ns │    58 ns │
  │ Seq. Insert    │    87 ns │    48 ns │    34 ns │    49 ns │    57 ns │
  │ Reserved Ins.  │    36 ns │    49 ns │    38 ns │    48 ns │    23 ns │
  │ Update         │    28 ns │    43 ns │    41 ns │    45 ns │    24 ns │
  │ Rand. Lookup   │    56 ns │    79 ns │    81 ns │    97 ns │    45 ns │
  │ High Load      │    55 ns │    81 ns │    73 ns │    96 ns │    46 ns │
  │ Lookup Miss    │    24 ns │    15 ns │    11 ns │    18 ns │    28 ns │
  │ Tombstone      │    37 ns │    38 ns │    32 ns │    54 ns │    30 ns │
  │ Delete         │    27 ns │    45 ns │    41 ns │    58 ns │    22 ns │
  │ Iteration      │     2 ns │     2 ns │     1 ns │     0 ns │     2 ns │
  │ Churn          │    71 ns │    90 ns │   112 ns │    77 ns │    62 ns │
  │ Mixed          │    98 ns │   138 ns │   148 ns │   140 ns │    61 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

════════════════════════════════════════════════════════════════════════════════
  string key → 64B value
════════════════════════════════════════════════════════════════════════════════

  10 elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    58 ns │    69 ns │    44 ns │    60 ns │    49 ns │
  │ Seq. Insert    │    31 ns │    40 ns │   195 ns │    51 ns │    38 ns │
  │ Reserved Ins.  │    18 ns │    35 ns │    23 ns │    49 ns │    14 ns │
  │ Update         │    24 ns │    43 ns │    45 ns │    42 ns │    22 ns │
  │ Rand. Lookup   │    39 ns │    18 ns │    16 ns │    17 ns │    14 ns │
  │ High Load      │    15 ns │    14 ns │    10 ns │    15 ns │    13 ns │
  │ Lookup Miss    │    24 ns │    14 ns │    15 ns │    15 ns │    16 ns │
  │ Tombstone      │    19 ns │    31 ns │    24 ns │    37 ns │    19 ns │
  │ Delete         │    16 ns │    37 ns │    32 ns │    42 ns │    15 ns │
  │ Iteration      │     4 ns │     6 ns │     6 ns │     2 ns │     4 ns │
  │ Churn          │    20 ns │    30 ns │    28 ns │    33 ns │    22 ns │
  │ Mixed          │    19 ns │    63 ns │    57 ns │    63 ns │    21 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

  1K elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │    58 ns │    41 ns │    31 ns │    26 ns │    42 ns │
  │ Seq. Insert    │    42 ns │    51 ns │    37 ns │    32 ns │    51 ns │
  │ Reserved Ins.  │    14 ns │    40 ns │    34 ns │    28 ns │    10 ns │
  │ Update         │    17 ns │    38 ns │    33 ns │    30 ns │    17 ns │
  │ Rand. Lookup   │    29 ns │    20 ns │    11 ns │    18 ns │    20 ns │
  │ High Load      │    21 ns │    20 ns │    11 ns │    15 ns │    18 ns │
  │ Lookup Miss    │     9 ns │    10 ns │     5 ns │     7 ns │    10 ns │
  │ Tombstone      │    13 ns │    28 ns │    23 ns │    28 ns │    15 ns │
  │ Delete         │    15 ns │    35 ns │    30 ns │    38 ns │    13 ns │
  │ Iteration      │     2 ns │     5 ns │     1 ns │     0 ns │     1 ns │
  │ Churn          │    20 ns │    34 ns │    26 ns │    30 ns │    18 ns │
  │ Mixed          │    18 ns │    50 ns │    45 ns │    45 ns │    18 ns │
  └────────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘

  100K elements:
  ┌────────────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
  │ Operation      │ This     │ Abseil   │ Boost    │ Ankerl   │ std      │
  ├────────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤
  │ Rand. Insert   │   166 ns │    95 ns │    75 ns │    70 ns │   123 ns │
  │ Seq. Insert    │   264 ns │    91 ns │   124 ns │    65 ns │   129 ns │
  │ Reserved Ins.  │    47 ns │   110 ns │    93 ns │    59 ns │    31 ns │
  │ Update         │    68 ns │    70 ns │    81 ns │    49 ns │    56 ns │
  │ Rand. Lookup   │    87 ns │   193 ns │   223 ns │   200 ns │    64 ns │
  │ High Load      │    77 ns │   162 ns │   156 ns │   184 ns │    66 ns │
  │ Lookup Miss    │    27 ns │    22 ns │    16 ns │    20 ns │    29 ns │
  │ Tombstone      │    58 ns │    64 ns │    66 ns │    58 ns │    45 ns │
  │ Delete         │    36 ns │    73 ns │    75 ns │    61 ns │    23 ns │
  │ Iteration      │     2 ns │     1 ns │     1 ns │     0 ns │     2 ns │
  │ Churn          │   106 ns │   105 ns │   109 ns │   110 ns │   100 ns │
  │ Mixed          │    93 ns │   163 ns │   153 ns │   183 ns │    87 ns │
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
