

ControlP5
=================



build
-----------------
install processing jar:

      mvn install:install-file -Dfile=core.jar -DgroupId=org.processing -DartifactId=core -Dversion=11 -Dpackaging=jar
     
then :

      mvn package


changes
-----------------
2012-06-20  Trey Marc

 * remove triangle in numberBox 
 
 * adding build with maven 

2012-05-30  Andreas Schlegel  <andi at sojamo.de>

 * version 0.7.5
      
 * src controlP5.Controller.java:
      adding empty methods onPress(), onClick(), onRelease(), onReleaseOutside(), 
      onScroll(int),onMove(),onDrag() for input access when extending a controller.
      
 * adding convenience constructor to Controllers when extending a Controller.
      
 * adding example use/ControlP5extendController
      
      
       
2012-05-18  Andreas Schlegel  <andi at sojamo.de>

 * version 0.7.3
      
 * src controlP5.ControlEvent.java:
      adding getArrayValue(int), returns a float value for a given index, does not check for ArrayIndexOutOfBounds
     
 * src controlP5.Slider.java:
      issue 47 http://code.google.com/p/controlp5/issues/detail?id=47 fixed
      
 * src controlP5.CheckBox.java, controlP5.RadioButton.java:
      issue 41 http://code.google.com/p/controlp5/issues/detail?id=41 fixed
      
 * src controlP5.Chart.java:      
      implemented
      
 * src controlP5.ControlFont.java:      
      issue 46 http://code.google.com/p/controlp5/issues/detail?id=46 fixed
      
 * src controlP5.ControlWindow.java:      
      sketches using controlP5 running in the browser as Applet did not work anymore, fixed

 * src controlP5.ColorPicker.java:      
      missing implementation reported in http://forum.processing.org/topic/controlp5-how-to-receive-colorpicker-controlevents fixed
      ColorPicker example has been modified accordingly 
      
 * src controlP5.Textfield.java:
      issue 44 http://code.google.com/p/controlp5/issues/detail?id=44 fixed
      
 * src controlP5.ControlWindowKeyHandler.java:
      issue 49 http://code.google.com/p/controlp5/issues/detail?id=49 fixed, keys boolean array size increased to 525 due to windows key issue
            
      

2012-01-15  Andreas Schlegel  <andi at sojamo.de>

 * version 0.7.0
      
 * src controlP5.ControllerInterface.java, controlP5.Controller.java,controlP5.ControllerGroup.java: 
      adding generic type declaration for object specific method chaining (fluent interface)
      
 * src controlP5.RadioButton.java:
      changed return type for methods addItem from Toggle to RadioButton
      changed return type for methods setImage from PImage to RadioButton
      
      
      

2011-10-14  Andreas Schlegel  <andi at sojamo.de>

 * version 0.6.9
      
 * src controlP5.Textarea.java:
      included isScrollable() to adapt to ListBox  


2011-10-13  Andreas Schlegel  <andi at sojamo.de>

 * version 0.6.8
      
 * src controlP5.ControllerGroup.java, controlP5.Controller.java:  
      making addition to isVisible() to check if the parent element is invisible 
      in which case the child element will return false as well although the visible 
      state might be true. this fixes an issue with mousewheel scroll being active 
      for an invisible child controller. The mouseoverlist handling was updated as well.
      
 * src controlP5.Slider.java:
      Slider will only broadcast when there is a change in value when pressed
      
 * src controlP5.ControlWindow.java:
      mouseWheelMoved() now only updates the first item in the mouseoverlist 
      and then exits the loop
      
      
2011-10-12  Andreas Schlegel  <andi at sojamo.de>

 * version 0.6.7
      
 * examples reorganized and grouped into 3 categories, 
      controllers, use, extra
      
      
2011-10-07  Andreas Schlegel  <andi at sojamo.de>

 * version 0.6.6
      
 * src controlP5/Textarea.java:
      scrollbar pixel offset fixed, setPosition update fixed.
		

2011-09-22  Andreas Schlegel  <andi at sojamo.de>

 * version 0.6.5      
      
 * src controlP5/ControlWindow.java:
      adding removeMouseOverFor() to remove controllers from the mouseoverlist. 
      Called when a controller or group is removed. Necessary when a controller/group is removed 
      when clicked or hovered by the mouse.		


