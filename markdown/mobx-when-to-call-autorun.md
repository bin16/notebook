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

	requestAgent.setToken(token)
})
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTIwNjA4NTYzNV19
-->