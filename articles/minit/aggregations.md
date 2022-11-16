---
title: Aggregations (preview)
description: Learn the aggregations you can use in custom metrics in the Minit desktop application for Microsoft Power Automate process advisor
author: maslejka
contributors:
  - maslejka
  - v-aangie
ms.subservice: process-advisor
ms.topic: conceptual
ms.date: 11/15/2022
ms.author: mmaslejova
ms.reviewer: angieandrews
ms.custom: bap-template
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
---

# Aggregations (preview)

[!INCLUDE[cc-beta-prerelease-disclaimer](../includes/cc-beta-prerelease-disclaimer.md)]

This article describes the aggregations you can use in custom metrics

## AVG([context],[value])

Calculates the average of values grouped according to the [context]

- **[context]**: The context in which the operation is calculated

- **[value]**: An attribute name, nested operation, or expression

   Data type: INT, FLOAT, DATE, TIME

**Output data type**: FLOAT, DATE, TIME

## AVGIF([context],[condition],[value])

Calculates the average of values that meet the [condition], grouped according to the [context]

- **[context]**: The context in which the operation is calculated (supported: process, case, event, edge)

- **[condition]**: The condition under which the [value] is included in the calculation

   Data type: BOOL

- **[value]**: An attribute name, nested operation, or expression

   Data type: INT, FLOAT, DATE, TIME

**Output data type**: INT, FLOAT, DATE, TIME

**Example**: `AVGIF(ViewEvents, userName == "Laura", eventCost)`

Can be used anywhere a custom metric can be used Returns the average event cost for events associated with the user "Laura"

## COUNT([context])

Counts the number of values grouped according to the [context]

- **[context]**: The context in which the operation is calculated

**Output data type**: INT

## COUNTIF([context],[condition])

Counts the number of values fulfilling the [condition], grouped according to the [context]

- **[context]**: The context in which the operation is calculated

- **[condition]**: The condition under which the [value] is included in the calculation

   Data type: BOOL

**Output data type**: INT

## COUNTUNIQUE([context],[value])

Counts the number of unique values, grouped according to the [context]

- **[context]**: The context in which the operation is calculated

- **[value]**: An attribute name, nested operation, or expression

   Data type: INT, FLOAT, BOOL, STRING, DATE, TIME

**Output data type**: INT

## COUNTUNIQUEIF([context],[condition],[value])

Counts the number of unique [value] that meet the [condition], grouped according to the [context]

- **[context]**: The context in which the operation is calculated

- **[condition]**: The condition under which the [value] is included in the calculation

   Data type: BOOL

- **[value]**: An attribute name, nested operation, or expression

   Data type: INT, FLOAT, TIME

**Output data type**: FLOAT, TIME

## MAX([context],[value])

Returns the maximum of [value], grouped according to the [context]

- **[context]**: The context in which the operation is calculated

- **[value]**: An attribute name, nested operation, or expression

   Data type: INT, FLOAT, DATE, TIME

**Output data type**: INT, FLOAT, DATE, TIME

## MAXIF([context],[condition],[value])

Returns the maximum of [values] that meet the [condition], grouped according to the [context]

- **[context]**: The context in which the operation is calculated

- **[condition]**: The condition under which the [value] is included in the calculation

   Data type: BOOL

- **[value]**: An attribute name, nested operation, or expression

   Data type: INT, FLOAT, TIME

**Output data type**: FLOAT, TIME

## MAXVAL([context],[value1],[value2])

Selects item with maximum value from [value1] and returns its calculated value defined by [value2], grouped according to the [context]

- **[context]**: The context in which the operation is calculated (supported: process, case, event, edge)

- **[value1]**: An attribute name, nested operation, or expression

   Data type: INT, FLOAT, TIME, DATE

- **[value2]**: An attribute name, nested operation, or expression

   Data type: INT, FLOAT, STRING, TIME, DATE

**Output data type**: INT, FLOAT, STRING, TIME, DATE

**Example**: `MAXVAL(EventsPerAttribute, Duration(), userName)`

Can be used on the process map Returns the username of a user who worked on the longest event per activity

## MAXVALIF([context],[condition],[value1],[value2])

Selects item with the maximum value defined by [value1] that meets the [condition] and returns its calculated value defined by [value2], grouped according to the [context]

- **[context]**: The context in which the operation is calculated (supported: process, case, event, edge)

- **[condition]**: The condition under which the [value1] is included in the calculation

   Data type: BOOL

- **[value1]**: An attribute name, nested operation, or expression

   Data type: INT, FLOAT, DATE, TIME

- **[value2]**: An attribute name, nested operation, or expression

   Data type: INT, FLOAT, STRING, TIME, DATE