2011-09-20  Andreas Schlegel  <andi at sojamo.de>

 * version 0.6.4      
      
 * src controlP5/Textfield.java:
      adding support for PFont
      
 * javadoc, new design
      
      
      
2011-08-27  Andreas Schlegel  <andi at sojamo.de>

 * version 0.6.3
      
 * src controlP5/ListBox.java, controlP5/DropdownList.java:
      adding mouseover support.
       
 * src controlP5/ControlP5.java:
      adding enableMouseWheel(), disableMouseWheel(), isMouseWheel()
      by default the mouse wheel is active for Slider, Knob, Numberbox, 
      ListBox  and DropdownList. The MouseWheelListener is handled 
      by each ControlWindow individually.      
      
 * src controlP5/ControlWindow.java:
      adding getFrame() to access the frame object of a ControlWindow.
      
            
2011-08-25  Andreas Schlegel  <andi at sojamo.de>

 * version 0.6.2
      
 * src controlP5/ControlP5.java:
      removing static from the papplet field, this had consequences for some internal 
      calls to papplet but do not affect any publicly available methods or constructors 
      except the Label class which requires a controlP5 instances as it's constructor's 
      first parameter.
      
 * src controlP5/ControlP5.java:
      field keyHandler is now non-static
      
 * src controlP5/Label.java:
      adding a ControlP5 parameter to all Label constructors due to changes made
      to field controlP5.papplet
      
 * src controlP5/Textlabel.java:
      Constructors with the first parameter of type Component have been deprecated
      and replaced with constructors using a reference to ControlP5 as first parameter.
      if this affects your programs, please make changes accordingly.   


2011-08-20  Andreas Schlegel  <andi at sojamo.de>

 * version 0.6.1
      
 * ongoing internal code refactoring, adding getter and setter methods for 
      existing methods (which are deprecated accordingly) 
      
 * reference cleanup
      
 * preparing for release
      
 * src controlP5/ControllerSprite.java:
      deprecated
      
 * src controlP5/ControlCanvas.java:
      deprecated, use ControlWindowCanvas instead
      
 * Names of controllers now follows the OSC address pattern specs,
      use controlP5.printControllerMap() to see the changed address space.
      This has been added to controlP5 since controllers now can be directly 
      linked to custom objects and not only to the instance of the main program.
      http://opensoundcontrol.org/spec-1_0-examples
      (OSC Address Parts not included)      
      
       
      
2011-06-25  Andreas Schlegel  <andi at sojamo.de>

 * version 0.6.0
	
	    * adding Annotation support, very much inspired by cp5magic by Karsten Schmidt (toxi)
	    see the ControlP5annotation example for further details
	    
	   	* src controlP5/ControllerAutomator.java:
	   	for internal use only, handles the reflection for the annotation implementation
	   	
	   	* src controlP5/FieldChangedListener.java:
	   	for internal use only, listens for changes of variables linked to controllers 
	   	(needs to be anabled, disabled by default)	   	
	   	
     	* src controlP5/ScrollList.java:
     	ScrollList removed, use ListBox.
     	
 * src controlP5/ControllerGroup.java:
      moveTo(Tab) changed according to issue http://code.google.com/p/controlp5/issues/detail?id=15
      
 * src controlP5/ListBox.java,controlP5/DropdownList.java:
      adding mousewheel support.
      
 * src controlP5/CallbackEvent.java, controlP5/CallbackListener.java:
      adding new callback event and listener for controller actions such as enter, leave, pressed, released, releasedoutside.
      how to use see the ControlP5callback example       
      
 * src controlP5/Radio.java:
      removed, has been deprecated. Use RadioButton or CheckBox instead. 
      
 * src controlP5/ControlWindow.Pointer.java:
      adding a pointer class which can be used as replacement for mouse activity. To make use of the Pointer, 
      disable the mouse first and then set coordinates and events such as released and pressed from your program to 
      control controllers. see example ControlP5pointer


