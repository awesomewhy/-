CREATE TABLE tpch.region (
  regionkey bigint,
  name varchar,
  comment varchar
) ENGINE = Log;

CREATE TABLE nation (
    n_nationkey UInt64,
    n_name String,
    n_regionkey UInt64,
    n_comment String
) ENGINE = Log;

assertThat(((String) computeScalar("SHOW CREATE VIEW " + viewName)))
    .matches("(?s)" +
        "CREATE VIEW " + catalogName + "\\." + schemaName + "\\." + viewName + ".* AS\\s+" +
        "SELECT \\*\\s+" +
        "FROM\\s+" +
        "nation");

        
assertThat(((String) computeScalar("SHOW CREATE VIEW " + viewName)))
        .matches("(?s)" +
                "CREATE VIEW \\Q" + catalogName + "." + schemaName + "." + viewName + "\\E\\s+AS\\s+" +
                "SELECT \\*\\s+" +
                "FROM\\s+" +
                "nation");


CREATE TABLE Orders (
    o_orderkey UInt64,                          -- Идентификатор заказа
    o_custkey UInt64,                           -- Идентификатор клиента
    o_orderstatus FixedString(1),               -- Статус заказа (один символ)
    o_totalprice Float64,                       -- Общая цена заказа
    o_orderdate Date,                           -- Дата заказа
    o_orderpriority String,                     -- Приоритет заказа
    o_clerk String,                             -- Клерк, оформивший заказ
    o_shippriority Int32,                       -- Приоритет доставки
    o_comment String                            -- Комментарий к заказу
) 
ENGINE = MergeTree()
ORDER BY o_orderkey;


