# README

## ENDPOINTS  
All endpoints are prefixed with `/api`

### /requests
#### POST /requests
To create a new request you need to include authentication headers.
You also need to provide :title=String and :description=String, and nothing else.
The response will be a 200 with a message and the id of the created resource
```
{ message: 'Your reQuest was successfully created!', id: <resource_id> }
```
If auth is missing, devise will throw the following with 401:
```
{"errors"=>["You need to sign in or sign up before continuing."]}
```
If a param, e.g. description is missing, you will get 422:
```
{ message: 'Description can't be blank' }
```
If a non-permitted param is sent, you will get 422:
```
{ message: 'found unpermitted parameter: :body' }
```

All devise endpoints are available at /auth.
Read more [here](https://devise-token-auth.gitbook.io/devise-token-auth/).
