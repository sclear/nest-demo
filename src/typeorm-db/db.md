### 单表基础查询

```ts
const User = await this.User.getRepository(User)
  .createQueryBuilder("user") // 指定表
  .where("user.id = :id", { id: 1 }); // 条件
```