2011-05-08  Andreas Schlegel  <andi at sojamo.de>

 * version 0.5.9
      
 * src controlP5/ControllerInterface.java:
      adding method float[] arrayValue()
      
 * src controlP5/ListBox.java:
      adding addItems(String[]), which allows to add a string array to a ListBox or a DropdownList 
      automatically resulting in a list of listBoxItems

 * src controlP5/ControlEvent.java:
      adding method isFrom(String) and isFrom(ControllerInterface) to identify the origin of a Control Event 

2011-05-08  Andreas Schlegel  <andi at sojamo.de>

 * version 0.5.8

 * src controlP5/ListBox.java:
      Scrollbar (when visible) is now included inside the dimensions of a listbox (and its derivatives).

 * src controlP5/Textfield.java:
      Frame which surrounds a textfield is back again after being removed in version 0.5.7.
      
 * src controlP5/ListBox.java, controlP5/DropdownList.java:
      adding key support. up and down arrows can be used to scroll listbox or dropdownList,
      up and down, use shift+up/down for faster scrolling, use alt+up/down to jump to the
      top or bottom.  
      
 * shuffle    

2011-02-14  Andreas Schlegel  <andi at sojamo.de>

 * version 0.5.7

 * src controlP5/Controller.java, controlP5/ControllerGroup.java:
      toString now prints out Type, name and value instead of all details including position, etc.
      detailed information can now be accessed through method info().
      
 * src controlP5/Controller.java, controlP5/ControllerGroup.java:
      adding method info() print out details such as position, visibility, label, id, etc. of
      a Controller or ControllerGroup.
       
 * src controlP5/ListBox.java:
      adding ControlListeners to ListBox, will also be inherited 
      by DropdownList.
		      
 * src controlP5/ControlWindowKeyHandler.java:
      Key combination ALT-L and ALT-S have been removed. 
      ControlP5 setups cant be saved at this point anymore. But 
      ControllerProperties have been introduced instead to save
      properties for single controllers - how to use ControllerProperties
      see the examples and source code of controlP5/ControllerProperties.java
      and controlP5/ControllerProperty.java
            
 * src controlP5/Textfield.java:
      Introducing a new text-cursor. Frame which surrounds a textfield has been removed.
      	
 * src controlP5/Slider.java, Slider2D.java,
      controlP5/Knob.java, controlP5/Numberbox.java:
      adding shuffle() command, when called, a random value will be set
      for the controller.
       
 * src controlP5/Knob.java:
      Caption Label was missing, now back.
      
 * controlP5/Slider2D.java:
      absolute, relative positioning issue resolved.
      see http://forum.processing.org/topic/three-problems-i-m-having-with-controlp5
      
 * src controlP5/ControlP5IOHandler.java:
      Loading and saving controllers in xml format has been removed due
      to incompletness. Alternatively ControllerProperties are introduced 
      with this release, see below for more details.
       
 * src controlP5/ControlWindow.java:
      Adding setPositionOfTabs() to change the origin of the tab bar. 
      Use controlP5.window().setPositionOfTabs(PVector) or 
      controlP5.window().setPositionOfTabs(int,int)  
      
 * src controlP5/ControlP5Base.java:
      Adding saveProperties(String) and loadProperties(String) to 
      save and load  serialized controller properties inside a file.
       The range of controllers implementing save/load properties is yet 
      limited to Slider, Knob, Numberbox, Toggle, Checkbox, 
      RadioButton, Textlabel, Matrix,Range, textarea, ListBox, Dropdown, 
      colorPicker. Properties are currently saved in the java serialization 
      format but xml and possibily json alternatives are being worked out. 	
      
 * src controlP5/ControllerProperty.java:
      Adding controller property. Controllers can register properties which 
      can be saved in a serialized format. 
      
 * src controlP5/Matrix.java:
      Adding setMode(int), please refer to to the documentation which 
      constants to use - cells can be activated by row, column, many-per-row-and-colum
      
 * src controlP5/CColor.java:
      Fields changed from protected to private, use setter and getter 
      to change color values. CColor is serializable so that instances can
      be saved as properties.
      
 * src controlP5/Accordion.java:
      Adding new class Accordion, an Accordion allows similar behavior 
      as a common UI accordion, here it combines ControlGroups where 
      one or no group can be active at a time.
      
 * src controlP5/CVector3f.java:
      Removed. Replaced with processing.core.PVector.
      
 * src controlP5/ControlP5.java:
      Removing setFilePath(), setUrlPath(), urlPath(), filePath()
      
 * src controlP5/ControlP5XMLElement.java,
      ControlP5/ControlP5XMLParseException:
      removed.
      
 * src controlP5/ControlP5.java:
      Adding convenience method window() which returns the controlWindow 
      of the sketch, before one had to use window(PApplet)
      
      
