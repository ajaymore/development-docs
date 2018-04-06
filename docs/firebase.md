# Firebase

## Create project through firebase console

## Local project Setup

```
mkdir firebase-boilerplate && cd firebase-boilerplate
exp init MobileClient
create-react-app webclient
firebase init
```

### Server setup

### MobileClient

### WebClient


### firebase.json
The app name comes from index.ts
```
"rewrites": [
  {
    "source": "**",
    "destination": "/index.html"
  },
  {
    "source": "/app",
    "destination": "helloWorld"
  }
]
```
`firebase serve --only functions,hosting`