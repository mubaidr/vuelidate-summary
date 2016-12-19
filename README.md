# vuelidate-summary
A tiny tiny helper function to display summaries in vuelidate (https://github.com/monterail/vuelidate)

## What is this?
This is helper fucntion with vuelidate validation to get error messages for all form fields. 

## How to use?
Simple, just import index.js and add this code to your component. 

```
import {
    Summary
  } from 'utilities/validationSummary'
```

Register as computed property:

```
....,
computed: {
      ...,
      validationSummary: Summary
    },
....
```

and use it like this to display animated validation error message list: 
```
<div v-show="validationSummary.messages.length" class="alert alert-danger">
  <ul class="validation-list">
    <transition-group name="slide-fade" mode="out-in">
      <li v-for="message in validationSummary.messages" :key="message">
        {{message}}
      </li>
    </transition-group>
  </ul>
</div>
```

## Is this complete?
Nope. This script only generates messages for fields, validation groups are not supported (duplicate messages will apear if validation messages are used). 