2010-11-07  Andreas Schlegel  <andi at sojamo.de>

 * version 0.5.6	
      
 * src/controlP5/ListBox.java: 
      adding updateListBoxItems() to update color changes.
      adding scoll() calls to color related methods to update color 
      changes for currently active listBox buttons.
      
 * src/controlP5/ListBox.java:
       adding item(Controller) to access a ListBoxItem by it's Button reference.
            
 * src/controlP5/ControlWindow.java:
      use isMouseOver(Controller), getMouseOverList() to check 
      if the mouse is inside a specific controller. This does not work for 
      groups, only for controllers.
      
       
      

2010-10-07  Andreas Schlegel  <andi at sojamo.de>

 * version 0.5.5	
      
 * src/controlP5/ControlP5.java: 
      enableShortcuts() and disableShortcuts() were interchanged, fixed now.
      
       
      
2010-09-30  Andreas Schlegel  <andi at sojamo.de>

 * version 0.5.4	
      
 * src/controlP5/RadioButton.java: 
      adding setNoneSelectedAllowed(true/false) default is true. 
      http://forum.processing.org/topic/controlp5-radiobutton-strange-behaviour
      
 * src/controlP5/DropdownList.java:
      renaming PulldownMenu to DropdownList.
      
 * src/controlP5/Range.java
      setMin() and setMax() bug fixed.
      
 * src/controlP5/ControlBroadcaster.java:
      adding addListner(), removeListener(), getListener()
      any object that implements ControlListener can register with the ControlBroadcaster to
      receive ControlEvents broadcasted.
      
 * src/controlP5/BitFontRenderer.java:
      fixed ArrayIndexOutOfBoundsException
      only characters between ASCII 32 and 127 are supported.
      
 * src/controlP5/ControlP5.java:
      disabled clear() call (called from within dispose()) when in applet mode. 
      Reason: all controllers will be cleared due to dispose call 
      when switching tabs. Fix required. 
      
 * src/controlP5/Button.java:
      colorForeground and colorActive are reveresed due to adding an active state to buttons
      when clicked. Rollovers no display colorForeground, clicked buttons will display
      colorActive. This also affects ListBoxItems.
      
      
2010-08-18  Andreas Schlegel  <andi at sojamo.de>

 * version 0.5.3
      
 * src/controlP5/ListBox.java:
      adding clear(). clears a ListBox in order to re-filling list.
      
 * src/controlP5/ListBox.java:
      changing behavior of a ListBox-Button. 
      a ListBox-button is clicked, it will call the Button's onLeave() 
      and setIsInside(false) function to solve problem addressed here:
      http://forum.processing.org/topic/controlp5-listbox-loses-mouseclicks
       
 * src/controlP5/ListBox.java: 
      adding actAsPulldownMenu() to enable/disable pulldown 
      functionality for a ListBox.
      
 * src/controlP5/PulldownMenu.java:
      new Controller, extends ListBox, acts as a pulldown-menu.
      
      
