<h1 align="center"><a href="#"><img src="https://static.zorin.space/assets/media/logos/ZorinProjectsSP.svg" alt="Image"></a></h1>

<h1 align="center">Aura GO SDK</h1>


## ✨ Key Features

- zero-reflection JSON decoder for high throughput,
- compile-time validation against the OpenAPI 3.0 spec,
- first-class `context.Context` support,
- pluggable middleware (`http.RoundTripper`, retries, tracing, …).

## 📦 Installation

```bash
go get github.com/localzet/aura-sdk-go@latest
````

---

### Dependencies
- `Go` (>=1.24)

## 🚀 Usage

Here’s a quick example to get you started:

```go


import (
	"context"
	"fmt"
	aura "github.com/localzet/aura-sdk-go/api"
)

func main() {
	ctx := context.Background()

	rclient, _ := aura.NewClient(
        // URL to your panel (ex. https://example.com or http://127.0.0.1:3000)
		"AURA_BASE_URL",
		// Bearer Token from panel (section: API Tokens)
        aura.StaticToken{Token: "AURA_TOKEN"},
	)

	resp, err := rclient.NodesControllerGetAllNodes(ctx)
	if err != nil {
		panic(err)
	}
	fmt.Println(resp)
}
```