# Full Cycle GraphQL Server

This repository contains a graphql server built during the full-cycle course

## Tecnologies

- go  
- graphql  
- sqlite3

## How to run the graphql server

To run the service, execute the following command in the terminal:

```bash
go mod tidy
go run cmd/server/server.go
```

## How to test

To test the graphql server first run the server and go to localhost:8080
after this user this queries to try 

```bash
mutation createCategory {
  createCategory(input: {name: "Tecnologia", description: "Cursos de tecnologia"}) {
    id
    name
    description
  }
}

mutation createCourse {
  createCourse(
    input: {name: "Full Cycle", description: "The best", categoryId: "99425d61-5fd1-494e-896f-666338b91b1d"}
  ) {
    id
    name
  }
}

query queryCoursesWithCategory {
  courses {
    id
    name
    category {
      name
      description
    }
  }
}

query queryCourses {
  courses {
    id
    name
  }
}

query queryCategories {
  categories {
    id
    name
  }
}

query categoriesWithCourses{
    categories {
    id
    name
    courses {
      id 
      name
    }
  }
}
```

Note: These queries can be used to create categories and courses, and retrieve them in different ways using GraphQL queries.
