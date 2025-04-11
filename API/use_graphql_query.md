### Příklady, jak použít:

graphql
```
type Todo @model {
  id: ID!
  name: String!
}
```

```
import { API, graphqlOperation } from '@aws-amplify/api';
import * as queries from './graphql/queries'; // Vygenerované Amplify CLI

async function fetchTodos() {
  try {
    const todoData = await API.graphql(
	  graphqlOperation(queries.listTodos)
	);
    console.log('Todos:', todoData.data.listTodos.items);
  } catch (error) {
    console.error('Chyba:', error);
  }
}

fetchTodos();
```

```
import { API, graphqlOperation } from '@aws-amplify/api';
import * as queries from './graphql/queries'; // Vygenerované Amplify CLI

async function fetchTodoById() {
  try {
    const todoData = await API.graphql(
      graphqlOperation(queries.getTodo, { id: '2' })
    );
    console.log('Todo:', todoData.data.getTodo);
  } catch (error) {
    console.error('Chyba:', error);
  }
}

fetchTodoById();
```

graphql/queries.js
```
query ListTodos {
  listTodos {
    items {
      id
      name
    }
  }
}

query GetTodo($id: ID!) {
  getTodo(id: $id) {
    id
    name
  }
}
```
Znak dolaru ($) v query označuje proměnnou ($id) v GraphQL, která umožňuje dynamicky zadat hodnotu pro argument id v getTodo. Díky tomu je query flexibilní a znovupoužitelná. $id: ID! říká, že proměnná je typu ID a musí být zadána.
