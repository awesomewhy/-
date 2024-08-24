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
    o_orderkey UInt64,                          
    o_custkey UInt64,                           
    o_orderstatus FixedString(1),              
    o_totalprice Float64,                       
    o_orderdate Date,                        
    o_orderpriority String,                     
    o_clerk String,                          
    o_shippriority Int32,                      
    o_comment String                         
) 
ENGINE = MergeTree()
ORDER BY o_orderkey;


CREATE TABLE Customers (
    c_custkey UInt64,                        
    c_name String,                           
    c_address String,                         
    c_nationkey UInt64,                         
    c_phone String,                          
    c_acctbal Float64,                         
    c_mktsegment String,                        
    c_comment String                          
) 
ENGINE = MergeTree()
ORDER BY c_custkey;