**Output data type**: INT, FLOAT, STRING, TIME, DATE

## MIN([context],[value])

Returns the minimum of [value], grouped according to the [context]

- **[context]**: The context in which the operation is calculated

- **[value]**: An attribute name, nested operation, or expression

   Data type: INT, FLOAT, DATE, TIME

**Output data type**: INT, FLOAT, DATE, TIME

## MINIF([context],[condition],[value])

Returns the minimum of [value] that meets the [condition], grouped according to the [context]

- **[context]**: The context in which the operation is calculated

- **[condition]**: The condition under which the [value] is included in the calculation

   Data type: BOOL

- **[value]**: An attribute name, nested operation, or expression

   Data type: INT, FLOAT, TIME

**Output data type**: FLOAT, TIME

## MINVAL([context],[value1],[value2])

Selects item with the minimum value defined by [value1] and returns its calculated value defined by [value2], grouped according to the [context]

- **[context]**: The context in which the operation is calculated (supported: process, case, event, edge)

- **[value1]**: An attribute name, nested operation, or expression

   Data type: INT, FLOAT, DATE, TIME

- **[value2]**: An attribute name, nested operation, or expression

   Data type: INT, FLOAT, STRING, TIME, DATE

**Output data type**: INT, FLOAT, STRING, TIME, DATE

## MINVALIF([context],[condition],[value1],[value2])

Selects item with the minimum value defined by [value1] that meets the [condition] and returns its calculated value defined by [value2], grouped according to the [context]

- **[context]**: The context in which the operation is calculated (supported: process, case, event, edge)

- **[condition]**: The condition under which the [value1] is included in the calculation

   Data type: BOOL

- **[value1]**: An attribute name, nested operation, or expression

   Data type: INT, FLOAT, DATE, TIME

- **[value2]**: An attribute name, nested operation, or expression

   Data type: INT, FLOAT, STRING, TIME, DATE

**Output data type**: INT, FLOAT, STRING, TIME, DATE

## RANGE([context],[value])

Returns the range (maximum-minimum) of [value], grouped according to the [context]

- **[context]**: Defines the context in which the operation is calculated

- **[value]**: An attribute name, nested operation, or expression

   Data type: INT, FLOAT, DATE, TIME

**Output data type**: INT, FLOAT, TIME

## RANGEIF([context],[condition],[value])

Returns the range (maximum-minimum) of [value] that meets the [condition], grouped according to the [context]

- **[context]**: The context in which the operation is calculated

- **[condition]**: The condition under which the [value] is included in the calculation

   Data type: BOOL

- [value] - An attribute name, nested operation, or expression

   Data type: INT, FLOAT, TIME

**Output data type**: FLOAT, TIME

## STDEV([context],[value])

Calculates the standard deviation of [value], grouped according to the [context]

- **[context]**: The context in which the operation is calculated

- **[value]**: An attribute name, nested operation, or expression

   Data type: INT, FLOAT, DATE, TIME

**Output data type**: FLOAT, TIME

## STDEVIF([context],[condition],[value])

Calculates the standard deviation of [value] that meets the [condition], grouped according to the [context]

- **[context]**: The context in which the operation is calculated

- **[condition]**: The condition under which the [value] is included in the calculation

   Data type: BOOL

- **[value]**: An attribute name, nested operation, or expression

   Data type: INT, FLOAT, TIME

**Output data type**: FLOAT, TIME

## SUM([context],[value])

Calculates the sum of [value], grouped according to the [context]

- **[context]**: The context in which the operation is calculated

- **[value]**: An attribute name, nested operation, or expression

   Data type: INT, FLOAT, TIME

**Output data type**: FLOAT, TIME

## SUMIF([context],[condition],[value])

Calculates the sum of [value] that meets the [condition], grouped according to the [context]

- **[context]**: The context in which the operation is calculated

- **[condition]**: The condition under which the [value] is included in the calculation

   Data type: BOOL

- **[value]**: An attribute name, nested operation, or expression

   Data type: INT, FLOAT, TIME

**Output data type**: FLOAT, TIME

## FIRST([context],[value])

Returns the first [value], grouped according to the [context]

- **[context]**: The context in which the operation is calculated

- **[value]**: An attribute name, nested operation, or expression

   Data type: INT, FLOAT, TIME

**Output data type**: FLOAT, TIME

## FIRSTIF([context],[condition],[value])

Returns the first [value] that meets the [condition], grouped according to the [context]

- **[context]**: The context in which the operation is calculated

- **[condition]**: The condition under which the [value] is included in the calculation

   Data type: BOOL

- **[value]**: An attribute name, nested operation, or expression

   Data type: INT, FLOAT, TIME