2010-08-03  Andreas Schlegel

 * version 0.5.2
 * Slider2D: a new Controller, 2D slider control.
 * Button, Bang, Toggle, : setImage() defines an image for DEFAULT,OVER,ACTIVE,HIGHLIGHT mode.
 * Button, Bang, Toggle, : setImages() defines an image for DEFAULT,OVER,ACTIVE,HIGHLIGHT mode.
 * Button: adding setSwitch() in order to use a button as a switch (makes toggle obsolete)
 * Button: adding booleanValue() returns true or false, useful in case a button is set to be a switch.
 * Button: adding setOn() setOff(), useful when button is a switch.
 * Toggle: changing default look to ControlP5.SWITCH, an on/off look for toggles. use toggle.setMode(ControlP5.DEFAULT) to reset to the old default look.
 * ControllerDisplay: adding interface ControllerDisplay to enable custom displays for a controller.
 * Controller: setImage, allows to replace the default look of a controller with an image (PImage).  
 * Controller: setDisplay allows custom displays for controller. the custom display is called from within a controller's draw function. A custom Display implements interface ControllerDisplay
 * Controller: adding lock(), unlock(), isLock(), setMoveable(), isMoveable(), isUserInteraction(), setUserInteraction()
 * Controller: adding plugTo(), unplugFrom() (if this causes any problems or error message, please report)
 * ControlP5: adding java.util.logging.Logger for logging error, debug, info messages - wrapped in ControlP5.error(), ControlP5.warning(), ControlP5.info(), ControlP5.debug() 
 * ControlP5: added registerDispose()
 * ControlP5: adding setMoveable() and isMoveable() to disable/enable controllers to be moved around.
 * ControlP5: adding disableShortcuts(), enableShortcuts() instead of disableKeys() and enableKeys()
 * ControlP5: deprecating lock(), unlock(), disableKeys(), enableKeys()
 * ControlWindow: adding begin() and end(). this allows to move controllers automatically to the main window or a separate controlWindow.
 * Toggle: adding setValue(boolean)
 * Matrix: mouseReleasedOutside error fixed.    
 * ControlWindow: window is now properly removed when closed, thanks henri.
 * TextLabel: adding setControlFont()
 * Knob: all new.
          	
2010-04-04  Andreas Schlegel

 * version 0.5.1
 * ControlP5: lock() and unlock() are working again.
 * ControlEvent: added function id() to make access to the id of  controller, group, tab, etc. easier
 * ControlEvent: added function type() for easier distinguishing between the type of Controller the event was triggered from, returns ControlEvent.UNDEFINED, ControlEvent.CONTROLLER, ControlEvent.TAB, ControlEvent.GROUP 
 * ListBoxItem: adding ListBoxItem to make changes to each item of a listBox especially the color settings of a listBoxItem.
 * CColor: now with getter and setter functions, supports changing the value of the alpha channel.
 * ControlWindow: adding begin() and end(). this allows to move controllers automatically to the main window or a separate controlWindow.
 * ControllerGroup: adding enableCollapse(), disableCollapse(), isCollapse() to enable/disable the collapsing and opening of a controllerGroup e.g. listBox.
           	
2010-03-26  Andreas Schlegel

 * version 0.5.0
 * making transition to 1.5+, no more java 1.4 support.
 * compiling against processing 1.1
 * ControlP5: added disableKeys() and enableKeys(), suggested in the discourse. disables and enables keyEvents such as hide/show with ALT-h.
 * Toggle: when inactive, the color refers to colorBackground instead of colorForeground now.
 * ControlFont: smooth related functions have been disabled and deprecated due to processing 1.1 changes.
 * Slider: use alignValueLabel() to position the value label of a slider on TOP, CENTER, or BOTTOM
 * example ControlP5quick: new, ControlP5quick shows how to quickly add Controllers with auto-arrangement.
                
2010-02-16  Andreas Schlegel

 * version 0.4.7
 * Slider: adding TickMarks and replacing steps with snapToTickMarks().
 * ControlWindow: adding setUndecorated(), isUndecorated(), toggleUndecorated()
 * ControllerSprite: sprites are now clone-able and state management has been improved, thanks to c.a. church. http://processing.org/discourse/yabb2/YaBB.pl?num=1265905257
 * Controller: adding getSprite() 
 * BitFontRenderer: adding warning for character that are not supported by the BitFontRenderer.
       	  
2010-02-06  Andreas Schlegel

 * version 0.4.6 
 * ControlWindow: imageMode was not set back to CENTER/CORNER correctly, now fixed.
 
0.4.5

 * ControllerGroup: adding moveTo(String). will move ControllerGroups such as e.g. Textarea to another tab.

0.4.4

 * ControlWindow: imageMode CENTER/CORNER issue fixed.

