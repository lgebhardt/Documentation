# C++ Naming Guide

In order to keep code formatting consistent across all files and projects created by the Team 2342 coding subteam, all C++ code submitted to official repositories must follow all or very close to all of the guidelines presented in these documents. Note that this policy is in effect starting with the 2017 build season, so code from before then may not represent proper code style. Please bring any concerns or questions you have to the leadership.

All variable names should be kept to a minimum possible length while still conveying enough information about what they do to make it clear to anyone who reads your code what they are. For small temporary variables, short names may suffice if commenting is adequate.

### Variables and Functions

Variables and functions both follow the same convention. Names should be camelcased. Here are some examples:

```C++
double distanceLeft;
int encoderTicks;
bool isFinished;
int sumInts (int x, int y);
```

Class variables should follow the same convention as other variables, but prefixed with `m_` (e.g. `x` would become `m_x`). Global variables should be prefixed with `g_` in a similar fashion. Boolean variables should generally follow the is/has noun form (e.g. `isLinedUp`, `hasMoved`, etc).

All constant variables are named with entirely uppercase letters and underscores for spaces. Here are some examples of constant variables:

```C++
const static uint32_t BL_WHEEL_MOTOR = 0; // back left
const static uint32_t FL_WHEEL_MOTOR = 1; // front left
const static uint32_t FR_WHEEL_MOTOR = 2; // front right
const static uint32_t BR_WHEEL_MOTOR = 3; // back right
```

### Classes

Naming classes is much like naming functions and variables. However, the first letter of the class name should also be capitalized. Examples:

```C++
class Action {}
class ActionLidarDriveDynamic {}
class Client {}
class LoaderController {}
```

### Enums

Considering `enum` declarations in C++ look much like any variable declaration, naming them can be confusing. We suggest naming enums the same way you name classes. The first letter of each word should be capitalized. Fields inside the enum should follow the same convention as constants. Here is an example enum:

```C++
enum ButtonNames {
   BUTTON_X,              // = 0
   BUTTON_A,              // = 1
   BUTTON_B,              // = 2
   BUTTON_Y,              // = 3
   BUTTON_LB,             // = 4
   BUTTON_RB,             // = 5
   TRIGGER_LT,            // = 6
   TRIGGER_RT,            // = 7
   BUTTON_BACK,           // = 8
   BUTTON_START,          // = 9
   BUTTON_JOYSTICK_LEFT,  // = 10
   BUTTON_JOYSTICK_RIGHT  // = 11
};
```