# MongoDB Docker Setup

Simple MongoDB setup using Docker Compose with persistent data storage for development and testing.

## Quick Start

```bash
# Start MongoDB
docker-compose up -d

# Verify it's running
docker-compose ps

# Stop MongoDB
docker-compose down
```

## Configuration

| Setting | Value |
|---------|-------|
| Port | 27017 |
| Username | admin |
| Password | admin |
| Data Directory | `./mongo-data` |

## Connection Strings

```bash
# Standard connection with authentication
mongodb://admin:admin@localhost:27017/mydatabase?authSource=admin

# MongoDB Compass
mongodb://admin:admin@localhost:27017/?authSource=admin

# Direct admin database connection
mongodb://admin:admin@localhost:27017/admin
```

## MongoDB Shell Access

```bash
# Connect with authentication
docker exec -it mongo-mongo-1 mongosh -u admin -p admin --authenticationDatabase admin
```

## Data Management

Data persists in `./mongo-data` directory.

```bash
# Reset database completely
docker-compose down
rm -rf mongo-data
```

## Common Commands

```bash
docker-compose logs -f mongo    # View logs
docker-compose restart          # Restart
docker-compose down            # Stop and remove containers
docker-compose down -v         # Remove everything including volumes
```

## License

MIT License - see [LICENSE](LICENSE) file for details.