# webapi-app-Dockerize


*Steps to use this Dockerfile:*

**Step 1:** Buiding an image.

`docker build -t webapi:latest .`

**Step 2:** Creating a bridged network between containers.

`docker network create webapi-net`

**Step 3:** Running a mongodb service.

`docker run --name mongodb --network webapi-net mongo:latest`

**Step 4:** Running the webapi container.

`docker run -d  --network webapi-net -p 3000:3000 webapi`



## API Reference

#### Get all items

```http
  GET localhost:3000/movies
```

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `api_key` | `string` | **Required**. Your API key |

#### Get item

```http
  GET localhost:3000/favorites
  Data stored in mongodb after POST method is done 
```

| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `id`      | `string` | **Required**. Id of item to fetch |


```http
  POST localhost:3000/favorites    
```

| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `type`    | `string` | **Required**. Id of item to fetch |
| `movie`   | `string` | **Required**. Id of item to fetch |
| `url`     | `string` | **Required**. Id of item to fetch |

