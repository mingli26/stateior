This document presents validation results of 2017 summary-level state IO
model.

### Prepare data

#### 0\. Load state and two-region IO data.

State and two-region IO data successfully loaded.

### Check state IO tables

#### 1\. Check if industry output from state Make and Use are almost equal (\<= 0.01).

There are no failures.

### Compare state to US IO tables (negativity in the same cell & state sum == US totals)

#### 2\. Sum of each cell across all state Make tables must almost equal (\<= 0.001) the same cell in US Make table.

There are no failures.

#### 3\. There should not be any negative values in state Make table, unless they are negative in US Make table.

Note: only exception being Overseas, which isn’t used for further
calculations, and if the same cell in US Make table is also negative.
There are no failures.

#### 4\. Sum of each industry’s output across all states must almost equal (\<= 1E7, or $10 million by industry) the industry output in US Make Table.

The threshold is set to 1E7 because there are differences (within +/-
$10 million) between US industry output summed from Make and that summed
from Use, comparing sum of state industry output (summed from state Use)
to US industry output summed from US Make should account for those
inherent differences at the national level. There are no failures.

#### 5\. Sum of each commodity’s output across all states must almost equal (\<= 1E7, or $10 million by commodity) the commodity output in US Make Table.

The threshold is set to 1E7 because there are differences (within +/-
$10 million) between US industry output summed from Make and that summed
from Use, comparing sum of state industry output (summed from state Use)
to US industry output summed from US Make should account for those
inherent differences at the national level. There are no failures.

#### 6\. Sum of each commodity’s output across all states must almost equal (\<= 1E^7, or $10 million by commodity) commodity output in US Use Table.

Note: even if the threshold is met, track the difference for each
commodity. Save result as a type of quality control check.

There are no failures.

|        | q\_state\_sum - q\_US\_use |
| ------ | -------------------------: |
| 111CA  |                \-2.000e+06 |
| 113FF  |                  2.000e+06 |
| 211    |                \-3.000e+06 |
| 212    |                \-1.000e+06 |
| 213    |                  1.530e-05 |
| 22     |                \-1.000e+06 |
| 23     |                  3.000e+06 |
| 321    |                  1.530e-05 |
| 327    |                \-1.000e+06 |
| 331    |                  6.000e+06 |
| 332    |                \-1.000e+06 |
| 333    |                \-2.000e+06 |
| 334    |                  3.000e+06 |
| 335    |                  3.050e-05 |
| 3361MV |                \-2.000e+06 |
| 3364OT |                \-3.000e+06 |
| 337    |                \-1.000e+06 |
| 339    |                  2.000e+06 |
| 311FT  |                  2.000e+06 |
| 313TT  |                \-7.600e-06 |
| 315AL  |                \-1.000e+06 |
| 322    |                \-7.000e+06 |
| 323    |                  6.000e+06 |
| 324    |                \-1.000e+06 |
| 325    |                \-2.000e+06 |
| 326    |                \-3.000e+06 |
| 42     |                \-2.000e+06 |
| 441    |                  2.000e+06 |
| 445    |                  1.000e+06 |
| 452    |                  1.000e+06 |
| 4A0    |                \-1.221e-04 |
| 481    |                \-4.000e+06 |
| 482    |                  0.000e+00 |
| 483    |                  3.000e+06 |
| 484    |                  4.000e+06 |
| 485    |                  3.000e+06 |
| 486    |                  5.000e+06 |
| 487OS  |                \-5.000e+06 |
| 493    |                \-4.000e+06 |
| 511    |                  3.000e+06 |
| 512    |                  1.000e+06 |
| 513    |                  0.000e+00 |
| 514    |                \-1.000e+06 |
| 521CI  |                  1.000e+06 |
| 523    |                  2.000e+06 |
| 524    |                \-4.000e+06 |
| 525    |                  0.000e+00 |
| HS     |                  2.441e-04 |
| ORE    |                  0.000e+00 |
| 532RL  |                \-1.000e+06 |
| 5411   |                  4.000e+06 |
| 5415   |                  1.000e+06 |
| 5412OP |                  7.000e+06 |
| 55     |                  1.000e+06 |
| 561    |                \-5.000e+06 |
| 562    |                  1.530e-05 |
| 61     |                  1.000e+06 |
| 621    |                  3.000e+06 |
| 622    |                  2.441e-04 |
| 623    |                  3.050e-05 |
| 624    |                  0.000e+00 |
| 711AS  |                  2.000e+06 |
| 713    |                  1.000e+06 |
| 721    |                  4.000e+06 |
| 722    |                \-1.000e+06 |
| 81     |                \-4.000e+06 |
| GFGD   |                \-1.221e-04 |
| GFGN   |                  0.000e+00 |
| GFE    |                \-1.000e+06 |
| GSLG   |                \-2.441e-04 |
| GSLE   |                \-3.050e-05 |
| Used   |                  2.000e+06 |
| Other  |                \-5.000e+06 |

