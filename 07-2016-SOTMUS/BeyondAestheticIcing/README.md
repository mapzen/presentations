1. Hi, I’m Meghan and I’m Ekta. 
Meghan: We are going to talk today about a project we’ve worked on together at Mapzen--Transitland--and about how we are using design to make better, friendlier geo tools

2. Ekta: This is us at State of the Map last year at the UN in New York. So happy and excited with all the geo folks with no idea that we were going to be up here speaking this year!
Meghan: I’m a Software Engineer at Mapzen with a background in urban planning. I’m working on building accessible platforms for exploring and understanding the urban environment and the ways people move through it--walking, biking, transit and driving.
Ekta: I’m a User Experience Designer at Mapzen. I spend most of my time talking to people and understanding how they use our services and how Mapzen tools can better meet their needs.

3. Meghan: We are going to start today with this photo. How many people recognise where this photo was taken?

4. That’s right, Disney World

5. Many of you may have been to a Disney theme park. The Disney theme park experience is pretty unique--a lot of people travel great distances to visit these parks all over the world.

6. These theme parks have been so successful for so long because they draw you in and immerse you in the environment. The parks are fantastical, you can soar over London at night in a flying ship...

7. They are absurd...you can spin around in giant teacups...

8. And they are often seemingly magical, such as when it “snows” on a hot December night in Orlando, Florida.

9. So, who makes all the magic happen?

10. There are people whose job it is to create fun. To bring characters to life. 

11. Surround us with these experiences to immerse ourselves in by recreating the things we see in the movies. Except we are in the movie!

12. They are called the Imagineers.

13. People like Harriet Burns, a designer and the first woman hired to work for Walt Disney Imagineering.

14. The Disney Imagineering department is responsible for the entire theme park experience, from coming up with new attractions to figuring out how to create the illusion of things like fire, outer space or human-sized rodents people actually wait in line to see.

15. The Imagineers come from a really wide variety of professional backgrounds; there are artists, designers, architects, engineers, sound artists, lighting designers, project managers and more.

16. But hold up. Why are we talking about Disney so much? Isn’t this a talk on designing geo tools?

17. Don’t worry, you’re not in the wrong talk.

18. Honestly, it’s hard not to think about theme parks when working on a project with a name like Transitland.

19. Transitland is an open source project aggregating transit data from all over the world. It started at Mapzen, but is very much a community-driven initiative. 
Transitland is loosely coupled with OpenStreetMap. We conflate things like bus stop locations with the nearest OSM way ID, which provides a way to work with both OpenStreetMap data and the temporal data of transit schedules.

20. Transit networks can be fragmented, with multiple operators serving one region. For example, these are a few of the many operators serving the greater Seattle area. If you wanted to make a map showing all of the transit options available here, you’d have to gather data from all of these different operators.

21. In Transitland, all of this data is available in one place, making it super easy to get a holistic view of transit coverage. 
This is our goal--to create a centralized place, that is open and accessible to everyone, where the data is kept fresh through a healthy ecosystem of users and contributors. A place that is serious and trust-worthy but at the same time approachable and easy to use. Maybe even a little fun.

22. In short, we wanted to make working with transit data less like this…

23. And more like this…

24. Let’s go back to the imagineers, how would they think about this?
To make sure they are all meeting the high standards of epicness that is Disney, the Imagineers adhere to a set of principles called Mickey’s ten commandments.
(We recommend you check ‘em out.) Turns out, creating immersive theme park experiences has a lot in common with creating experiences for the web. And we found the Imagineers’ principles to be great guidelines for creating a similar user experience for Transitland.

25. 5 of those 10 principles particularly stood out to us and we would like to talk about how we applied them to create the Transitland Playground. 

26. Principle #1: Know your audience

27. We started by listing out all the different types of people who might be interested in using or contributing to Transitland. Some of them are..

28. But trying to make a tool that works for everyone is a foolish endeavor.
We wanted to narrow our list to meet the needs of a few but meet them well. It’s a hard decision.

29. Because Transitland is a completely open source project, we decided to focus on these three groups – community builders, app developers and data enthusiasts. We realized the involvement of these groups from the very beginning would be essential for creating engagement and start building the community we imagined.

30. Principle #2: organize the flow of people and ideas

31. Once we had narrowed down the users we would focus on, the next step was to identify their needs and create entry points to Transitland.
This is a chart showing how the different parts of the Transitland system connect. At the center is the Datastore, the heart of Transitland, where the data lives.
Transit operators release their data as a feed consisting of schedule times, routes, and stop locations. In the Datastore, we have 346 feeds, most of which have come from community contributions. Using the Feed Registry, you can browse information about all of these feeds, their operators, and also license information.

32. An API response to a Datastore query for routes would look like this JSON, which shows how the data would be formatted for each route.
The way this data is represented in the API response works well for some--app developers and data enthusiasts, for example. For others, though, it’s hard to look at this and understand a transit network and its coverage. We knew we’d need to make another entry point that presented the transit data in a different way.

