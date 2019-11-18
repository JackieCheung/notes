**Js添加、读取、删除cookie，判断cookie是否有效，指定domain域下主路径path下设置cookie，设置expires过期时间**

*https://www.cnblogs.com/codeon/p/7403418.html*



**原生js删除指定域名的cookie**

`function deleteDomainCookies(domain) {`
    `for (var i = 0; i < cookies.length; i++) {`
        `var cookie = cookies[i];`
        `if (cookie.indexOf(domain) != -1) {`
            `var eqPos = cookie.indexOf("=");`
            `var name = cookie.substr(0, eqPos);`
            `document.cookie = name + "=; expires=Thu, 01 Jan 1970 00:00:00 GMT; domain=" + domain;`
        `}`
    `}`
`}`



**js-cookie中文文档**

*https://blog.csdn.net/qq_20802379/article/details/81436634*

[js-cookie官方文档](https://github.com/js-cookie/js-cookie/tree/latest#readme)