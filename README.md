# Status

[![Join the chat at https://gitter.im/talenguyen/PrettyBundle](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/talenguyen/PrettyBundle?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![Build Status](https://travis-ci.org/talenguyen/PrettyBundle.svg?branch=development)](https://travis-ci.org/talenguyen/PrettyBundle)
# PrettyBundle
Android library which uses annotation processor to help Android Developer easy to deal with Bundle to communicate between Activity, Fragment and Service.

PrettyBundle is inspired by [Dart](https://github.com/f2prateek/dart)

## How it work
### Activity
Inject extras in Activity. (Borrow the idea of ButterKnife and Dart).
```java
public class TargetActivity {
    @Extra String name;
    @Extra int age;

    @Override public void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        PrettyBundle.inject(this); // call to inject the extra.
        // TODO: uses the extras properties
    }
}
```
To set extras and start the TargetActivity
```java
Intent intent = Activities.createTargetActivityIntent("Giang", 26);
startActivity(intent);
```
***Activities*** is the utility class which is generated by the library processor. 

***Activityes.createTargetActivityIntent()*** is the corresponding method to create new instance of the ***Intent*** class which will be used to start the ***TargetActivity***

### Fragment
Inject extras in Fragment. 
```java
public class TargetFragment {
    @Extra String name;
    @Extra int age;

    @Override public void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        PrettyBundle.inject(this); // call to inject the extra.
        // TODO: uses the extras properties
    }
}
```
Set extras and create an instance of TargetFragment.
```java
TargetFragment targetFragment = Fragments.createTargetFragment("Giang", 26);
```
***Fragments*** is the utility class which is generated by the library processor. 

***Fragments.createTargetFragment()*** is the corresponding method to create new instance of the ***TargetFragment***.

## Download
