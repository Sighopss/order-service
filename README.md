# Order-Service

RESTful API for order processing and management.

## Technology Stack

- Node.js
- Express.js
- MongoDB with Mongoose

## API Endpoints

- `GET /health` - Health check
- `GET /api/orders` - Get all orders
- `GET /api/orders/:id` - Get order by ID
- `POST /api/orders` - Create new order
- `PATCH /api/orders/:id` - Update order status
- `DELETE /api/orders/:id` - Delete order

## Local Development

```bash
npm install
npm start
```

For development with auto-reload:

```bash
npm run dev
```

Application will be available at http://localhost:3002

## Environment Variables

- `PORT`: Server port (default: 3002)
- `MONGODB_URI`: MongoDB connection string (default: mongodb://localhost:27017/petstore)
- `NODE_ENV`: Environment (development/production)

## Docker Build

```bash
docker build -t order-service:latest .
docker run -p 3002:3002 order-service:latest
```

## Health Check

```bash
curl http://localhost:3002/health
```

## Example API Calls

### Create Order

```bash
curl -X POST http://localhost:3002/api/orders \
  -H "Content-Type: application/json" \
  -d '{
    "productId": "product123",
    "quantity": 2
  }'
```

### Get All Orders

```bash
curl http://localhost:3002/api/orders
```

### Update Order Status

```bash
curl -X PATCH http://localhost:3002/api/orders/order123 \
  -H "Content-Type: application/json" \
  -d '{
    "status": "processing"
  }'
```

