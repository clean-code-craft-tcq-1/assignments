# Recap: Statistics with Unit Tests

## Compliments

[Thoughtful test - no alert when things are ok](https://github.com/clean-code-craft-tcq-1/start-stats-c-VishalSubban/blob/master/stats-test.cpp)

[Names with comments in .c implementation](https://github.com/clean-code-craft-tcq-1/start-stats-c-NaveenBalachandar-dev/blob/master/stats.c)

> Notice that the test names are like statements of behavior.

## Watch out

### Array as Parameter - its size is global

```c
int emailAlertCallCount = 0;
int ledAlertCallCount = 0;
int sizeofalertbuffer = 0;

void check_and_alert(float maxThreshold,
                     alerter_funcptr alerters[], struct Stats computedStats)
{
	for (int loop_counter = 0; loop_counter < sizeofalertbuffer; loop_counter++)
	{
		if (computedStats.max > maxThreshold)
		{
			alerters[loop_counter]();
		}
	}
}
```

### Test to pass the code that returns 'not nan'

```c
TEST_CASE("average is NaN for empty array") {
    float numberset[] = {1.5, 8.9, 3.2, 4.5};
    int setlength = sizeof(numberset) / sizeof(numberset[0]);
    struct Stats computedStats = compute_statistics(numberset, setlength);    
    REQUIRE(isnan(computedStats.average) == 0);
    REQUIRE(isnan(computedStats.min) == 0);
    REQUIRE(isnan(computedStats.max) == 0);
}
```

### Empty array in C - how

```c
TEST_CASE("average is NaN for empty array") {
    int setlength = 0;
    float numberset[] = {1.5, 8.9, 3.2, 4.5};
    stats_s computedStats;
    computedStats = compute_statistics(numberset, setlength);
    
    REQUIRE(isnan(computedStats.average) == TRUE);
}
```

## Imagine a Real-world Use of this Code

> Can the input contain NaN? How about a test for that?

- Think of a telemetry problem, where you need maximum, minimum, average
- What does an empty array mean?
- What does nan mean?
- What tests do we miss?