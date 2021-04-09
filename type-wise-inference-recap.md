# Recap of Type-wise inference

## Test Doubles

References:

- [Terminology](https://stackoverflow.com/questions/346372/whats-the-difference-between-faking-mocking-and-stubbing/)
- [Using Mocks and Stubs](https://martinfowler.com/articles/mocksArentStubs.html)

### Fake

Used in place of the real one.
Examples: Printing instead of sending email; In-memory variant of database.

### Stub

When the fake just performs pre-defined behavior.
Example: Return pre-defined response instead of fetching it from a controller.

### Mock

When the fake records something that can be asserted.
Example: Record the parameters passed to the email-sender.

## Examples

[Mocking](https://github.com/clean-code-craft-tcq-1/add-variety-c-sembooooo/blob/main/test/test_stub.c)

[Test progression](https://github.com/clean-code-craft-tcq-1/add-variety-c-SreeKiruthika/blob/main/test_breach.cpp)

Test code and marker together

```cpp
void EmailAlert::sendAlert(BreachType breachType)
{
    if (breachType != NORMAL)
    {
        sendToEmail(breachType);
        m_EmailAlertSent = true;
    }
}
```

check_and_alert as a data-convertion

```python
assertEqual(check_and_alert('to_controller', batteryLimits, 16), true)
```