#### 7\. All cells that are zero in US Make table must remain zero in state Make tables. Find zero values in US Make table.

There are no failures.

#### 8\. Sum of each cell across all state Use tables must almost equal (\<= 5E6, or $5 million) the same cell in US Use table. This validates that Total state demand == Total national demand.

Note: failures associated with ‘F050 - Imports’ are acceptable. Because
state imports are not directly derived from US imports, a gap in imports
between state sum and national total is reasonable.

##### 8.1 State Use tables (checking absolute differences)

There is 1 failure, and it is

| Commodity | Industry/Final Demand | Absolute Diff | Validation               | AbsDiffPortioninNationalTotals |
| :-------- | :-------------------- | ------------: | :----------------------- | -----------------------------: |
| 562       | F050                  |         6e+06 | abs(result) \< tolerance |                     \-0.025641 |

##### 8.2 State Domestic Use tables (checking absolute differences)

There are no failures.

##### 8.3 State Use tables (checking relative differences)

There are 11 failures, and they are

| Commodity | Industry/Final Demand | Relative Diff | Validation               |          US |     StateSum |
| :-------- | :-------------------- | ------------: | :----------------------- | ----------: | -----------: |
| 212       | F050                  |         0.002 | abs(result) \< tolerance |   4.380e+08 |    438935544 |
| 487OS     | F050                  |         0.001 | abs(result) \< tolerance |   3.293e+09 |   3296933173 |
| 513       | F050                  |       \-0.025 | abs(result) \< tolerance | \-1.590e+08 |  \-155000000 |
| 514       | F050                  |       \-0.003 | abs(result) \< tolerance | \-1.253e+09 | \-1249000000 |
| 521CI     | F050                  |       \-0.022 | abs(result) \< tolerance | \-4.500e+07 |   \-44000000 |
| 523       | F050                  |       \-0.053 | abs(result) \< tolerance | \-5.700e+07 |   \-54000000 |
| 5411      | F050                  |         0.001 | abs(result) \< tolerance | \-3.861e+09 | \-3865000000 |
| 561       | F050                  |       \-0.001 | abs(result) \< tolerance | \-1.938e+09 | \-1936000000 |
| 562       | F050                  |       \-0.026 | abs(result) \< tolerance | \-2.340e+08 |  \-228000000 |
| 711AS     | F050                  |       \-0.002 | abs(result) \< tolerance | \-1.325e+09 | \-1322000000 |
| GFE       | F050                  |       \-0.010 | abs(result) \< tolerance | \-2.890e+08 |  \-286000000 |

##### 8.4 State Domestic Use tables (checking relative differences)

There are 3 failures, and they are

| Commodity | Industry/Final Demand | Relative Diff | Validation               |        US | StateSum |
| :-------- | :-------------------- | ------------: | :----------------------- | --------: | -------: |
| 211       | 326                   |       \-1.000 | abs(result) \< tolerance | \-1000000 |        0 |
| 211       | 711AS                 |       \-1.000 | abs(result) \< tolerance | \-3000000 |        0 |
| Other     | F051                  |       \-0.001 | abs(result) \< tolerance |  27000000 | 26959917 |

### Check two-region model results

#### 9\. Check if commodity output from two-region Make and Domestic Use are almost equal (relative difference \<= 0.01).

There are no failures.

#### 10\. If SoI commodity output == 0, SoI2SoI ICF ratio == 0

There are no failures.

#### 11\. SoI and RoUS interregional exports \>= 0, interregional imports \>= 0

There are no failures.

#### 12\. SoI net exports + RoUS net exports == 0

There are no failures.

