# Add Capabilities

This exercise is about adding capabilities with minimal impact.

When we can add capability easily, we keep up with evolving customer-needs.

This assignment is a continuation of the [Battery Monitoring](bms-statement.md)
exercise.

## Consolidate and Report

Add the ability to consolidate measurements and report them in a suitable way.

Currently, your code may output on console as each threshold breaches.
This exercise is about _adding_ features:

### Consolidation

To start with, assume the 3 parameters get reported together.
Accumulate the parameters that are crossing thresholds and report them together.

### Multiple reporting possibilities

Reporting can either be to the console,
or it could be sent to a controller for taking action. Make a dummy controller.

### Constraints

- Test the accumulator and reporter separately.

- It must be possible to extend the system with newer accumulators and reporters,
with minimal modifications to existing code.

## Customer Domain

_This section is not for implementation!_

The Customer's Domain is useful in making sensible design choices: Keeping things simple yet flexible.

Imaginary Customer Domain: A battery-farm reporting from multiple sensors.

Multiple sources simultaneously stream the data, perhaps a reading every 5 seconds.
As of now, the customer has requested a consolidated report
across sensors of a battery.
They _could_ request accumulation per set of batteries -
maybe they are grouped in rooms and shelves.

Similarly, different stakeholders in the system may need different reports
Think of supply-chains like BMS OEMs, battery-farm-facilities and supply-chain.
