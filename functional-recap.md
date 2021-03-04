# Functional - recap

[Notice the filenames](https://github.com/clean-code-craft-tcq-1/functional-c-Arunava-Paul).
Can [temperature checking](https://github.com/clean-code-craft-tcq-1/functional-c-Arunava-Paul/blob/master/BMS_Sys_Temperature_eavaluation.c)
complexity be reduced? Do other _eavaluation.c files have duplicates?

How would [this evolve](https://github.com/clean-code-craft-tcq-1/functional-c-abhijeetlc/blob/master/checker.c)
with more parameters? Battery types?

[Notice naming of the Index, separation of message and the output](https://github.com/clean-code-craft-tcq-1/functional-c-Padmashree-DJ/pull/1/files).

[Low duplication and nice tests](https://github.com/clean-code-craft-tcq-1/functional-c-NaveenBalachandar-dev/blob/master/BatteryStateManagement_proj.c).
Spot the missing test :)

[Data-abstraction](https://github.com/clean-code-craft-tcq-1/functional-c-Tamilarasan-Aruchamy/blob/master/checker.c)
**+** [overall-battery-health complexity](https://github.com/clean-code-craft-tcq-1/functional-c-Harshitha0306)

[Use of lambdas](https://github.com/clean-code-craft-tcq-1/functional-cpp-Niyas12/blob/master/BMS.cpp)

[A 'latch' to reduce complexity](https://github.com/clean-code-craft-tcq-1/functional-cpp-6872Vishal/blob/master/checker.cpp)

[Pure functions as data-converters](https://github.com/clean-code-craft-tcq-1/functional-python-reetika97/blob/main/check_limits.py)

[Property-based tests](https://github.com/clean-code-craft-tcq-1/functional-python-ccharan94/blob/main/check_limits.py)



---

What would a true or a false mean here?

```c
int StateOfHealth_check (float currentsoh);
```

Coding for the tool!

```c
sohstatus =  BMS_StateOfHealth(StateofHealth);
socstatus = BMS_StateOfCharge(stateofcharge);
chargeratecheck = BMS_ChargeRateCheck(ChargeRate);
temperaturecheck = BMS_TemperatureCheck(temperature);
status= (sohstatus & sohstatus & chargeratecheck & temperaturecheck);
```
