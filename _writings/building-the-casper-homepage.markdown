---
title: Building the Casper homepage
date: 2016-01-02 15:02:00 -05:00
published: false
---

In September, I decided that it was time to take a break from client work. I would focus 100% of my time on my freelancing app, Cushion, and hopefully double its subscriber count by the end of the year. 

One week later, however, I received an email from Gabe Flateman, CTO and co-founder of Casper. If you live in New York, you’re already well aware of Casper because their subway ads are everywhere. In short, Casper is mattress startup with emphasis on quality and customer support.

Typically, I would’ve stuck to the plan of going clientless, but Casper is an enticing client, and I simply couldn’t pass up the opportunity to at least chat. If anything, this would allow me to work full-time on Cushion for even longer.

I met with Gabe and he filled me in on their plan to start offering pillows and sheets along with their signature mattress (not my typical client). And to announce their new products, they needed a fancy new website. 

I’ve worked on a few animated websites in the past, and that’s exactly how Gabe found me. These websites are fun because they give me the chance to experiment. I also do my best work under the pressure of their challenges and countless unknowns, like whether the website is even possible.

[sandwich sketch]

Gabe told me about their “Dream Sandwich” concept, designed by the creative studio, JaegerSloan. The bed would separate in mid-air and each product would float up the page as the user scrolls. Then, the products would float back down and land as a complete bed.

We discussed possible approaches, like scrubbing through a video or swapping out still images. Video is easy, but sacrifices quality and control. Stills are more flexible and higher quality, but at the cost of file size. Regardless of the direction we took, it was clear that this would be a challenge.

[pencil animation]

I had experience animating with still images from my work on the FiftyThree Pencil page, where a hand holding a Pencil rotates as the user scrolls. However, that was only a small section of the page with only a dozen images. The Casper website, on the other hand, would potentially be hundreds of hi-res images spanning the entire window.

The countless challenges raced through my mind as Gabe and I chatted—file size, performance, file size, image quality, file size, deadline. I could’ve walked away, but after brainstorming and talking through all the obstacles, I felt invested in the website—I wanted to be the one to make this special. 

I accepted the gig. 

I need to constantly remind myself of how fortunate I am to attract this caliber of client, and more importantly, that building websites actually counts as a profession—let alone a lucrative one. At any time, tides could shift and the industry could take a nosedive. It sounds far-fetched, but I was once a skilled Flash developer.

[video prototype]

Gabe sent me a CodePen prototype they made for scrubbing a video with the scrollbar. CodePen and other web-based IDEs were completely foreign to me, so this was a first. I forked Casper’s prototype and added friction to make the scrubbing smoother. I was blown away by how easy it was to set up and share iterations. So much, in fact, that I decided to use it for the rest of the project. 

[codepen iterations]

These websites tend to go through dozens of iterations, so CodePen was the perfect tool for me to quickly make changes and get instant feedback from Casper. Whenever we decided to go in a different direction, I would simply fork the latest prototype and move on. This left me with shareable save points that I could easily link to.

After considering all of the potential issues with video, like aspect ratio and browser compatibility, we decided to ditch the video approach. This was definitely for the best because if we were to discover a deal-breaker after shooting the video, we would be in a really sticky situation. By using still images, we would at least have some outs if anything went south.

[gazelle video]

JaegerSloan was smart and shot each product individually—this gave us more control over scaling and positioning. They used a Gazelle camera crane on a green screen, which provided us with a smooth series of angles that we could select from. If I learned anything throughout this project, it’s that Casper does not mess around when it comes to big ideas.

[color blocks]

With a tight deadline and no readily available assets, I had to make the most of my time. While JaegerSloan worked on touching up the images, I started coding a prototype using colored blocks as placeholders. This allowed me to focus on the timing, positioning, and feel of the animation before even thinking about actual images.

[draft images]

A few days later, JaegerSloan provided us with draft images that could be used to help pick which frames we would need for the final animation. Because of the tight deadline, we didn’t have the luxury of touching up every single image from the photoshoot. And because of the concern with file size, we needed to know the frame rate that would use the least amount of images while still feeling smooth.

