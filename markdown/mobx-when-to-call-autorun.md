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

What would happen, when `authStore.loadToken` is called? 

The answer is, request rejected for reason of 401. Because`@action authStore.setToken` is called in `@action authStore.loadToken`, yes, `authStore.token` is set as well. HOWEVER, the autorun is called, after the action `loadToken` is done.
<!--stackedit_data:
eyJoaXN0b3J5IjpbODA1MjQ0ODM1XX0=
-->