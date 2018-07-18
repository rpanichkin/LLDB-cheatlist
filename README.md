# LLDB most used commands cheatlist

### • print description:

*po self.var*

### • make changes just for debugging:

*expression self.var = false*

### • declare a variable (only visible in LLDB):

*e NSString \*$globalConstant = @"What's up"*

### • Set one breakpoint that enables another: put that in the expression command in the debugger line of the breakpoint:
*breakpoint set --one-shot true "-[UILabel setText:]"*

### • Symbolic breakpoints - to print arguments use:
*po $arg1* - is receiver

*po (SEL)$arg2* - is the selector

*po $arg3* - is the first argument

### • Move the instruction pointer by dragging it. Or using LLDB:
*thread jump --by 2* - move to lines forward

*thread jump 100* - move to line 23

*thread return* - instantly executes returns, rest of the method doesn't get executed

### In the variable navigator, you can set 'Watch' which will auto-break when the variable is changed. Using LLDB:
*watchpoint set variable _currentModel->_title*

*watchpoint list* - list of watchpoints

*watchpoint delete 1* - delete watchpoint at the position 1 in watpoints list

### • Print recursive description of view (with all subviews)
*po [self.view recursiveDescription]*

### • Make the screen redraw after editing frames, etc.
*e (void)[CATransaction flush]*

### Commands from Chisel
https://github.com/facebook/chisel

### • Open a UIImage, CGImageRef, UIView, CALayer, NSData (of an image), UIColor, CIColor, or CGColorRef in Preview.app on your Mac.
*visualize self.searchBar*

### • Show or hide the given view or layer. You don't even have to continue the process to see the changes!
*show/hide self.view*

### • Alias for(void)[CATransaction flush]
*caflush* 

### • And much more, check out Chisel repo
