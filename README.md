# modern-rx-cheatsheet
Cheatsheets? Guide? for Mordern Rhymix Development. this guidelines written and applied in [zodkr](https://github.com/zodkr)

# Frontend

## remove all `jquery` or `$`(jquery shorthand)


## using `fetch` except for `exec_json` or `exec_xml`
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
