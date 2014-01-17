#LIKES ME

##Finds your best facebook photos!

* Best photos selected based on 
  * number of likes
    * 1 min
  * number of other people in the photo
    *4 max
* Photos can be sort by
  * total likes
  * likes by females only
  * likes by males only
* Photos can be export to dating websites - not implemented yet
  * OKCupid
  * tinder
  
  
##Visit at
HEROKU: http://likes-me.herokuapp.com

##Screenshots

![Example1](public/images/male_example.png)
1. Organize photos by popularity (All Likes, By Females, By Males)

![Example1](public/images/female_example.png)
2. Another example. Find your most liked images!

![Example1](public/images/male_example2.png)
3. Even more fun than facebook.

![Example1](public/images/female_example2.png)
4. Conveniently export to dating websites - not yet implememted

![Example1](public/images/male_example3.png)
5. *OKCupid* and *tinder* compatible - not yet implemented

##Testing!
![Testing coverage](public/images/test_coverage.png)

##Implementation
Incorporates Facebook's Graph API using the *Koala* gem.

Uses batched facebook queries to improved efficiency, and reduce API calls!
```ruby
results = graph.batch do |batch_api|
  batch_api.get_connections(photo["id"], "likes", {:limit => 25}, :batch_args => {:name => "get-likes", :omit_response_on_success => false})
  batch_api.get_objects("{result=get-likes:$.data.*.id}")  
end
````



