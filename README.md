# phwebs-cookiebar

Vue simple file component for displaying cookie bar with simple success and valid for 1 year.

## Installation

> npm install phwebs-cookiebar --save

## Dependencies

```json
"vue": "^2.6.14"
"vue-cookie": "^1.1.4"
```

## Usage

Before init your Vue application, you need to import a **vue-cookie** and **use** it for Vue.

```javascript
import Vue from "vue"
import VueCookies from "vue-cookie"

Vue.use(VueCookies)
```

Then place phwebs-cookiebar component in your root component.

```vue
<template>
    <div id="app">
        <!-- your other components -->
        <phwebs-cookiebar />
    </div>
</template>

<script>
    import PhwebsCookiebar from "phwebs-cookiebar"
    
    export default {
        components: {PhwebsCookiebar},
        data() {
            return {}
        }
    }
</script>
```