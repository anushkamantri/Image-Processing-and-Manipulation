# LIME: Layered Image Manipulation and Enhancement (Java)

[Code available on request]
This project forms the GUI of our image processor and enhancer. The model can be used to read
.ppm images or images in any other format (.jpeg, etc.), convert them into image models
corresponding to our base model, and filter or transform these images. The filters supported in this
version are "blur" and "sharpen", and the transformations supported are "sepia", "mosaic" and "greyscale".
This project can also be used to create custom programmatic images like a "checkerboard", and then
export any image models to our device in .ppm, .jpeg, or .png format.

#### The following commands are available in the GUI:

- Blur: Blurs the current image.
  ####
- Sharpen: Used to apply the "sharpen" filter to the current layer.
  ####
- Sepia: Used to apply the sepia transformation to the current layer.

####

- Greyscale: Used to apply the greyscale transformation to the current layer.

####               

- Copy Layer: Adds a copy of the given layer.
  ####
- Create: Creates a new layer.
  ####
- Current: Marks a given layer as current to apply commands to.

####

- Load All: Loads a layered image that was previously saved.

####

- Save All: Saves all layers in an image as separate images and generates a corresponding text
  file.

####

- Save: Used to save the topmost visible layer of the image onto the device.

####

- Load: Used to load an image onto the current layer.

####

- Toggle Visibility: Makes a given layer visible or invisible based on its current visibility
  status.

####

- Remove: Removes a given layer from the model.

####

- Mosaic: Applies the mosaic filter to the current layer.

#### Disclaimer
This project was developed as part of the Object Oriented Design course at Northeastern University. The code will be available on request due to the university honor code.

## Authors

Anushka Mantri [mantri.an@northeastern.edu]
Christopher Carlsson [carlsson.c@northeastern.edu]

## Acknowledgments

The original 'rainbow' picture was obtained from
https://unsplash.com/images/nature/rainbow, by Steve Johnson
