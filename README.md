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