#### 13\. Check row sum of SoI2SoI \<= state commodity supply. Row sum of RoUS2RoUS \<= RoUS commodity supply.

There are no failures.

#### 14\. Value in SoI2SoI and RoUS2RoUS can be negative only when the same cell is negative in national Use table

There are no failures.

#### 15\. SoI interregional imports == RoUS interregional exports, or difference \<= 0.001

There are no failures.

#### 16.1. Total state commodity supply == state demand by intermediate consumption, plus final demand (except imports and international trade adjustment) + Interregional Exports + Export Residual. Difference must be \<= 0.001.

There are no failures.

#### 16.2. Total SoI and RoUS commodity supply (output) == SoI and RoUS demand (domestic intermediate consumption + ITA + Export Residual).

There are no failures.

#### 17\. Number of negative cells in SoI2SoI, SoI2RoUS, RoUS2SoI and RoUS2RoUS \<= Number of negative cells in national Use table

There are no failures.

#### 18\. Non-square model verification. Validate L matrix of two-region model and final demand against SoI and RoUS output.

##### Absolute difference: L\*y - output \<= 1^6, or $1 million.

##### Relative difference: (L\*y - output)/output \<= 1^-2, or 1%.

##### 18.1 Alabama and Rest of the US

Absolute Difference: There are no failures.

Relative Difference: There are no failures.

##### 18.2 Alaska and Rest of the US

Absolute Difference: There are no failures.

Relative Difference: There are no failures.

##### 18.3 Arizona and Rest of the US

Absolute Difference: There are no failures.

Relative Difference: There are no failures.

##### 18.4 Arkansas and Rest of the US

Absolute Difference: There are no failures.

Relative Difference: There are no failures.

##### 18.5 California and Rest of the US

Absolute Difference: There are 6 failures, and they are

|     | rownames                   |    result | check       |
| --- | :------------------------- | --------: | :---------- |
| 148 | California.113FF.Industry  | \-1390804 | L\*y-output |
| 189 | California.514.Industry    |   1735135 | L\*y-output |
| 199 | California.5412OP.Industry |   1149664 | L\*y-output |
| 219 | RoUS.113FF.Industry        |   1367734 | L\*y-output |
| 260 | RoUS.514.Industry          | \-1727663 | L\*y-output |
| 270 | RoUS.5412OP.Industry       | \-1151038 | L\*y-output |

Relative Difference: There are no failures.

##### 18.6 Colorado and Rest of the US

Absolute Difference: There are no failures.

Relative Difference: There are no failures.

##### 18.7 Connecticut and Rest of the US

Absolute Difference: There are no failures.

Relative Difference: There are no failures.

##### 18.8 Delaware and Rest of the US

Absolute Difference: There are no failures.

Relative Difference: There are no failures.

##### 18.10 Florida and Rest of the US

Absolute Difference: There are no failures.

Relative Difference: There are no failures.

##### 18.11 Georgia and Rest of the US

Absolute Difference: There are 2 failures, and they are

|     | rownames               |    result | check       |
| --- | :--------------------- | --------: | :---------- |
| 166 | Georgia.313TT.Industry |   1372866 | L\*y-output |
| 237 | RoUS.313TT.Industry    | \-1357661 | L\*y-output |

Relative Difference: There are no failures.

##### 18.12 Hawaii and Rest of the US

Absolute Difference: There are no failures.

Relative Difference: There are no failures.

##### 18.13 Idaho and Rest of the US

Absolute Difference: There are no failures.

Relative Difference: There are no failures.

##### 18.14 Illinois and Rest of the US

Absolute Difference: There are no failures.

Relative Difference: There are no failures.

##### 18.15 Indiana and Rest of the US

Absolute Difference: There are no failures.

Relative Difference: There are no failures.

##### 18.16 Iowa and Rest of the US

Absolute Difference: There are no failures.

Relative Difference: There are no failures.

##### 18.17 Kansas and Rest of the US

Absolute Difference: There are no failures.

Relative Difference: There are no failures.

##### 18.18 Kentucky and Rest of the US

Absolute Difference: There are no failures.

Relative Difference: There are no failures.

##### 18.19 Louisiana and Rest of the US

Absolute Difference: There are no failures.

Relative Difference: There are no failures.

##### 18.20 Maine and Rest of the US

