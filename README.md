# go-getresponse
A golang API client for [GetResponse V3](https://apidocs.getresponse.com/v3)

## Supported APIs
- [Contacts](https://apidocs.getresponse.com/v3/resources/contacts)

## Usage

```sh
go get github.com/arturwwl/go-getresponse/getresponse
```

```go
package main

import (
	"context"
    "log"
    "time"

    "github.com/arturwwl/go-getresponse/getresponse"
    "github.com/golang/protobuf/proto"
)

func main() {
    timeout := 5 * time.Second
    client := getresponse.NewClient("my get response api key", timeout)

    campaignID := "123"
    err := client.CreateContact(context.Background(), "jsmith@example.com", proto.String("John Smith"), nil, campaignID, nil, nil)
    if err != nil {
        log.Printf("Error creating contact in GR: %s", err.Error())
    }
}
```
