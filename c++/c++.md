# Fundamental Types: 

## Format specifiers:
![fs](2022-05-07_06-27-13_chrome.png)
![somemore](2022-05-07_06-30-30_chrome.png)


## Integer:
![int](2022-05-02_07-11-01_SumatraPDF.png)

### Signed and unsigned:
In laymen's terms an unsigned int is an integer that can not be negative and thus has a higher range of positive values that it can assume. A signed int is an integer that can be negative but has a lower positive range in exchange for more negative values it can assume.

## Floating Point Numbers:
![fpn](2022-05-02_08-28-53_SumatraPDF.png)

## Charater types:
![char](2022-05-02_08-34-58_SumatraPDF.png)

## Boolean:
![bool](2022-05-02_17-10-39_SumatraPDF.png)

### size_t type:
![size_t](2022-05-03_20-04-21_SumatraPDF.png)


## void:
none

# Array:
![arr](2022-05-03_07-40-26_SumatraPDF.png)

# User-Defined Types:
## Enumerations:
The simplest of the user-defined types.
The values that an enumeration can take are restricted to a set of possible values.
Enumerations are excellent for modeling categorical concepts.

Under the hood, these values are simply integers, but they allow you towrite safer, more expressive code by using programmer-defined types rather than integers that could mean anything.

Eg:
```c++
enum class Race {
 Dinan,
 Teklan,
 Ivyn,
 Moiran,
 Camite,
 Julian,
 Aidan
};
```
Inialize using 
```
Race langobard_race = Race::Aidan;
```
![enum](2022-05-07_06-59-55_SumatraPDF.png)

## Classses (POD) (Plain-Old-Data Classes):
Classes are user-defined types that contain data and functions, and they’re the heart and soul of C++. The simplest kind of classes are plain-old-data classes (PODs). PODs are simple containers.
Think of them as a sort of heterogeneous array of elements of potentially different types. Each element of a class is called a member.
![class](2022-05-07_07-46-46_SumatraPDF.png)

## Unions:
Dont use them.

## 