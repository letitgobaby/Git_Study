# Thymeleaf + Vue.js(CDN) + IE11

- 화살함수 X

```
// before
(pram) => { 
  someFunc();
}

// after
function(param) {
  someFunc();
}
```

<br>

- 객체 줄여서 표시 X
```
// before
axios.post("/url", { data });

~~~
methods: {
  someFunc() {

  },

}
~~~


// after 
axios.post("/url", { data: data });

~~~
methods: {
  someFunc: function() {

  },
  
}
~~~


```

<br>

- API GET 한글 파라미터 불가

```
// before
const str = "한글";
axios.get("/url?str=" + str);


// after
const str = encodeURI(encodeURIComponent("한글")); // encode
axios.get("/url?str=" + str);

// in backend (ex java )
String decodeStr = URLDecoder.decode(param.get("str"),"UTF-8"); // decode

```