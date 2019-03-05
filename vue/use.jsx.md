# 在vue中使用jsx时需要注意的语法

## v-model
```js
{
  props:['value']
}

this.$emit('input',value)
```  
## $attrs / $listeners
```js
const attributes = {
  attrs:this.$attrs,
  on:this.$listeners
}
```  
```jsx
<tag ...attributes></tag>
```  
## slot
```jsx
<tag>
  {this.$slot.default}
</tag>
```
## slot-scope
```jsx
// parent
<tag>
  {
    this.$scopedSlots.default({data})
  }
</tag>
```  
```jsx
// children
const scopedSlots = {
  scopedSlots:{
    default:scope=>(<span>{scope.data}</span>)
  }
}

<Parent {...scopedSlots}></Parent>
```