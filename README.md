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

