 To avoid hard coding credential data.
 Use environment variable or runtime parameters.

 ### set environment variable
 add configuration in ~/.profile or ~/.bash_profile
 ```
 export MY_DATA=value
 ```

 use environment variable in node code.
 ```javascript
 const mydata = process.env.MY_DATA;
 ```
