# Fetch Commands

```js
const options = {
    method: 'POST',
    mode: 'cors', // no-cors, *cors, same-origin
    cache: 'no-cache', // *default, no-cache, reload, force-cache, only-if-cached
    credentials: 'same-origin', // include, *same-origin, omit
    headers: {
        'Content-Type': 'application/json' // 'application/x-www-form-urlencoded'
    },
    redirect: 'follow', // manual, *follow, error
    referrerPolicy: 'no-referrer', // no-referrer, *client
    body: JSON.stringify(data) // body data type must match "Content-Type" header
}
const json = await (await fetch(`${url}/api/books`, options)).json();
```

## Form Data

```js
const formData = new FormData();
const fileField = document.querySelector('input[type="file"]');

formData.append('username', 'abc123');
formData.append('avatar', fileField.files[0]);

const options = {
    method: 'PUT',
    headers: {
        'Content-Type': 'application/x-www-form-urlencoded'
    },
    body: formData
}
const json = await (await fetch(`${url}/api/books`, options)).json();
```
