# 文档地址

- [员工端](https://youyingxiang.github.io/apidoc/docs/staff-client.html)

- [活动端](https://youyingxiang.github.io/apidoc/docs/yun-client.html)

# 这是什么？

这是项目的 API Specification，它使用 OpenAPI 来描述一个 api 的 url，请求体，请求头，返回头，返回体等。有了这个描述文件，就可以 mock 数据，生成代码，或者用来做 数据校验，测试等等。

# 为什么？

其实 API Specification 是个比较重要的东西，api 是项目的桥梁，所以保持一致性能够避免很多问题。

何为一致性？例如，你写了一份文档，前端照着文档写了代码，后端照着文档写了代码，测试测 api 时照着文档又写了一份代码。

这样，三个人有一份文档三份代码，他们都是靠人来维持一致，人会出错， 所以会出现下面的情况：

- 后端改代码，没有改文档，没有通知前端和测试，忘了。
- 或者改了文档，代码还没上。
- 或者代码和文档没对上，字段名手残写错了。

如何避免这个问题：`文档即代码`。以前有`代码即文档`，根据代码去生成文档。但那样并不好，只是解决了不用写文档的问题。这个问题，前端、后端、测试，其实是需要一个协议（Specification）来统一规范，生成代码，用这个 Spec 来描述你的 api，然后用它来生成可读文档或者代码或者 mock 数据。这样即使手残写错，也能错得一致，运行时不会出问题。

# 怎么用？

- 看一下 [OpenAPI](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.0.2.md) 怎么使用。或者参考已有的 [specs](./specs) ，再去看文档。

- 这个文件用了一个工具来生成一个可读的[API 文档](./docs)，redoc-cli。当你修改完一个 spec 之后，只需要:

  首次运行安装依赖

  ```
  yarn
  ```

  之后

  ```
  yarn build
  ```

  这样就可以生成新的文档，供人查看。

- 如果你需要使用 postman 进行测试，那么也很简单。[点此查看方法](https://learning.getpostman.com/docs/postman/collections/working_with_openAPI/)

- 如果你想用这些 specs 来生成请求代码，有 [openapi-generator](https://openapi-generator.tech/)

- 如果你想用 specs 来生成 mock 数据，有[prism](https://github.com/stoplightio/prism)

- 你还要？太累了，[自己看吧](https://openapi.tools/)
