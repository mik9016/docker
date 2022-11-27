FROM php:7.2-apache
COPY ./main.php ./
EXPOSE 8080

CMD [ "php", "-S", "0.0.0.0:8080" ,"./main.php"]

# docker  run -p 8080:8080 --rm -v $(pwd):$(pwd) php:7.2-apache php -S 0.0.0.0:8080  $(pwd)/main.php