**Output data type**: FLOAT, TIME

## LAST([context],[value])

Returns the last [value], grouped according to the [context]

- **[context]**: The context in which the operation is calculated

- **[value]**: An attribute name, nested operation, or expression

   Data type: INT, FLOAT, TIME

**Output data type**: FLOAT, TIME

## LASTIF([context],[condition],[value])

Returns the last value that meets the [condition], grouped according to the [context]

- **[context]**: The context in which the operation is calculated

- **[condition]**: The condition under which the [value] is included in the calculation

   Data type: BOOL

- **[value]**: An attribute name, nested operation, or expression

   Data type: INT, FLOAT, TIME

**Output data type**: FLOAT, TIME

## SELFLOOP([context],[attributeName])

Calculates a count of self-loop events, grouped according to the [context]; short version of COUNTIF(ISSELFLOOP()) expression

- **[context]**: The context in which the operation is calculated

- **[attributeName]**: An attribute name; if no attribute is defined, the current activity (mining) attribute is used

   Data type: STRING

**Output data type**: INT

## LOOP([context],[attributeName])

Calculates a count of loop events, grouped according to the [context]; short version of COUNTIF(ISLOOP()) expression

- **[context]**: The context in which the operation is calculated

- **[attributeName]**: An attribute name; if no attribute is defined, the current activity (mining) attribute is used

   Data type: STRING

**Output data type**: INT

## REWORK([context],[attributeName])

Calculates a count of rework events, grouped according to the [context]; short version of COUNTIF(ISREWORK()) expression

- **[context]**: The context in which the operation is calculated

- **[attributeName]**: An attribute name; if no attribute is defined, the current activity (mining) attribute is used

   Data type: STRING

**Output data type**: INT

## LOOPINFLOW([context],[attributeName])

Calculates a count of loop inflows, grouped according to the [context]; short version of COUNTIF(ISLOOPINFLOW()) expression

- **[context]**: The context in which the operation is calculated

- **[attributeName]**: An attribute name; if no attribute is defined, the current activity (mining) attribute is used

   Data type: STRING

**Output data type**: INT

## LOOPOUTFLOW([context],[attributeName])

Calculates a count of loop outflows, grouped according to the [context]; short version of COUNTIF(ISLOOPOUTFLOW()) expression

- **[context]**: The context in which the operation is calculated

- **[attributeName]**: An attribute name; if no attribute is defined, the current activity (mining) attribute is used

   Data type: STRING

**Output data type**: INT

## NETLOOPGAIN([context],[attributeName])

Calculates the sum of loop gains, grouped according to the [context]; short version of SUM(LOOPGAIN()) expression

- **[context]**: The context in which the operation is calculated

- **[attributeName]**: An attribute name; if no attribute is defined, the current activity (mining) attribute is used

   Data type: STRING

**Output data type**: INT

## MODE([context],[value])

Returns the most common [value] from [context]

- **[context]**: The context in which the operation is calculated

- **[value]**: An attribute name, nested operation, or expression

   Data type: STRING, INT, FLOAT, DATE, TIME, BOOL

**Output data type**: STRING, INT, FLOAT, DATE, TIME, BOOL

## MODEIF([context],[condition],[value])

Returns the most common [value] from data elements that meet the [condition] in the [context]

- **[context]**: The context in which the operation is calculated

- **[condition]**: The condition under which the [value] is included in the calculation

- **[value]**: An attribute name, nested operation, or expression

   Data type: STRING, INT, FLOAT, DATE, TIME, BOOL

**Output data type**: STRING, INT, FLOAT, DATE, TIME, BOOL

## ALL([context],[condition])

Returns true if all values, grouped according to the [context], meet the [condition]

- **[context]**: The context in which the operation is calculated (supported: process, case, event, edge)

- **[condition]**: The condition under which the [value] is included in the calculation

   Data type: BOOL

**Output data type**: BOOL

**Example** `ALL(CaseEvents, eventCost > 0)`

Can be used on case metrics filters or case overview statistics. Returns true if all events in the case have an event cost greater than zero.

## ANY([context],[condition])

Returns true if any of the values, grouped according to the [context], meet the [condition]

- **[context]**: The context in which the operation is calculated (supported: case [implicit])

- **[condition]**: The condition under which the [value] is included in the calculation

   Data type: BOOL

**Output data type**: BOOL

**Example**: `ANY(CaseEvents, eventCost > 0)`

Can be used on case metrics filters or case overview statistics. Returns true if any event in the case has an event cost greater than zero.

### See also

For a list of all calculation contexts for aggregation operations, go to [Calculation context](calculation-context.md)