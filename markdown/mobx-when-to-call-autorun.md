Suppose we have a store

``` javascript
class AuthStore {
	@oberservable token
	@action loadToken() {
		const token = localStorage.getItem('token')
		// if token is valid
		this.getSomeData()
	}
	
	@action setToken(token) {
		this.token = token
	}

	@action getSomeData() {
		requestAgent.getSomeData()
		// then set data
	}
}

const authStore = new AuthStore()

autorun(() => {
	const { token } = authStore

	requestAgent.setAuthentication(token)
})
```

What would happen, when `authStore.loadToken` is called? Answer is, request failed for reason of 401.

`authStore.setToken` is called `authStore.loadToken`, yes, `authStore.token` is set as well. However, the autorun is called, after the load
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTY1ODA1MzcxXX0=
-->