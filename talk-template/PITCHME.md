#Hello
This is the gitpitch template
footnote : "© 2017 Jason Rigden"

---?image=http://lofrev.net/wp-content/photos/2016/06/thundercats-logo_-1.png&size=auto 90%

---
This is anthorer

---

```
function test() {
  console.log("notice the blank line before this function?");
}
```
---
```ruby
require 'redcarpet'
markdown = Redcarpet.new("Hello World!")
puts markdown.to_html
```
---

```python
from time import localtime

activities = {8: 'Sleeping', 9: 'Commuting', 17: 'Working',
              18: 'Commuting', 20: 'Eating', 22: 'Resting' }

time_now = localtime()
hour = time_now.tm_hour

for activity_time in sorted(activities.keys()):
    if hour < activity_time:
        print activities[activity_time]
        break
else:
    print 'Unknown, AFK or sleeping!'
```

@[1](Python from..import statement)
@[3-4](Python dictionary initialization block)
@[6-7](Python working with time)
@[9-14](Python for..else statement)
