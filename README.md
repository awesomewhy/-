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