Absolute Difference: There are no failures.

Relative Difference: There are no failures.

##### 18.21 Maryland and Rest of the US

Absolute Difference: There are no failures.

Relative Difference: There are no failures.

##### 18.22 Massachusetts and Rest of the US

Absolute Difference: There are no failures.

Relative Difference: There are no failures.

##### 18.23 Michigan and Rest of the US

Absolute Difference: There are no failures.

Relative Difference: There are no failures.

##### 18.24 Minnesota and Rest of the US

Absolute Difference: There are no failures.

Relative Difference: There are no failures.

##### 18.25 Mississippi and Rest of the US

Absolute Difference: There are no failures.

Relative Difference: There are no failures.

##### 18.26 Missouri and Rest of the US

Absolute Difference: There are no failures.

Relative Difference: There are no failures.

##### 18.27 Montana and Rest of the US

Absolute Difference: There are no failures.

Relative Difference: There are no failures.

##### 18.28 Nebraska and Rest of the US

Absolute Difference: There are no failures.

Relative Difference: There are no failures.

##### 18.29 Nevada and Rest of the US

Absolute Difference: There are no failures.

Relative Difference: There are no failures.

##### 18.30 New Hampshire and Rest of the US

Absolute Difference: There are no failures.

Relative Difference: There are no failures.

##### 18.31 New Jersey and Rest of the US

Absolute Difference: There are no failures.

Relative Difference: There are no failures.

##### 18.32 New Mexico and Rest of the US

Absolute Difference: There are no failures.

Relative Difference: There are no failures.

##### 18.33 New York and Rest of the US

Absolute Difference: There are no failures.

Relative Difference: There are no failures.

##### 18.34 North Carolina and Rest of the US

Absolute Difference: There are no failures.

Relative Difference: There are no failures.

##### 18.35 North Dakota and Rest of the US

Absolute Difference: There are no failures.

Relative Difference: There are no failures.

##### 18.36 Ohio and Rest of the US

Absolute Difference: There are no failures.

Relative Difference: There are no failures.

##### 18.37 Oklahoma and Rest of the US

Absolute Difference: There are no failures.

Relative Difference: There are no failures.

##### 18.38 Oregon and Rest of the US

Absolute Difference: There are no failures.

Relative Difference: There are no failures.

##### 18.40 Pennsylvania and Rest of the US

Absolute Difference: There are no failures.

Relative Difference: There are no failures.

##### 18.41 Rhode Island and Rest of the US

Absolute Difference: There are no failures.

Relative Difference: There are no failures.

##### 18.42 South Carolina and Rest of the US

Absolute Difference: There are no failures.

Relative Difference: There are no failures.

##### 18.43 South Dakota and Rest of the US

Absolute Difference: There are no failures.

Relative Difference: There are no failures.

##### 18.44 Tennessee and Rest of the US

Absolute Difference: There are no failures.

Relative Difference: There are no failures.

##### 18.45 Texas and Rest of the US

Absolute Difference: There are 4 failures, and they are

|     | rownames           |    result | check       |
| --- | :----------------- | --------: | :---------- |
| 149 | Texas.211.Industry |   2885645 | L\*y-output |
| 183 | Texas.486.Industry | \-1002642 | L\*y-output |
| 220 | RoUS.211.Industry  | \-2889116 | L\*y-output |
| 254 | RoUS.486.Industry  |   1004157 | L\*y-output |

Relative Difference: There are no failures.

##### 18.46 Utah and Rest of the US

Absolute Difference: There are no failures.

Relative Difference: There are no failures.

##### 18.47 Vermont and Rest of the US

Absolute Difference: There are no failures.

Relative Difference: There are no failures.

##### 18.48 Virginia and Rest of the US

Absolute Difference: There are no failures.

Relative Difference: There are no failures.

##### 18.49 Washington and Rest of the US

Absolute Difference: There are no failures.

Relative Difference: There are no failures.

##### 18.50 West Virginia and Rest of the US

Absolute Difference: There are no failures.

Relative Difference: There are no failures.

##### 18.51 Wisconsin and Rest of the US

Absolute Difference: There are no failures.

Relative Difference: There are no failures.

##### 18.52 Wyoming and Rest of the US

Absolute Difference: There are no failures.

Relative Difference: There are no failures.
