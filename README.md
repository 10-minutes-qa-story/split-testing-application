# split-testing-application

## How to setup
It's just a plain HTML files, you can open it in any browser

## How it works
You should open options.html file and then redirect will happen. It's pretty simple emulation of split testing application for user.
There are 2 options to specify which page you want to open:

- Explicitly specify "ab" parameter in query string. Available values are 1 and 2 (e.g. with /options?ab=2 you will be redirected to /options2.html)
- Set localstorage parameter "ab" to 1 or 2
- If none option specified the first implementation would be opened (option1.html)

### Decision table for redirecting
| ab Query param | ab LocalStorage param | Result page              |
| -------------- |---------------------- | ------------------------ |
| Not specified  | Not specified         | option1.html             |
| Not specified  | Specified             | value from local storage |
| Specified      | Not specified         | value from query param   |
| Specified      | Specified             | value from query param   |
