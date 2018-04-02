# How to use swagger w/z docker

## swagger-editor

```
docker run -d -p 8080:8080 --name swagger-editor swaggerapi/swagger-editor
```

## swagger-ui

env.ui.list

```
# reload env for swagger-ui
API_URLS=[{name:'user', url:'src/user.yaml'}, {name:'team', url:'src/team.yaml'}, {name:'card', url:'src/card.yaml'}, {name:'date', url:'src/date.yaml'}]
```


```
alias swagger-ui='docker run -it --rm -v `pwd`:/usr/share/nginx/html/src/ -p 8081:8080 -d --name swagger-ui --env-file env.ui.list swaggerapi/swagger-ui'
```

## swagger-codegen

```
# generate Goloang source code.
docker run --rm -v `pwd`:/local swaggerapi/swagger-codegen-cli generate -i /local/src/sample_v2.yaml -l go -o /local/out/

# generate HTML Documents
docker run --rm -v `pwd`:/local swaggerapi/swagger-codegen-cli generate -i /local/src/sample_v2.yaml -l html2 -o /local/out/html/
```
