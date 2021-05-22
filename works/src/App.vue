<template>
  <p @click="clickHandler">Sample TS Error: 
  {{foo.bar}}</p>
</template>

<script lang="ts">

import { defineComponent } from 'vue';

class Foo {
  constructor(readonly bar: string, private readonly baz: string) {
    console.log(bar);
    console.log(baz);
  }
  log(): void {
    console.log(`Bar: ${this.bar}, Baz: ${this.baz}`)
  }
}

function usesFoo(foo: Foo) {
  foo.log();
}


export default defineComponent({
  name: 'App',
  data() {
    const foo = new Foo('bar', 'baz');
    usesFoo(foo);
    return {
      foo
    }
  },
  methods: {
    clickHandler() {
      usesFoo(this.foo);
    }
  }
})
</script>
