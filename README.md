# README

* Implementing Action Cable


## Sidekiq commands

* bundle exec irb -r ./worker.rb, 
* bundle exec sidekiq -r ./worker.rb 

OR 


## Sidekiq :

* bundle exec sidekiq -q default  - to run sidekiq

* config.autoload_paths += %W(#{config.root}/app/workers) - In application.rb

* Classname should be same as file name.

```
Eg : HardWorker.perform_in(5.seconds, "Abhishek", 10)
```


1. Bundle exec sidekiq
2. Sidekiq::Queue.new.size

## In console

* rails c
* Require ’sidekiq/api’

```
OurWorker.perform_at(20.seconds.from_now, "C")
 => "7e32b5fc27e62df366202038" 
 Sidekiq::ScheduledSet.new.size
 => 5
```
### DBMS important command

```
SELECT city FROM weather WHERE temp_lo = max(temp_lo);     WRONG
but this will not work since the aggregate max cannot be used in the WHERE clause. (This restriction exists because the WHERE clause determines the rows that will go into the aggregation stage; so it has to be evaluated before aggregate functions are computed.) However, as is often the case the query can be restated to accomplish the intended result, here by using a subquery:
SELECT city FROM weather
    WHERE temp_lo = (SELECT max(temp_lo) FROM weather);
```



# To open gem in VS code:

* EDITOR="code" bundle open devise

