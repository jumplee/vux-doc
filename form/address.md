# Address

> Address 依赖于`Popup`, `Picker`, `Cell`

## Props

| 名字 | 类型 | 默认 | 描述 |
|-----|-----|-----|-----|
| title | String | 无 | 标题 |
| value | Array | [] | 表单值，`双向绑定` |
| list | Array | 无 | 地址库, address源码目录下有`list.json` |
| inline-desc | String | 无 | cell的子标题 |


## Demos

``` html
<template>
  <div>
    <group>
      <address :title="title" :value.sync="value" :list="addressData"></address>
      <cell title="上面value值" :value="value | json"></cell>
      <address :title="title2" :value.sync="value2" raw-value :list="addressData"></address>
      <address title="二级省市" :value.sync="value3" raw-value :list="addressData"></address>
    </group>
    <br/>
    <x-button type="primary" @click="changeData">改变数据</x-button>
  </div>
</template>

<script>
import { Group, Address, AddressChinaData, XButton, Cell } from '../components'

export default {
  components: {
    Group,
    Address,
    XButton,
    Cell
  },
  data () {
    return {
      title: '默认为北京',
      value: [],
      title2: '手动设定',
      value2: ['广东省', '深圳市', '南山区'],
      value3: ['海南省', '儋州市', '--'],
      addressData: AddressChinaData
    }
  },
  methods: {
    changeData () {
      this.value2 = ['430000', '430400', '430407']
    }
  }
}
</script>
```