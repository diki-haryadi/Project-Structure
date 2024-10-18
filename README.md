# Project-Structure
  This project structure refers to [golang-standards/project-layout](https://github.com/golang-standards/project-layout)

    root-project/
    ├── README.md               # Project description
    ├── LICENSE                 # Project license
    ├── Makefile                # Build scripts and common commands
    ├── go.mod                  # Go module
    ├── go.sum                  # Dependency list
    ├── api/                    # API definitions (e.g., gRPC protocol)
    │   ├── graphql/            # GraphQL API definitions
    │   ├── grpc/               # gRPC API definitions
    │   │   ├── api/            # gRPC API implementation
    │   │   │   ├── client.go   # gRPC client implementation
    │   │   │   ├── info/       # Directory for gRPC info
    │   │   │   ├── pb/         # Directory for protocol buffers
    │   │   │   └── server.go   # gRPC server implementation
    │   ├── rest/               # REST API definitions
    │   │   ├── api/            # REST API implementation
    │   │   │   ├── routes/     # Routes for REST API
    │   │   │   └── server.go   # Server setup for REST API
    │   └── worker/             # Worker API definitions
    │       ├── consumer/       # Consumer for messages
    │       └── scheduler/      # Scheduler for tasks
    ├── build/                  # Build-related files
    │    └── package/            # Package-related files
    │        └── Dockerfile      # Dockerfile for building the application
    ├── cmd/                    # Contains main applications
    │   ├── graphql/            # GraphQL application
    │   │   └── graphql.go      # Entry point Cobra Command for GraphQL app
    │   ├── grpc/               # gRPC application
    │   │   └── grpc.go         # Entry point for gRPC app
    │   ├── rest/               # REST application
    │   │   └── rest.go         # Entry point Cobra Command for REST app
    │   ├── worker/             # Worker application
    │   │   ├── consumer/       # Consumer for messages
    │   │   │   └── consumer.go # Entry point Cobra Command for consumer
    │   │   └── scheduler/      # Scheduler for tasks
    │   │      └── scheduler.go # Entry point Cobra Command for scheduler
    │   └── root.go             # Entry point for the root Cobra Command
    ├── configs/                # Configuration files
    │   └── configs.go          # Configuration Global
    ├── deployments/            # Deployment-related files
    │   └── docker-compose.yml   # Docker Compose configuration file
    ├── docs/                   # Project documentation
    │   ├── api/                # API documentation
    │   ├── architecture/       # Architecture documentation
    │   └── images/             # Images related to documentation
    ├── internal/               # Code that can only be used by this project
    │   ├── application/        # Application logic
    │   │   ├── adapters/       # Adapters for external services
    │   │   │   └── info/       # Info related adapters
    │   │   │       └── info.go # Info adapter
    │   │   ├── controllers/    # Controllers for handling requests
    │   │   │   └── info/       # Info related controllers
    │   │   │       └── info.go # Info controller
    │   │   ├── presenters/     # Presenters for formatting responses
    │   │   │   ├── request/    # Request related presenters
    │   │   │   │   └── FindInfoDetailByIDRequest.go # Find info detail request
    │   │   │   └── response/   # Response related presenters
    │   │   │       └── InfoDetailResponse.go # Info detail response
    │   │   ├── repositories/   # Repositories for data access
    │   │   │   └── info/       # Info related repositories
    │   │   │       ├── info.go     # Info repository
    │   │   │       ├── info_mock.go # Mock for info repository
    │   │   │       └── interface.go # Info repository interface
    │   │   └── usecases/       # Use cases for application logic
    │   │       └── info/       # Info related use cases
    │   │           ├── add_info.go # Use case for adding info
    │   │           ├── find_info.go # Use case for finding info
    │   │           ├── find_info_test.go # Tests for finding info
    │   │           └── interface.go # Info use case interface
    │   ├── domain/             # Domain models
    │   │   └── entities/       # Domain entities
    │   │       └── info/       # Info related entities group
    │   │           └── info.go # Info entity definition
    │   └── pkg/                # Internal packages
    │       ├── database/       # Database related code
    │       │   ├── nosql/      # NoSQL database connection code
    │       │   └── sql/        # SQL database connection code
    │       ├── logger/         # Logging utilities
    │       └── utils/          # Utility functions
    ├── pkg/                    # Code that can be used by other projects
    │   ├── pkg1/               # Package global for used all application
    ├── scripts/                # Scripts for development and deployment
    │   └── setup.sh            # Setup script
    ├── test/                   # Contains test files
    │   ├── testdata/           # Test data
    │   └── integration_test.go  # Integration test
    └── migrations/             # Database migration scripts
        └── 20210101_init.sql   # Initial migration script
