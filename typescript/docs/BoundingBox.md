
# BoundingBox

Corner coordinates of the area surrounding the place.

## Properties

Name | Type
------------ | -------------
`left` | number
`bottom` | number
`right` | number
`top` | number

## Example

```typescript
import type { BoundingBox } from ''

// TODO: Update the object below with actual values
const example = {
  "left": null,
  "bottom": null,
  "right": null,
  "top": null,
} satisfies BoundingBox

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as BoundingBox
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


