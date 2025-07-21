# Seam-Carver

I created this seam carving program as an assignment for Accelerated Fundamentals of Computer Science 2 where the given image is resized by removing the 'least important' seam of pixels. 

Please contact me directly to view the source code. 

Here's how the program works: 

## Step 1 ## 
The 'importance' of each pixel is determined by a formula that essentially calculates how much the current pixel (**e**, in this case) differs from its horizontal and vertical neighbors. 
```
  a b c
  d e f
  g h i
```

```
  horizontalEnergy(e) = (brightness(a) + 2*brightness(d) + brightness(g)) - (brightness(c) + 2*brightness(f) + brightness(i))

  verticalEnergy(e) = (brightness(a) + 2*brightness(b) + brightness(c)) - (brightness(g) + 2*brightness(h) + brightness(i))

  energy(e) = sqrt(horizontalEnergy(e)^2 + verticalEnergy(e)^2)
```

  With this formula, border pixels have higher energy (i.e. more importance) while areas with uniform colors have lower energy (i.e. lower importance) 

  ## Step 2 ##
  Compute the energy of every single seam, a path of adjacent pixels (including immediate neighbors and diagonal neighbors). Seams can run vertically (bottom-to-top) or horizontally (left-to-right) on an image.

  The seam with the least energy is deemed the 'least important'. 

  ## Step 3 ##
  Remove the least important seam and shift the rest of the pixels accordingly to stitch the gap caused by removing the least important seam. 

  ## Step 4 ##
  This process is repeated until the image is shrunk to appropriate size. 


  ## Key Bindings ##
  - space : start/pause the carving of seams
  - "e" : renders each pixel's energy as opposed to the original image (which renders energy in grayscale)
  - "v" : removes a single vertical seam only when carving is paused and paints the removed seam red
  - "h" : removes a single horizontal seam only when carving is paused and paints the removed seam red
  - "u" : reinserts removed seams into the photo, undoing the seam carving 


  Watch the demo, which includes timestamps outlining the features being shown! <br>
  Click [here] (https://www.youtube.com/watch?v=DgdfHFr-LkQ)

  
