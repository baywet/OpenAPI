# OpenAPI extension: x-ms-sse-terminal-event

This extension is used to flag which event is the terminal event in a text/event-stream response. It is a boolean extension to be used on any/oneOf members. Only single entry per any/oneOf collection is permitted.

## Schema

```yaml
type: boolean
```

## Example

```yaml

openapi: 3.2.0
info:
  title: Example of streaming with terminal event.
paths:
  /audio/speech:
    post:
      responses:
        '200':
          content:
            text/event-stream:
              itemSchema:
                discriminator:
                  propertyName: type
                anyOf:
                  - $ref: "#/components/schemas/Foo"
                  - $ref: "#/components/schemas/Finished"
                    x-ms-sse-terminal-event: true
```

Used by: (informational)

* [TypeSpec](https://typespec.io)