With the FiftyThree page, I was able to keep it simple by loading a dozen images individually. With Casper, I would be dealing with hundreds of images, so the number of requests became a big concern. 

[sprite sheet]

Instead of loading images one-by-one, we needed to use sprite sheets—combining every frame of a product as one image. If we have 5 products on the page, the browser would only need to load 5 images with 100 frames versus 500 single-frame images. The file size would also be much lower because the images within the sprite sheet can share colors.

I wrote a script that takes a folder of images, compiles them into a sprite sheet, and optimizes the sheet to save even more on file size. The result is a single image and a CSS file of the background positions of the frames within the sprite sheet. In the animation code, I would simply change the class name of a given product and it will move the sheet to display the right frame.

The code I used to control the positioning and timing of the animation is step-based, similar to the system I wrote for carousel.com. Each step has a duration and an array of items to animate. And each item has start/end values for each property (x, y, etc). The current step is detected based on the scroll position. Each item then animates based on the scroll position within that step. Everything is based on relative percentages, so if a specific step needs to feel shorter or longer, I could increase the duration of that step and the animation would adjust itself.

[draft animation]

Now that we were actually using draft images instead of colored blocks, I was able to get a much better sense of the animation’s feel. It was exciting to see everything starting to come together, even as a rough draft. I tweaked the timing and positioning to smooth out the rough spots and shared the new prototype with Casper. 

When we received the final images from JaegerSloan, it felt like Christmas. I’ve been working with the draft images for so long that I forgot that they were drafts—my brain automatically ignored their rough edges and color. Once I swapped out the drafts for the retouched images, everything instantly felt like a real webpage—no longer a prototype.

While I worked on the website, the Casper QA team performed user tests with each major iteration I sent them—rather than launching and hoping for the best. With the final images in place, they were able to discover a few difficult truths. 1) Users weren’t connecting with the room. 2) Users didn’t realize that Casper was announcing pillows and sheets. 3) Users thought Casper was introducing pajamas.

With two weeks remaining before launch, these results were hard to swallow. We had to make some big changes, but fortunately, not all was lost. To make the room more relatable, Casper brought back the hero with one of their lifestyle photos. This provided a more realistic image of a bedroom with more emphasis on the announcement copy. Instead of distracting the user with an animation right off-the-bat, the still image would give them time to see that Casper now has sheets and pillows.

The rest of the page, including the animation, was more up-in-the-air at this point. Casper’s director of design, Huy Vu, and senior designer, Jarrod Barretto, focused on a new design, reusing the elements of the animation, but ditching the idea of the step-based animation. At the same time, I had an idea for what might work, so I started a new prototype.

[peeling off the mattress]

Thinking back to why the FiftyThree Pencil animation was so well-received, with the pencil pulling apart as the user scrolled, I decided to reattempt this approach with the bed. As the user scrolls down the page, the mattress locks to the bottom and the products rise off the mattress one-by-one and continue off the page. Once the mattress is the only product remaining, the page returns to normal and the mattress scrolls up with the rest.

[huy flats]

We discussed the possible directions the next day and decided to go with Huy’s design. After the hero, the user would see the “sandwich” separated, with buttons linking to each product. The user would then scroll through the individual products before hitting the rest of the page. As the products move up the page, their frames adjust to match their position on the page to create the illusion of 3D perspective.

I started on the new prototype and was blown away by how much code I would be able to remove. By treating each section of the page as self-contained modules that stack like any other HTML element, then controlling the rotation of each item independently based on its position on the page, I would only need about 20 lines of code. The items moved up the page like normal HTML elements, but the class that indicates the image to use would update based on their position.

[end result]

This immediately felt more like a webpage than any of the previous iterations, which I think is more effective than any parallax animation. It didn’t hijack the scroll or move elements against the grain of the page. If the user scrolled quickly from top to bottom, they might not even notice the rotating products, but once they do, it will wow them even more.

I spent the last week before launch moving the code from Codepen into Casper’s repo. Joseph Cortwabi worked closely with Jarrod to fine-tune the hero across screen resolutions and orientations, and Kei Sato helped with the shop modules at the bottom of the page. In the final hours, Betty Liao stayed with me to test a gnarly VH bug on iOS7.