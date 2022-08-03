# Employee Demo Schema

Import the data:

````
% /opt/couchbase/bin/cbimport json --format list -c http://1.2.3.4:8091 -u Administrator -p password -d file://employees.demo.json -b employees -g "%id%"
````

Build the indexes:

````
CREATE INDEX employees_record_id_ix ON employees(record_id) WITH {"num_replica": 1};
````

````
CREATE INDEX employees_store_id_ix ON employees(store_id) WITH {"num_replica": 1};
````

````
CREATE INDEX employees_employee_id_ix ON employees(employee_id) WITH {"num_replica": 1};
````
