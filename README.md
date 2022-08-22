# J.A.T.E.

## Description

This app is a PWA text editor.

---

## Table of Contents

* [Installation](#installation)
* [Usage](#usage)
* [Code Snippets](#code-snippets)
* [Technology](#technology)
* [Credits](#credits)
* [Testing](#testing)
* [License](#license)

---

## Installation

This app has been deployed to heroku. Upon visiting the site, the user can click the "install" button to install the app locally, or can use it in a web browser.

---

## Usage

The user can enter text into the text editor. The text will be saved in the database, so it will persist if the page is reloaded or closed and revisited. 

The user can use the text editor app without an internet connection.

---

## Code Snippets

```javascript
export const getDb = async () => {
  console.log('GET all from the database');
  const jateDb = await openDB('jate', 1);
  const tx = jateDb.transaction('jate', 'readonly');
  const store = tx.objectStore('jate');
  const request = store.get(1);
  const result = await request;
  console.log('Retrieved!', result);
  return result.value;
};
```

getDB opens the 'jate' database in a readonly transaction. It objectStore's the database. The database is then returned.

```javascript
export const putDb = async (content) => {
  console.log('PUT to the database');
  const jateDb = await openDB('jate', 1);
  const tx = jateDb.transaction('jate', 'readwrite');
  const store = tx.objectStore('jate');
  const request = store.put({ id: 1, text: content });
  const result = await request;
  console.log('Data saved to the database', result);
};
```

putDB takes content as a parameter. It opens the 'jate' database and sets the transcation to be able to read and write.It then puts the content to the database and console logs the result.

---

## Technology

Technology Used:
* [GitHub](https://github.com/)
* [GitBash](https://gitforwindows.org/)
* [Visual Studio Code](https://code.visualstudio.com/)
* [Javascipt](https://www.javascript.com/)
* [node.js](https://nodejs.org/en/)
* [Mongoose](https://mongoosejs.com/docs/)
* [Heroku](https://heroku.com)
* [Webpack](https://www.npmjs.com/package/webpack)

---

## Credits

All coding credited to Phillip Besse.

---

## Testing

There are no tests for this app.

---

## License

Phillip Besse's J.A.T.E. is licensed under the [MIT License](https://choosealicense.com/licenses/mit/).

MIT License

Copyright (c) 2022 Phillip Besse

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

---