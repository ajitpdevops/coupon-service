# coupon-service

docker network create microservices

docker run --name postgresdb -p 5432:5432 -e POSTGRES_USER=postgres --network microservices -e POSTGRES_PASSWORD=postgres -d postgres

docker build -t couponservice .

docker run --name couponapp -p 8080:8080 -e SPRING_DATASOURCE_URL=jdbc:postgresql://postgresdb:5432/postgres -e SPRING_DATASOURCE_USERNAME=postgres -e SPRING_DATASOURCE_PASSWORD=postgres -e SPRING_PORT=8080 --network microservices -d couponservice

docker tag couponservice:latest 243302161856.dkr.ecr.us-east-1.amazonaws.com/coupon:latest
docker push 243302161856.dkr.ecr.us-east-1.amazonaws.com/coupon:latest


jdbc:postgresql://postgres.ckcrtwddlse1.us-east-1.rds.amazonaws.com:5432/postgres
