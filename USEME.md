# LIME: Layered Image Manipulation and Enhancement USEME

## Explanation of Each Element in the gui

### File Tab

Used for file operations. Elements:

#### Load Submenu:

- Checkerboard: Creates a checkerboard (containing black and white checkers) of ___ dimensions

####

- Upload: Uploads an image in ppm/jpeg/jpg/png format, or a script of commands as a txt file

#### Load All:

Loads a previously saved layered image using a txt file corresponding to the layer data

#### Save:

Saves the topmost visible layer as an image to the file name (with an extension) entered in the
corresponding text box

#### Save All

Saves all layers as separate images in the format (only extension) entered in the corresponding text
box, along with a txt file corresponding to the layer data

### Edit Tab

Used for editing the image. Elements:

#### Filter Submenu:

- Blur: Blurs the current image

####

- Sharpen: Sharpens the current image

####

- Mosaic: Creates a mosaic of the current image, using the number of seeds entered in the
  corresponding text box

####

#### Transform Submenu:

- Greyscale: Applies the greyscale transformation to the current image

####

- Sepia: Applies the sepia transformation to the current image

### Layers Tab

Used for performing operations on layers. Elements:

#### Create:

Creates a layer with the name entered in the corresponding text box

####

#### Current:

Makes the layer with the name corresponding to the one entered in the corresponding text box, the
current layer

####

#### Copy:

Makes a copy of the layer with the name corresponding to the one entered in the corresponding text
box

####                      

#### Visibility:

Toggles the visibility (visible/invisible) of the layer with the name corresponding to the one
entered in the corresponding text box

#### Remove:

Removes the layer with the name corresponding to the one entered in the corresponding text box

#### Layer List

Gives a list of all of the layers present in the model, regardless of their visibility

#### Visible Layers

Gives a list of all of the visible layers present in the model

## Using The GUI: A Step-by-Step Guide

- A layer must be created and made current before trying to upload anything onto it. The only
  exception is while loading a script. A script can be uploaded directly, without any steps
  preceding it.
  ####
- The user can only see the topmost visible layer of an image. If the first layer is visible and the
  second layer is the current layer, it would still be the first layer that is visible to the user.

####

- A layer can be created by going to the Layers tab → Create, and then entering what you want the
  layer to be called in the text box, and pressing enter. It can be made current from Layers →
  Current → Enter the name of the layer to be made current.

####

- The above procedure is the same for all layer operations (Create, Current, Copy, Visibility,
  Remove). A layer name must be entered in the corresponding text boxes for all layer operations.
  Pressing the enter key in these text boxes is necessary.

####

- Once a checkerboard or an image is uploaded to a layer, it can be edited using any of the items in
  the Edit tab. Once a script is run, the topmost visible layer created will be rendered on the
  screen, and any further operations can be performed on it using the gui. The same also stands for
  loading a previously saved layered image through a txt file using 'Load All'.

####

- To save the topmost visible layer of an image, use the 'Save' in the File tab, and enter the file
  name to use while saving the image, along with its extension (ex: pic1.png) in the corresponding
  text box.

####

- To save all the layers of an image, use the 'Save All' in the File tab, and enter the format to
  use while saving the images (ex: png) in the corresponding text box. All the layers will be saved
  as separate images in the given format, along with a txt file corresponding to the layer data
  which may subsequently be re-loaded using 'Load All'.

## Authors

Anushka Mantri [mantri.an@northeastern.edu]

####

Christopher Carlsson [carlsson.c@northeastern.edu]
