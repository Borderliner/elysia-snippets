# ElysiaJS quick and useful snippets (Alpha)

* `elyctrl`
Creates an empty controller:

```typescript
export const ExampleController = new Elysia({ name: 'Controller.Example' })`
```

* `elycrud`

Creates a full CRUD rest controller:

```typescript
import { Elysia, t } from 'elysia'

export const ExampleController = new Elysia({ name: 'Controller.Example', prefix: '/examples' })
  .get('/', () => {

  }, {
    detail: {
      description: 'Get all examples'
    },
  })
  .get('/:id', ({ params: { id } }) => {

  }, {
    params: t.Object({
      id: t.Number()
    }),
    detail: {
      description: 'Get one Example'
    }
  })
  .post('/', ({ body }) => {

  }, {
    body: t.Any(),
    detail: {
      description: 'Create one Example'
    }
  })
  .put('/:id', ({ body, params: { id } }) => {

  }, {
    params: t.Object({
      id: t.Number()
    }),
    body: t.Any(),
    detail: {
      description: 'Edit one Example'
    }
  })
  .delete('/:id', ({ params: { id } }) => {

  }, {
    params: t.Object({
      id: t.Number()
    }),
    detail: {
      description: 'Delete one Example'
    }
  })
```

* `elymod`

Creates an empty model:

```typescript
export const ExampleModel = new Elysia({ name: 'Model.Example' })
  .model({
    id: t.Number()
  })
```
## Note: You may append `i` to any snippet shorthand to also import `Elysia` and `t` types. 

# License
Apache-2.0

# Created By
Mohammadreza Hajianpour ([Borderliner](https://github.com/Borderliner))