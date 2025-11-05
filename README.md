# my-new-project
Building AI Course project
<!-- This is the markdown template for the final project of the Building AI course, 
created by Reaktor Innovations and University of Helsinki. 

# Foghorn - find me the best route

Final project for the Building AI course

## Summary

Personalised app/portal that helps user to find the best route for any sport (e.g. cycling, canoeing, running) using route features, significantly enhanced by textual data from user prompts/reviews/qualitative preferences
On that basis, I created a POC focussed on two user cases - road bike and gravel bike


## Background

Which problems does your idea solve? How common or frequent is this problem? What is your personal motivation? Why is this topic important or interesting?

Finding suitable route is a tedious process, requiring lot of clicks through various portals, information often not complete, not aligned to personal preferences.
With multitudes of data available users are losing time and often not get a good result
Current routing applications or “portals” are typically one-dimensional (e.g. distance), but would not reflect qualitative views such as: what the users written about it, what my personal preferences are (e.g. training phase I am in, type of weather, what I like “long climbs”.

## How is it used?

User is any person seeking a route for sport or sport-like activity, whether for training purposes or leisure.
Instead of using existing apps and tediously filtering, the user can use natural language prompt such as "I want to do a 10k run in a forrest, that is not very hilly, accessible by car from my address in 10 minutes, with a parking lot. Has to be a round-trip. Typical user would be somebody training for half-marathon"
On that basis, I created POC focussed on road bike and gravel bike - Foghorn a routing assistant

## Data sources and AI methods
The data source are OSM maps, geocoding based on nominatim enhanced by smart algorithm to for example avoid routing to a location with the same name but in a different country.
The actual routing application is Graphhopper
The AI method is based on ollama with an option to use one of the small LLMs - such as mistral or llama. The development tested various degrees of quantisation. llama3.2 failed with complex location names and user preferences, mistral q3 not up to that task. llama3.1:latest mistral:latest provide reasonable performance and quality {those are models around 4 GB size, for details one can look at the comparisons of quantised models). A test was run for using llama for parsing and mistral for json instructions for Graphhopper. at the end, better case is using just one model.

## Challenges
The initial jave-script version proved to be very solid in terms of build, but difficult for integrating iterative routing UX requests. It works but not that great in practice. Further enhancements are recognized. "Legacy" solution - routing engine - not possible to replace by LLM, however, there is a case for tight integration and enhancements. All recognized for future pipeline - even better UX and even more options.
Hardware architecture and commmercial considerations limit a use of more sophisticated AI models - in the test phase.

Commercialisation is still an open question. Certainly, the AI drives a need for costly infrastructure and any further development would require investment in that. 

## What next?
IN theory, there are plenty options how to evolve this - in quality and user reach. Many enhancements could be added through the machine learning (by use) and through incorporating user/community feedback to provide superb experience....
In addition, the integrated approach to topology (map), route optimisation (path), geocoding (coordinates), direction (vectors) and multi-criteria based navigation through those (ad hoc, learned, interactive, specified) could be a re-usable model for any other purposes (combining virtual 3D environments and models plus navigation and routing through defined 3d space)....etc 

