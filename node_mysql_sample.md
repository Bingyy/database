```js
const express = require('express');
const mysql = require('mysql');

const app = express();

// 创建一个连接对象
const db = mysql.createConnection(
{
        host: '10.212.47.232',
        user: 'bing',
        password: '*******',
        database: 'acme'
}
);

// 数据库连接
db.connect();

// URL 请求端点
app.get('/users', (req, res) => {
        const sql = 'SELECT * FROM users';
        db.query(sql, (err, result) => {
                if (err) throw err;
                res.send(result);
        });
});

app.listen(7000, () => console.log('Server started'));
```

#### 使用示例

`http://10.212.47.232:7000/users`

获取数据：

```json
[{"id":1,"first_name":"BING","last_name":"W","email":"bing@bingw.me","password":"123456","location":"ZJU","dept":"CCNT","is_admin":1,"register_date":"2019-05-08T07:35:28.000Z","age":21},{"id":2,"first_name":"Fred","last_name":"Smith","email":"fred@gmail.com","password":"123456","location":"New York","dept":"design","is_admin":0,"register_date":"2019-05-08T07:51:07.000Z","age":22},{"id":3,"first_name":"Sara","last_name":"Watson","email":"sara@gmail.com","password":"123456","location":"New York","dept":"design","is_admin":0,"register_date":"2019-05-08T07:51:07.000Z","age":23},{"id":4,"first_name":"Will","last_name":"Jackson","email":"will@yahoo.com","password":"123456","location":"Rhode Island","dept":"development","is_admin":1,"register_date":"2019-05-08T07:51:07.000Z","age":24},{"id":5,"first_name":"Paula","last_name":"Johnson","email":"paula@yahoo.com","password":"123456","location":"Massachusetts","dept":"sales","is_admin":0,"register_date":"2019-05-08T07:51:07.000Z","age":25}]
```
