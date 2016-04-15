# C++ General Code Style Guide

In order to keep code formatting consistent across all files and projects created by the Team 2342 coding subteam, all C++ code submitted to official repositories must follow all or very close to all of the guidelines presented in these documents. Note that this policy is in effect starting with the 2017 build season, so code from before then may not represent proper code style. Please bring any concerns or questions you have to the leadership.

### Intelligent Use of Spacing

One of the easiest and most impactful changes you can make to your code styling are the way you use whitespace. We advise that you put spaces between all operators, brackets, and commands. Even if they aren't required. Here are some before and after examples:

```C++
int centerx=(x1+x2+x3+x4)/4;     -->     int centerx = (x1 + x2 + x3 + x4) / 4;
if(x==4){}                       -->     if (x == 4) {}
for(int i=0;i<10;i++) {}         -->     for (int i = 0; i < 10; i++) {}
```

Additionally, adding blank lines between large blocks of code and between linked sections of code can greatly increase readability. Consider this example which converts raw encoder values to degrees:

```C++
int Aiming::encoderDistanceToDegrees (int encoder1, int encoder2)
{
    int degrees;
    int encoderTickDifference;
    double fractionOfCircumference;
    encoderTickDifference = encoder1 - encoder2;
    encoderTickDifference /=2;
    fractionOfCircumference = (double) (encoderTickDifference / AimingConstants::circumferenceOfRotation);
    degrees = fractionOfCircumference * 360;
    return degrees;
}
```

This is a simple example, but compare it to the same code split up into logical blocks. It naturally guides the eyes across different sections:

```C++
int Aiming::encoderDistanceToDegrees (int encoder1, int encoder2)
{
 
    int degrees;
    int encoderTickDifference;
    double fractionOfCircumference;
 
    encoderTickDifference = encoder1 - encoder2;
    encoderTickDifference /=2;
    fractionOfCircumference = (double) (encoderTickDifference / AimingConstants::circumferenceOfRotation);
    degrees = fractionOfCircumference * 360;
 
    return degrees;
    
}
```

Another problem you may run into when trying to make code neat is what to do when you have a lot of arguments in a function. If you find your function headers are becoming too long, use this convention:

```C++
int doSomethingComplicated (VeryLongType sourceData, // you can add comments here if needed
                            int x, // the x coordinate
                            int y, // the y coordinate
                            bool arg) //boolean argument
{
    // Do something very important here
}
```

### Indentation

When many developers use different methods of indentation, it can make code very hard to maintain. In order to keep everything consistent and make copying and pasting code easier, the Team Phoenix subteam (from the 2017 build season onwards) uses four space indentation. To set this up in Eclipse, see the code style section of the `eclipse-setup` guide in the `eclipse` folder.

### Brackets

There are many different ways of using brackets in C++, but for the purposes of projects related to robotics, we follow the convention of putting brackets on new lines, and always including them, even for single line if statements. For bracketed blocks that contain larger blocks of code, we also recommend putting blank lines between the top and bottom brackets. Here is an example of a single line if statement:

```C++
if (true)
{
    //do something
}
```
