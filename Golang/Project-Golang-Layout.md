## Project-Layout
my-microservices-app/
├── cmd/
│   ├── user-service/
│   │   └── main.go
│   ├── product-service/
│   │   └── main.go
│   └── ...
├── internal/
│   ├── user/
│   │   ├── handler/
│   │   │   ├── user_handler.go
│   │   │   └── ...
│   │   ├── repository/
│   │   │   ├── user_repository.go
│   │   │   └── ...
│   │   ├── model/
│   │   │   ├── user.go
│   │   │   └── ...
│   │   └── service/
│   │       ├── user_service.go
│   │       └── ...
│   ├── product/
│   │   ├── handler/
│   │   │   ├── product_handler.go
│   │   │   └── ...
│   │   ├── repository/
│   │   │   ├── product_repository.go
│   │   │   └── ...
│   │   ├── model/
│   │   │   ├── product.go
│   │   │   └── ...
│   │   └── service/
│   │       ├── product_service.go
│   │       └── ...
│   └── ...
├── pkg/
│   ├── logger/
│   │   ├── logger.go
│   │   └── ...
│   └── ...
├── configs/
│   ├── user_config.yaml
│   └── product_config.yaml
├── test/
│   ├── user/
│   │   ├── user_handler_test.go
│   │   └── ...
│   ├── product/
│   │   ├── product_handler_test.go
│   │   └── ...
│   └── ...
├── scripts/
│   ├── deploy.sh
│   └── ...
├── docs/
│   ├── api_documentation.md
│   └── ...
├── Dockerfile
├── docker-compose.yml
└── README.md
