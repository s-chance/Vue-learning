## Vue学习记录

### 关于组件引入

使用export default时，对应的import语句不需要使用大括号；不使用export default时，对应的import语句需要使用大括号。

> export default命令用于指定模块的默认输出。显然，一个模块只能有一个默认输出，因此export default命令只能使用一次。所以，import命令后面才不用加大括号，因为只可能唯一对应export default命令

### 反应性变量

#### 组合式API

方式一：ref

```vue
<template>
  <p>{{ counter }}</p>
  <button @click.prevent="click">click</button>
</template>

<script setup>
import { ref, reactive } from "vue";

let counter = ref(0);

function click() {
  counter.value++;
}
</script>
```

方式二：reactive

```vue
<template>
  <p>{{ data.counter }}</p>
  <button @click.prevent="click">click</button>
</template>

<script setup>
import { ref, reactive } from "vue";

const data = reactive({counter: 0});

function click() {
data.counter++;
}
</script>
```

#### 选项式API

```vue
<template>
  <p>{{ data.counter }}</p>
  <button @click.prevent="data.counter++">click</button>
</template>

<script setup>
import { ref, reactive } from "vue";

// let counter = ref(0);
const data = reactive({counter: 0});

</script>
```

