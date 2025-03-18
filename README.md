# Java Notes

# Base
## Hierarchy/ Syntax
```
package
libraries

class
	variables
	functions
```

Variables need to be inside the class
```
public class Main {  
    int resX = 1290;  
    int resY = 720;
}
```
Otherwise java throws a fit and shits itself

BUT you need to import libraries outside of everything
```
package org.clkairos
import example.bullshit.kys;

public class Main {  
    public static void main(String[] args){
    }
}
```
ALSO you need to have a package set, the formatting looks like
```
package org.your-username
```
this needs to be set first thing in your code or again, java throws a fit and shits itself
## Functions/ Methods
```
public class Main {
	public static void main(String[] args){
		int x = 1;
		int x += 1;
	}
}
```
static variables are useful but they can't be used outside of the method 
```
public class Main {  
    int x = 1;  
  
    public static void main(String[] args){  
        Main main = new Main();  
        int x += 1;
    }    
}
```
so in order to have non-static variables and actually use them
you need to do some weird shit
```
public class Main {  
    public static void main(String[] args){  
	    Main main = new Main();  
	    main.compile();  
	}  
}
```
because the main method NEEDS to be public static
it cannot use non-static variables
so if we make the variables public
they are able to be used out of the method
but they aren't able to be used by that main method
because they are no longer static
```
public static void main(String[] args){  
    Main main = new Main();  
}
```
so what you have to do is initialize the class as the main method 
# JFrame
EVERYTHING has a different library
```
import javax.swing.JFrame;  
import javax.swing.JLabel;  
import javax.swing.JButton;  
import javax.swing.JPanel;
```
ts pmo

Alternatively you can use
```
import javax.swing.*;  
import java.awt.*;
```
which fortunately just adds all of the libraries needed

```
JFrame frame = new JFrame("Test JFrame");  
JPanel panel = new JPanel();  
JButton button = new JButton("Click Me");  
JLabel label = new JLabel("Hello World!");  
panel.add(button);  
panel.add(label);  
frame.add(panel);
```
First you gotta initialize the window using 
```
JFrame frame = new JFrame("Window Name");
```
Optionally you can use Panels to organize your objects
but remember to add them to the panel and not the frame
because my dumbass didn't realize that and spent 10 minutes trying to figure it out
```
JPanel panel = new JPanel();  
JButton button = new JButton("Click Me");  
JLabel label = new JLabel("Hello World!");  
```
That initializes all of the objects, obviously.
but you need to add them to frame so they actually show up
```
panel.add(button);  
panel.add(label);  
frame.add(panel);
```
again, you need to add the object to the panel, and then add the panel to the frame
otherwise, ts don't work

## Button Interactions
Button interactions are very straight forward
```
button.addActionListener(new ActionListener() {  
    @Override  
    public void actionPerformed(ActionEvent e) {  
        JOptionPane.showMessageDialog(frame, "Button was clicked");  
    }  
});
```
with this we get to install more LIBRARIES 
```
import javax.swing.JOptionPane;  
import java.awt.event.ActionEvent;  
import java.awt.event.ActionListener;
```
add you can see
```
button.addActionListener(new ActionListener(){});
```
first it says "HEY BUTTON, ADD THIS ACTION LISTENER"
and then clarifies what action listener it wants it to use
which is a completely new one so fuck me ig
```
public void actionPerformed(ActionEvent e) {  
    JOptionPane.showMessageDialog(frame, "Button was clicked");  
}
```
moving on the the actions they are basically glorified functions
if the button is pressed the open a dialog saying the button was clicked

