- - -
Now we need to create a Provider that wraps the entire Application(App).
![[Pasted image 20240313162205.png|800]]
- - -

### A Query is just getting data from Somewhere.
### A Mutation is changing some type of data.

Our Custom Data 
![[Pasted image 20240313162646.png|500]]

### useQuery and useMutation are two hooks that come with React-Query Library.
- - -

## Query ->
![[Pasted image 20240313174822.png|600]]
We have a unique query key that identifies that particular query. We can write multiple values inside the queryKey Array.
'queryFn' will run to query our data. We can either use fetch API OR Axios inside it to fetch data. This function always accepts a PRomise. So we want to return a PROMISE.

![[Pasted image 20240313175525.png|600]]
We can see that there are Multiple inbuilt functions and states of our Query.
![[Pasted image 20240313185236.png|600]]

OUTPUT
![[Pasted image 20240313185311.png|300]]

### Lets say we have to submit a new data. For that after submitting we have invalidate the Current to make the NEW QUERY load.
![[Pasted image 20240315190930.png|600]]
- - -

## Query Key
In React Query, the query key is a unique identifier for a query. It is used to cache the results of the query and to determine when the query should be refetched.

The query key can be a string or an array. If it is an array, the first element of the array must be a string. The remaining elements of the array can be any serializable value.
```javascript
// A string query key
useQuery('todos', ...)

// An array query key with a string and a number
useQuery(['todos', 1], ...)

// An array query key with a string and an object
useQuery(['todos', { id: 1 }], ...)
```
You can use multiple arguments in the query key to uniquely identify a query. This is useful for hierarchical or nested resources, or for queries with additional parameters.

For example, you could use the following query key to fetch a todo item with the ID of 1:
```javascript
useQuery(['todos', 1], ...)
```

You could also use the following query key to fetch all of the todo items for a specific user:
```javascript
useQuery(['todos', { userId: 1 }], ...)
```

When you use multiple arguments in the query key, React Query will cache the results of the query separately for each unique combination of arguments. This means that if you fetch the todo item with the ID of 1 and then fetch the todo item with the ID of 2, React Query will cache the results of each query separately.
This can be useful for performance reasons, as it can prevent React Query from having to refetch the same data multiple times.

### But, how do we invalidate the nested queries ?
```javascript
const handleInvalidateQuery = () => { invalidateQueries(['todos', 1]); // Invalidating the query with key ['todos', 1] };
```
---
## Caching ->
![[Pasted image 20240423070911.png|500]]
It means that the Data will remain Fresh i.e. the data will remain in the cache for 1000 ms before it turns STALE.
So, if the user requests the data within 1000ms , it will fetch from the Cache otherwise it will be Refetched from the main Database.