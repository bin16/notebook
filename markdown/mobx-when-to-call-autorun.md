Suppose we have a store

``` javascript
class AuthStore {
	@oberservable token
	@action loadToken() {
	
	}
	
	@action setToken(token) {
		this.token = tok
	}
}

const authStore = new AuthStore()

autorun(() => {
	const { token } = authStore

	requestAgent.setToken(token)
})
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE4NDUyMDkwMDJdfQ==
-->