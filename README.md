## Sleepy

#### A RESTful framework for Go

Sleepy is a micro-framework for building RESTful APIs.

```go
package main

import (
    "net/url"

    "github.com/dougblack/sleepy"
)

type Item struct {
<<<<<<< HEAD
    sleepy.BaseResource
=======
>>>>>>> da9d8e922d0198a324af1f1b6df97d3e1d5938aa
}

func (item Item) Get(values url.Values) (int, interface{}) {
    items := []string{"item1", "item2"}
    data := map[string][]string{"items": items}

    return 200, data
}

func main() {
    item := new(Item)

    var api = new(sleepy.Api)
    api.AddResource(item, "/items")
    api.Start(3000)
}
```

Now if we curl that endpoint:

```bash
curl localhost:3000/items
{"items": ["item1", "item2"]}
```

Stay tuned.

## License

Sleepy is released under the [MIT License](http://opensource.org/licenses/MIT).
