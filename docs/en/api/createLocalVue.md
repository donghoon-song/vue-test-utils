# createLocalVue()

- **Returns:**
  - `{Component}`

- **Usage:**

createLocalVue returns a Vue class for you to add components, mixins and install plugins without polluting the global Vue class.

Use it with `options.localVue`

```js
import { createLocalVue, shallow } from 'vue-test-utils'
import { expect } from 'chai'
import Foo from './Foo.vue'

const localVue = createLocalVue()
const wrapper = shallow(Foo, {
  localVue,
  intercept: { foo: true }
})
expect(wrapper.vm.foo).to.equal(true)

const freshWrapper = shallow(Foo)
expect(freshWrapper.vm.foo).to.equal(false)
```

- **See also:** [Common Gotchas](common-gotchas.md)