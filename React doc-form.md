## React Doc-form

## 1.what is a 'controlled component'?

 _*its a javascrip function that handles the submission of the form and has access to the form*_

 ## Should we wait to store the users responses from the form into state when they submit the form OR should we update the state with their responses as soon as they enter them? Why.

 _*No,since handlechange function runs on every keystroke to update the react state ,the displayed value will update as the user types*_ 

 ## How do we target what the user is entering if we have an event handler on an input field?
 _*the input value is always driven by the rect state while this means you have to type a bit more code you cn pass the value to other UI elemants too , or reset from other event handler*_

 ## Why would we use a ternary operator?
 _*to shorter code by written if statement in one line*_
 ## Rewrite the following statement using a ternary statement: if(x===y){ console.log(true);} else {console.log(false);}

 x==y ? console.log('true') : console.log ('false')
 