# reactive-r2db

#Follow the below confluence link for r2-postgracedc
Link- https://medium.com/zero-equals-false/dealing-with-postgres-specific-json-enum-type-and-notifier-listener-with-r2dbc-f15cc104aa10

Master Git link for R2DB : Gitlink:https://github.com/hantsy/spring-r2dbc-sample

#This git contains, how to save a String(Json) to postgraceDB in Jsonb format
1. Use io.r2dbc.postgresql.codec.Json dependency and type for json
2. Write JsonSerializer and deserializer and annotate in your enity object

    EX: @Table("tablename")
        class{
           ....
           ...
          @JsonSerialize(using = PgJsonObjectSerializer.class)
          @JsonDeserialize(using = PgJsonObjectDeserializer.class)
          @Column("customerfacilityentity")
          private Json customerfacilityentity;
          
          }
          
3. you can convert a string(json) to Json(r2db type json) by the method using 'Json.of("your json")' and set In the entity object.
4. Refer to this below link for the git code and before refering to the git read the above confluence page.
  Gitlink:https://github.com/hantsy/spring-r2dbc-sample/tree/master/data-r2dbc-repositories



Note: You can also achieve this using the below approach.
  link: https://medium.com/@nikola.babic1/mapping-to-json-fields-with-spring-data-r2dbc-and-reactive-postgres-driver-1db765067dc5

