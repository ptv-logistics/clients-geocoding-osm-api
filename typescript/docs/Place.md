
# Place


## Properties

Name | Type
------------ | -------------
`referencePosition` | [ReferencePosition](ReferencePosition.md)
`boundingBox` | [BoundingBox](BoundingBox.md)
`formattedAddress` | string
`category` | string
`type` | string

## Example

```typescript
import type { Place } from ''

// TODO: Update the object below with actual values
const example = {
  "referencePosition": null,
  "boundingBox": null,
  "formattedAddress": null,
  "category": null,
  "type": null,
} satisfies Place

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as Place
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


