# Logger

[This is a middleware](https://github.com/kataras/iris/tree/master/middleware/logger)

Logs the incoming requests

```go
Custom(writer io.Writer, prefix string, flag int) iris.HandlerFunc
Default() iris.HandlerFunc
```

How to use

```go
package main

import (
    "github.com/kataras/iris"
    "github.com/kataras/iris/middleware/logger"
)

func main() {

    iris.UseFunc(logger.Default())
    // iris.UseFunc(logger.New(config.DefaultLogger()))

    iris.Get("/", func(ctx *iris.Context) {
        ctx.Write("hello")
    })

    iris.Get("/1", func(ctx *iris.Context) {
        ctx.Write("hello")
    })

    iris.Get("/3", func(ctx *iris.Context) {
        ctx.Write("hello")
    })

    iris.Listen(":80")
}

```