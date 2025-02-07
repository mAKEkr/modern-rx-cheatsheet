# modern-rx-cheatsheet
Cheatsheets? Guide? for Mordern Rhymix Development. this guidelines written and applied in [zodkr](https://github.com/zodkr)

# Frontend

## remove all `jQuery` or `$`(jquery shorthand)
jQuery is too slow. be aware using jquery syntax and libraries.

We livin in 2025.

- jQuery.animate -> CSS Transition / Animation
- $(selector) -> document.querySelector(selector)
- $(selector).addClass(class) -> document.querySelector(selector).classList.add(class)

many other replacement options in 

## using `fetch` except for `exec_json` or `exec_xml` on Production Envrionment
```js
fetch(window.request_uri, {
  method: 'POST',
  body: JSON.stringify({
    module: 'module_name',
    act: 'action_name',
  }),
  headers: {
    _rx_ajax_compat: 'JSON',
    _rx_csrf_token: window.getCSRFToken()
  },
  credentials: 'include'
}).then(response => {
  const responseBody = response.json()
}).catch(err => {

})
```
