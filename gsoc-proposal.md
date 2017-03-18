# WikiPathway Slides
**Aim:** Enable researchers to easily create presentations from pathways in WikiPathways.

## Methods
Using the manipulation API, create a UI with tools to create different slides, in which manipulation API methods are specified for nodes in that pathway. Each new "slide" represents a pathway "state". Each state contains specification for which manipulation API methods are called on entering that state. 

For example:
- Slide 1:
  - Hides all elements in pathway except for `node_1` and `node_2`, and highlights these nodes
- Slide 2:
  - Un-highlights `node-1` and `node_2`.
  - Animates in `node_3` `node_4` and `node_5`
  - Zooms in to those three nodes.
  
 
### Data Strorage
All data is stored as a JSON object in a similiar way to the [Google Slides API](https://developers.google.com/slides/reference/rest/v1/presentations#Presentation). The presentation object contains attributes such as a Title, Description and an orderered list of the Slide Objects. The Slide object contains key: value pair manipulation API methods that should be called for each node. 

Example Presentation:
```json
{
  id: string,
  wpId: string,
  title: string,
  description: string,
  slides: [
    {
      object(Slide)
    }, ...
  ]
}
```

Example Slide:
```json
{
   node_1: [
    {
      hidden: false,
      animate: 50
    },
    {
      zoomOn: true,
      animate: 100
    }
  ],
  node_2: [
    {
      highlight: true,
      color: 'red',
    }
  ]
}
```
  
  
