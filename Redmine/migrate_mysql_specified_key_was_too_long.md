# Mysql2::Error: Specified key was too long; max key length is 767 bytes.

Create file with  the following content.   
```
File path : [REDMINE PATH]/config/initializers/ar_innodb_row_format.rb
Content :

ActiveSupport.on_load :active_record do
    module ActiveRecord::ConnectionAdapters
        class AbstractMysqlAdapter
            def create_table_with_innodb_row_format(table_name, options = {})
                table_options = options.reverse_merge(:options => 'ENGINE=InnoDB ROW_FORMAT=DYNAMIC')
                create_table_without_innodb_row_format(table_name, table_options) do |td|
                    yield td if block_given?
                end
            end
            alias_method_chain :create_table, :innodb_row_format
        end
    end
end
```


Change mysql conf.   
```
File path : /etc/mysql/mariadb.conf.d/50-server.cnf
Content:

innodb_large_prefix = 1
innodb_file_format = barracuda
innodb_file_per_table = 1
```   


Done.


# Reference
http://www.redmine.org/issues/23586#note-8
