VENCalculatorInputView
=========

VENCalculatorInputView is the calculator keyboard that is used in the Venmo iOS app. Enjoy.

Installation
----

The easiest way to get started is to use [CocoaPods](http://cocoapods.org/). Just add the following line to your Podfile:

![alt text](http://imgur.com/QIFX8Oa "VENCalculatorInputView")
![alt text](http://imgur.com/G3h13uv "VENCalculatorInputView highlighted")

```ruby
pod 'VENCalculatorInputView'
```

Sample Usage
----
You can choose to use just ```VENCalculatorInputView``` (only the keyboard) and define your own behavior or use ```VENCalculatorInputTextField``` (keyboard + text field with money calculation built in).

### Using just the calculator keyboard

#### 1. Set the input view.
Find the ```UITextField``` or ```UITextView``` that you want to display the keyboard and set its ```inputView``` to an instance of ```VENCalculatorInputView```.

```obj-c
myTextField.inputView = [VENCalculatorInputView alloc] init];
```

#### 2. Implement the ```<VENCalculatorInputViewDelegate>``` methods.

First, have a class implement the ```<VENCalculatorInputViewDelegate>``` protocol and set ```myTextField.inputView.delegate``` to an instance of that class.

Next, implement the delegate method that handles keyboard input:

```obj-c
- (void)calculatorInputView:(VENCalculatorInputView *)inputView didTapKey:(NSString *)key {
    NSLog(@"Just tapped key: %@", key);
    // Handle the input. Something like [myTextField insertText:key];
}
```

Finally, implement the delegate method that handles the backspace key:

```obj-c
- (void)calculatorInputViewDidTapBackspace:(VENCalculatorInputView *)calculatorInputView {
    NSLog(@"Just tapped backspace.");
    // Handle the backspace. Something like [myTextField deleteBackward];
}
```

### Using the calculator text field (optimized for money calculation)

All you need to do is use ```VENCalculatorInputTextField``` instead of ```UITextField``` and use it like normal text field. It will automagically handle the input and make calculations. Take a look at out our ```VENCalculatorInputViewSample``` project.

Version
----
1.0.0

License
----

MIT