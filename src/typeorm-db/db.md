### 关键字

- select

  - 查询 id select('id')：参数为查询项, 默认全部

- where

  - 逻辑判断 AND OR

    ```ts
    where("user.id = :id OR user.name = :name", { id: 1, name: "xm" });

    // andWhere
    .where("user.id = :id", { id: 1 })
    .andWhere("user.name = :name", { name: 'xm' })
    // orWhere
    .where("user.id = :id", { id: 1 })
    .orWhere("user.name = :name", { name: 'xm' })
    ```

- like

  ```ts
   .where("user.title like :title", { title: 'xxx' })
  ```

- having

- orderBy `DESC`升序 `ASC`降序

  ```ts
  .orderBy("user.id", "DESC")
  ```

- group-by

  ```ts
  .groupBy("user.name")
  .addGroupBy("user.id")
  ```

- limit

  ```ts
  limit(10);
  ```

- 取值
  - getOne
  - getMany

### 单表基础查询

```ts
const User = await this.User.getRepository(User)
  .createQueryBuilder("user") // 指定表
  .where("user.id = :id", { id: 1 }); // 条件
```

### nest 中应用

```ts
createQueryBuilder("tb_user"); // 表别名
```

-