0.4.3

 * Controller.isInside is private now. use setIsInside(true/false) and getIsInside() to access this boolean field.
 * trying to solve the problem of overlapping described here:
      http://processing.org/discourse/yabb2/YaBB.pl?num=1259885420/0#0
      yet not successful, but loops managing the mouseEvents have been reversed from i++ to i--
 * CheckBox,RadioButton: adding activateAll, activate, deactivate, getState to CheckBox and RadioButton to be able to control individual items by code.
 * CheckBox: adding toggle() to CheckBox to be able to toggle individual items of a checkBox.
 * CheckBox,RadioButton: adding  setItemHeight(), setItemWidth() to radioButton and checkBox
 * Toggle: adding toggle()
 
0.4.2



0.4.1

 * Controller: added changeValue() to change the float value of a controller without broadcasting its change as a event. 
 * Numberbox: added setMultiplier() and multiplier() to customize the value sensitivity.
 * Toggle: setLabelVisible() is now working.
 * ControlWindow: adding setTitle, showCoordinates, hideCoordinates to ControlWindow. only applies to controlWindows of type PAppletWindow (external window).
 * adding Matrix.set
 * Controller: Controller.isInside() is public now
 * added ControlFont. does not support textarea and textfield yet.

(note: take a look at subversion changelog generator http://ch.tudelft.nl/~arthur/svn2cl/)

0.3.15

 * Texfield: textfield scrolls to the left if text is larger than display area.
 * Knob: knob setValue issue solved.

 * BitFontRenderer: removed getWidth(String theText, int theFontIndex) 
      is now getWidth(String theText, Label theLabel);
      removed getWidth(String theText, int theFontIndex, int theLength))
      is now getWidth(String theText, Label theLabel, int theLength));


0.3.14

 * ScrollList: adding void hideScrollbar()
      adding void showScrollbar()
      adding void showScrollbar()
      adding void scroll(float)
      adding boolean isScrollbarVisible()

 * Textarea: adding void hideScrollbar()
      adding void showScrollbar()
      adding void showScrollbar()
      adding void scroll(float)
      adding boolean isScrollbarVisible()

 * Textfield: textinput now works from a controlWindow

 * Label: adding adjust() to fix the cutting off of Labels when changing fonts.
      use e.g. mySlider.captionLabel().setFont(ControlP5.grixel).adjust();

0.3.13

 * Textfield: adding setAutoClear(true/false) prevents the textfield to be cleared after pressing RETURN.
      adding clear(), clears the current textline
      adding keepFocus(true/false)
      adding getTextList()
      adding setAutoClear(true/false)
      adding isAutoClear()
      adding submit()

0.3.12

 * Radio: if deactiveAll is set before the first button is added, the first button will not trigger an event.
 * ControlGroup: added method getBackgroundHeight() to get the height of a group's background that has been set before.
 * Textfield: fixed bug with clearing the variable myTextline too early.

0.3.11

 * Textfield: added method setText to Textfield
 * Range: made corrections to Range, _myUnit was not set properly. now fixed. Range remains experimental.

0.3.10

 * fixed little issues with setColor, again.
 * removed decimal point when setDecimalPrecision(0)

0.3.9

 * Range: defautValue for min shows correct value now.
 * Radio: added deactivateAll()
 * TextLabel: added setWidth, setHeight
 * setColor -Label(), -Active(), -Value(), -Foreground(), -Background(): issues resolved and tested for slider, range, button, knob, sliderlist, multilist, toggle, radio
 * Controller: added method setDecimalPrecision(int theNum) to set the decimal precision for floats when displayed as valueLabel. the precision does not apply to the returned float value.
      Controller.captionLabel().set("txt") is fixed.
 * ControlP5: controlP5.setAutoDraw(true/false) issue is fixed.
 * ControlWindow: controlWindow.post() has been deleted.
 * Knob: issue with minimum value has been resolved.

how to move a textlabel that has been created with "new" to another tab than the default:
Tab myTab = controlP5.addTab("new");
Textlabel myTextlabel = new Textlabel(this,"a single textlabel.",20,100,400,200,0xffff0000,ControlP5.synt24);
myTab.addDrawable(myTextlabel);


