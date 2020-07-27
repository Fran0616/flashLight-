# flashLight-

**Objective**

The purpose of this lab is to create a simple flash light using the user interface. 

**Swift** 

[Swift](https://developer.apple.com/swift/) is a programming language for macOS, IOS, watchOS, tvOS and more. Swift is an interactive language with syntax that is concise yet expressive. 

**XCode**

[Xcode](https://help.apple.com/xcode/mac/current/#/devc8c2a6be1) is apple’s integrated development environment (IDE). It is used to build apps for apple devices. Xcode provides tools to manage the entire development workflow.

**Goal**

  1. Flash ON and OFF when button is press
  
**Software Overview**  

Ukit: 

I will import the UIKit which is used to construct and manage the graphical, event-driven user interface for an IOS device. It provides the window and view architecture for implementing an interface, the event handling infrastructure for delivering multi-Touch and other types of input to your app. Some additional features offered by this framework includes animation support, document support, drawing and printing support. 

ViewController: 

The [view controllers](https://developer.apple.com/documentation/uikit/view_controllers) manage the interface using view controllers and facilitate navigation around the app's content. 
The view controller consists of the button object and the label. They are both types within the UIkit framework. The UIButton is connected with the storyboard as an interface builder outlet. And the label is set as an action. 

Variable lightOn:

The variable lightOn is set to equal to true. The screen is white by default so the flash is on. The light is in this case. 

Variable lightButton: 

UIButton is the button that is displayed in the user interface and it will be used to change the title of the button from ON or OFF. When the light is on the button will be OFF and when it’s off it will write OFF. 

updateUI: 

The updateUI method will be used to update the user interface with a separate function. This is used to keep the code clean and easy to read. The update function used an if/else statement to change the title of the button depending on its state, and to change the background color. If the light is on the background will be white and the button title will be OFF suggesting that if the user touches it it will be. The else statement will be triggered when the button is pressed, changing the button title to ON and changing the background color to black. 

buttonPressed:

The button pressed function includes the statement lightOn.toggle() which will toggle the boolean expression from false. Recall the variable lightOn is true by default, this function will be used to change that manually. 

**User Interface**

The button interface can be clicked from anywhere on the screen, so the user can tap anyway to toggle the off and on action. The button is also blue so the title will appear whether the light is on or off. This makes the design really friendly to the user. 

**Source Code**


import UIKit

class ViewController: UIViewController {

    var lightOn = true //the screen starts of as white so light is on
    @IBOutlet weak var lightButton: UIButton!// will be used to change the title of button after button is clicked    
    override func viewDidLoad() {
        super.viewDidLoad()
        updateUI()
        // Do any additional setup after loading the view.
    }
    
    @IBAction func buttonPressed(_ sender: UIButton) {
        lightOn.toggle() // the toggle() method changes from false to true each time the button is tapped.
        updateUI()// this method is used to update the interface. look for the updateUI function
    
 
    }
    // this function below will be used to update the entire user interface
    func updateUI(){

        if lightOn {
            view.backgroundColor = .white //when the light is on and the lightOn boolean is true the background will be white
            lightButton.setTitle("OFF", for: .normal)
            }
            else {
            view.backgroundColor = . black // when the button is tap and the boolean expression is false the background changes to black
             lightButton.setTitle("ON", for: .normal)
            
        }
    }
}


