<script>
	import HyperparameterView from '../detail-view/Hyperparameterview.svelte';
  import Youtube from './Youtube.svelte';

	let softmaxEquation = `$$\\text{Softmax}(x_{i}) = \\frac{\\exp(x_i)}{\\sum_j \\exp(x_j)}$$`;
	let reluEquation = `$$\\text{ReLU}(x) = \\max(0,x)$$`;

  let currentPlayer;
</script>

<style>
	#description {
    margin-bottom: 60px;
    margin-left: auto;
    margin-right: auto;
    max-width: 78ch;
  }

  #description h2 {
    color: #444;
    font-size: 40px;
    font-weight: 450;
    margin-bottom: 12px;
    margin-top: 60px;
  }

  #description h4 {
    color: #444;
    font-size: 32px;
    font-weight: 450;
    margin-bottom: 8px;
    margin-top: 44px;
  }

  #description h6 {
    color: #444;
    font-size: 24px;
    font-weight: 450;
    margin-bottom: 8px;
    margin-top: 44px;
  }

  #description p {
    margin: 16px 0;
  }

  #description p img {
    vertical-align: middle;
  }

  #description .figure-caption {
    font-size: 13px;
    margin-top: 5px;
  }

  #description ol {
    margin-left: 40px;
  }

  #description p, 
  #description div,
  #description li {
    color: #555;
    font-size: 17px;
    line-height: 1.6;
  }

  #description small {
    font-size: 12px;
  }

  #description ol li img {
    vertical-align: middle;
  }

  #description .video-link {
    color: #3273DC;
    cursor: pointer;
    font-weight: normal;
    text-decoration: none;
  }

  #description ul {
      list-style-type: disc;
      margin-top: -10px;
      margin-left: 40px;
      margin-bottom: 15px;
  }
    
  #description a:hover, 
  #description .video-link:hover {
    text-decoration: underline;
  }

  .figure, .video {
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
  }
</style>

<body>
  <div id="description">
    <h2>Let us understand how computers can be trained to see images</h2>
    <p>
      Once upon a time in the land of Computoria, there was a magical machine that could dream about pictures. It had a special eye called the Camera Eye, which could look at things and see them not like we do, but in a way that made sense to machines.

When the Camera Eye saw a picture, it didn't see a dog, a car, or an apple. Instead, it saw a mix of tiny dots in red, green, and blue. These were like the magic dust that made up everything it saw.

