FROM hseeberger/scala-sbt:11.0.10_1.5.2_3.0.0 AS scala-builder
COPY . /app
WORKDIR /app
RUN sbt app/assembly

FROM adoptopenjdk/openjdk11:jre
COPY --from=scala-builder /target/scala-3.0.0/$name;format="space,snake"$.jar /app
WORKDIR /app
EXPOSE 4000
CMD ["java", "-jar", "$name;format="space,snake"$.jar"]