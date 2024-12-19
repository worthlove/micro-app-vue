<template>
  <div style="width: 100px;height: 100px;background-color: yellowgreen;">{{arr}} - {{str}}</div>
</template>

<script setup lang="ts">
const arr = [1,2,3,4,5,6,7,8,9,10]
const str:String = '123456789'

// Bug修复：将number类型转换为string类型
function arrayStringConversionFn (arr:Array<number>):String {
  let str:String = ''
  for (let i = 0; i < arr.length; i++) {
    // Bug修复：使用toString()方法将number类型转换为string类型
    str += arr[i].toString()
  }
  return str
}

// 使用修复后的函数
const convertedStr = arrayStringConversionFn(arr)

// 打印结果
console.log(convertedStr) // 输出："123456789"
console.log(str) // 输出："123456789"
console.log(arr)

</script>
<style scoped></style>
