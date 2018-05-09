# Callbacks 09

```js
function higherOrder(arg1, arg2, callBack) {
	var err = null;
	var result = null;
	if((typeof arg1 == 'number') &&  (typeof arg2 == 'number'))	{
		result = arg1 + arg2;
		callBack(err, result);
	} else {
		err = 'result aint no number';
		callBack(err, result);
	};
};

function callBack(err, argument) {
	// if there was an error, don't use arguments
	//   it would break your code
	if(err) {
		console.log(err);
	} else {
		console.log(argument);
	};
};

higherOrder(4, 5, callBack);
higherOrder(4, '5', callBack);

```

[PythonTutor Link](https://goo.gl/6FkoZr)

---

## Step 0

__Predicted Happenings:__  
* __Global Context__   
  * _Objects_  
    a. higherOrder: Function  
    b. callBack: Function  
* __Other Contexts__  
  * no other contexts  
* __Behaviors:__
  * variables defined and hoisted, functions defined

__Actual Happenings:__  
* __Global Context__  
  * _Primitives_    
    a. var_variable: undefined  
    b. var_anonymous: undefined  
  * _Objects_    
    a. named: Function  
* __Other Contexts__  
  * no other contexts  
* __Behaviors:__
  * named function was created

---

## Step 1

__Predicted Happenings:__  
* __Global Context__  
  * _Primitives_    
    a. var_variable: undefined  
    b. var_anonymous: undefined  
    c. let_variable: "let"  
  * _Objects_    
    a. named: Function  
* __Behaviors:__
  * the let variable is created, since they aren't hoisted but are made just in time

Got this one right.

---

## Step 2

__Predicted Happenings:__  
* __Global Context__  
  * _Primitives_    
    a. var_variable: "var"  
    b. var_anonymous: undefined  
    c. let_variable: "let"  
  * _Objects_    
    a. named: Function  
* __Behaviors:__
  * "var_variable" is assigned a value

Got this one right.

---

## Step 3

__Predicted Happenings:__  
* __Global Context__  
  * _Primitives_    
    a. var_variable: "var"  
    b. var_anonymous: undefined  
    c. let_variable: "let"  
    d. let_anonymous: undefined  
  * _Objects_   
    a. named: Function 
* __Behaviors:__
  * "let_anonymous" will be created but not defined

__Actual Happenings:__  
* __Global Context__  
  * _Primitives_    
    a. var_variable: "var"  
    b. var_anonymous: undefined  
    c. let_variable: "let"  
  * _Objects_    
    a. named: Function  
    b. let_anonymous: Function  
* __Behaviors:__
  * "let_anonymous" was created and defined


Turns out "let" variables are constructed __and__ given values in the same step.  In other words: "let" variables are not created until they are defined in the file.

___

## Step 4

__Predicted Happenings:__  
* __Global Context__  
  * _Primitives_    
    a. var_variable: "var"  
    c. let_variable: "let"  
  * _Objects_    
    a. named: Function  
    b. let_anonymous: Function  
    c. var_anonymous: Function  
* __Behaviors:__
  * "var_anonymous" will be created and defined

Got this one right.


___
___
### <a href="http://elewa.education/blog" target="_blank"><img src="https://user-images.githubusercontent.com/18554853/34921062-506450ae-f97d-11e7-875f-6feeb26ad72d.png" width="100" height="40"/></a>











