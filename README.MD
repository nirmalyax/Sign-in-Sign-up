# DOUBLE SLIDER - SIGN IN/UP FORM


Some of you might already know but for those who don't, I'm starting a weekly Coding Challenge with all of you! 😄

**This is how I'm planning to make it work**: Every **Monday** I'm going to post an article about how I'm solving a different Coding Challenge by selecting a theme like: creating a new animation, a Sign in/up form, a Notes app, etc... (the sky is the limit). You are free to take a peek 👀 at my solution, BUT, you MUST come up with your own version in order to participate.


## *Create a Sign in or Sign up form (or both)*

Below you can see a demo of what I've created:

 ![Example GIF](https://media.giphy.com/media/1rK9pvvWZUBReNAt56/giphy.gif)

Truth to be told, I've struggled a bit with creating the animation 😅, but at the end I managed to make it work. 👍 I was inspired by this shot on [Dribbble](https://dribbble.com/shots/5311359-Diprella-Login) by [SELECTO](https://dribbble.com/selecto) - they have some awesome designs, you should check them out!

## Project description

Before we move to the actual code, I'd like to break down the things we're going to have in the component. This will help as it will make the code we write much clearer.

We have 4 smaller screens/boxes inside the main component (the `.container`):


1. The **Sign In** form
2. The *Sign Up* form
3. The **Sign In** overlay
4. The *Sign Up* overlay

Also, at one moment in time you can see either:

* The **Sign In** form alongside the *Sign Up* overlay
* The *Sign Up* form alongside the **Sign In** overlay

In the *overlay* panels we have some text and a `button` - by clicking it you will bring up the other combination of screens and vice-versa. Check the GIF above one more time to see what I mean.

### The overlay animation - explained

This is where it might be a little trickier, but I'll do my best to explain so you can understand the logic behind it.

We have the following *layers* for the overlay component:

**The overlay-container** - this will display the **visible** area (more on this below) at a certain moment in time. It has a `width` of `50%` of the total container's width.

**The overlay** - this div has a double `width` size (`200%`) so it's taking the full width of the main container. (`200% * 50%= 100%`. The 50% is from the `.overlay-container` above).

**The overlay-panel**s - are the divs which are holding the actual content (the text and the button) we are seeing on the screen. They both have a `position` of `absolute` -> meaning that we can position them wherever we want in the `.overlay` component. One of the panels is positioned to the `left` and the other one is positioned to the `right`, both having a width of `50%` of the `.overlay` component.

"Why do we need 3 layers?" you might ask... Well, let's see how it would look like without the first layer:


[ ![Overlay example](https://www.florin-pop.com/static/83e0e35ed177d2591bbd01c9f6db1f10/70ccf/double-slider-overlay-demo.png "Overlay example")](https://www.florin-pop.com/static/83e0e35ed177d2591bbd01c9f6db1f10/3bb8e/double-slider-overlay-demo.png)

In the picture above you can see that both of the panels are "visible", which is not what we want, and this is why we're adding the `.overlay-container` to act like a "focus area" by allowing us to hide the panel which is **overflow**ing, or which is out of its boundaries. This is why we needed the `.overlay` to be twice as big as the `.overlay-container`. By moving around the `.overlay-container`, which also has a `position` of `absolute`, we can hide or show which panel we want.

It was a little bit confusing 😅, I'll admit, but I hope I made it more clear.

 \n 