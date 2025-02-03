# modern-rx-cheatsheet
Cheatsheets? Guide? for Mordern Rhymix Development. this guidelines using in [zodkr](https://github.com/zodkr)

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
