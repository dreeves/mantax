okay

so you can get the user's email address on the page
and then you can confirm it
can we turn an email address into a substack id / username?


we need to be able to verify that the person predicting who *say* they own the substack profile
actually owns it
we could just link the logged in person
with a mantax id forever more
and track when people discover?


1. person predicts
   - provides email
2. if no mantax cookie
   3. "what is your email address"? enter email address (or glom from site)
      4. email sets cookie

oh! we could inject a button on scott's dashboard, which would have access to
the subscriber list and can verify the link between each subscribers
email and substack id

post /prediction
   - user id
   - email
   - subscription id
   - stripe user id



setting expectations
   - set expectations (might break the site, might not work, I might get bored)

   - I'm willing to try it for a bit
   - might break the site
   - just uses a score
   - this code will run in the browser of everyone who visits the site
      - that means technically I could take administrative actions using your account
         - in fact it kind of relies on that to get a subscriber list

   - this gives me personally a lot of power, but there's some things we could do to mitigate that
      - wholesale paste in the code
      - have the code come from a git endpoint that I make pull requests to
         - if you have someone you trust to verify it
   
   - we could expand this out to be able to make arbitrary predictions

   - could also use crypto, if that's easy enough

   - I don't want any money for this (unless expenses become a thing)
      - I'm currently working things out   



"here is my subscription id, which is not public"

- we can then verify that on scott's end



okay

so you could wait for the page to load

and then be like
   - see what the ban looks like

   - add a button to each comment
      - predict "scott will ban this"

   - operations
      - make prediction

      - get user scores to display next to name
         - cache a json object of users and scores for the article

         - we need something to support the batch retrival of many scores given a set of keys

         - and then any comments that have been added in the mean time get requested and added to the cache

         - given the users on the page
         - give back all user scores
         - (might have to fire as users are loaded in)
      
      - get predictions for this user (so as to color)

      - update scores (cron)
         - could 

   - that prediction then goes into a db
      - postgrest?
      - cloud flare worker KV?

      - whatever has the most generous free tier?
      - whatever can be bundled with compute to calculate the new bans?
      - you'll want caching on the calls to get the predictions

   - and needs to be reconciled whenver scott does ban something

   - needs to display that persons record


   - each person who predicts needs to be put in the db, and a record of their predictions tracked over time


   - each person starts with 100 credits and can fund bets they like

   - if they get below 10 they get topped up at the end of every week?
