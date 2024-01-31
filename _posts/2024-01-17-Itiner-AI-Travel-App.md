---
layout: post
title: Itiner-AI - A Bespoke Travel App
---

Prototype of an Artificial Intelligence App using Generative AI to create bespoke itineraries and keepsake images for travellers. Check out the beginnings of an online version of the app [here](https://itiner-ai.streamlit.app/)!

### Concept
As a keen traveller, I am constantly looking for recommendations when going to a new place to make sure I can have the best possible experience. This is particularly the case when I have a limited time to spend in specific cities, where there is not currently an app available in the market that allows for specific personalization. This led me to come up with an idea for a new travel app, named **Itiner-AI** which uses **Generative AI** to come up with itineraries based on a users like/dislikes. To incorporate further use of Artificial Intelligence techniques, the app will also generate an image of a defined style including various different locations that have been visited, for the user to keep as a memento. The concept and flow of the application is shown in the image below.

*App Concept*
![concept]({{ site.baseurl }}/images/itinerai/concept.png)

### Artificial Intelligence Tools
A number of readily available AI tools were used within the development of this application idea, which are detailed below along with the tasks carried out:
1. **ChatGPT**
    - Market research into existing products in this field
    - Generates an itinerary based on a prompt with specific parameters
2. **Adobe Firefly**
    - Generate a bespoke image to represent the overall trip.
    - Experiment with a variety of image options to allow for further personalization.
3. **Canva**
    - Research into ideas for a travel itinerary template.
    - Create a baseline template to be populated within the app.
4. **logomaster.ai**
    - Generate logo ideas to be used in the future product.

*AI Tools Used*
![tools]({{ site.baseurl }}/images/itinerai/tools.png)

### Prompt Engineering
Multiple prompt engineering techniques were then used come up with the baseline prompt to be used within the **Large Language Model (LLM)** used to generate the itinerary, which at this stage of the project will be *ChatGPT*. The idea behind this is that the input for the app will include a set of parameters which can be personalised, and these will be fed directly into the prompt to create the itinerary in the required layout. Prompt engineering techniques used in this task were:
1. Role Prompting
2. Instruction Prompting
3. Model Feedback
4. Combination Prompting

### Itinerary Generation
With the prompt engineering complete and example itineraries created, a prototype of the app was then developed using **Figma** to show an example of the flow that would be included within the app to create the itinerary. In this current design, the user will define the following:
- Location of trip
- Duration of trip
- Likes
- Dislikes
- Specific requirements

The app will then generate a detailed itinerary for the specified time period which will be available within the app, and also extract the key details to be added to a *Canva* template for easier viewing when offline. This is shown in the image below, which details the flow for itinerary generation.

*Itinerary Generation Flow*
![flow1]({{ site.baseurl }}/images/itinerai/flow1.png)

### Image Generation

The final phase of completing the prototype is to include a location for image generation, which was developed using *Adobe Firefly* and making use of their different artistic styles in order to fully personalise the image that is created. In this case, the prompt used is very simplistic, with only the desired contents of the image being specified, and the rest selections from pre-defined dropdown lists. Images from each of the trips will then be saved within a **Scrapbook** within the app, for the user to browse at their leisure. The image below shows how the image generation flow would work, specifying how the same prompt can create two very different images depending on the artistic inputs.

*Image Generation Flow*
![flow2]({{ site.baseurl }}/images/itinerai/flow2.png)

### Conclusion and Next Steps
This project allowed me to really dig deeper into the Artificial Intelligence options that are readily available, and also learn about what is required when bringing an app to market. There were a few challenges met along the way, namely due to the short-term 'memory' issues of ChatGPT3.5 and the occasional sensoring of specific words when generating images (i.e. Space Needle), however these can be rectified with re-training new models on specific documentation should the idea progress. There are many routes available for improvement, for example including a mapping feature to visualize the route to be taken, as well as an option for providing feedback and also a potential revenue stream from selling physical copies of the Scrapbook. Watch this space to see what happens next, but in the mean time feel free to check out my [Streamlit App](https://itiner-ai.streamlit.app/).

<p align="center">
  <img src="{{ site.baseurl }}/images/itinerai/logo_small.png" alt="logo"/>
</p>
