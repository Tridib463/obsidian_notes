- - -
- Install the dependencies via Vite.
- `npm create vite@latest `  - Create a Vite Project Setup.

Install modern - normalize - > Creates consistent styles across modern websites

### Before the designing the main components, design the utility classes 
- html and body - understand
- Fonts from Fontshare website and paste the link in the head of the html file.
- Customise colors from color picker and converter in W3 Schools.
- Inside the styles folder create a file named 'utils.css' to create utility classes.
- We can download free images from the website named  'Unsplash'.

20:00 minute of the video 25:50 to 27:00

Anything i add outside the media query, will apply to all screen sizes and the screen up to the first breakpoint(extra-small). That means it will apply primarily to the mobile screen. (mobile first approach)



## Responsive Design -->
If we see the "Inspect Elements", then we can see that each Section has a Container inside it. That red border is the container.
FOR LAPTOP -->
![[Pasted image 20240228194219.png|820]]

FOR EXTRA-LARGE LAPTOP -->
![[Pasted image 20240228194519.png|820]]

### The moment the viewport touches the red border, the Container responsively shrinks. This is a superior way of responsive designs.

If we add min-width parameter in media - query then , anything outside the media-query will apply to media query below the  First Break-point i.e. 475 px and the Default Stylesbe considered the default style, applying to all situations unless overridden by a more specific rule. . This is called Mobile First approach.       In the case of Max-width it is just the OPPOSITE.

![[Pasted image 20240228195212.png|400]]

### We should not use percentages in deciding container size cause it ruins the layout in 4K Monitor, but sizes below 475 px , we don't have a choice.
When we use percentage in container size, the container shrinks continuously BUT here the container shrinks only when the viewport reaches the min-width.

## About Section ->
When the screen size is small the section has a column layout and the screen size is big the Section has a Row layout(Side by side)
The Text on the left is going to wrapped inside a div and the image on the right in a seperate div. AND those two inside the common container.
![[Pasted image 20240302163633.png|500]]

![[Pasted image 20240302163652.png|300]]
- - -
## Featured Section ->

Selects all div elements inside the Container
![[Pasted image 20240520183657.png|600]]
![[Pasted image 20240520184024.png|600]]


### Difference between justify content and flex - 1 ->

Justify-Content
![[Pasted image 20240520184211.png]]


Flex - 1
![[Pasted image 20240520184306.png|500]]
So that they all have the same width.
![[Pasted image 20240524181145.png]]


![[Pasted image 20240520205427.png|700]]

## If we want the user to be taken to the desired section, when clicking on a particular nav button ->
![[Pasted image 20240524080250.png|500]]

### Now, in the about section Add id="about"
![[Pasted image 20240524080359.png|700]]