# Pathway Presenter presentation
## Intro slide
- Hi I'm Jacob Windsor, a bachelor student at the Maastricht Science Programme.
- I'm applying for the google summer of code project with the national resource for network biology.
- Given the project I am proposing, it seems appropriate to give a presentation that accompanies the written proposal.
- I would like to create a WikiPathways "Pathway Presenter".
- In short, this will allow researchers to create dynamic presentations from the pathway diagrams in WikiPathways. They can then share them and even embed them into other presentation formats, such as PowerPoint.

## What is WikiPathways?
- WikiPathways is an open and collaborative database for biological pathways.
- Each pathway page features an interactive pathway diagram.
- Below is a static version of the miRNA biogenesis pathway in humans
- In WikiPathways, you can zoom and pan around the diagram. Clicking on the pathway nodes will open up a useful pop-up filled with extra annotation information.

## The problem?
- You already saw one of the problems in the previous slide [go back to previous slie], I couldn't embed the interactive pathway into this presentation. But, nor would I want to with the way it is used at the moment. A presenter can't use their mouse to zoom around a diagram or open the annotations pop-up in the middle of a lecture.
- [Go to next slide] That is one problem but it is part of a larger issue with pathway diagrams in general...

# Pathways can be confusing
- They can be confusing
- This is the MAP kinase signalling cascade.
- It's extremely large with many sub-networks. Clearly, it would take some time and effort to study and understand it

# Can we do something
- So the quesition is, can we do something about this?
- [click] Of course we can

# Improving Educational Capabilities
- I am currently working on my thesis titled "Extending WikiPathways to Improve educational capabilities".
- I am doing this at the BiGCaT department in Maaastricht University
- This GIF is a working prototype of the end goal of my project.
- In a Proteopedia style way, clicking on links within the pathway's accompanying description the visualisation of the diagram is changed.
- You can highlight nodes, zoom into them or just pan to them. Everything works with a single node, or groups of nodes. So if you need to zoom in on an interaction, just zoom into the interacting nodes and it will go to the center of all of them.
- This will help biologists understand the pathway diagrams much more easily. It creates a pathway "story" that is easy to follow.

# The Manipulation API
- So how have I achieved this?
- I have created a "Manipulation API" within Pvjs, the JavaScript library that renders pathway diagrams in WikiPathways.
- This simple API allows developer's to alter the pathway visualisation. 
- The description links simply fire one of the API methods

# Can we do more?
- Can we improve upon this some more?
- [click] Of course we can

# Pathway presentations
- I already mentioned how pathway "stories" increase the comprehensibility of pathways. The interactive descriptions are a great way of creating stories within the WikiPathways domain
- But what about all those times when pathways are not shown from WikiPathways? In presentations like this one, in blogs, in journal articles.
- I also mentioned earlier that it was an issue that I couldn't embed the interactive pathway in this presentation.
- The solution is pathway presentations that include a time aspect. 
- These presentations contain slides that each have a different pathway visualisation state. For example, the first slide may hide all but two metabolites, and the second would show two more and highlight them in different colours.
- This has a two fold effect: 
- Understandability is increased by allowing a time aspect. By only showing the viewer what they need to see at any one point in time, they don't become overwhelmed with information.
- It also provides a great means of sharing the interactive pathways in WikiPathways. You can include pathway presentations within other lectures without having to worry about dragging around the diagram. You just click through the different pathway slides and talk about each individually. 
- The same is true for other mediums such as blogs.

# Presentation editor
- I made this wireframe of the presentation editor interface. Apologies for my drawing skills
- In the center you see the pathway diagram rendered in the visualisation state as specified in the current slide
- At the bottom you see a preview of all the slides and can select one
- At the side you select what manipulation you want to perform and on which nodes. You may choose to zoom in, pan to, highlight or open the annotations pop-up. You can also animate each of the manipulations

# Pathway Presenter flow
- This pathway presenter relies on a few external libraries
- This diagram will show you how they all interact. In fact, it's quite similiar to what a pathway presentation will look like
- [click] you start off with the view. This could be the pathway presentation itself or the editor interface.
- [click] PathPresentJs, a JavaScript library that I will write, provides the presentation data to the view. This data contains information such as what pathway is being used, the title, a description, and the manipulation API methods to be called for each slide.
- PathPresentJs also provides methods that the view can activate. These are for creating and updating the presentations.
- [click] Pvjs, the library that renders pathway diagrams, is called by the view to render the pathway specified in the data. 
- Pvjs is actually a wrapper around a more generic library called Kaavio. Pvjs adds the bioligical functionality needed for WikiPathways
- The Manipulation API is called by the view with the methods specified in the presentation data. When it is called, it causes Pvjs to change the pathway visualisation.

# Looking forward 
- This project represents a starting point to allowing for high quality pathway presentations in WikiPathways

# Embed slide
- Embedding is a crucial feature that should be implemented into the pathway presenter as soon after the first product as possible. With the frameworks I have decided to use, this should be fairly easy to implement. You can find out more about the gory details of this in the written proposal
- [click] Text. Allowing for additional text in the slides is another feature that could be implemented after the first product. 
- [click] Hopefully, one day, these pathway presenations could be embedded in digital versions of journal articals from publishers. This would be a significant advantage over conventional static diagrams.

# Thanks for listening
- So, thank-you for sitting through my presentation
- The full written proposal is available online via the link below. 
- If you have any questions, or maybe even suggestions, then please contact me via email or twitter.
- I have a blog if you are interested. I recently wrote a post about my current thesis project
- Special thanks to my thesis supervisor's Egon Willighagen and Anders Riutta.
- Good-bye!
