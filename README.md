# ObjMakerJS
A JQuery plugin for dynamic creation of JS objects in the DOM
Allows the user to dynamically compose a Javascript object that is arbitarily composed of floats, strings, arrays and nested-objects.
instantiate a div/span:
```html
<div id="maker_space"></div>
```
then instantiate:
```javascript
var maker = $("#maker_space").makeObjEditor()
```
get-and-set:
```javascript
maker.set({bananas:55,melons:3})
console.log(maker.get())
```
or attach change handler
```javascript
maker.setRefreshHandler(function (obj) {console.log("oh - a change!"); console.log(obj);})
```
:-)

# Options

instantiation either by:
```javascript
$("#maker_space").makeObjEditor(args)
```
Or
```javascript
$.makeObjEditor("#maker_space", args)
```
either case will return an object with callable functions:
* get() - return the javascript object from the object maker
* set(obj) - setup the maker according to supplied object
* setRefreshHandler(func) - func will be called with the maker's object every time a change is made
* resetConfig(config) - sets the maker to behave according to the new supplied config (config specification following)

the arguments 'args' that these two above functions take are:
* obj - the javascript object to set the maker to initially
* config - the configuration of the maker instance (config specification following)

# Config

the configuration of the maker obeys sensible defaults, however these can be changed. the object can be composed of:
* include_spacers - boolean, true or false whether or not to insert 'spacer' divs between elements (can be usefull for styling - default = false)
* refreshHandler - function called with maker's object as first parameter everytime the object is changed (default = do-nothing)
* modifiable_form - boolean, true or false whether or not the User can modify the form of the object, or only just its values (default = true)
* class_names - the names of all the classes used, recognised and assigned throughout the maker's operation (defaults below)
* drop_labels - the labels used from the 'select-type' drop-down boxes, can redily be changed but should be unique (defaults below)

# Default Class_Names

```javascript
{
    string_content:"string_content",
    numeric_content:"numeric_content",
    array_content:"array_content",
    object_content:"object_content",
    sub_element:"sub_element",
    content:"content",
    container:"container",
    spacer:"spacer",
    additional:"additional",
    needed:"needed",
    duplicate:"duplicate",
    name_box:"name_box"
}
```

# Default Drop_Labels

```javascript
{
    None:"",
    String:"String",
    Number:"Number",
    Array:"Array",
    Object:"Object"
}
```