One day, the machine was given a challenge: to learn to recognize different things just by looking at them, like a koala, a pizza, or a school bus. But the machine didn’t know these things yet. It had to learn, just like you learn your ABCs.
    </p>

    <h2>Part 1: Seeing the colors</h2>
    <p>
      The story begins when the Camera Eye looks at a picture. It first breaks down the picture into three parts: one part is just red, another just green, and the last part just blue. It's like having glasses that only show you one color at a time.
    </p>
    <div class="figure">
      <img src="/assets/figures/CNN_Part1.gif" alt="clicking to reveal three components - red, green, blue" width=60% height=60% align="middle"/>
      <div class="figure-caption">
  		  Figure 1.  You can see that each image can be broken down into 3 parts: red, green and blue.
  	  </div>
    </div>

    <h2>Part 2: The dream layers</h2>
    <p>
      After splitting the colors, the picture goes into the machine's dream world. Here, there are special elves called Neurons that live in layers. The first layer elves are the 'see-the-big-picture' kind. They look at the broad strokes, like whether the picture is bright or dark, or if there are edges or blobs of color.
    </p>
    <div class="figure">
      <img src="/assets/figures/CNN_Part2.gif" alt="clicking to reveal three components - red, green, blue" width=100% height=100% align="middle"/>
      <div class="figure-caption">
  		  Figure 2.  Have a look at the special elves - neurons, who detect broader elements of an image like edges, brightness etc
  	  </div>
    </div>

    <h2>Part 3: How do the neurons work?</h2>
    <p>
      As we dive back into the machine's magical dream, we discover that the neurons (elves) have a set of special tools called 'Magic Kernels'. These are like little wands that they wave over the picture to highlight different parts of it. One kernel might be enchanted to find edges, another to spot areas of light and shadow, and another to see textures.

      The elves use these kernels to filter through the picture, creating new pictures from the old one that show only the features they're interested in. They create a gallery of these filtered images, which are like pieces of a puzzle that they'll use to build their final guess.
    </p>
    <div class="figure">
      <img src="/assets/figures/CNN_Part3.gif" alt="clicking to reveal three components - red, green, blue" width=60% height=60% align="middle"/>
      <div class="figure-caption">
  		  Figure 3.  Magic Kernels: Little wands which neurons wave over the picture to highlight different parts of it. 
  	  </div>
    </div>

    <h6>Understanding Kernels interactively</h6>
    <p>
    	<HyperparameterView/>
    </p>

    <h2>Part 4: The puzzle pieces</h2>
    <p>
      Then the picture goes deeper into the dream, to the second layer of elves. These elves are the 'detail-lovers'. They take the broad strokes and start to see patterns, like stripes, dots, or curves. They're like detectives finding clues in a mystery.
    </p>
    <div class="figure">
      <img src="/assets/figures/CNN_Part4.gif" alt="clicking to reveal three components - red, green, blue" width=100% height=60% align="middle"/>
      <div class="figure-caption">
  		  Figure 4.  Going to the second layer. Neurons in the second layer take the broad strokes and start to see patterns, like stripes, dots, or curves.
  	  </div>
    </div>

    <h2>Part 5: Building the patterns</h2>
    <p>
      As the picture moves through more layers, the elves pass on their clues down the line. With each layer, the elves get smarter and start to guess what they're seeing. "Hmm, these stripes could belong to a zebra," one might say, or "These curves look like the wheels of a car," another might guess.
    </p>
    <div class="figure">
      <img src="/assets/figures/CNN_Part5.gif" alt="clicking to reveal three components - red, green, blue" width=100% height=60% align="middle"/>
      <div class="figure-caption">
  		  Figure 5.  As we go deeper, neurons get smarter and smarter. "Hmm, these stripes could belong to a zebra," one might say, or "These curves look like the wheels of a car," another might guess.
  	  </div>
    </div>

    <h2>Part 6: Making the final guess</h2>
    <p>
      At the very end of the dream, the elves gather around and start to guess. "It's a koala!" one elf might shout. "No, it's a pizza!" another argues. They vote, and the guess with the most votes is what the machine will say it sees.
    </p>
    <div class="figure">
      <img src="/assets/figures/CNN_Part6.gif" alt="clicking to reveal three components - red, green, blue" width=60% height=60% align="middle"/>
      <div class="figure-caption">
  		  Figure 6. The neurons make their final guess!
  	  </div>
    </div>


   <h2>Conclusion</h2>
   <p>
    As we wrap up our journey into the world of how computers see, we've discovered that it's not just about cameras and pixels. It's about how layers upon layers of neurons, much like the neurons in our own brains, work together to make sense of the world. These tiny detectives, the kernels, dance across images to find clues, and with each step of training, the computer becomes a little more 'intelligent.'

But what's truly exciting is imagining the possibilities. Through our interactive activities, you've pretended to hover over neurons and witnessed kernels in action, even if only in your mind's eye. You've seen how a computer can learn, much like we do, from its mistakes, getting better with practice.

As we close the book on this adventure, remember that what we've learned is just the beginning. Every time you use a computer or a smartphone, you're commanding an intricate network of artificial neurons, a network that's continually learning and evolving. The next time you see a photo or a video on a screen, think of the invisible dance going on behind the pixels, the intricate ballet of data and decisions that allows you to see a captured moment in time.

The journey doesn't end here. As technology advances, so will the capabilities of computers in understanding and interpreting the visual world. And who knows? Maybe one day, you'll be the one to teach them a new way to see. Keep exploring, keep imagining, and keep learning, for the adventure is just beginning.
   </p>
  </div>
</body>
