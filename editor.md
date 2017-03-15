# Editor
To allow for user's to easily use the new manipulation API, some way for them to easily add interactive links needs to be implemented.

## Markdown
Can use a custom markdown syntax using [markdown-js](https://github.com/evilstreak/markdown-js).

```markdown
This process describes the conversion of precursor messenger RNA into mature messenger RNA (mRNA).
The pre-mRNA molecule undergoes [three main modifications](zoomOn, ['node1', 'node2', 'node3']). These modifications are [5' capping](highlightOn, 'node_id'), [3' polyadenylation](highlightOn, nod_id), and [RNA splicing](highlightOn, node_id), which occur in the cell nucleus before the RNA is translated.
[5' Capping](panTo, [node_ids,...]): Capping of the pre-mRNA involves the addition of 7-methylguanosine (m7G) to the 5' end. The cap protects the 5' end of the primary RNA transcript from attack by ribonucleases that have specificity to the 3'5' phosphodiester bonds.
[3' Processing](panTo, [node_ids, ...]): The pre-mRNA processing at the 3' end of the RNA molecule involves cleavage of its 3' end and then the addition of about 200 adenine residues to form a poly(A) tail. As the poly(A) tails is synthesised, it binds multiple copies of poly(A) binding protein, which protects the 3'end from ribonuclease digestion.
[Splicing](panTo, [node_ids, ...]): RNA splicing is the process by which introns, regions of RNA that do not code for protein, are removed from the pre-mRNA and the remaining exons connected to re-form a single continuous molecule.
```

So that the user knows the relevent IDs to use in the custom markdown braces, there would be a list of node name/ID mappings next to the editor. As well as a live preview.

### Disadvantages
- Maybe hard for non-dev-types who are not comfortable with Markdown
- Relatively steep learning curve

### Advantages
- Once you know how to use it, it's very fast to use
- Simple to develop
- Can have live preview of the accompanying pathway and the text

## WYSIWYG

"What you see is what you get" editor. This option shows a conventional WYSIWYG editor with a button for interactive descriptions in the toolbar. Clicking this would open up a modal with a form to select the pathway element, the action (highlight, pan, zoom) and allow the user to place it the link in the text.

### Disadvantages
- Hard to develop
- Slow to use
- More difficult to add new features since any new manipulation API functions will have to be hard-coded in the modal

### Advantages
- Many people are already used to WYSIWYG editors
- Low learning curve
- No need for live preview since, well, WYSIWYG
