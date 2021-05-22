`ts-type-error` uses Vue 3.0.8. `works` uses Vue 3.0.7. The two projects are otherwise identical.


`works` builds correctly and runs correctly.


`ts-type-error` fails to build with the following error:


    ERROR in src/App.vue:36:15
    TS2345: Argument of type '{ readonly bar: string; log: () => void; }' is not assignable to parameter of type 'Foo'.
      Property 'baz' is missing in type '{ readonly bar: string; log: () => void; }' but required in type 'Foo'.
        34 |   methods: {
        35 |     clickHandler() {
      > 36 |       usesFoo(this.foo);
           |               ^^^^^^^^
        37 |     }
        38 |   }
        39 | })
