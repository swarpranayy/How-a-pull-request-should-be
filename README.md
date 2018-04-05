# How-a-pull-request-should-be
Basic checkpoints before submitting a pull request/ merge request for iOS Development using Xcode and Swift/ObjC.

These are some of the check points that we follow in the company where I work. These checkpoints are not for the reviewer per se but more for the person submitting the Pull/Merge request to have list to go through before finally raising the flag for 'ready for peer review'. 

- [x] Does the code compile for all relevant targets.
I know this sounds rather obvious, but there are times when we would make this one line change or even one character change for may be a defect fix and don't really compile and check since the results are obvious.

- [x] Does the code compile cleanly without warnings/errors. 
This is to make sure that your changes did not add any new warnings to the code. By warnings/errors, I mean two types a) those given by the compiler. b) The warning/errors given by any other linting program that you could be using in your software development peocess. We use SwiftLint for Swift source code. This also makes sure the entire code base is in agreement with the set standards for styling and convention.

- [x] Static Analysis and Memory Graph Analysis
This is one of the overloked areas especially after introduction of ARC and with tools like Memory Graph Debugger, it has become much easier to find and detect leaks in your code. Although these tools might fails in detecting leaks sometime, they are great way to quickly scan the code and find the obvious ones. So, make sure you run the code through these. 

- [x] Used private and final where appropriate. 
By default all the members of the class/struct/enums are internal. But there could be instances where you want to hide members properties or methods for the purpose of abstraction or encapsulation, from someone who could potentially use your interface. This is the checkmark to make sure you comply to that. Also, marking the class as final help the compiler optimize and redcue the binary size. So, make sure to use the keyword and mark classes as final to indicate the compiler that this wont be inherted further. (until you actuall need to inherit it)

- [x] Remove unnecessary inferencing to Objective-C dispatch using @objc
This one is not so important, after the Swift 4 stopped implictly adding @objc to all classes inherited from NSObject. But this checkmark is just there to double check that which helps in reducing the size of the binary. 

- [x] Runs as expected on all the size classes
Size classes helps our UI adapt to the wide variety of idevice that exist. This is especially important when you are working on the User Interfact. However small change it may be, it may not necessarily work on other size classes. So, this check is just to make sure you have ran your code on all the different size classes. 

- [x] Not Errors/Warnings in Storyboard, View Debugger and console (waring in console for unsatisfiable layouts)
This is again relevant to you if you have made even slightest of the changes related to User Interface. This check mark is to make sure to remove and fix those warnings/Erros (most likely because the constraints are not defined in the right way). View Debugger is again a great tool introduce in the recent years to Xcode and with Xcode 8.0 it detects the Ambigious layouts right in the view Debugger. Ambigious layouts are one of those things that you won't know about it until you know, because unlike Unsatidfiable layouts, it doen't display it on cosole and goes undetected. With the view debugging tool, it has become easier to deal with it. Also, stating the obvious, before checking this point as good, its a good time to look at the console and see if the layout engine broke some constraint because of unsatisfiable layout. If yes, than the constraints should be defined in some other way. 



TO BE CONTINUED...








