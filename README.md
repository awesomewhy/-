{
  "catalogs": {
    "default": "deny",
    "my_catalog": {
      "schemas": {
        "my_schema": {
          "allow": [
            {
              "user": "user1",
              "password": "password1"
            },
            {
              "user": "user2",
              "password": "password2"
            }
          ]
        }
      }
    }
  }
}



{
  "catalogs": {
    "file": {
      "schemas": {
        "*": {
          "owner": "admin",
          "permissions": {
            "select": ["alice"]
          }
        }
      }
    }
  },
  "catalogs-default": {
    "schemas": {
      "*": {
        "owner": "admin",
        "permissions": {
          "select": []
        }
      }
    }
  }
}

