!SLIDE bullets incremental

# Modern App Architecture #

* App/UI Servers
* Low Latency Datastores
* Background Processing

!SLIDE bullets incremental

# App/UI Servers #

* ![heroku](heroku.png)
* ![duostack](duostack.png)
* ![cloudfoundry](cloudfoundry.png)


!SLIDE bullets incremental

# Low Latency Datastores #

* ![mongo](mongodb.png)
* ![couch](couchdb.png)
* ![redis](redis.png)
* many more...


!SLIDE bullets incremental

# Background Processing #

* Open Source: DelayedJob, Resque, Workling
* ![peter](background-peter.png)


!SLIDE ruby-code smaller

# Ruby Code #

    @@@ ruby

    def import_users
      @friends = @twitter.get_all_friends

      t1 = Time.now
      @count = User.transfer_to_mongo(@friends)
      t2 = Time.now

      flash[:success] = "#{@count} users copied to MongoDB in #{t2 - t1} seconds"
      redirect_to :action => :index
    end