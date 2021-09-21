# LIME: Layered Image Manipulation and Enhancement

This project forms the base model of our image processor and enhancer. The model can be used to read
.ppm images or images in any other format (.jpeg, etc.), convert them into image models
corresponding to our base model, and filter or transform these images. The filters supported in this
version are "blur" and "sharpen", and the transformations supported are "sepia" and "greyscale".
This project can also be used to create custom programmatic images like a "checkerboard", and then
export any image models to our device in .ppm format.

## Overview of Interfaces and Classes

### Interface: ImageState<K>

Observes the state of the image, including its height, width, pixels, and the image itself. K is the
Pixel type an Image is parameterized over. In this project, our pixel type is the Pixel class.

### Interface: ImageModel<K>

Extends the ImageState<K> interface. Defines the tasks a model of an image can perform and observes
the state of the image. The tasks an image model can perform include filtering, transforming,
creating programmatic images, and exporting an image model as an image to the device. K is the Pixel
type an Image is parameterized over. In this project, our pixel type is the Pixel class.

### Interface: ImportImage

An interface used for importing images by reading from given files and converting them into image
models.

### Interface: ExportImage

An interface used for exporting image models to the device.

### Interface: FilterCommand

An interface for filters that can be applied to an image (ex: blur, sharpen).

### Interface: TransformationCommand

An interface for transformations that can be applied to an image (ex: sepia, greyscale).

### Interface: ProgrammaticImages

An interface for making images programatically (ex: checkerboard).

### Class: SimpleImageModel

Implements ImageModel<K>. A class to represent the inner workings and functionalities of an image
model. A SimpleImageModel can be created by directly providing the dimensions and pixels of the
image.

### Class: Pixel

A class to represent a single pixel in an image. Our image model is parameterized over this type. A
pixel has a position (Position2D) in the image and a color (RGBClr).

### Class: RGBClr

To represent the red, green, and blue color channels of a pixel in an image.

### Class: Position2D

To represent 2D (x, y) coordinates of a pixel in an image.

### Class: ImportImagePPM

To read a PPM image from a file and create a SimpleImageModel with the properties of the PPM image.

### Class: ImportImageNotPP

To read any non-PPM format image from file and create a SimpleImageModel with the properties of the
image.

### Class: ImageUtils

A class to contain utility methods for images. Currently contains a method to clamp the numerical
values of RGB colors.

### Class: ExportImagePPM

A class to export an image model as a PPM image.

### Class: Filter

Abstract class to represent a filter to be applied on any image. Contains methods to use the given
filter kernel and apply it to the given image.

### Class: BlurFilter

A class to apply the blur filter to an image.

### Class: SharpenFilter

A class to apply the sharpen filter to an image.

### Class: CheckerboardProgImage

To create a checkerboard with the specified dimensions and colors. A checkerboard is like a chess
board, alternating between two colors.

### Class: Transformation

Abstract class to represent a transformation to be applied on any image. Contains methods to use the
given transformation kernel and apply it to the given image.

### Class: GreyScaleTransformation

A class to apply the greyscale transformation to an image.

### Class: SepiaTransformation

A class to apply the sepia transformation to an image.

### Design

For the execution of filters, transformations, and programmatic images, we used the Command Design
Pattern to allow for flexibility in the future, and have each of the above tasks delegated to a
class designed exactly for that purpose. This makes our code extensible to add more features,
including extra filters, transformations, and programmatic images.

### Class: Main Method

A class to run any commands on the model.

### Res Folder

The res folder contains some original images and all the currently supported filters and
transformations applied to them.

### BatchCommands

A class for interaction with the client. Takes input and delegates to its available commands of type
CommandController.

#### The following classes are available commands in the BatchCommands class. They implement the CommandController interface:

- BlurCommand: Blurs the current image.
  ####
- SharpenCommand: Used to apply the "sharpen" filter to the current layer.
  ####
- SepiaCommand: Used to apply the sepia transformation to the current layer.

####

- GreyscaleCommand: Used to apply the greyscale transformation to the current layer.

####               

- CopyLayerCommand: Adds a copy of the given layer.
  ####
- CreateCommand: Creates a new layer.
  ####
- CurrentCommand: Marks a given layer as current to apply commands to.

####

- LoadAllCommand: Loads a layered image that was saved.

####

- SaveAllCommand: Saves all layers in an image as separate images and generates a corresponding text
  file.

####

- SaveCommand: Used to save the topmost visible layer of the image onto the device.

####

- LoadCommand: Used to load an image onto the current layer.

####

- ToggleVisibilityCommand: Makes a given layer visible or invisible based on its current visibility
  status.

####

- RemoveCommand: Removes a given layer from the model.

####

- MosaicCommand: Applies the mosaic filter to the current layer.

### Interface: ViewGUI

An interface used for the view classes that support GUIs.

### Class: ViewOperations

The class used to build the gui for our Image Processing Application. Contains methods that build
all elements of the gui and renders messages and images onto the screen.

### Class: GUI_Main

The class containing the main method used to visualize the gui.

### Class: GUIController

The controller that handles all events in the gui. Implements the ActionListener interface.

### Design

Using a GUIController that implements ActionListener instead of having the ViewOperations class
implement all the gui view features as well as the inner functionalities, makes it convenient to add
more features in the long run, and separate the actual implementation of the tasks to be performed
to handle an event from the view by itself. This was done in an attempt to adhere to the MVC design.

### How to Use the Program

Open command-prompt/terminal, and use one of the three following command line inputs:

- java -jar Program.jar -script path-of-script-file The program should opens the given script file,
  executes it and then shuts down.

- java -jar Program.jar -text The program should opens in an interactive text mode, allowing the
  user to type the script and it one line at a time.

- java -jar Program.jar -interactive The program opens the graphical user interface.

If an invalid command is entered, the program quits. For detailed information on how to use the gui
or other interactions, please refer to the USEME from HW7 and HW6.

### Changes Made for the Mosaic Extra Credit

To implement the Mosaic filter, we added a class to our filters package that contained the full
implementation that we required to make the mosaic feature work. Then, we simply made a
MosaicCommand class in our layeredimagescontroller package, from where we called the MosaicFilter
class to do the heavy lifting for us. Then, we only needed to add this feature to our gui, and
created an action command on it that would lead us to the MosaicCommand class and help us achieve
the mosaic effect.

## Changelog

Created a view interface and a dedicated progress log that documents events (ex: blurring,
uploading, etc.) as they are happening, for easier use and inference by the user (added after grader
remarks for HW6). Also added a remove method for removing layers (RemoveCommand).

## Authors

Anushka Mantri [mantri.an@northeastern.edu]
Christopher Carlsson [carlsson.c@northeastern.edu]

## Acknowledgments

The original 'rainbow' picture was obtained from
https://unsplash.com/images/nature/rainbow, by Steve Johnson