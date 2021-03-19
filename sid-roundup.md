# SolID roundup

## Encapsulation pitfalls

The issue of state - global or static

```python
  global ALERTS

def printErrorMessages(ALERTS):
    for error in ALERTS:
        error_type = error['status']
        print ( error_messages[error_type][LANGUAGE] + error['criteria'] )
            
    if ALERTS.__len__ != 0:
        ALERTS.clear()
```

### Un-intentional coupling

Watch out for these design decisions.
_They sound like encapsulation, but they may be traps!_

**Sample Design#1**: Everything related to temperature in a class - input, check, print, control

**Sample Design#2**: Everything related to data in a class - collect all parameters _like a database_

## Single Responsibility

Checkpoints:

- One reason for change
- One level of abstraction

## Interface Segregation

Interface says `Check`. But it restricts the check to a range:
```c++
virtual void BatteryParametersCheck(
  string parameterStatus1, string parameterStatus2, 
  double actualValue,
  double minValue, double MaxVAlue) = 0;
```

Suggesting the implementation in the interface:
```c++
{
protected:
  std::string accumulator_str;
public:
  virtual void accumulator(std::string) = 0;
  virtual void reporting() = 0;
};
```

## Open-close

Try to refactor [this code](https://github.com/clean-code-craft-tcq-1/function-ext-python-AkshayUHegde/blob/ac4ffc6d0ea080a374bcc68d30e6b6cd50be462c/reporter.py#L5)
to add without modifying.

An example of [configuration by composition](https://github.com/clean-code-craft-tcq-1/function-ext-python-aswinmath94/blob/71f140921dbee691639493ae71dfb3873ab4c687/bms_health.py#L21-L22)
