FROM php:8.1 AS builder
WORKDIR /app
COPY . .
RUN docker-php-ext-install pdo pdo_mysql

FROM php:8.1-alpine
WORKDIR /var/www/html
RUN apk add --no-cache bash
COPY --from=builder /app .
RUN docker-php-ext-install pdo pdo_mysql
RUN chmod +x wait-for-it.sh
EXPOSE 8000
CMD ["php", "-S", "0.0.0.0:8000"]