33. An entry point that would abstract away some of the mechanics of this system and make it more comprehendible, and accessible.
Which brings us to the 3rd principle we wanted to discuss...

34. Principle #3: Communicate with visual literacy. This one is a little weird I know. Think of it more like “A picture is worth a thousand words.” The Disney imagineers really emphasized the use of rich imagery in their work. 

35. And what better visual tool to do this than a map!

36. We decided to build what we are calling the Transitland Playground, to give Transitland a visual language. The Playground is an interface to query and visualize Transitland data on a map. 

37. We looked at this before… this is a snippet of a JSON response about all the transit routes in Seattle. It represents just 1 of the 282 Seattle-area routes. But you get the idea. 

38. This is what the same information looks like represented visually. On a map. Right? (mind blown)
Not only does it tell you a better story of transit coverage in Seattle, it looks beautiful! It draws you in.

39. Another way to look at Seattle transit data is by operator; these shapes show operator service areas and help us understand transit coverage.

40. Another aspect you can look at is the density of transit stops in an area. This view shows number of stops as clusters from seven operators. Pause
Even if you don’t know much about Seattle, this map can be incredibly helpful. 

41. Principle #4: Avoid overload.

42. You don’t need to make everything available to everyone all at once.
In Transitland, there is a way to contribute data, there is a way to check what data is available, there is an API to query for data, and with the Playground, a way to view and analyze the data.

43.  If you have a lot of information, like we do in Transitland, dividing it into smaller parts that are distinct and clear can help people absorb and retain information.

44. It helps to use an analogy that people are already familiar with. We wanted to build a tool that allowed for querying Transitland without needing to know how to write a query. We used a “Madlibs”, or “fill-in-the-blank” format for constructing a request. This format allows people to step through building a query, but in a clear way that doesn’t require programming knowledge.

45. Principle #5: Tell one story at a time.

46. At Disneyland, you don’t worry about how the ride works, you just suspend your disbelief and know you are about to be immersed in a movie’s narrative, a Disney narrative.

47. When trying to surface the narrative of a large open source system like Transitland, we are trying to fade the mechanics of the system into the background. The Playground creates a way for people to be immersed in transit data and play with it without understanding the nuts and bolts of the Transitland system.

48. We intentionally designed a very linear way to build queries and look at the data. In this case, looking at routes by map view focused right here in Seattle.

49. All routes serviced by Sound Transit ONLY.

50. All the transit stops around Seattle University.
Each of these tell a different story or answer a different question.

51. You can use this too...
This approach can be used for any data set. The idea of a data playground doesn’t have to be limited to transit data. Any kind of data exploration can use a more visual approach. Projects like Overpass Turbo and Wheel Map are good examples of other interfaces that help us understand and use OpenStreetMap data.

52. To recap:
* Start by thinking about who will use the thing you are making and what they will get out of it. Don’t try to design for everyone. 
* This is especially important for open source projects like OpenStreetMap, where a community’s sense of ownership of a project is essential.
* Don’t forget you are designing for people, and often you are designing for a wide variety of people--not just other developers.
* Organize and present the information in a familiar and understandable way.
* Using visuals can help make abstract ideas more concrete.
* Aim to avoid overload by telling one story at a time

53. What lessons did we learn?
If you heard Katherine said this morning in her awesome keynote, building communities is always a work in progress. It requires care, patience and a lot of listening
* The Playground has been incredibly helpful to us while importing new data into Transitland, it’s been useful for answering questions about data coverage, and it’s provided a way to visualize the work we are doing in blog posts and in the press.
* It’s one of the main pages visited on the Transitland web site, and a lot of queries have been run using the Playground.
* But not all our assumptions were right. 
For example, one of the features we thought would be important to people was --the option to download the data resulting from a query
Turns out not so much. We haven’t seen too many data downloads and we are continuing to investigate why.
* It was important for us to make the Playground easy to understand. So we made the flow of building a query linear
You start with either routes, stops or operators and go deeper as you add filters such as a metro area or an operator name. This linear format although easy to understand ended up being too restrictive and didn’t allow for exploration.
* Also, people expressed the need to be able to interact with individual routes and stops on the map and get more detailed information about them but couldn’t do that. 
* And of course, the Playground is a very solo experience right now. We wanted people to be able to have conversations about what they were looking at.

54. This first version of the Playground has been very useful to us internally and has had positive reactions from the transit community. 
We are taking all of this into account as we continue to improve the way we visualize and understand transit data. We’re modifying the way users navigate the data--allowing them to freely explore the connections between operators, routes, and stops, and then focus in and get more details. We are also making it easier to share a link to the specific data you are interested in for discussion and analysis.
Finally, public transit is just one facet of a transportation network--we’re expanding our vision to include understanding how public transit systems connect to other modes of transportation, such as walking, biking, and driving.

55. (Applause) 

56. Questions.