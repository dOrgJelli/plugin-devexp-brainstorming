```typescript
import { examplePlugin } from "./typescript";

const client = new PolywrapClient({
  plugins: [{
    name: "example", // -> "plugin/example"
    plugin: examplePlugin(...)
  }]
})

client.invoke({
  uri: "ens/example-interface.eth/1.0.0",
  method: "commonMethod"
});

client.invoke({
  uri: "plugin/example",
  method: "typescriptSpecificMethod"
});
```

# Use a plugin in your wrapper?
```graphql
#import { Module } into Interface from "ens/example-interface.eth/1.0.0"

...
```

```typescript
export moduleMethod() {
  Interface.commonMethod()
}
```
