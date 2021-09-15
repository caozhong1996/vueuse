---
category: Sensors
---

# useVirtualList

Virtual list migrating from ahooks to Composition API.

## Usage

```typescript
import { useVirtualList } from '.'

const { list, containerProps, wrapperProps } = useVirtualList(
  Array.from(Array(99999).keys()),
  {
    itemHeight: 22,
  },
)
```

```html
<template>
  <div
    v-bind="containerProps"
    style="height: 300px;"
  >
    <div v-bind="wrapperProps">
      <div
        v-for="ele in list"
        :key="ele.index"
      >
        Row: {{ ele.data }}
      </div>
    </div>
  </div>
</template>
```

<!--FOOTER_STARTS-->
## Type Declarations

```typescript
export interface UseVirtualListOptions {
  /**
   * item height, accept a pixel value or a function that returns the height
   *
   * @default 0
   */
  itemHeight: number | ((index: number) => number)
  /**
   * the extra buffer items outside of the view area
   *
   * @default 5
   */
  overscan?: number
}


export declare function useVirtualList <T = any> (
  list: T[],
  options: UseVirtualListOptions
): {
  list: T[]
  scrollTo: Function
  containerProps: {
    ref: Ref
    onScroll: Function
    style: { overflowY: String }
  }
  wrapperProps: Ref<{
    style: {
      width: String
      height: String
      marginTop: String
    }
  }>
}
```
<!--FOOTER_ENDS-->
