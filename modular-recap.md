

Self-evaluation notes in README:

- https://github.com/clean-code-craft-tcq-1/modular-c-sembooooo

New feature in its own file

- https://github.com/clean-code-craft-tcq-1/modular-python-AkshayUHegde/blob/main/wiring_color_code_printer.py
- https://github.com/clean-code-craft-tcq-1/modular-python-BhavaniSingam/blob/main/ColorCodeRefManual.py
- https://github.com/clean-code-craft-tcq-1/modular-c-Tamilarasan-Aruchamy

Separation of data-creation and output

- https://github.com/clean-code-craft-tcq-1/modular-python-DivyaK-bit/blob/main/main.py
- https://github.com/clean-code-craft-tcq-1/modular-python-wanderer-soul92


A name for the total number of enums:
```c
typedef enum {
  MajorColor_WHITE ,
  MajorColor_RED,
  MajorColor_BLACK,
  MajorColor_YELLOW,
  MajorColor_VIOLET,
  MajorColor_TotalNumber
} MajorColor_t;
```

Comments - what's the opportunity to clarify:
```c
/* \return  ColorPair stucture
 * \retval  colorPair */
 ColorPair GetColorFromPairNumber(int pairNumber) {
    ColorPair colorPair;
    /* ... */
    return colorPair;
}
```

Common mistake missed by tests that don't cover data-variance:
```c
colorPair.majorColor = 
        (enum MajorColor)(zeroBasedPairNumber / numberOfMajorColors);
```

The value of consistency - from / to
```c
void ColorPairToString(const ColorPair* colorPair, char* buffer)
ColorPair GetColorFromPairNumber(int pairNumber)
int GetPairNumberFromColor(const ColorPair* colorPair)
```

Coherence: keep related things together

https://github.com/clean-code-craft-tcq-1/modular-c-NaveenBalachandar-dev/blob/master/ColorCodeProj.h

```c
const char* MinorColorNames[] = {"Blue", "Orange", "Green", "Brown", "Slate"};
/* --- differnt file --- */
enum MinorColor {BLUE, ORANGE, GREEN, BROWN, SLATE};
```

Naming the tests with the expected result
```c
void TCC_testPairNumber_AgaintColours(int pairNumber, enum MajorColor_e expectedMajor,...
```

Get... for string?
```c
void formatToString_v(const colorPair_t* colorPair_p, char* strOutput_p)
```
