```
SELECT o.order_id, o.product, o.quantity FROM orders o INNER JOIN customers c ON o.customer_id = c.customer_id WHERE c.name = ‘Viraj Sharma’;
```