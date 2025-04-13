
we're making an ai-managed content distribution system. it can basically construct tweets, make insta posts and reels based on a conversation that the content creator will have with the sage model (smth)

the sage model will ask the user for the basic idea after which it will continue asking the user questions based on the idea so that it can build a corpus of information for itself.

there will be an overall corpus that will have persistent knowledge from each separate idea. this corpus will be updated after each idea and it will serve as the overarching knowledge base. every time a new idea is created, after the posting is done (i guess?) the corpus is added to the RAG and then the overall corpus is updated.

NOTE:
1. each corpus (the small ones for the ideas themselves) is a few pages long that the sage model uses to generate content for each social media platform.
2. questions can be stuff like "please elaborate on {topic A}" or "why do you think {topic B} is important", etc.

after this, our api will take the generated content and post it on the site (PITA)
