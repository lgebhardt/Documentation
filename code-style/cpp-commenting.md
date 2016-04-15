# C++ Commenting Guide

In order to keep code formatting consistent across all files and projects created by the Team 2342 coding subteam, all C++ code submitted to official repositories must follow all or very close to all of the guidelines presented in these documents. Note that this policy is in effect starting with the 2017 build season, so code from before then may not represent proper code style. Please bring any concerns or questions you have to the leadership.

Comments are a very important element to consider whenever writing code. They help make code more maintainable, easier for others to read, and explain what's going on in different sections of a program. However, good comments are no replacement for good code. Comments tell you why, while code tells you how.

In addition to the information provided here, there are also metadata comments that need to be added before code is pushed to the public Team Phoenix repositories. For more information about that, look at the `git` folder.

### When to Comment

Not every line needs a comment. In many cases, adding comments can make code more cluttered and harder to read. for example, consider this if statement:

```C++
if (m_motor.isMoving()) {
    // do something
}
```

This if statement does not need a comment above it that reads "If the motor is moving". However, it may be useful to write a comment about the contents of the if statement. For example you could write a comment saying "Wait for the motor to stop moving" and then write code to accomplish that inside the if statement.

One important thing to remember, though, is that while we did mention that code tells you how farther up, sometimes the "how" can be very complex. This may be a good time for a comment. Code that makes perfect sense to you after hours of debugging may make no sense at all to fresh eyes. Another great place to include comments is when you use an alternative method to accomplish something, and it may not be clear why that method was used. For example, this is a very useful comment:

```C++
/* A binary search turned out to be slower than the Boyer-Moore algorithm for the data sets
of interest, thus we have used the more complex, but faster method even though this problem
does not at first seem amenable to a string search technique. */
```

### Form of a Comment

Comments should be kept brief and impersonal, and the use of first and second person should generally be avoided. For example, combining this knowledge with the previous section, here is a before and after for a block of code.

Before:

```C++
// Decide if we need to move forward or backwards
if (m_lidar->getFastAverage() < AimingConstants::aimedDistance - AimingConstants::distanceVariance){
    m_driveTrainController->moveRobotStraight(-6,0.5f);
}
else if (m_lidar->getFastAverage() > AimingConstants::aimedDistance + AimingConstants::distanceVariance){
    m_driveTrainController->moveRobotStraight(6,0.5f);
}

// We're done approaching and can move to the next phase we need!
else {

    hasApproached=true;
    if (fullProcess){
        setCurrentState(CENTERING);
    }
    else {
        setCurrentState(IDLE);
    }
    
}
```

And after:

```C++

/* approach to the right distance */

// move backwards if too close to the target
if (m_lidar->getFastAverage() < AimingConstants::aimedDistance - AimingConstants::distanceVariance){
    m_driveTrainController->moveRobotStraight(-6,0.5f);
}
// otherwise move forwards if too far
else if (m_lidar->getFastAverage() > AimingConstants::aimedDistance + AimingConstants::distanceVariance){
    m_driveTrainController->moveRobotStraight(6,0.5f);
}
// go to next state if within range
else {

    hasApproached=true;
    // only go to centering if the client requested full aiming
    if (fullProcess) {
        setCurrentState(CENTERING);
    }
    else {
        setCurrentState(IDLE);
    }
    
}
```

### Disclaimer

Keep in mind that these are all just guidelines, and they may not be applicable to every snippet of code. Comments are the most variable part of these guidelines, and some parts of code may need more of them than other parts of code. The most important thing is to maintain as much readability and maintainability as possible. You are free to use your own judgement on how and when to comment, within reason.
